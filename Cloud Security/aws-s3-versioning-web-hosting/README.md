# AWS S3 Versioning & Static Website Hosting

## Practical Overview
This practical demonstrates how to create an Amazon S3 bucket, enable bucket versioning, upload an HTML file, configure static website hosting, and make the website content publicly readable using a bucket policy.

## Objective
- Create an S3 bucket.
- Enable S3 Bucket Versioning.
- Upload an `index.html` file.
- Enable Static Website Hosting.
- Configure public read access for website objects.
- Open the website endpoint and verify the result.

## Tools and Services
- Amazon Web Services (AWS) Management Console
- Amazon S3
- HTML
- AWS Region: Asia Pacific (Mumbai) `ap-south-1`

## Bucket Details
- **Bucket name:** `cyber-practical-s3-2026-unique123`
- **Region:** Asia Pacific (Mumbai) `ap-south-1`
- **Versioning:** Enabled
- **Static website hosting:** Enabled
- **Default index document:** `index.html`

## Procedure

### 1. Create an S3 bucket
1. Open the AWS Management Console and navigate to **Amazon S3**.
2. Create a general-purpose bucket in the Mumbai region.
3. Use a globally unique bucket name. The name above is the one used for this demonstration.

### 2. Enable Bucket Versioning
1. Open the bucket and select **Properties**.
2. Find **Bucket Versioning** and choose **Edit**.
3. Enable versioning and save the changes.

Versioning keeps multiple versions of an object when it is uploaded again with the same key. It can help recover from accidental overwrites or deletions. It does not replace a separate backup strategy.

### 3. Upload the website file
1. Open the bucket's **Objects** tab.
2. Upload `index.html` to the root of the bucket.
3. Confirm that `index.html` appears in the object list.

### 4. Enable Static Website Hosting
1. Open **Properties** and locate **Static website hosting**.
2. Select **Edit**, enable static website hosting, and choose **Host a static website**.
3. Set the index document to `index.html`.
4. Save the changes.
5. Copy the bucket website endpoint shown by AWS.

### 5. Configure public read access for the website
For a public static website, the website objects must be readable by visitors.
1. Open **Permissions**.
2. Under **Block public access (bucket settings)**, review the settings and disable the relevant block only if your assignment requires a public website and you understand the implications.
3. Add a bucket policy that grants `s3:GetObject` to everyone for objects in this bucket.
4. Save the policy.

The policy used in this practical is:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForWebsite",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::cyber-practical-s3-2026-unique123/*"
    }
  ]
}
```

**Security note:** This policy makes objects in the bucket publicly readable. Use it only for non-sensitive website files in a practice bucket. Never upload passwords, personal information, credentials, or private documents.

### 6. Test the website
1. Open the website endpoint from the **Static website hosting** section.
2. If the page returns `403 Forbidden`, check that:
   - `index.html` exists at the bucket root and is spelled correctly.
   - Static website hosting is enabled with `index.html` as the index document.
   - The bucket policy resource contains the correct bucket name and ends in `/*`.
   - Public access settings and any organization-level policies permit the intended public access.
3. Refresh the endpoint after saving the settings.

## Sample `index.html`

A ready-to-upload page is included in this project as `index.html`.

## Result
The S3 bucket was configured with versioning enabled and static website hosting enabled. The HTML page displayed successfully through the S3 website endpoint after the public-read configuration was applied.

## Evidence Screenshots
Add your actual AWS screenshots to the `screenshots/` folder and update the filenames below to match your uploaded images.

1. `screenshots/01-bucket-created.png` — S3 bucket and region.
2. `screenshots/02-versioning-enabled.png` — Bucket Versioning set to Enabled.
3. `screenshots/03-index-uploaded.png` — `index.html` visible in Objects.
4. `screenshots/04-static-hosting-enabled.png` — Static website hosting enabled and endpoint shown.
5. `screenshots/05-bucket-policy.png` — Bucket policy configured.
6. `screenshots/06-website-working.png` — Website displayed in the browser.

## Conclusion
This practical demonstrates object versioning and static website hosting using Amazon S3. Versioning supports recovery of previous object versions, while static website hosting serves HTML content through an S3 website endpoint. Public access should be limited to the files intentionally meant for public viewing.
