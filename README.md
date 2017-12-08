# Ssh access
-----------------------------
Below instructions explain how allow connect in server via ssh external host with private and public key (rsa cryptosystem).

# Usage
-----------------------------

### **In external host:** run ssh-keygen (Unix utility that is used to generate, manage, and convert authentication keys for ssh authentication).
```
ssh-keygen
```

### **In external host:** Just can skip all steps in command line interface.
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/vagrant/.ssh/id_rsa.
Your public key has been saved in /home/vagrant/.ssh/id_rsa.pub.
The key fingerprint is:
a6:74:cf:88:90:a3:7f:9b:a3:07:ff:4c:1f:ac:ee:0a vagrant@cms
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|                 |
|                 |
|     .           |
|    + . S        |
|   ..+ = =       |
|  . Eoo o =      |
|   . .=+ o .     |
|    o++B* .      |
+-----------------+
```

### **In external host:** Above statement generate in **~/.ssh** folder private and public ssh keys in **id_rsa** and **id_rsa.pub** respectively.
### **In external host:** Copy public key (**id_rsa.pub**).
```
cat ~/.ssh/id_rsa.pub
```

### **In server:** Just paste the external host public key in **~/.ssh/authorized_keys** (In this file per line you can find all external host allowed to access to this server)
```
nano ~/.ssh/authorized_keys
```

### Finish :D

### **In external host:** Just access to server.
```
ssh root@serverip
```
### Or
```
ssh root@serverdomain
```