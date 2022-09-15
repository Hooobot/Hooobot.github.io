---
layout: project
type: project
image: img/vm/vms.jpg
title: "Virtualization: Sandbox Pentesting"
date: 2022
published: true
labels:
  - Virtualization
  - VirtualBox
  - VMWare
  - Kali Linux
  - Ruby
summary: "Created and utilized a virtual environment to execute Red Team practices."
---

<div class="text-center p-4">
  <img width="1158px" height="405px" src="../img/vm/vm1.png" class="img-thumbnail" >
</div>

With the use of multiple Virtual Machines, I created an environment that allowed for Red Team attacking practices incorporating the aspects of reconnaissance, exploitation, and exfiltration.

The above picture depicts the two environments of Metasploitable 2 (on the left) and Kali Linux (on the right).
<br> By the setup of the above machines I utilized Metasploitable 2 as a victim environment to gain access to, whereas the Metasploit Framwork(MSF) within Kali Linux was used to attack the victim machine. To do so, I detailed my steps in the following pictures:

<div class="text-center p-4">
  <img width="652px" height="615px" src="../img/vm/msf1.png" class="img-thumbnail" >
  <img width="531px" height="181px" src="../img/vm/msf2.png" class="img-thumbnail" >
  <img width="442px" height="166px" src="../img/vm/msf3.png" class="img-thumbnail" >
</div>

In the above pictures we see the startup for the msf console, whereas we additionally load up an exploit of VSFTPD to be thrown at the machine of Metasploitable 2.
This step incorporates the setup, exploit, and access of the machine we are targetting. By running "exploit" we then see a "shell session found" which indicates that we have successfully gotten access to our victim machine.


