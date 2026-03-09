# Windows Access Control Lab

## Objective
Practice user, group, and file permission management in Windows.

## Commands Used

Create Users
New-LocalUser -Name user_a
New-LocalUser -Name user_b

Create Group
New-LocalGroup -Name "Administrators"

Add Users to Group
Add-LocalGroupMember -Group "Administrators" -Member "user_a"
Add-LocalGroupMember -Group "Administrators" -Member "user_b"

Create File
New-Item test.txt

Grant Permission
icacls test.txt /grant user_a:F

Run command as user
runas /user:user_a cmd
runas /user:user_b cmd

Check user
whoami

Test access
type test.txt

## Observation
user_a → access allowed  
user_b → access denied
