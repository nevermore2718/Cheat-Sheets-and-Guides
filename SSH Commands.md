## What is SSH?
SSH (short for "Secure Shell" or "Secure Socket Shell") is a network protocol for accessing network services securely over unsecured networks. It includes the suite of utilities implementing it, such as:

* ssh-keygen: for creating new authentication key pairs for SSH.
* SCP (Secure Copy Protocol): for copying files between hosts on a network.
* SFTP (Secure File Transfer Protocol): for sending and receiving files. It's an SSH-secured version of FTP (File Transfer Protocol), and it ahs replaced FTP and FTPS (FTP Secure) as the preferred mechanism for file sharing over the Internet.

An SSH server, by default, listens for connections on the standard Transmission Control Protocol (TCP) port 22. Your applications may listen for SSH connections on other ports.

SSH lets us securely manage remote systems and applications, such as logging into another computer over a network, executing commands, and moving files from one computer to another. An advanced SSH functionality is the creation of secure tunnels to run other application protocols remotely.

## Basic SSH Commands
| Command | Description |
| ------- | ----------- |
| ssh | Connect to a remote server | 
| ssh pi@raspberry | Connect to the device raspberry on the default SSH port 22 as user pi |
| ssh pi@raspberry -p 3344 | Connect to the device raspberry on a specifc port 3344 as user pi |
| ssh -i /path/file.pem admin@192.168.1.1 | Connect to root@192.168.1.1 via the key file /path/file.pem as user admin |
| ssh root@192.168.2. 'ls -l' | Execute remote command ls -l on 192.168.2.2 as user root |
| $ ssh user@192.168.3.3 bash < script.sh | Invoke the script script.sh in the current working directory spawning the SSH session to 192.168.3.3 as user user |
| ssh friend@Best.local "tar cvzf = ~/ffmpeg" > output.tgz | Compress the ~/ffmpeg directory and download it from a server Best.local as user friend |
| ssh-keygen | Generate SSH keys (follow the prompts) |
| ssh-keygen -F [ip/hostname] | Search for some IP address or hostname from ~/.ssh/known_hosts (logged-in host) |
| ssh-keygen -R [ip/hostname] | Remove some IP address or hostname from ~/.ssh/known_hosts(logged-in host) |
| ssh-keygen -f ~/.ssh/filename | Specify file name |
| ssh-keygen -y -f private.key > public.pub | Generate public key from private key |
| ssh-keygen -c -f ~/.ssh/id_rsa | Change the comment of the key file ~/.ssh/id_rsa |
| ssh-keygen -p -f ~/.ssh/id_rsa | Change passphrase of private key ~/.ssh/id_rsa |
| ssh-keygen -t rsa -b 4096 -c "my@email.com" | Generate an RSA 4096-bit key with "my@email.com" as a comment:  -t Type of key (rsa, ed25519, dsa, ecdsa), b: The number of bits in the key, c: Provides a new comment |
| scp | Copy files securely between servers |
| scp user@server:/folder/file.ext dest/ | Copy from remote to local destination dest/|
| scp dest/file.ext user@server:/folder | Copy from local to remote |
| scp user@server1:/file.ext user2@server2:/folder| Copy between two different servers |
| scp user@server:/folder/* | Copies from a server folder to the current folder on the local machine |
| scp -r | Recursively copy entire directories | 
| scp -r user@server:/ folder dest/| Copy the entire folder to the local destination dest/ |
| scp -C | Option to compress data |
| scp -v | Option to print verbose into |
| scp -p | Option to preserve the last modifiication timestamps of the transferred files |
| scp -P 8080 | Option to connect to remote host port 8080 |
| scp -B | Option for batch mode and prevent you from entering passwords or passphrases | sftp | Securely transfer files between servers |
| sftp -p | Option to preserve the last modification timestamps of the transferred files |
| sftp -P 8080 | Option to connect to remote host port 8080 |
| sftp -r | Recursively copy entire directories when uploading and downloading. SFTP doesn't follow symbolic links encountered in the tree traversal.

## Remote Server Management
| Command | Description |
| ------- | ----------- |
| cd | Change the current working directory |
| kill | Stop a running process |
| ls | List files and directory |
| mkdir | Create a new directory |
| mv | Move files or directories |
| nano | Edit a file in the terminal using Nano |
| ps | List running processes |
| pwd | Display the current working directory |
| tail | View the last few (10, by default) lines of a file |
| top | Monitor system resources and processes |
| touch | Create a new file or update the timestamp of an existing file |
| vim | Edit a file in the terminal using Vim |
| exit | Close the SSH session | 

## Advanced SSH Commands
| Some comples SSH utilites that can help with network administration tasks: SSH File System (SSHFS), data compression, and X11 forwarding.

To conduct X11 forwarding over SSH, do these three things:
1. Set up your client (~/ssh/config) to forward X11 by setting these parameters:

     Host *

     ForwardingAgent yes
     
     ForwardX11 yes

2. Set up your server (/etc/ssh/sshd_config) to allow X11 by setting these parameters:

     X11Forwarding yes

     X11DisplayOffest 10

     X11UseLocalhost no

3. Set up X11 authentication on your server by installing xauth.

| Command | Description |
| ------- | ----------- |
| sshfs | Mount a remote server's file system on a local directory. Remember to install this program onto your machine before use. |
| ssh -C hostname | Compress SSH traffic to improve performance on slow connections. Alternatively, insert Compression yes into your SSH configuration files. |
| ssh o- "Compression yes" -v hostname | An alternative method to compress SSH traffic to improve performance on slow connections. |
| ssh -X user@server | Enable X11 forwarding over SSH: forward graphical applications from a remote server as a user to a local machine. |
| ssh -o ForwardX11=yes user@server | Enable X11 forwarding over SSH: forward graphical applications from a remote server as a user to a local machine. |
| ssh -x | Disable X11 forwarding |
| ssh -Y | Enable trusted X11 forwarding. This option is riskrer than ssh -X as it forwards the entire display of the SSH server to the client. |
