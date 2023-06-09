<p align="center">
<img src="https://imgur.com/Owq9lOV.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
<p align="center">~This tutorial covers the prerequisites and installation for osTicket - an open-source help desk ticketing system.~<br /></p>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install / Enable IIS (Internet Information Services)
- Install PHP Manager for IIS
- Install Rewrite Module
- Download and Unzip PHP
- Install C++ Redistributable 
- Install MySQL
- Configure Permissions
<h2>Links:
osTicket Installation Files
</h2>https://drive.google.com/drive/folders/1HhS1aa-H8trQa0IPt1hn0Q7-X_vTCk5n?usp=share_link<h2>
Virtual Machine Creation</h2>

<p>
Stage 1: Create a Resource Group in Azure
<img src="https://imgur.com/nNY8hrj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<li>Give your Resource Group a name</li>
<li>Choose a Region</li> 
<li> Click the "Review + Create" tab</li>  
NOTE: Use the same Region when creating your Virtual machines
<img src="https://imgur.com/TuybLQq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click the "Create" tab (bottom left corner)</li>  
<img src="https://imgur.com/OLxYtk5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
Stage 2: Create a Virtual Machine in Azure
<ul>
<li>Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPU</li>
NOTE: When creating the VM, allow it to create a new Virtual Network (Vnet)

</p>
<img src="https://imgur.com/F5j2Ukt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Assign the resource group you created</li>
<li>Name your virtual machine</li>
<li>Select your Region</li>
<li>Generate a Windows 10 computer under Image</li>
<img src="https://imgur.com/ay9MfRj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Choose the size of your virtual machine (2 vcpus)</li>
<li>Choose a user name and password</li>
<img src="https://imgur.com/3Cjhjwb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Check the box to confirm Licensing</li>
<li>Click the tab "Next : Disks >" then "Next : Networking >"</li>
</p>
<img src="https://imgur.com/JEvqBAi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
<img src="https://imgur.com/9VdXzrS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<li>Here you can take note of your new Virtual Network, private IP followed by your public IP.</li>
<li>Click the "Review + Create" tab  and once validation is complete click "Create".</li>
</p>
<br />

<p>
<img src="https://imgur.com/5tbmena.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Installation</h2> 
<li>In Azure under Virtual Machines find and click your virtual machine. Locate its Public IP address. Click to copy it.</li>
<li>In Windows click start and type: Remote Desktop Connection. (Mac users install Microsoft Remote Desktop)</li>
<img src="https://imgur.com/PneTRfI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<li>Paste the IP address and click the Connect tab</li>
<li>Enter your user name and password you made when you created your virtual machine</li>
<img src="https://imgur.com/kXcqJgR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<li>Click "Yes"</li>
<img src="https://imgur.com/mBmdCxB.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<br />
<li>Right click the start menu and click "Run"</li>
<li>Type "control" for Control Panel and press enter</li>
<img src="https://imgur.com/lM0F2of.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<li>CLick Programs and select "Turn Windows Features On or Off"</li>
<img src="https://imgur.com/JEaj2Sw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/IEIkrMR.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<li>Turn on "Internet Information Services (IIS) and then click the box to the left to expand</li>
<li>Expand "World Wide Web Services"</li>
<li>Expand "Application Development Features"</li>
<li>Check the box for "CGI" and press OK and once changes have been applied click Close</li>
<img src="https://imgur.com/vEaf4nV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<li>To confirm your web server is working, open a browser and type 127.0.0.1</li>
<li>This should load the default ISS website:</li>
<img src="https://imgur.com/850Le0m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<h2>For this next stage refer back to Links: osTicket Installation Files:</h2>
https://drive.google.com/drive/folders/1HhS1aa-H8trQa0IPt1hn0Q7-X_vTCk5n?usp=share_link</h2> 

<p>
<li> Install PHP Manager for IIS</li> 
<img src="https://imgur.com/wksFCHu.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/kNCt1xp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
  
<li>Open the Downloads folder and double click and install it (Next; I Agree; Next; Close).
<p>
<p>  
<li>Download and install the URL Rewrite Module</li>
<img src="https://imgur.com/eU1TVw8.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
  
<br />
<p>
<p>
<li>Create the directory C:\PHP</li>
<li>To do this go to "This PC" and under Devices and drivers choose Windows (C:)</li>
<img src="https://imgur.com/mLo3568.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>  
<li>Right click and create and name a Folder "PHP"</li>  

<li> Next refer back to osTicket Installation Files and download 
<a href="https://drive.google.com/file/d/1LmwEE6wNKhfijJ1pyQj_cPVh8rYFzIpa/view?usp=share_link" target="_blank">PHP Manager for IIS</a>
<li>In the downloads folder right click and Extract All...</li>
<img src="https://imgur.com/z9XMFEI.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<li>Extract to the PHP folder you created: Browse; This PC; Windows (C:); then click on the PHP folder
<img src="https://imgur.com/1Uu58GZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click "Extract"  </li>
  <p>
    
