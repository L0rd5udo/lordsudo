---
layout : page
---
<img src="/MayhemCTF/Charter/banner.png" width="640" height="360" />

# GLOBAL CYBER GAMES NEW YEAR MAYHEM CTF 2024
## Forensic and OSINT Challenges Writeups

-----
### Forensics Challenge 1 : Charter

#### Description
The attackers deleted all our files in a recent breach. We managed to recover almost all of them from offsite backups but are missing some important files that were stored on the compromised file server. We managed to capture the traffic during the attack. Can you please help us with this situation and recover our files?

#### Solution

Having downloaded the zip file, we extract and come across a file ```traffic.pcapng```.
Since, we are in a ctf, the first thought that comes to mind is to grep for any important strings in this file and test our luck.

Well,well,well, with lady luck smiling upon us, we have the flag.

*HTB{r3cov3ry_1s_fun_409df1!!}*

<img src="/MayhemCTF//Charter/charterflag.png" width="640" height="100" />

NB: Check back later for a detailed way of solving this, for now let's proceed to the second challenge.

-----

### Forensics Challenge 2: Penetrated

#### Description
We detected a strange file in the Wordpress uploads folder. Luckily we still have a dump of the network traffic at the same time as the file timestamp. We wonder if it was created by the attacker and did he succeed with his goal?

#### Solution

Downloading the file given, we extract to get ```capture.pcap``` and we can proceed with our analysis from here.






-----

### OSINT Challenge 1 : Jon Tweets a lot

#### Description
Jonathan Witherson is a cyber security professional who tweets a lot of information. Can you find his first secret? Target the presence of individuals on Social Media and gather information.

#### Solution

Since we are told that he tweets a lot, the first step is to search for a twitter account using his name and voila, it is right there.

<img src="/MayhemCTF/OSINT/jontwitter.png" width="640" height="420" />

Scrolling through the feed, we come across a QR code.

<img src="/MayhemCTF/OSINT/qrcode.png" width="640" height="550" />


Running the code against a scanner, we get our flag.

*HTB{qRc0d5sc4nbeUs3dT0spr34dm4lw4r3}*

<img src="/MayhemCTF/OSINT/scannedcode.png" width="640" height="450" />

-----
### OSINT Challenge 2 : Signature leaks

#### Description
Jonathan tends to leak information in his email replies.

#### Solution

As we were scrolling through his twitter account, we saw him mention his email as a means to reach out, and we shall do just that.

His response gives us the flag.

*HTB{yoUr_em41l_maY_p0s3_4_r1sK}*

<img src="/MayhemCTF/OSINT/email.png" width="640" height="180" />

-----
### OSINT Challenge 3 : Git Commit

#### Description
Are you really committed to becoming an OSINT master? Because version-control and collaboration platforms may expose valuable information and Jonathan is using one of them.

#### Solution

Key Words 'Version Control' and 'Collaboration Platform' are hints that suggest it has something to do with github.

A quick google search leads us to his github profile where we see that he has one repository.

<img src="/MayhemCTF/OSINT/github.png" width="640" height="360" />

Heading to the repository, we see that he has 2 files committed, but 3 commits in total. Delving deeper we find his first commit of the hello world program and here we get our flag.

*HTB{H1dd3n_d4t4_1n_pl4in_s1ghT???}*

<img src="/MayhemCTF/OSINT/commit.png" width="640" height="300" />


-----
 


<!-- <img src="/assets/ls tsp.png" width="30" height="30" />   -->
Nos vemos en mi próximo artículo...