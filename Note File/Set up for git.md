## 1.Set your connection with your github account
```bash
$ ssh-keygen -t rsa -C "your@e-mail_account"
```
enter the passphrase if you need, then you'll get your key fingerprint
## 2.Remotely verify your github account
```bash
$ ssh -v git@github.com
```
while you may still get the result below(it's OK, just continue):  
`debug1: No more authentication methods to try.`  
`git@github.com: Permission denied (publickey).`
## 3.Run the following command
```bash
$ ssh-agent -s
$ ssh-add ~/.ssh/id_rsa
```
if you get `Could not open a connection to your authentication agent.`, run 
```bash
$ ssh-agent bash`
$ ssh-add ~/.ssh/id_rsa`
```
## 4.Now you can successfully run the command:
```bash
$ ssh -T git@github.com
#you will get the result like "Hi XXX! You've successfully authenticated, but GitHub does not provide shell access."
$ git init #creat the git file foder
```
## 5.Now it's time to pull your git
```bash
$ git remote add origin git@github.com:XXX.git #XXX is your repository
$ git pull origin master
$ git rm -r --cached Leetcode-Note/ #use this command to remove the file folder in your repository
$ git commit -m 'remove Leetcode-Note/' #commit the change and add the operation description
```
