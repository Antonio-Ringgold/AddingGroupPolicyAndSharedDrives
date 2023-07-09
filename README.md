# <h1>Adding Group Policies and Shared Drives To Our Home Lab</h1>



<h2>Description</h2>
This is a continued project from the Active Director Home Lab. Here we will be setting up Security Group Policies and creating a shared drive for our home lab we created in the other project. This lab was created using Azure Virtual Machines but it is setup the same as the previous lab that was using Virtual Box.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Command Prompt</b> 
- <b>Server Manager</b>
- <b>Group Policy Management</b>
- <b>File and Storage Services</b>

<h2>Environments Used </h2>

- <b>Windows Server OS 2019</b>
- <b>Windows 10</b>
- <b>Microsoft Azure</b>

<h2>Lab walk-through:</h2>

Sign into our Domain Controller and open Group Policy Management. Right Click "Default Domain Controllers Policy and click "Edit":  <br/>
<img src="https://i.imgur.com/OrdWOvu.png" height="70%" width="70%" alt="Home Lab"/>
<br />
<br />
Here you will navigate to Policies>Security Settings>Account Policies>Account Lockout Policy. You normally will set them to company standards but for our home lab I changed the Account policies as follows: <br/>
<img src="https://i.imgur.com/mNojiXA.png" height="70%" width="70%" alt="Home Lab"/>
<img src="https://i.imgur.com/K7oEvkY.png" height="70%" width="70%" alt="Home Lab"/>
<br />
<br />
After setting and saving your policies you can update and verify these policies by opening command prompt then enter "gpupdate /force" which will force the group policy to update. Then enter "gpresult /r to view the summary of the policies set in place. :  <br/>
<img src="https://i.imgur.com/IzprJv1.png" height="60%" width="60%" alt="Home Lab"/>
<br />
<br />
Now we will setup our shared drive. Navigate to Server Manager>File And Storage Services>Shares. Here you will right click and choose "New Share.." You can go to your C: drive to verify the folder is there:  <br/>
<img src="https://i.imgur.com/nOqE7YV.png" height="60%" width="60%" alt="Home Lab"/>
<br />
<br />
Once you see your new shared folder, open it and create a new folder inside called "Home". This will be our home drive for our environment:  <br/>
<img src="https://i.imgur.com/lqOslZe.png" height="80%" width="80%" alt="Home Lab"/>
<br />
<br />
Right Click on the Home folder and click "Properties" then click the "Sharing" tab then choose "Advanced Sharing". Check the box that says "Share this folder":  <br/>
<img src="https://i.imgur.com/zU2AG9N.png" height="60%" width="60%" alt="Home Lab"/>
<br />
<br />
Open Active Directory (which was setup in the previous lab) and open the properties to your normal account. Go to profile then choose the "Connect" radio button then select the letter H (or whatever letter you want) from the dropdown then paste the Home drive network path in the "To" space: <br/>
 <img src="https://i.imgur.com/jyZ1mjw.png" height="60%" width="60%" alt="Home Lab"/>
<br />
<br />
To verify this folder is now accessible on the domain sign into the Windows10 VM we created in the previous lab as your normal account and open file explorer. You should see the Home drive there: <br/>
<img src="https://i.imgur.com/gb2qv3Y.png" height="60%" width="60%" alt="Home Lab"/>
<br />
<br />
You can even add a test file or folder to the Home drive then sign back into the DC to verify the test file or folder is there and the Home Drive is functioning as expected: <br/>
<img src="https://i.imgur.com/5rNOjz6.png" height="65%" width="70%" alt="Home Lab"/>
<img src="https://i.imgur.com/5UNTjI9.png" height="65%" width="70%" alt="Home Lab"/>
<br />
<br />
Group Policy and A Home Drive Have Been Setup Successfully!
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
