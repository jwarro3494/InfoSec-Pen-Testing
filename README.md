# InfoSec-Pen-Testing
In this project we attempted to penetrate Windows 7 Home Premium (before SP1) using Kali Linux and the Metasploit framework.

Tools Used:

Nmap, OpenVas and the Metasploit framework. We were initially going to include Hot Potato as as tool, however, we realized that it was not necessary as user elevation can be achieved through the Meterpreter in Metasploit and the user account on the target machine is an admin account.

Target Machine Setup and Issues:

 The target machine was setup using a Windows 7 Home Premium iso disk that came with an old Dell Inspiron 1545 laptop from 2009. We decided to use this copy of Windows 7 as it was readily available and intended for demostration purposes only. After setting up the target machince, the Background Intelligent Transfer Service and Windows Update services were disabled which was done to free up resources as the same machine was used for both virtual machines. During vulnerability scanning and penetration testing, the network types for both machines had to be changed. For example, while performing vulnerability detection with OpenVas, the Kali machine had to be set to NAT while the Windows machine had to be set to bridged in order for any data to be collected. Also, the Windows 7 machine could only connect to the network if the network type was set to NAT or Bridged. Another issue from the network type selected was when the target machine would try to connect to the local Kali server. If Kali was set to anything other than Bridged, then the target machine would not be able to connect. This issue did not affect the Windows machine with any network type, however, we did not feel safe using a Bridged connection. 

 Exploit Used:
 
 The exploit used was exploit/windows/browser/ms10_046_shortcut_icon_dllloader inside the msfconsole part of Metasploit due to the overall power of the expoit (See https://sathisharthars.com/2014/05/21/hack-windows-7-with-metasploit-using-kali-linux/ for the complete procedure). While it is a very powerful exploit, it comes with some downsides. THe downsides include the use of Internet Explorer, typing in the ip address of the Kali machine into the browser (which may or may not connect), allowing the exploit to go through (pressing allow or not if protected mode) and having to repeat the process if the target should be turned off. 

Resources Used:

Hack Windows 7 with Metaspoit using Kali Linux: https://sathisharthars.com/2014/05/21/hack-windows-7-with-metasploit-using-kali-linux/
Windows Privilege Escalation: https://foxglovesecurity.com/2016/01/16/hot-potato/
Pratical Approach for Securing Windows Environment: http://aircconline.com/ijnsa/V9N6/9617ijnsa02.pdf (for conclusion)
Penetration Testing for Beginners: Nmap: https://medium.com/@anuraagbaishya/penetration-testing-for-beginners-nmap-b3691682686d  
Installing Windows 7 machine on VirtualBox:  https://o7planning.org/en/11883/installing-windows-7-virtual-machine-on-virtualbox 
Conducting a Penetration Test on an Organization: https://www.sans.org/reading-room/whitepapers/auditing/conducting-penetration-test-organization-67 
Writing a Penetration Testing Report: https://www.sans.org/reading-room/whitepapers/bestprac/writing-penetration-testing-report-33343 