<li> Download and Install VC_redist.x86.exe (C++ Redistributable)</li>
<img src="https://imgur.com/EgQzNPu.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<li>Go back to Downloads and click on it to install: I agree; Install; Close</li>    
<img src="https://imgur.com/W8OjLpp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

<p>
<li>Download and install MySQL Server</li>   
<img src="https://imgur.com/atZnobW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Next</li>  
<img src="https://imgur.com/Zg4AkCm.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Tick the box for "I accept..." and click "Next"</li>  
<img src="https://imgur.com/Zg4AkCm.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Choose Typical and Install</li>  
<img src="https://imgur.com/AUyOpZB.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>The box for "Launch the MySQL Instance Configuration Wizard" should be checked. Click Finish</li>
<img src="https://imgur.com/Eak8nJh.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Click Next then choose "Standard Configuration" and click Next</li> 
<img src="https://imgur.com/byg5A7Q.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Check "Install As Windows Service" and click Next</li>

<p>
<li>Note that in MySQL your User Name is "root"</li>
<li>Assign a password and click Next then click Execute</li>
<img src="https://imgur.com/lElrevv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<li>Execute and allow it to finish configuring MySQL Server</li>  
<img src="https://imgur.com/lwunntS.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<Li>and click Finish</li>
<img src="https://imgur.com/5gx7izp.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>  
  
<p>
<h2>Configuration in IIS</h2>   

<li> Open IIS as an Admin: click on Start and type "IIS"</li>  
NOTE: To open as Admin, right click it and choose Run as Administrator  
<img src="https://imgur.com/ddvXcf4.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  
<li>Click on PHP Manager</li>
<img src="https://imgur.com/zzPConW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click on "Register new PHP version" (bottom left)</li>
<img src="https://imgur.com/Q5fPE8i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click the ellipsis (three dots) to browse to your recently created PHP file</li>
<img src="https://imgur.com/smtl4uA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click on the folder named PHP</li>  
<img src="https://imgur.com/3bvp41T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Find php-cgi and click on it and click OK</li>  
<img src="https://imgur.com/f93mNhV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/B1GGwfU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>A good rule of thumb: Anytime you make changes to IIS restart it</li> 
<li>Click on the server and then click "Restart". Alternatively you can click "Stop" then "Start"</li>  
<img src=https://imgur.com/yw5brMg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  
<h2>Install osTicket</h2>
<li>Download osTicket from the Installation Files Folder</li>
https://drive.google.com/drive/folders/1HhS1aa-H8trQa0IPt1hn0Q7-X_vTCk5n?usp=share_link
<li>Extract and copy “upload” folder to c:\inetpub\wwwroot</li>
To do this go to the Downloads folder and click on the zipped osTicket folder.
Click Start and type "This PC" Click it and find Windows (C:) 
Then go to "inetpub" then "wwwroot"
<li>Drag the upload folder into the wwwroot folder</li> 
<img src=https://imgur.com/16P0hUW.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<li>Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</li>
NOTE: Make sure it's named exactly "osTicket" with no spaces.
 <p>
If it's not named correctly or has a space, you will get a "404 page not found"
 <p>
   
<img src="https://imgur.com/pxuwsDq.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>  

 <p>
<li>Reload IIS</li>  
<li>As before click on the server and then click "Restart". Alternatively you can click "Stop" then "Start"</li>  
<img src=https://imgur.com/yw5brMg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>                                                                                              
<li>While in IIS now is a good time to check that your installation has been performed correctly</li>
<li>Expand the "Sites" folder then expand the "Default Web Site" then click on the "osTicket folder"</li>
<li>On the right click on Browse *:80 (http)</li>
<img src=https://imgur.com/Y1xOpyd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src=https://imgur.com/LlJ0nGi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Note that some extensions are not enabled. The next step will modify some recommended features.</li>

<p>
<li>Go back to IIS and click osTicket then double click PHP Manager</li> 
<img src=https://imgur.com/BiOXJcY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>At the bottom select "Enable or disable an extension"</li>
<img src=https://imgur.com/WDvlHi0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <li>Enable the following by right clicking on them and choosing "Enable"</li>

<p>
                                                                                                             
Enable: php_imap.dll
                                                                                                             
Enable: php_intl.dll
                                                                                                             
Enable: php_opcache.dll
                                                                                                             
