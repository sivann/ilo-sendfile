# ilo-sendfile
Send a binary file to the server filesystem (Linux) via the HP iLO serial console. 

Use case/why I wrote this: imagine your server lost network connectivity after updating a linux network driver. 
This is a quick hack to upload the new binary driver via the iLO serial console CLI (vsp). 


It uploads an already  base64-encoded file slowly with rate-limiting allowing for a successful upload.

# Howto:
* edit sendfile-ilo.exp and replace the following strings 
* MY_SERVER_IP: set to the ilo IP
* MY_ILO_PASSWORD: set to the ilo Password (for user Administrator)
* MY_ROOT_PASSWORD: set to the server root password. If you require another user, also change the "root"


```
my_pc $ base64 file_to_be_uploaded.tgz > tosend #  base64 your file in a file named "tosend":
my_pc $ ./sendfile-ilo.exp                      # run the script
# Your file should now be transefered and named "sent" on the server, decode it on the remote server prompt:
my_server $ base64  -d sent > file_to_be_uploaded.tgz
```


