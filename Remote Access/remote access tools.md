### Configuring Remote Access / Remote Access Tools on Ubuntu Desktop.

Remote access tools are software programs that allows individuals to access and take control of other peoples computers remotely over the internet. When the user accesses the remote computer, he/she is able to perform tasks on the target system as if the computer is physically present.

Once the user gains access to the remote computer system, he can transfer files between the computers, execute commands on the remote system, monitor the remote system activity as well as control the remote desktop. Majority of  Remote Access Tools are multi-platform working across Windows, macOS, Linux as well Android devices.

Ethical and unethical hackers deploy these tools to achieve their roles in cyberattacks, espionage and for Ransomware support to lock or manipulate the remote systems.

#### How Remote Access Tools work.

Remote Access Tools work on Client-Server model. The remote system runs the remote access tool software and acts as the server. The controlling system is the client and connects to the server using an IP address, port number or a fully qualified domain name. The connection occurs over an encrypted channel to avoid detection and for hardening the security.

### 1. Configuring SSH (Secure Shell) for Remote Access

SSH is a network protocol that provides a secure tunnel to access a remote computer through an unsecured network. Communication between the client and server occurs using encryption and authentication to protect data and ensure secure remote login and data transfer. The client application connects to an SSH server to establish a secure connection.

SSH ensures secure remote login, secure file transfer and port forwarding. OpenSSH suite comprises of open-source tools that implements Secure Shell protocol to facilitate secure, encrypted remote login and file transfer.

The OpenSSH suite consists of the following tools.

- Tools for remote operations e.g ssh, scp and sftp

- Tools for key management e.g ssh-add, ssh-keysign, ssh-keyscan and ssh_keygen

- Tools for service side e.g sshd, sftp-server and ssh-agent

To configure SSH for remote access on Ubuntu Desktop, carry the steps below.

#### Step 1 : Install OpenSSH Server

Install OpenSSH server on Ubuntu desktop by the command below.

```bash
sudo apt install openssh-server
```

#### Step 2 : Enable the SSH service

Enable and start the SSH service by the commands below.

```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```

Confirm the status of the SSH service.

```bash
systemctl status ssh
```

#### Step 3 : Connect to a remote system

To connect to a remote deskop, get its IP address, and the username of the remote system, then use ssh command as below.

```bash
ssh <username>@<remote_desktop_ip_address>
```

replace <**username**> and <**remote_desktop_ip_address**> with the actual remote system username and IP address.

#### Step 4 : Configure Firewall (Optional)

If your remote system sits behind an edge firewall, the default port SSH port 22 might be blocked for security enhancements. Allow SSH traffic through port 22 by the command below.

```bash
sudo ufw allow ssh
```

#### Step 5 : Securing authentication with keys

To harden security, its expidient to use SSH keys instead of passwords.

To generate a key pair on your remote desktop, run the command below.

```bash
ssh-keygen
```

The command generates both public/private key pair. You can share the public key with others but ensure to keep the private key guarded. Ensure too that you harden the key pais with a passphrase

To use the keys, copy the public key generated above to your remote desktop using the command below.

```bash
ssh-copy-id ssh <username>@<remote_desktop_ip_address>
```

Finally connect to the remote desktop via ssh command without supplying the password.

```bash
ssh <username>@<remote_desktop_ip_address>
```

### 2. Configuring VNC (Virtual Network Computing) for Remote Desktop Access in Ubuntu Desktop.

VNC is a cross-platform screen sharing system that aids in remote control of a computer to allow the user to view and interact with the remote desktop as if he was sitting infront of the remote desktop.

VNC operates on client/server model where VNC server is installed on the remote computer and a VNC viewer installed on the device used for remote access.

I will install [TightVNC](https://www.tightvnc.com/) server for demonstration purposes. TightVNC is a free and Open Source remote desktop software with an easy to use interface that lets the user to access and control a computer remotely over the network.

Follow the steps below.

#### Step 1 : Install and setup VNC Server

As earlier stated, i will install TightVNC Server for demonstration purposes. TightVNC is available for installation in the default APT package index. This can be confirmed by the command below:

```bash
apt search tightvnc
```

To install the server, run the command below on the terminal.

```bash
sudo apt -y install tightvncserver
```

#### Step 2 : Set VNC Password

To use TightVNC Server, you must set a password to access your desktops. To set VNC Password, run the command below.

```bash
vncserver
```

The command will prompt you to set a password and verify it. The user is then prompted to confirm if he would like to *enter a view-only password* . View-only password allows users to connect and observe the desktop remotely without being able to control the mouse and the keyboard. Type **n** and **Enter** to proceed. 

#### Step 3 : Configure VNC Server

Upon installation of the VNC Server, the default VNC Server startup configuration script is located in the home directory under *~/.vnc/xstartup* . 

This writing assumes that you already have a Desktop Environment running but if not, you can install it by running the command below.

```bash
sudo apt install ubuntu-desktop
## For lighter alternative
sudo apt install xfce4 xfce4-goodies
```

Stop the VNC instance to allow you to modify the VNC Server configurations by the running the following command.

```bash
vncserver -kill :1
```

The command will kill the Xtightvnc processes if running.

Using your text editor, open the VNC Server configuration file but make sure you backup the original configuration file.

```bash
mv ~/.vnc/xstartup ~/.vnc/xstartup.bak
sudo vim ~/.vnc/xstartup
```

Modify the file with the below configs.

```bash
#!/bin/bash
xrdb $HOME/.Xresources
startxfce4 &
```

To make sure VNC Server uses the new configurations, make the created file executable by the command below.

```bash
sudo chmod +x ~/.vnc/xstartup
```

Restart the VNC Server so that the changes made can take effect.

```bash
vncserver -localhost
```

Appending the *-localhost* on the command binds the VNC Server to your localhost. This causes the VNC Server to allow connections that come from the localhost.

### 3. Configure Remote Access Using Remote Desktop Protocol (RDP) in Ubuntu Desktop.

RDP is a secure network communication protocol by Microsoft that enables users to remotely access and control other computers, servers or vitual machines. Communication between remotely connected computers happens over an encrypted communication tunnel.

The RDP uses a Client-Server model to facilitate secure communication between the communicating devices. The user installs RDP Server on the computer to be managed remotely. The connections are initiated from the RDP Client.
