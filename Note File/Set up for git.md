## 1.Set your connection with your github account
```bash
> $ ssh-keygen -t rsa -C "your@e-mail_account"
```
enter the passphrase if you need, then you'll get your key fingerprint
## 2.Remotely verify your github account
```bash
$ ssh -v git@github.com
```
while you may still get the result below(it's OK, just continue):
`
debug1: No more authentication methods to try.
git@github.com: Permission denied (publickey).
`
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
