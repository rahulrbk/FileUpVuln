# How To Discover & Exploit Basic Code Execution Vulnerabilities To Hack Websites
## Things we need for the Lab:
1. Kali linux
2. Metasploitable linux
3. Netcat
4. Terminator
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
## Open the browser and try to connect to the Metasploitable linux.
   * After terminal opens type <mark>"ifconfig"</mark>
   * see for the inet address assigned to the machine and copy it.
   * Make sure the virtual machines are connect in a virtual network.
   * if not then goto virtual box preference>network>add virtual network
   ![file](https://github.com/rahulrbk/Docs/blob/master/filevuln/file.PNG)
## Coming back to Kali machine
  * type the ip address of metasploitable linux and press enter.
  * Goto the navigation and use the tool DVWA.
  * Access the dvwa using default username <mark>admin</mark> and password <mark>password</mark>.
  * navigate to the command execution section.  
  * Try to ping hackers machine ip address.

![code](https://github.com/rahulrbk/Docs/blob/master/filevuln/code.png)

![code1](https://github.com/rahulrbk/Docs/blob/master/filevuln/code1.png)

## Using Netcat tool in Terminator

> Now you need to listen for port 8080 using the following command:

```sh
nc -vv -l -p 8080 

```
![code2](https://github.com/rahulrbk/Docs/blob/master/filevuln/code2.png)

> Try to write the following command to the dvwa.

![code3](https://github.com/rahulrbk/Docs/blob/master/filevuln/code3.png) 

> After executing the command the netcat listens the request.

![code3](https://github.com/rahulrbk/Docs/blob/master/filevuln/code4.png)

<mark>Finally you can run the shell commands inside the terminal of target machine</mark>

