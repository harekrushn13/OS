## sftp command
- The sftp (Secure File Transfer Protocol) command is used to securely transfer files between a local and a remote system over an encrypted SSH connection. 
- It provides an interactive interface similar to FTP but with the security of SSH.

## Options
- `-P <port>`	Specify the SSH port to connect to (default is 22).
- `-i <identity_file>`	Use a specific private key file for authentication.
- `-b <batch_file>`	Run a batch file containing SFTP commands.
- `-v`	Verbose mode (shows detailed connection information).
- `get <remote_file>`	Download a file from the remote system.
- `put <local_file>`	Upload a file to the remote system.
- `mget <remote_files>`	Download multiple files (supports wildcards).
- `mput <local_files>`	Upload multiple files (supports wildcards).

## Syntax
```bash
sftp user@remote_host
sftp> get remote_file.txt


sftp user@remote_host
sftp> put local_file.txt

sftp user@remote_host
sftp> mget *.txt


sftp user@remote_host
sftp> mput *.txt
```