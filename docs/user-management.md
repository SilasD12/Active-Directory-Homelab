#### The goal: 
To simulate usual user scenarios in AD, like password resets,
unlocking accounts, forcing password changes, adding users and removing users,
disabling accounts, and moving users.


#### What I configured:
**1. Password Management** - 
The user Alice Smith in the Accounting OU needed their password reset and account unlocked after too many failed attempts - used the "reset password" tab to set a temporary password that the user will change on startup. The "unlock account" option was selected before accepting the changes. 


- <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/7c6df0fa-1215-41ba-b8c2-0013f1b368d4" />

- #### What this mirrors:
  - In a real environment, users constantly forget their passwords and end up       locking themselves out after trying to guess it. We've all had to send a       code to our email to reset the password to an online account. Luckily, AD       allows IT to simply change a user's password, prompt them to change it         when they logon, and unlock their account after failed attemps - all in         one place.

**2. Adding a new user** - 
A new hire, Jack Smart, is joining the Accounting department. Created a new user in the Accounting OU and entered the user's name and username. His account will have a temporary password that will be changed on logon. 

The Accounting OU provides the necessary files and objects for Jack Smart's job in the Accounting department, ensuring his account follows the Principle of Least Privilege. 

- <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/b6cd6264-1143-4670-90a5-08f285350317" />

- #### What this mirrors:
  - In a real environment, new employees will need an account within the local
    domain, and the domain's AD will need a new account for them to manage and
    control resources to. This demonstrates how to complete a task that will
    be completed often, especially at larger companies. 

  - This task can and should be automated when multiple users need 
    to simultaneously be created repeatedly. This can be done through a
    Powershell script that uses a CSV file as input. 

**3. Disable a user's account** - 
Accounting employee Charlie Brown is leaving the company today. The domain account must be offboarded following standard procedure. His account is disabled through right-clicking on it and is moved from the Accounting OU to the Disabled Users OU. In a production environment, additional steps would include revoking MFA tokens, delegating the user's email to their manager, and deactivating any VPN certificates.

- The audit trail
  - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/e6d2fb12-b0a7-4d65-b21a-c2a75eb20eb5" />

- Removing the user from the Accounting Group
  -  <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/e4559357-1bd7-4636-a7db-a5fd02ddd640" />

- Disabling the user's account and adding it to the DisabledUsers OU
  - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/a22bfce8-1db4-40c1-bfe3-bd58883c1bfe" />

- Resetting the account's password to a random string
  - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/c7e60a45-3ef3-4ce4-a4a5-0be025bd356f" />

- #### What this mirrors:
  - When an employee leaves a company, their domain account must be disabled, and eventually deleted if the employee doesn't come back. This is to make sure that the user cannot access company resources, but if they are rehired, their account and associated OUs, groups, and objects can be reinstated easily. This is why an audit trail of the account is important to take. 

**4. Migrating a user's domain account to another OU**
- Jane Doe has accepted a new position in the Management department. Jane Doe's domain account must be updated and placed into the proper OUs and security groups. The account will be removed from the accounting security group and moved to the management security group and the Management OU. 

- The audit trail
  - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/9ea34246-af4c-4e5e-a810-de857369724a" />

- 