<li>Refresh the osTicket site in your browser, observe the changes</li>
<img src=https://imgur.com/2p6hbXy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Rename: ost-config.php</h2> 
<li>Browse to "This PC" then "Windows (C:)" then "inetpub" then "wwwroot"</li>
<img src=https://imgur.com/M1uKTXz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click osTicket and click the folder named "include"</li>
<li>Inside the "include" folder find "ost-sampleconfig.php" and rename it "ost-config.php" (in other words remove "sample" from the name</li>  
<img src=https://imgur.com/SRrhUNM.png" height="20%" width="20%" alt="Disk Sanitization Steps"/>
<h2>Assign Permissions: ost-config.php</h2>
<li>Right click ost-config.php and go to "Properties"</li>
<li>Go to "Security" and the click on Advanced</li>
<img src=https://imgur.com/IItPWyy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click "Disable inheritance" and "Remove all inherited permissions from this object" </li>
<img src=https://imgur.com/Jj5mpOv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Next click "Add" and "Select a principal" </li>
<img src=https://imgur.com/DQjqF9G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>In the box named "Enter the object name to select" type everyone and click on Check Names and then OK</li>
<img src=https://imgur.com/QgV8DXy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>For now tick the box to give everyone "Full control" and click "OK"</li>
<img src=https://imgur.com/lKoSG4b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click "Apply" and then "OK"</li>                                                                                              
<img src=https://imgur.com/wYjSOem.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Click "OK"</li>
<img src=https://imgur.com/PEE1sWz.png" height="40%" width="40%" alt="Disk Sanitization Steps"/> 
<h2>Continue Setting up osTicket in the browser</h2>
<li>Go back to the osTicket browser and click "continue"</li>
<img src=https://imgur.com/h9J39ou.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>Fill out the needed information (below are random illustrations)</li>
<img src=https://imgur.com/rUUJL3k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Install HeidiSQL</h2>
<li>From the Installation Files, download and install <a href="https://docs.google.com/document/d/1oUNbBfMjZzbKvxaj8HEkYr9LC97T4IZT/edit?usp=share_link&ouid=111802367886707317994&rtpof=true&sd=true">HeidiSQL</a></li>

<p>
<img src=https://imgur.com/sIEcCHh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 


<p>
<li>In the Downloads folder double click HeidiSQL</li>
<il>Tick the radio button for "I accept" then click "Next" until you reach "Install" </li> 
<img src=https://imgur.com/JDoBNIM.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> 
<li>Once installation is complete click "Finish"</li>
<img src=https://imgur.com/u3Kwtxr.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>   
<h2>Open Heidi SQL</h2>
<li>Click "New"</li>
<li>Your User name is "root". Enter the password you created when you set up MySQL</li>
<li>Click "Open"</li>
<img src=https://imgur.com/WaUNHBs.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<h2>Create a database in HeidiSQL called “osTicket”</h2>
<li>Right click "Unnamed" and under "Create new" click "Database"</li>                                                                                            
<img src=https://imgur.com/4H1e42w.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<li>For the Name enter "osTicket" and click OK</li>
<img src=https://imgur.com/QCHc9kG.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>

<p>
                                                                                              
<li>Back in your browser for osTiket enter the name for MySQL Database as "osTicket"</li>
<li>MySQL User name is root</li>                                                                                    
<li>Enter the password you created when you set up MySQL and click "Install Now"</li>   
<img src=https://imgur.com/YK6DH79.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> 
<img src=https://imgur.com/nC83ao8.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<h2>Clean up!</h2>
<li>Delete: C:\inetpub\wwwroot\osTicket\setup</li>
<li>Go to This PC and Windows (C:) > inetpub > wwwroot > osTicket</li> 
<li>Right click on the "setup" folder and click Delete</li>
<img src=https://imgur.com/gRr2cCJ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> 
<li>Next double click the "include" folder (bringing you to Windows (C:) > inetpub > wwwroot > osTicket > include)</li>
<li>Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li>
<li>Scroll until you find "ost-config.php" and right click on it and choose "Properties"
<li>Select "Security" and then Advanced</li>
<img src=https://imgur.com/pNx58vm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<li>Select "Everyone" and click "Edit"</li> 
<img src=https://imgur.com/BP7X5h4.png" height="50%" width="50%" alt="Disk Sanitization Steps"/> 
<li>Uncheck Full control, Modify and Write and click "OK"</li>
<img src=https://imgur.com/Ja7aKCd.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<li>Click Apply and OK. You have now set the permissions to Read only again.</li>
<h2>Useful Links</h2>                                                                                              
<li>Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</li>
<li>End Users osTicket URL: <a href="http://localhost/osTicket/">http://localhost/osTicket/ </li>                                                  
<p>
<b>
<h1><p align="center"> For further questions and help go to the <a href="https://forum.osticket.com/">osTicket Forum</a></h1>
<img src="https://imgur.com/HERPGUd.png" alt="osTicket logo"/></h2>
