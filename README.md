# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2), at least 2vCPUs, 8GB RAM

<h2>List of Prerequisites</h2>

- <b>PHP manager for IIS</b> - ensures PHP is correctly configured to run IIS
- <b>Rewrite module </b> - facilitates URL rewriting and redirect users to URLs
- <b>VC_redist.x86</b> (redistributable) - osTicket relies on libraries that are part of Microsoft Visual C++ and ensures the program runs smoothly
- <b>MySQL</b> - for storing data into databases
- <b>HeidiSQL</b> - interface for accessing MySQL 


<h2>Installation Steps</h2>

<p>
Once the Windows 10 VM has been set up in Azure, log into the machine with your credentials. It is best to create a notepad and save a copy of any credentials used along the way for this lab, as there'll be many.
</p>

![image](https://github.com/user-attachments/assets/0c1fea0b-8a1f-4bc5-9ddf-08577ff8522e)


![image](https://github.com/user-attachments/assets/727fedad-dccd-4bab-ba08-49bf9cd6f16a)

<p>

within the VM,open the Microsoft Edge web browser and download <a href= https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD>osTicket-Installation-Files.zip</a>. Extract the files and you should see the following.
</p>


<p>
Now we'll need to enable Internet Information Services.go to Control Panel in the search bar at the bottom, then click Uninstall a Program, then Turn Windows features on or off, then check the box next to Internet Information Services. We'll also need to enable CGI under World Wide Wide Services -> Application Development Features.
</p>

![image](https://github.com/user-attachments/assets/7cfe3069-0aa3-4083-a0f3-d886652394cd)

<br />

<p>
  Once that's done, install the PHP Manager for IIS. Open the file and click OK to accept all the default selections. Do the same for the rewrite module (rewrite_amd64 file).Next, create a directory in C:\ called PHP (C:\PHP). Open File Explorer by clicking the folder icon on the taskbar or searching for it. This directory will be used to extract the zipped PHP folder, allowing osTicket to work with PHP.
</p>
<p>
Now, install the Redistributable package and accept all defaults. Then, install MySQL, selecting Standard Configuration and setting both the username and password to root.After that, open Internet Information Services (IIS) by searching for "IIS" and selecting Run as Administrator. Click on PHP Manager, then select Register New PHP Version and choose C:\PHP\php-cgi.exe.Finally, reload IIS by clicking Stop, then Start on the right-hand side. This will ensure the new PHP version is loaded.
</p>

![image](https://github.com/user-attachments/assets/acf3b1ac-e9aa-4ff0-9494-44dd06b6e392)

<p>
  "Extract the osTicket zipped folder and move the extracted upload folder into C:\inetpub\wwwroot, then rename upload to osTicket (the name must be exact).Reload IIS. In the left-side pane, go to Sites, click the dropdown arrow until you reach osTicket, then click Browse in the right-side pane. You should now see the osTicket setup page.Next, enable some required PHP extensions. Navigate to the osTicket folder in the left-side pane, then click PHP Manager in the middle pane. Select Enable or Disable an Extension, then enable php_imap.dll, php_intl.dll, and php_opcache.dll. Refresh the osTicket webpage, and it should be updated.Continue with the osTicket installation in the browser by clicking Install Now. You should now see a confirmation page indicating that osTicket is successfully installed, along with links to log in:

General user: http://localhost/osTicket
Staff/Admin: http://localhost/osTicket/scp
</p>

![image](https://github.com/user-attachments/assets/5b9fd456-46b5-4e81-b4c8-46a202b3bde0)


<br />

<p>
</p>
<p>
</p>
<br />
