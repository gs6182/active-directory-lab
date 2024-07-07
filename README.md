[ACTIVE DIR VIDEOS NOTES](https://www.notion.so/ACTIVE-DIR-VIDEOS-NOTES-9d865c4a752141e5b23b52573ce88e68?pvs=21)

Definition : the main idea behind a domain is to centralize the administration of common components of a window computer network in a single repository called active directory 

The server that runs the active directory is known as a domain controller (DC)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5fa90a95-9740-403b-bc02-f80f99ab7c02/b0eb3bc5-969c-44cc-a2ef-7421753404f2/Untitled.png)

advantages of this are that everything could be managed from one place with minimum efforts and also security policies can configure place 

ACTIVE DIRECTORY DOMAIN SERVICE (AD DS):  the core of any windows service acts as a catalouge that holds the information of all the objects that exists on your network 

amongst the many objects supported by ad we have users groups machines printers shares and many others 

### users:

user are one of the most common object type in active directory 

users are known as security PRINCIPALS that they can be authenticated by the domain and can be assigned privileges over resources like files or printer 

two entities 

people : user will generally represent person in your organization that need to access the network like employees 

services:you can also define users to be used by services like IIS or MYSQL. Every single service requires a user to run but service users are different from regular users as they will only have the privileges needed to run their specific service 

### machines

they are another type of object within Active Directory for every computer that joins active Directory a machine object will be created 

they are also considered security principals

domain admins user of this group have administrative privileges over the entire domain 

server operators user in this group can administer domain controllers they cannot change any administrative group membership 

backup operator ; user in this group are allowed to access any file ignoring the their permission they are used to perform backups of data on computers

account operator user in this group can create or modify other accounts in the domain 

domain user includes all existing computers in the domain 

domain controllers includes all existing DCs on the domain 

## Delegation

giving some specific users some control over some OUs(organizational    unit) this process is called delegation 

login using :

THM\username 

password 

command : 

`Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose`

The command you've provided seems to be a PowerShell command used to reset the password for an Active Directory (AD) user account named "sophie". Let me break it down for you:

- `Set-ADAccountPassword`: This cmdlet is used to modify the password of an Active Directory user account.
- `sophie`: This is the username of the Active Directory account for which you want to reset the password.
- `Reset`: This parameter specifies that the password should be reset.
- `NewPassword`: This parameter specifies the new password for the user account.
- `(Read-Host -AsSecureString -Prompt 'New Password')`: This part of the command prompts the user to enter the new password securely. The `Read-Host` cmdlet is used to accept user input, and `AsSecureString` ensures that the password is masked as it is typed in. The `Prompt` parameter provides a message prompting the user to enter the new password.
- `Verbose`: This parameter specifies that the cmdlet should provide detailed information about the actions it is taking while executing.

So, when you run this command, it will prompt you to enter a new password for the "sophie" account, and then it will reset the password for that account using the provided password. Additionally, it will provide verbose output about the actions it performs. Make sure you have the necessary permissions to perform this action within your Active Directory environment.

`Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose`

ie”. Let’s break down the command:

- `Set-ADUser`: This cmdlet is used to modify properties of an Active Directory user account.
- `-ChangePasswordAtLogon $true`: This parameter sets the “Change Password at Next Logon” attribute to true for the specified user account. This means that when the user “sophie” next logs in, they will be required to change their password.
- `-Identity sophie`: This specifies the identity of the user account for which you want to modify properties, in this case, “sophie”.
- `-Verbose`: This parameter specifies that the cmdlet should provide detailed information about the actions it is taking while executing.

So, when you run this command, it will set the “Change Password at Next Logon” attribute to true for the “sophie” user account in Active Directory. This ensures that the next time Sophie logs in, she will be prompted to change

The PowerShell command you've provided is used to set the "Change Password at Next Logon" attribute for the Active Directory user account named "sophie". Let's break down the command:

- `Set-ADUser`: This cmdlet is used to modify properties of an Active Directory user account.
- `ChangePasswordAtLogon $true`: This parameter sets the "Change Password at Next Logon" attribute to true for the specified user account. This means that when the user "sophie" next logs in, they will be required to change their password.
- `Identity sophie`: This specifies the identity of the user account for which you want to modify properties, in this case, "sophie".
- `Verbose`: This parameter specifies that the cmdlet should provide detailed information about the actions it is taking while executing.

So, when you run this command, it will set the "Change Password at Next Logon" attribute to true for the "sophie" user account in Active Directory. This ensures that the next time Sophie logs in, she will be prompted to change her password. Make sure you have the necessary permissions to perform this action within your Active Directory environment.
