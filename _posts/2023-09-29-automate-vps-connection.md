---
title: How to Automate VPS Login with Bash Script 
author:
  name: mujtabasec
  link: https://twitter.com/mujtabasec
# date: 9/26/2024
categories: [ automation, bugbounty ]
tags: [ automation, bugbounty, bash, linux ]
---

## How to Automate VPS Login with Bash Script 
Connecting to your Virtual Private Server (VPS) regularly can become a tedious process if you need to enter the IP address, username, and password manually each time. Luckily, with some automation, you can make this process smoother. In this tutorial, we’ll explore how to use a Bash script and the sshpass utility to automate the SSH login process, even if you don’t want to set up SSH key-based authentication.
By the end of this guide, you'll be able to connect to your VPS with a single command — no need to manually type the SSH credentials each time!

## Why Automate VPS Login?
Whether you're managing multiple servers or frequently accessing a single VPS, automating SSH logins saves time and improves workflow efficiency. While SSH keys are the most secure method of logging into remote systems, using passwords with sshpass can be an easier short-term solution.

## Steps to Automate VPS Login Using sshpass

### Step 1: Install sshpass 
sshpass is a simple utility that allows non-interactive SSH login by passing the password directly in the command line. 

```bash
sudo apt-get install sshpass
```

### Step 2: Create a Bash Script
After installing sshpass, you can create a simple bash script that automatically logs into your VPS. The script will use sshpass to pass your SSH credentials (username, password, and IP address) without requiring interaction.

Open a terminal and create a new file 
```bash
nano connect_vps.sh
```
  
Add the following code to the file. Make sure to replace username, password, and ip_address with the actual values for your VPS:
  
 ```bash
#!/bin/bash
echo "Connecting to a VPS"

sshpass -p 'your_password' ssh username@ip_address

echo " "
  ```

This command uses sshpass to pass your password when executing the ssh command, automating the login process.

### Step 3: Make the Script Executable
To ensure that the script can be executed, you’ll need to change its permissions. Run the following command:
  
```bash
chmod +x vps.sh
```
  
### Step 4: Connect to Your VPS
First, move your script to /usr/local/bin so you can run it from anywhere:
  
```bash
sudo mv vps.sh /usr/bin/vps
```

```bash
vps
```

I hope you find this write-up helpful. Thank you for reading!

Follow me On [Twitter](https://twitter.com/mujtabasec) 