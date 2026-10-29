# AWS CloudWatch Monitoring & Alerts

## Overview
This practical demonstrates how to monitor an Amazon EC2 instance with Amazon CloudWatch and create a CPU utilization alarm.

## Objective
- View EC2 CPU utilization metrics in CloudWatch.
- Create a metric alarm using a 70% CPU utilization threshold.
- Configure an alarm notification action using Amazon SNS.
- Verify that the alarm is created and check its state.

## AWS Services Used
- **Amazon EC2** — the monitored web-server instance.
- **Amazon CloudWatch** — metric graphs and alarm evaluation.
- **Amazon SNS** — optional email notifications for alarm state changes.

## Configuration
- **Metric namespace:** `AWS/EC2`
- **Metric:** `CPUUtilization`
- **Statistic:** Average
- **Period:** 5 minutes
- **Condition:** CPU utilization greater than 70%
- **Evaluation:** 1 datapoint within 5 minutes
- **Alarm name:** `EC2-CPU-High-Alarm`
- **Notification topic:** `EC2-CPU-Alerts` (as configured during the practical)

## Procedure
1. Open the AWS Management Console and select the **Asia Pacific (Mumbai)** region.
2. Open **CloudWatch → Metrics → EC2 → Per-Instance Metrics**.
3. Select the `CPUUtilization` metric for the EC2 instance.
4. Choose **Create alarm**.
5. Set the threshold to **Greater than 70** and use a 5-minute period.
6. Configure an SNS topic and email endpoint if notifications are required. Create the topic and confirm the subscription from the email AWS sends.
7. Name the alarm `EC2-CPU-High-Alarm`, review the settings, and create the alarm.
8. Open **CloudWatch → Alarms** and verify the alarm state.

## Result
The alarm was created successfully. The final captured screen shows the alarm in the **OK** state, with actions enabled. This indicates the alarm condition was not breached at the time of the screenshot. The alarm changes to `ALARM` only when the configured threshold and evaluation criteria are met.

## Screenshots
Screenshots are stored in the [`screenshots/`](screenshots/) folder.

| File | What it shows |
|---|---|
| `01-cloudwatch-cpu-metric.png` | EC2 CPU utilization metric graph |
| `02-create-alarm-threshold-70.png` | Alarm metric and threshold configuration |
| `03-configure-notification-actions.png` | Alarm notification actions |
| `04-add-alarm-details.png` | Alarm name and description |
| `05-preview-and-create-alarm.png` | Final review before creation |
| `06-alarm-created.png` | Alarm visible in the alarms list |
| `07-alarm-status-ok.png` | Final alarm details and OK state |

## Important Notes
- An `OK` state is a valid result when CPU utilization remains below the configured threshold.
- `Insufficient data` may appear briefly while CloudWatch gathers enough metric data.
- Email notifications require a successfully created SNS topic and a confirmed email subscription.
- Do not commit AWS passwords, access keys, secret keys, MFA codes, or other credentials to GitHub.
- Before publishing, review screenshots and blur account IDs, email addresses, instance IDs, or other details if you do not want them public.

## GitHub Upload Checklist
- [ ] Create a new GitHub repository named `AWS-CloudWatch-Monitoring-Alerts`.
- [ ] Keep this `README.md` in the repository root.
- [ ] Upload the `screenshots/` folder and its image files.
- [ ] Check that all images render correctly in the README.
- [ ] Review screenshots for personal or account details before making the repository public.
- [ ] Commit the files and push them to GitHub.
- [ ] Open the repository page once after upload to confirm the README and screenshots are visible.

## Suggested Git commit message
`Add AWS CloudWatch monitoring and CPU alarm practical`
