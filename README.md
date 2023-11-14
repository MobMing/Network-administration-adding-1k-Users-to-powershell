# Network-administration-adding-1k-Users-to-powershell
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Add Users to Active Directory with PowerShell</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      max-width: 800px;
      margin: 20px auto;
    }
    h1, h2 {
      color: #007BFF;
    }
    p {
      margin-bottom: 20px;
    }
  </style>
</head>
<body>

<h1>Add Users to Active Directory with PowerShell</h1>

<p>
  Windows PowerShell provides a powerful command-line interface for managing Active Directory. Follow the steps below to add users to Active Directory using PowerShell:
</p>

<h2>Step 1: Open PowerShell</h2>
<p>
  Open PowerShell with administrative privileges. Right-click on the PowerShell icon and select "Run as Administrator."

<p align="center">
Open PowerShell: <br/>
<img src="https://i.imgur.com/UnbkmZR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

</p>

<h2>Step 2: Import Active Directory Module</h2>
<p>
  Import the Active Directory module by running the following command:

<p align="center">
Active Directory Module w/ users: <br/>
<img src="https://i.imgur.com/V9Nt5dO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
</p>

<pre>
<code>
Import-Module ActiveDirectory
</code>
</pre>

<h2>Step 3: Add a New User</h2>

<p align="center">
User addition code: <br/>
<img src="https://i.imgur.com/OKi27C2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
  Use the following command to add a new user to Active Directory:
</p>

<pre>
<code>
New-ADUser -SamAccountName "Username" -UserPrincipalName "Username@domain.com" -Name "Full Name" -GivenName "First" -Surname "Last" -Enabled $true -AccountPassword (ConvertTo-SecureString "Password123" -AsPlainText -Force)
</code>
</pre>

<p>
  Modify the parameters (Username, Full Name, First, Last, Password123) with the actual user details.
</p>

<h2>Step 4: Verify User Addition</h2>
<p>
  Confirm the addition of the user by running a command to retrieve user details:
</p>

<pre>
<code>
Get-ADUser -Filter {SamAccountName -eq "Username"}
</code>
</pre>

<p>
  This command should display the information of the newly added user.
</p>

<p>
  PowerShell makes it efficient to manage Active Directory users, providing automation and flexibility in user administration.
</p>

</body>
</html>
