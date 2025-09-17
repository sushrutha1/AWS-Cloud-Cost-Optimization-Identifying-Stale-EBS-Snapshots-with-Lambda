# AWS-Cloud-Cost-Optimization-Identifying-Stale-EBS-Snapshots-with-Lambda

AWS Cloud Cost Optimization – Identifying Stale EBS Snapshots with Lambda
📌 Project Overview

This project demonstrates cloud cost optimization on AWS by automatically identifying and deleting stale EBS snapshots.
The Lambda function:

*Fetches all EBS snapshots owned by the account.

*Retrieves a list of active EC2 instances (running and stopped).

*Checks if snapshots are linked to any active volume/instance.

*Deletes stale snapshots to optimize storage costs.

*Technology used: AWS Lambda, IAM, EC2, EBS, Boto3.

⚙️ Steps to Implement
1️⃣ Create an EC2 Instance & Snapshot

*Launch a t2.micro / t3.micro EC2 instance (Free Tier eligible).

*Attach an EBS volume if not already present.

*Create a snapshot of the attached EBS volume.

*Stop and terminate the EC2 instance → snapshot remains in the account.

2️⃣ Create the Lambda Function

*Go to AWS Lambda → Create function.

*Choose Author from scratch.

*Add the following Boto3 code:

3️⃣ Create IAM Role for Lambda

*Go to IAM → Roles → Create role.

*Select Lambda as trusted entity.

*Attach a custom policy with permissions

*Name it LambdaEBSStaleCleanupRole.

*Attach this role to the Lambda function.

4️⃣ Run the Lambda Function

*First run → no snapshot deleted if EC2 is active.

*Delete your EC2 instance → snapshots remain.

*Re-run the Lambda → stale snapshots are deleted.

✅ Outcome

*Any orphaned snapshots (not linked to an active instance/volume) are automatically deleted.

*This reduces unnecessary storage costs in AWS.

🙏 Acknowledgment
special Thanks to Abhishek.Veeramalla  who guided me in understanding AWS cost optimization.
