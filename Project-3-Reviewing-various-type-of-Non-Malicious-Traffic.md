# Reviewing various type of Non Malicious Traffic

## Introduction
This project covers what non-malicious and normal traffic looks like. we shall also review various types of non-malicious activity that security professionals may run across when checking packet capture (pcaps) of network traffic. This includes operating system traffic, traffic generated by web browsers, application updates, IRC traffic, FTP traffic, email traffic.

## Lab Set-up and Tools

1. **Tool**: Wireshark v4.2.6
2. **Sample PCAP File**: Download a sample PCAP file containing malware traffic for analysis.

## Exercises

### Exercise 1: Investigate possible windows malware alert to confirm if its actually a Windows malware alert.

#### Steps

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed. lets use basic filter.
4. when we verify the domains and URLs that indicate this host is running fedora linux.
5. The alert shows a port 55358, we will find this port in column display and follow TCP stream.

#### Expected Output

6. The user-agent line in the HTTP Headers also shows that the host is using Fedora, Linux.

![image](https://github.com/user-attachments/assets/391a8abf-ee7a-4981-a2d7-974be490a199)


### Exercise 2: Verify the Traffic caused by Web Browsers

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.
4. **updates for Google chrome and chromium based Microsoft Edge** generate traffic to domains ending in **.gvt1.com**

#### Expected Output

5. please find the screen shot below for theTraffic generated by Google chrome 
    ![image](https://github.com/user-attachments/assets/7143c9f0-81dc-49ea-a83d-737ed86ecfaa)
6. please find the screen shot below for theTraffic generated by chromium based Microsoft Edge
   ![image](https://github.com/user-attachments/assets/a688ccd2-7b2f-429e-81c4-7158dd99b86e)

### Exercise 3: Recognize DNS over HTTPS Traffic in a PCAP file.

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.

**NOTE** - 
* The big 3 windows web browsers (Chrome, Edge and Firefox) now have DNS over HTTPS enabled by default.
* DNS over HTTPS (DoH) is an internet security protocol that encrypts domain name system communication by routing DNS requests through an encrypted session of HTTPS.

#### Expected Output

4. please find the screen shot below for the DNS over HTTPS Traffic as implemented in Firefox.

![image](https://github.com/user-attachments/assets/08698f79-9f40-4850-8033-bfbc46added7)

### Exercise 4: Verify update traffic for Adobe Reader as part of Application updates.

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.
4. Adobe readers updates are provided through domain ardownload.adobe.com

#### Expected Output

5. please find the screen shot below for the update traffic for Adobe Reader application.

![image](https://github.com/user-attachments/assets/db10bfdd-e24f-45c8-9df3-167bac5fb5fd)

### Exercise 5: Verify the Internet Relay Chat (IRC) Traffic generated using IceChat 9.50 on Windows 10 host.

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.
4. By basic+dns filtering we can see the IRC traffic.
5. Also by doing quick filter check irc, we can see if there is IRC chat un encrypted in the PCAP.

#### Expected Output

![image](https://github.com/user-attachments/assets/e6710e3f-da34-44e8-93df-9aadce27b265)

![image](https://github.com/user-attachments/assets/72f473a7-376b-4f1f-bbf5-3f3fa9cbb87c)

![image](https://github.com/user-attachments/assets/2fc3ac9f-b43e-47c9-96b8-114b5c6473be)

### Exercise 6: Verify the File Transfer Protocol (FTP) Traffic generated using FileZilla on Windows 10 host.

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.
4. using basic+dns filter, traffic to 193.104.215.67 over TCP port 21 is the FTP control channel.
5. Traffic to 193.104.215.67 over TCP port 21637 and 50926 is the FTP data channel
6. To see the flow of events use ftp.request.command or ftp-data.

#### Expected Output

TCP port 21 - User retreiveing a file license.txt
![image](https://github.com/user-attachments/assets/c4b682ea-c69a-4772-a289-a8144f12f1c9)

TCP port 50926 - shows the content of the file license.txt
![image](https://github.com/user-attachments/assets/d6ef73fd-baf0-4aac-b031-5acec443bb3d)

List of FTP commands and data that got generated by that command
![image](https://github.com/user-attachments/assets/a23075ca-66a7-4fd3-b0f6-41bba9c06b59)

### Exercise 7: Verify the Email Traffic generated for Gmail used through Thunderbird email client on Windows 10 host. 

1. Open Wireshark.
2. Go to "File" > "Open" and select the sample PCAP file you downloaded.
3. The file will load, and the captured traffic will be displayed.
4. lets use our basic+dns filter. as you can see dns queries for imap.gmail.com and smtp.gmail.com, there is also encrypted    traffic to these domains over tcp port 993 for imap.gmail.com and tcp port 465 for smtp.gmail.com but that imap and smtp    traffic is all encrypted. so we cannot see any of the email commands in that tcp stream
5. we can also filter on imap or pop or smtp you wont find anything.
   
#### Expected Output

![image](https://github.com/user-attachments/assets/f1e04d75-113f-416d-95ad-00d7cd9cd9ca)

![image](https://github.com/user-attachments/assets/c5948b91-9c32-474b-a576-88540e33d348)


