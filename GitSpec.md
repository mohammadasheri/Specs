# Git Specifications

## add Credentials and save them in git 
```
git config --global user.email "mhm.asheri@gmail.com"
git config --global user.name "Mohamamd Asheri"
git config credential.helper store
```
## generate new ssh key
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```
## Adding your SSH key to the ssh-agent
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```
## copy generated ssh key from system
```
gedit id_rsa.pub
```
