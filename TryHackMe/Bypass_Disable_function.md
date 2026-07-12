# Bypass Disable Function
## Instruments Description
Chankro: tool to evade disable_functions and open_basedir

Through Chankro, we generate a PHP script that will act as a dropper, creating on the server a .so library and the binary (a meterpreter, for example) or bash script (reverse shell, for example) that we want to execute freely, and that will later call putenv() and mail() to launch the process.

Install tool:

*git clone https://github.com/TarlogicSecurity/Chankro.git*
*cd Chankro*
*python2 chankro.py --help*

*python chankro.py --arch 64 --input c.sh --output tryhackme.php --path /var/www/html*

--arch = Architecture of system victim 32 o 64.
--input = file with your payload to execute
--output = Name of the PHP file you are going to create; this is the file you will need to upload.
--path = It is necessary to specify the absolute path where our uploaded PHP file is located. For example, if our file is located in the uploads folder DOCUMENTROOT + uploads. (Это локация где расположится мой php файл)



Now, when executing the PHP script in the web server, the necessary files will be created to execute our payload.

My command run successfully, and I created a file in the directory with the output of the command

## Conditions to use Chankro:
* Backend written in PHP;
* It is possible to upload a file, which is then processed by the PHP interpreter;
* Dangerous PHP functions are disabled: system, exec, shell_exec, passthru, popen, proc_open;
* The system runs on Linux;
* PHP uses a dynamic loader (which is the case on most systems);
* There are directories with write access (so that Chankro can place a .so file);
* You have external access to the PHP file;

## WriteUP
I ran dirb on the server:
*gobuster dir -u http://10.113.175.54/ -w /usr/share/wordlists/dirb/common.txt*
![Screenshot](.github/images/6.png)

I received the **phpinfo.php** file and the **uploads** directory. I looked at phpinfo.php, specifically the site's root directory:
![Screenshot](.github/images/8.png)

I created a Bash script with a reverse shell that will run on a remote server:
![Screenshot](.github/images/4.png)

Launched Chankro:
![Screenshot](.github/images/7.png)

When a file is uploaded to the server, it is scanned for malicious content. In this case, I was able to bypass the security measure by adding bytes from a GIF file to the header of the PHP file:
![Screenshot](.github/images/5.png)
I uploaded the file to the server and saw it in the uploads directory:  
![Screenshot](.github/images/1.png)  
I started the listener on port 4444:  
![Screenshot](.github/images/2.png)  
I opened a PHP file on a remote server and got a reverse shell:  
![Screenshot](.github/images/3.png)
