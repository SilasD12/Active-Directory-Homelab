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
      - Users besides IT do not have a reason to access the Windows Control Panel for their job duties. This follows the Principle of Least Privilege and ensures users are not accessing more than necessary. Plus, the control panel houses settings that can be problematic if accessed by the wrong or malicious actor. 
  
- **Password Policy**
  - This policy sets password requirements to make domain accounts more secure.
  - The policy is linked domain-wide and set in the Default Domain Policy GPO, since it already has a password policy applied.
  - What changed was the maximum password age to 90 days, minimum password length to 10 characters, complexity enforcement, and the 5 passwords remembered. 
    - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/9bdeea45-0dbc-4dad-b669-94abe3a1a213" />

  - What this mirrors:
    - Password expiration policies like 90-day rotation are common in enterprise environments and align with traditional security standards. If a user is forced to change their password frequently, the password the user sets will be similar to their previous password, and the password becomes weaker overtime. The settings also protect against password brute force attacks due to the increased minimum length. Finally, password leaks occur constantly and a password policy is necessary to make sure users are protecting themselves from such attacks by not setting a basic password. 

- **Disable USB Storage**
  - This policy is to ensure no external USB drives can be plugged into the computer.
  - The policy is linked to all OUs that do not need to use external USB drives.
  - The GPO made it to where users cannot connect external storage devices, preventing data being copied from and to the machine. This mitigates data leakage and prevents malware from bad actors.
  - <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/56b33479-8428-4539-b4f2-ea0462b89526" />

  - What this mirrors:
    - End users will want to plug in their own USB drives for various reasons; more storage, transfer files between the driev and pc, or possibly to infect the computer and inflict damage to the company. This GPO policy mitigates this risk by ensuring that no read and writes occur between the PC and USB drive, keeping employees from breaking security or data compliances and the computer and company safe. 
 
