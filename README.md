#  File Upload Vulnerabilities

## Things we need for the Lab:
1. Kali linux
2. Metasploitable linux
3. weevely
4. Terminator
5. BurpSuite

<strong>Metasploitable linux</strong> The intentionally vulnerable target machine for evaluating Metasploit.

 * Make a new target machine in virtual box and try to login using the default username & password 
   * username: msfadmin
   * password :msfadmin 
> Download page:
```sh
https://information.rapid7.com/download-metasploitable-2017.html
```


<strong>Terminator</strong> A Linux Terminal Emulator With Multiple Terminals In One Window
Install Terminator In Linux

```sh
sudo apt-get install terminator
```

## Weevely
<strong>Featured snippet from the web</strong>
<i>Weevely is a stealth PHP web shell that simulate telnet-like connection. It is an essential tool for web application post exploitation, and can be used as stealth backdoor or as a web shell to manage legit web accounts, even free hosted ones.</i>

## Using Terminator try typing the following command In Weevely In Kali linux

* This command is used to create a 'shell.php' file.
```sh

kali@kali:~$ weevely generate 12345 /home/kali/shell.php

```
## Open the browser and try to connect to the Metasploitable linux.
   * After terminal opens type <mark>"ifconfig"</mark>
   * see for the inet address assigned to the machine and copy it.
   * Make sure the virtual machines are connect in a virtual network.
   * if not then goto virtual box preference>network>add virtual network
   ![file](https://github.com/rahulrbk/Docs/blob/master/filevuln/file.PNG)

## Coming back to Kali machine
  * type the ip address of metasploitable linux and press enter.
  * Goto the navigation and use the tool DVWA 
  * Access the dvwa using default username <mark>admin</mark> and password <mark>password</mark>
  * navigate to the upload section
  ![file1](https://github.com/rahulrbk/Docs/blob/master/filevuln/file1.png)
  > Try to upload the file which was previosly created 'shell.php' in medium security setting.
  ![file2](https://github.com/rahulrbk/Docs/blob/master/filevuln/file2.png)
  ## Now open BurpSuite 
     * Capture the packets making the intercept on 
     * Navigate to header section and change the file type to 'shell.php'
  ![file3](https://github.com/rahulrbk/Docs/blob/master/filevuln/file3.png)
    * And click on upload to see the changes
  ![file4](https://github.com/rahulrbk/Docs/blob/master/filevuln/file4.png) 
  > To check whether the file is uploaded or not
  >Goto Kali terminal and type the following command:   
```sh

kali@kali:~$ weevely http://10.0.2.4/dvwa/hackable/uploads/shell.php 12345

```
You will get the following Output:
![](https://github.com/rahulrbk/Docs/blob/master/filevuln/file5.png)