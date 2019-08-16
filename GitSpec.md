# Git Specifications

## add Credentials and save them in git 
```
git config --global user.email "mhm.asheri@gmail.com"
git config --global user.name "Mohamamd Asheri"
git config credential.helper store
```
## Generate new ssh key
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
## Copy generated ssh key from system
```
cd ~/.ssh
gedit id_rsa.pub
```

## Reset the origin master to a previous commit
```
git push origin +91299e1442356d550cbb77a49a80a34df942d90b^:master
```

## Cherry-pick
```
git cherry-pick c90fd66
```
## Change the url for a remote git repository
```
git remote set-url origin git://new.url.here
```
## New repo on github
```
git remote add origin https://github.com/your username/project name.git
```
## Remove an existing repo
```
git remote remove origin (or other remote name)
```
## Reset hard the origin master branch to a specific log id
```
git push origin +91299e1442356d550cbb77a49a80a34df942d90b^:master
```
## Clone a specific Git branch
```
git clone git-url -b branch-name
```
## Unstage the commit
```
Git rm --cashed
```


