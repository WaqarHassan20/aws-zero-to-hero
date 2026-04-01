## What Is IAM in AWS

IAM (Identity and Access Management) is the AWS service used to control who can access AWS resources and what actions they can perform.

- you must be the authenticated person to access AWS resources, and IAM helps you manage that access securely.
- just like the bank system only allow its staff to access certain areas, IAM allows you to define who can do what in your AWS environment.
- without authentication and authorization, anyone could access your AWS resources, which is a huge security risk. 

### Main Key Points

- `Users`: Identities for people or applications. This simply creates a user account for accessing AWS resources.
  
- `Policies`: JSON documents that define actions. Like what this user can do and on which resources.
  
- `Groups`: Collection of users with shared permissions. in companies people daily leave and join, so instead of managing permissions for each user, you can manage them at the group level. you makes groups for developers, QA, DBadmins, others etc. and assign users to those groups. the new created user will request and tell who i am and you join them in that specific group, and they will automatically get the permissions of that group.
  
- `Roles`: Temporary access identities that can be assumed by users or services.
- Principle of least privilege: Grant only the permissions needed.

### Steps for creating a new user in IAM

1. Go to the IAM console in AWS.
2. Click on "Users" and then "Add user".
3. Enter a username and select the type of access (programmatic, AWS Management Console, or both).
4. check the provide user acces to console check box.
5. check the auto generated password check box.
6. check the user must create a new password at next sign-in check box.
7. for now just add the user to a group with no permissions, we will add permissions later.and no policies for now. We'll  cover that in the next section.

This is the .csv file generated after creating the user, it contains the username, password, and console sign-in URL for the new user. You should keep this information secure and share it only with the intended user.

now login using the iam user credentials to the AWS console, and you will see that you have no permissions to do anything, because we haven't assigned any permissions to this user yet. in the next section we will learn how to assign permissions to users using policies.

now again go to the IAM console and click on "Users", then click on the username you just created, and then click on the "Permissions" tab. here you can see that there are no permissions assigned to this user. click on "Add permissions" to assign permissions to this user.
then click the add policies directly button

<!-- D60ghkd[*& -->