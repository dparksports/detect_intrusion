# detect_intrusion


## To check if any known backdoored XZ version is present on your system
```sh
strings `which xz` | grep '5\.6\.[01]'
```

## To check whether there is an OpenSSH server loading the Liblzma library
```sh
lsof -p $(ps -aux | grep 'sshd' | grep 'listener' | awk '{print $2}') | grep '\.so' | grep 'liblzma'
```


## checks whether a malicious version of xz or liblzma is installed on the system
```sh
./cve-2024-3094-detector.sh
```
