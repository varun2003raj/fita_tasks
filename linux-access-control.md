# Linux Access Control Lab (Kali)

## Objective
Create two users in the same group and demonstrate file access control where one user has permission and the other does not.

## Commands Used

Create Users--
sudo adduser user_a
sudo adduser user_b

Add Users to Group--
sudo usermod -aG sudo user_a
sudo usermod -aG sudo user_b

Create Test File--
touch /tmp/test.txt

Change File Owner--
sudo chown user_a /tmp/test.txt

Set File Permission--
sudo chmod 700 /tmp/test.txt

## Test Access

Login as user_a
su - user_a
cat /tmp/test.txt
exit

Result: Access Allowed

Login as user_b
su - user_b
cat /tmp/test.txt
exit

Result: Permission Denied

## Observation

User: user_a
Group: sudo
Access: Allowed

User: user_b
Group: sudo
Access: Denied

## Conclusion
Linux file permissions are controlled by ownership and permission bits. 
Since the file owner is user_a and permission is set to 700, only the owner has access to the file while other users are denied access.
