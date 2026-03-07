#### The goal: 
To simulate usual user scenarios in AD, like password resets,
unlocking accounts, forcing password changes, adding users and removing users,
disablling accounts, and moving users.


#### What I configured:
**1. Password Management** - 
In an OU called "Accounting", the user Alice Smith needed their password reset, so I right-clicked their name and selected, "reset password", and then entered a temperary password and selected the option for the user to change it on logon. Then, I went to the user's properties and, in the account tab, checked "Unlocked account"

- <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/7c6df0fa-1215-41ba-b8c2-0013f1b368d4" />

- #### What this mirrors:
  - In a real environment, users constantly forget their passwords and end up       locking themselves out after trying to guess it. We've all had to send a       code to our email to reset the password to an online account. Luckily, AD       allows IT to simply change a user's password, prompt them to change it         when they logon, and unlock their account after failed attemps - all in         one place.

**2. Adding a new user** - 
I will showcase how to add a new user to a preexisting OU. Let's say a new employee named Jack Smart was hired for an accounting role. It is necessary to add him to the accounting group to have access to all the necessary files and objects for him to complete his job, as well as the policies so the Principal of Least Privilege can be followed. 

To do this, I go back to the Active Directory Users and Computers tool, find the Accounting OU inside the homelab.local domain, right-click it, and select New > User. From here, I enter his name, lastname, and a username of "jsmart@homelab.local". I give him a temperary password and select "User must change password at next logon." Then, I finish the account setup. 

- <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/b6cd6264-1143-4670-90a5-08f285350317" />

- #### What this mirrors:
  - In a real environment, new employees will need an account within the local
    domain, and the domain's AD will need a new account for them to manage and
    control resources to. This demonstraits how to complete a task that will
    be completed often, especially at larger companies. 
