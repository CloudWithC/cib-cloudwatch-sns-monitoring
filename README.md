# CloudWatch Monitoring & SNS Alerting on AWS

## Project Overview

This project demonstrates how to monitor AWS EC2 instance performance using Amazon CloudWatch and automatically send email notifications using Amazon SNS when CPU utilization exceeds a defined threshold.

The solution helps administrators detect performance issues in real time and receive alerts without manually checking server metrics.

---

## Architecture

```text
EC2 Instance
      ↓
CloudWatch Metrics
      ↓
CloudWatch Alarm
      ↓
SNS Topic
      ↓
Email Notification
```

---

## AWS Services Used

- Amazon EC2
- Amazon CloudWatch
- Amazon SNS
- AWS IAM
- Linux (Ubuntu)

---

## Project Workflow

1. Launch an EC2 instance.
2. Monitor CPU utilization using CloudWatch metrics.
3. Create a CloudWatch Alarm with a CPU threshold.
4. Create an SNS Topic and Email Subscription.
5. Connect the CloudWatch Alarm to the SNS Topic.
6. Simulate high CPU usage on the EC2 instance.
7. Trigger the alarm when CPU exceeds the threshold.
8. Receive an email notification through SNS.

---

## Implementation Steps

### Step 1: Launch EC2 Instance

- Created an Ubuntu EC2 instance.
- Connected using SSH.

### Step 2: Create SNS Topic

- Created an SNS topic for notifications.
- Added an email subscription.
- Confirmed the subscription through email.

### Step 3: Configure CloudWatch Alarm

- Monitored CPUUtilization metric.
- Set threshold above normal CPU usage.
- Configured alarm action to send notifications through SNS.

### Step 4: Generate CPU Load

Used the following command to simulate high CPU utilization:

```bash
yes > /dev/null &
```

Multiple processes were started to increase CPU usage.

### Step 5: Verify Alerting

- Alarm state changed from OK to In Alarm.
- SNS successfully sent email notifications.

---

## Added Screenshots

### Alarm in OK State
### Alarm Triggered
### SNS Email Notification

---

## Key Learnings

- AWS CloudWatch monitoring
- CloudWatch Metrics and Alarms
- Amazon SNS notifications
- EC2 performance monitoring
- Event-driven alerting
- Troubleshooting SNS subscriptions
- Monitoring Linux server workloads

---

## Skills Demonstrated

- AWS Monitoring
- Cloud Operations
- Incident Alerting
- Infrastructure Monitoring
- Linux Administration
- AWS SNS
- CloudWatch Alarms

---

## Future Improvements

- SMS Notifications
- Slack Integration
- Multiple Alarm Conditions
- Dashboard Visualization
- Automated Incident Response
