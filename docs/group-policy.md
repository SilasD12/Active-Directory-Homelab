### List of GPOs in my Domain and OUs. 

- **Screensaver Lock Policy**
  - This policy is enabled domain-wide and locks a user's screen after 10 minutes of inactivity
  - Has Screen Saver Timeout, Password Protect the screen saver, and enable screen saver enabled. 
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/8077d566-e019-4db9-9016-225eaf8a934e" />

  - What this mirrors:
    - It is a compliance requirement in many industries to have users screenlocks, so their computer cannot be accessed while they are away.  

- **Restrict Control Panel Policy**
  - This policy is applied to select OUs and prohibits their users from accesing the control panel.
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/3baaa210-bdba-4577-b672-f168d2d01b1a" />

- **Password Policy**
  - This policy is enabled domain-wide and is configured in the Default Domain Policy GPO
  - Sets password requirements to make domain accounts more secure
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/9bdeea45-0dbc-4dad-b669-94abe3a1a213" />

  - What this mirrors:
    - It follows NIST's password guidelines, such as a minimum password length of 8 characters, as well as potential company security standards. Password brute force attacks or leaks occur constantly and a password policy is necessary to make sure users are protecting themselves from such attacks. 
