## scp command
- The `scp` (secure copy) command is used in Linux and Unix-like operating systems to securely copy files and directories between two locations. 
- It uses the SSH protocol for secure data transfer, ensuring both authentication and encryption.

## Syntax
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~/Desktop$ scp qwe.txt dhyanesh@10.20.40.165:/home/dhyanesh/Desktop
dhyanesh@10.20.40.165's password: 
qwe.txt                                                                         100%   57    16.8KB/s   00:00    
```

## Options
`-P <port>`: Specify the port to connect to on the remote host (default is 22).
`-r`: Recursively copy entire directories.
`-v`: Verbose mode (shows detailed information about the transfer process).
`-C`: Compress data during transfer.
`-i <identity_file>`: Use a specific private key file for authentication.
`-q`: Quiet mode (suppresses progress and error messages).

## Commands
1. Copy a file from local to remote:
    ```bash
    scp file.txt user@remote_host:/path/to/destination/
    ```
1. Copy a file from remote to local:
    ```bash
    scp user@remote_host:/path/to/file.txt /local/destination/
    ````
1. Copy a directory recursively:
    ```bash
    scp -r /local/directory/ user@remote_host:/path/to/destination/
    ```
1. Copy a file using a specific port:
    ```bash
    scp -P 2222 file.txt user@remote_host:/path/to/destination/
    ```
1. Copy a file using a specific private key:
    ```bash
    scp -i ~/.ssh/id_rsa file.txt user@remote_host:/path/to/destination/
    ```
1. Verbose mode:
    ```bash
    scp -v file.txt user@remote_host:/path/to/destination/
    ```
1. Quiet mode:
    ```bash
    scp -q file.txt user@remote_host:/path/to/destination/
    ```