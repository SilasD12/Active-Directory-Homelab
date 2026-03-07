#### The goal: 
To simulate usual user scenarios in AD, like password resets,
unlocking accounts, forcing password changes, adding users and removing users,
disablling accounts, and moving users.

#### What I configured:
In an OU called "Accounting", the user Alice Smith needed their password reset, so I right-clicked their name and selected, "reset password", and then entered a temperary password and selected the option for the user to change it on logon. Then, I went to the user's properties and, in the account tab, checked "Unlocked account"

- <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/7c6df0fa-1215-41ba-b8c2-0013f1b368d4" />

#### What this mirrors:
In a real environment, users constantly forget their passwords and end up locking themselves out after trying to guess it. We've all had to send a code to our email to reset the password to an online account. Luckily, AD allows IT to simply change a user's password, prompt them to change it when they logon, and unlock their account after failed attemps - all in one place. 

I learned how to navigate to a user's OU and manage their account and its properties, including their password. 


