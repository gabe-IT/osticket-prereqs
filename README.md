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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

<ol>
  <li><strong>Azure VM Setup:</strong>
    <ul>
      <li>Create Resource Group and Windows 10 VM.</li>
    </ul>
  </li>
  <li><strong>IIS Installation:</strong>
    <ul>
      <li>Enable IIS with CGI, HTTP Features.</li>
    </ul>
  </li>
  <li><strong>PHP & MySQL Setup:</strong>
    <ul>
      <li>Install PHP Manager, Rewrite Module, PHP 7.3.8, MySQL 5.5.62.</li>
    </ul>
  </li>
  <li><strong>osTicket Installation:</strong>
    <ul>
      <li>Install osTicket, configure IIS, PHP extensions.</li>
    </ul>
  </li>
  <li><strong>Database Configuration:</strong>
    <ul>
      <li>Setup with HeidiSQL.</li>
    </ul>
  </li>
  <li><strong>Post-Installation:</strong>
    <ul>
      <li>Configure roles, departments, teams, SLAs, help topics.</li>
    </ul>
  </li>
  <li><strong>Ticket Lifecycle:</strong>
    <ul>
      <li>Practice ticket creation, triaging, solving.</li>
    </ul>
  </li>
  <li><strong>Final Steps:</strong>
    <ul>
      <li>Cleanup, finalize permissions, note URLs.</li>
    </ul>
  </li>
</ol>



<h2>Installation Steps</h2>

<h3>Install / Enable IIS in Windows WITH CGI and Common HTTP Features</h3>

<p>
  <ul>
    <li>In your VM, go to the <b>Control Panel</b> and head to <b>Programs</b>. </li>
    <li>Under <b>Program and Features</b> click on <b>Turn Windows features on or off</b></li>
    <li>Navigate the list and check the box for <b>Internet Information Services</b></li>
    <li>Expand the list for <b>Internet Information Services</b>, navigate to <b>World Wide Web Services</b> then expand that to find <b>Application Development Features</b>, expand that and check the box for <b>CGI</b>.</li>
    <li>Before closing, make sure the boxes under <b>Common HTTP Features</b> in World Wide Web Services are checked.</li>
      <ul>
        <li><b>Check these boxes in Turn Windows Features on or off</b></li>
        <li><img src="https://github.com/ColtonTrauCC/osticket-prereqs/assets/147654000/e770403c-5def-4c58-a2ad-24b61a859078" height="50%" width="50%" alt="Disk Sanitization Steps"/></li>
      </ul>
    <li>To confirm everything is set accordingly, go to your browser in your VM and type in <b>127.0.0.1</b>, it should load the page to Internet Information Services</li>
      <ul>
        <li><img src="https://github.com/ColtonTrauCC/osticket-prereqs/assets/147654000/b6fdbb5f-73c6-4aaf-ac8c-3e9690303d7b" height="50%" width="50%" alt="Disk Sanitization Steps"/></li>
      </ul>
  </ul>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
