<h1>Creating a Cybersecurity Lab using a Rasberry Pi </h1>

<h2>Description</h2>
Project consists of Setting on creating a cybersecurity lab using a Rasberry Pi 4 Model B as server and by installing WebGoat to learn about different pentration attacks 
<br />


<h2>Utilities Used</h2>

- <b> Rasberry Pi Imager </b> 
- <b> Angry IP Scanner</b>
- <b> Command Prompt (CMD) or Powershell</b>
- <b> Secure Shell Protocol (SSH)</b>
- <b> Terminal</b>
- <b> Containers</b>
- <b> WebGoat</b>

<h2>Environments Used </h2>

- <b>Windows 11 Pro</b> (23H2)
- <b>Ubuntu Server </b> (23.10) (64-bit) 

<h2>Program walk-through:</h2>

<h3> Part One: Imaging OS onto to a microSD memory card </h3>
The first part of the project will be getting a image of the operating system onto to memory card that the Rasberry Pi will be using to boot up from. <br/>
<br />
<br /> 
<p align="center">
Download and install the Rasberry Pi Imager by going to https://www.raspberrypi.com/software/ and click on Download for Windows and follow the instructions to install the program: <br/>
<img src="https://i.imgur.com/NgaXOhL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Launch Rasberry Pi Imager and select device depending a which rasberry Pi you have, this project would require a Rasberry Pi 4 Model B or later with 2GB of RAM:  <br/>
<img src="https://i.imgur.com/W6tAFDo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the Operating System, you can choose any of the distrubutions on Linux, in this project I'm using the Ubuntu Server 23.10 (64-bit) whis under other general-purpose OS and Ubuntu, if don't care you can use the Rasberry Pi OS which is derived from Debian much like Ubuntu: <br/>
<img src="https://i.imgur.com/vHQjYjZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/MbjO4LM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<img src="https://i.imgur.com/93VwXYP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/GTrZAGc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>    
<br />
<br />
Insert a microSD card into a card reader and select the storage device it should be label as "SDHC Card - size" other external hard drives will also appear :  <br/>
<img src="https://i.imgur.com/X9xxnL8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The Rasberry Pi Imager should be filled out like this and then click NEXT:  <br/>
<img src="https://i.imgur.com/dwyUoXk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click on EDIT SETTINGS:  <br/>
<img src="https://i.imgur.com/scsE3Hz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Make sure all that set user name and password box are check marked and create a user name and password, make sure you write the password down as it will be neeed for connecting to the Rasberry Pi later  <br/>
Note: If you do not have have a extra monitor make sure all check marks are marked and fill in, you can ignore Configure wireless LAN if you are using a ethernet cable, although this setting should be the same for the computer you are going SSH from. <br/>
<img src="https://i.imgur.com/KfZFBjx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the services tab click on enable SSH and make sure use password authentication is selected and click on save at the bottom of the window:   <br/>
<img src="https://i.imgur.com/wp0499j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click on yes:   <br/>
<img src="https://i.imgur.com/8ViacqV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click on yes:   <br/>
<img src="https://i.imgur.com/N5UKJtx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for the imager to complete the image on the memory card, it might take a minute or so, it will display Wirte Sucessful with the name of the OS that you selected:   <br/>
<img src="https://i.imgur.com/ibwaUuQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Remove the memory card from the reader and insert it into the Rasberry Pi: <br/> 
<br />
<br />

<h3> Part Two: Connecting to the Rasberry Pi via SSH </h3>
The second part of the lab consists on SSH into the rasberry Pi by using a different computer, in this case it would be laptop running Windows, although this project could be done with a laptop using Linux or MacOS. Although prior to connecting to the Rasberry Pi you will need to find the IP address. 
<br />
<br />
<p align="center">
Download and install Angry IP Scanner from https://angryip.org, by clicking on the free download button and select the operating system, install the current version for Windows use the Windows Installer   
<img src="https://i.imgur.com/4FjI5cs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<br />
<br />
Download and install Angry IP Scanner from https://angryip.org, by clicking on the free download button and select the operating system, install the current version for Windows use the Windows Installer   
<img src="https://i.imgur.com/4FjI5cs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<br />
<br />
Launch Windows Powershell or Command Prompt by going to the Search in the Taskbar and Search for Powershell or CMD
<img src="https://i.imgur.com/Zt96kaR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<img src="https://i.imgur.com/gvW0MlI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<br />
<br />  
Type in the command: ipconfig /all
<img src="https://i.imgur.com/fgJm0vt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<br />
<br />
Search for the IP address depending on how your network is setup, if it is a wired connection it would be Ethernet adpator or if wireless the IP address would be found Wireless LAN adaptor LAN adaptor Wi-Fi  
<img src="https://i.imgur.com/fgJm0vt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>    
<img src="https://i.imgur.com/GKEU1tR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>    
<br />
<br /> 
Once you have the computer IP address launch Angry IP scanner, in this example of the network adjust the IP range from 192.168.1.1 to 192.168.1.255
<img src="https://i.imgur.com/NJjTk8S.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br /> 
Click on the double columns  to bring out the fetchers and add MAC Vendor to the Selected fetchers 
<img src="https://i.imgur.com/MbPBHOh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br /> 
Run the scan by clicking on start button and then look in the MAC Vendor for Rasberry Pi Trading, this would be the Rasberry Pi Address 
<img src="https://i.imgur.com/QIf47Ex.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br /> 
Check the connection for the Rasberry Pi by the Ping command,
<img src="https://i.imgur.com/RsJcl2T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br /> 
Type in the command "ssh username@rasberry pi ip address", then type in the password, both were setup when setting up the Rasberry Pi in the frist part, there would be prompt asking to save the keychain type in yes 
<img src="https://i.imgur.com/v7T4NAZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br />   
If sucessful this will chanage the command line to look more like Linux terminal then Windows Powershell 
<img src="https://i.imgur.com/9vQBpTF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br /> 

<h3> Part Two: Installing Portainer and installing the container containing WebGoat the Rasberry Pi </h3>
In this part is installing portainer into the Rasberry Pi and creating a container that would contain WebGoat 
<br />
<br />
<p align="center">
Before installing anything in Linux make sure the resporitory is up to date by running the command sudo apt update, and then type in the password,  the amount depends on how many updates there are, if it is a fresh install there would be more updates, 
<img src="https://i.imgur.com/LysZ7Ee.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br />
Then run the command sudo apt upgrade to install the updates, then say yes if you want to continue, this can be bypass by adding -y to the end of the command like this: sudo apt upgrade -y
<img src="https://i.imgur.com/aHRr4C3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>   
<br />
<br />
This would take a couple minutes to install all updates once you see  the username@ip address or service name this means that the upgrade is completed,type in sudo shutdown -r to restart the rasberry Pi, this will also close the connection so you will need to log back in 
<img src="https://i.imgur.com/hZ86mf2.png.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
<br />
<br />





</p>
