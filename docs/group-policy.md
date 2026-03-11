### List of GPOs in my Domain and OUs. 

- **Screensaver Lock Policy**
  - This policy locks a user's screen after 10 minutes of inactivity to prevent other employees or people from accessing their computer.
  - The policy is linked domain-wide
  - Has Screen Saver Timeout, Password Protect the screen saver, and enable screen saver enabled. 
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/8077d566-e019-4db9-9016-225eaf8a934e" />

  - What this mirrors:
    - It is a compliance requirement in many industries to have users screenlocks, so their computer cannot be accessed while they are away.  

- **Restrict Control Panel Policy**
  - This policy is applied to prohibit users from accessing the control panel and changing/configuring settings. 
  - The policy is linked to all OUs besides the IT department's OU.
  - Only has prohibit access to Control Panel and PC settings, since the rest are settings for the Control Panel. 
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/3baaa210-bdba-4577-b672-f168d2d01b1a" />
    
    - What this mirrors:
      - Users besides IT do not have a reason to access the Window's Control Panel for their job duties. This follows the Principle of Least Privilege and ensures users are not accessing more than necessary. Plus, the control panel houses settings that can be problematic if accessed by the wrong or malicious actor. 
  
- **Password Policy**
  - This policy sets password requirements to make domain accounts more secure.
  - The policy is linked domain-wide and set in the Default Domain Policy GPO, since it already has a password policy applied.
  - What changed was the maximum password age to 90 days, minimum password length to 10 characters, and the 5 passwords remembered. 
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/9bdeea45-0dbc-4dad-b669-94abe3a1a213" />

  - What this mirrors:
    - It follows NIST's password guidelines, such as a minimum password length of 8 characters, as well as potential company security standards. Password brute force attacks or leaks occur constantly and a password policy is necessary to make sure users are protecting themselves from such attacks by not setting a basic password. 
