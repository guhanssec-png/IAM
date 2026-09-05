IAM

Aim

To create and configure IAM users and groups in AWS, assign permissions using IAM policies, enable console access, and verify role-based access to Amazon S3.


Procedure

Step 1: Login to AWS Management Console
Open a web browser.
Go to the AWS Management Console.
Sign in using the AWS account credentials.
Search for IAM using the AWS search bar.
Open IAM (Identity and Access Management).

Step 2: Create an IAM Group
In the IAM dashboard, select User groups from the left-side menu.
Click Create group.
Enter the group name: cloudSecurity_2026
Do not add users at this stage if the user will be created separately.
Click Create user group. The group cloudSecurity_2026 is now created.

Step 3: Attach an IAM Policy to the Group
Open the cloudSecurity_2026 group.
Select the Permissions tab.
Click Add permissions.
Select Attach policies directly.
Search for: AmazonS3ReadOnlyAccess
Select the checkbox for AmazonS3ReadOnlyAccess.
Click Next and then Add permissions. The group now has read-only access to Amazon S3.

Step 4: Create an IAM User
From the IAM navigation menu, select Users.
Click Create user.
Enter the username: student01
Click Next.

Step 5: Add the User to the IAM Group
On the Permissions page, select Add user to group.
Select: cloudSecurity_2026
Click Next.
Review the configuration.
Click Create user. The user is now a member of the cloudSecurity_2026 group.

Step 6: Verify User Permissions
Open IAM → Users.
Click student01.
Open the Permissions tab.
Verify that the following policy is displayed: AmazonS3ReadOnlyAccess
Check the Attached via column.
It should indicate that the policy is attached through:

Group: cloudSecurity_2026 This demonstrates: student01 ↓ cloudSecurity_2026 ↓ AmazonS3ReadOnlyAccess ↓ Amazon S3 Read-only Access

Step 7: Enable Console Access
Initially, console access for student01 may be disabled.

Open IAM → Users → student01.
Select Security credentials.
Locate Console access / AWS Management Console access.
Enable console access.
Create a console password for student01.
Complete the configuration. Note: Do not share the password with other users.

Step 8: Obtain the AWS Account ID
The IAM user login requires the AWS account ID.

Your AWS account ID is a 12-digit number.
It can be found in the AWS account information.
For the demonstration account used in this experiment, the account ID was: 360416501079 Students should use their own AWS account ID when performing the experiment.

Step 9: Login as the IAM User
Sign out from the current AWS administrator/root session.
Open a new browser window or Incognito/Private window.
Open the AWS sign-in page.
Select IAM user login.
Enter the AWS account ID.
Enter the IAM username: student01
Enter the password created in Step 7.

Click Sign in. The AWS Management Console should now open under the IAM user student01.

Step 10: Verify Amazon S3 Access
After logging in as student01, search for S3.
Open Amazon S3.
Select General purpose buckets.
Verify that the previously created S3 bucket is visible.
Open the bucket.
Verify that the user can view the bucket and its objects. This confirms that the IAM policy is providing S3 read access.
Step 11: Verify Least-Privilege Access
The user student01 has been assigned: AmazonS3ReadOnlyAccess Therefore, the user should have read access but should not have permission to perform S3 write/delete operations. For testing:

Open the S3 bucket as student01.
Observe the available operations.
Do not delete any existing object.
If you test an upload operation, do not use an important file.
The actual permission check occurs when AWS attempts the S3 operation.
A read-only user should receive an Access Denied response for unauthorized write/delete operations.

output:
<img width="1257" height="622" alt="644823447-d8c1603d-2d3a-4d2e-b068-b2e6213e8f7a" src="https://github.com/user-attachments/assets/b85e446c-1417-4b6b-b23c-9bcebfaa569a" />
<img width="1229" height="597" alt="644823812-bc9569fb-35a5-452b-b0a4-5071c608d1cd" src="https://github.com/user-attachments/assets/a40a3d90-0260-4924-b5a8-6701a19af261" />

Result:
Thus, Identity and Access Management (IAM) was successfully implemented in AWS by creating an IAM group, assigning an S3 read-only policy, creating an IAM user, enabling console access, and verifying permission-based access to Amazon S3.
