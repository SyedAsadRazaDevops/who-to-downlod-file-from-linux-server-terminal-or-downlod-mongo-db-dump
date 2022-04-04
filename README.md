# who-to-downlod-file-from-linux-server-terminal-or-downlod-mongo-db-dump

it seem very difficault to downlod file and folder from linux server throw the terminal or cloud server.

# 1 make mongo db dump
```
sudo mongodump --db <mydbname>
```
# 2 make tar.gz ZIP file of folder
```
sudo tar –czvf <mydbname>.tar.gz <path of db dump($home/project/)>
```
[[[Some older versions of tar don't like the " - " at the start of the commands try "tar cvpfz ..." ]]]
```
sudo tar czvf <mydbname>.tar.gz
```
# 3 downlod this zip file or folder
**Make sure**,your local server private key is attached in cloud or othere server. The **authorized_keys** file in SSH specifies the SSH keys that can be used for logging into the user account for which the file is configured.

on the path:
```
nano ~/.ssh/authorized_keys 
```


just run this command:

```
scp -i .ssh/id_rsa root@123.45.67.89:/home/project/mydbname.tar.gz <local-server-downlod-path(/home/devops/mydumps)
```
# 4 extract the zip folder
```
tar -xvf mydbname.tar.gz
```





