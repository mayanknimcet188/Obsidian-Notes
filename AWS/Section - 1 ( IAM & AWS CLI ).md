## IAM Introduction
### IAM: Users & Groups (Global Service)
- **IAM** = Identity and Access Management, Global Service
- Root account created by default, shoudn't be used or shared.
- Users are people within your organization and can be grouped.

### IAM: Permissions
- Users or Groups can be assigned JSON documents called **policies**.
- These policies define the permissions of the users.
- In AWS, we apply a principle called the **Least Privilege Principle** don't give more permissions than a user needs.

### IAM MFA Overview
To protect users and groups from being compromised
- **IAM Password Policy**
	- In AWS, we can set up password policy with different options:
		- Set a minimum password length.
		- Require specific character types.
		- Allow all IAM users to change their own passwords.
		- Require users to change their password after some time (password expiration).
		- Prevent password re-use.
- **Mutli Factor Authentication - MFA**
	- Users have access to your account and can possibly change configuration or delete resources in your AWS account.
	- We want to protect our Root Account and IAM users.
	- **MFA** = password you know + security device your own.
		- **Benefit**: even if password is stolen, the account is not compromised.
	- MFA devices options in AWS 
		- Virtual MFA device
			- Google Authenticator (phone only)
			- Authy (multi-device)
		- Universal 2nd Factor (U2F) Security Key eg. Yubikey (3rd party)
		- Hardware Key Fob MFA device.

### How can users access AWS?
1. AWS Management Console (protected by password + MFA)
2. AWS Command Line Interface (CLI) : protected by access keys.
3. AWS Software Developer Kit (SDK) - for code : protected by access keys
	- Access Keys generated through AWS console and users manage their own access keys. They are like secret keys and should be confidential and are not to be shared.
		- Access Key ID ~= password
		- Secret Access Key ~= password
		- Access keys useful for AWS CLI / or using SDK.