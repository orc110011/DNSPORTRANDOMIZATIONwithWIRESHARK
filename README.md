# DNSPORTRANDOMIZATIONwithWIRESHARK

<h2>Description</h2>
To run vuln scans on Windows 10 VM.

<h2>Languages and Utilities Used</h2>
- <b>Tenable's NESSUS</b>
- <b>VMWARE Workstation Pro </b>

<h2>Environments Used </h2>

- <b> WINDOWS Server 2022 </b> 
  
<h2>Program walk-through:</h2>
-Testing your DNS Server
<p align="center">
Login to Nessus.
Your server should show processes listening on both TCP and UDP ports 53, as shown below.
<p align="center">
<img src="https://i.imgur.com/E3DeM4K.png height="65%" width="65%" />
<br />
<br /> 

In a Command Prompt, we need to execute the following command: 
nslookup yahoo.com 8.8.8.8
This looks up the A record for yahoo.com using Google's server.
You should see non-authoritative answers from the google-public-dns server, as shown below.
<p align="center">
<img src="https://i.imgur.com/VzPYS1V.png height="65%" width="65%" />
<br />
<br /> 
<p align="center">
In a Command Prompt window, we need to execute this command:
nslookup @ modernstoicism.com 127.0.0.1
This looks up the A record for modernstoicism using your my DNS server.
We should see non-authoritative answers from the google-public-dns server, as shown below.
<p align="center">
<img src="https://i.imgur.com/93SQlyi.png height="65%" width="65%" />
<br />
<br />
-Clearing the DNS Server Cache <br/>
<p align="center">
<img src="https://i.imgur.com/yMtCKSl.png height="65%" width="65%" />
<br />
<br />
-Performing Three Recursive Queries <br/>
<p align="center">
In a Command Prompt, execute the following commands:
nslookup attack.samsclass.info 127.0.0.1, nslookup fog.modernstoicsm.com 127.0.0.1 nslookup ftp.modernstoicism.com 127.0.0.1 
<p align="center">
<img src="https://i.imgur.com/p7t7Ot1.png height="65%" width="65%" />
<br />
<br />
WIRESHARK
-Observing Source Ports
<p align="center">
In Wireshark, click Capture, Stop.
Look in the Info column, on the right side, and click a "Standard query..." packet.
In the middle pane, expand the "User Datagram Protocol..." line.
Right-click "Source port..." and click "Apply as Column", as shown below.
<img src="https://i.imgur.com/PGNpG8z.png height="65%" width="65%" />

<p align="center">
As we can see; the Source Port is RANDOMIZED, unlock WINSERVER 2008, which is a serious server vulnerability, making it far easier to poison the cache on the server.





  







