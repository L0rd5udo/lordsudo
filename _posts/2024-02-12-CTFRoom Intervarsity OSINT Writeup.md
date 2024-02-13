---
layout : page
---

# East Africa Intervasity CTF - Pre qualifications
-----

## OSINT Challenge: TekaTeka Writeup
-----

### Question 1 - If 41.204.161.167 is my IP, what's my domain name?(15pts)

There are tons of sites that can give us the required information and for this particular challenge i opted to go with site "DNSlytics".
Inputting the given IP, we can get information about the domain name.

<img src='/CTFRoom/OSINT-Intervarsity/dnslytics.png' width="640" height="140">


*Flag: jooust.ac.ke*

-----

### Question 2 - What CMS I am likely running?(15pts)

Accessing the IP on a web browser, we can proceed to use the "Wappalyzer" extension to give us quick access to the requested data.

<img src='/CTFRoom/OSINT-Intervarsity/wappalyzer.png' width="640" height="300">

*Flag: Joomla*

-----

### Question 3 - What PHP version am I running?(15pts)

This can also be fetched using the same extension.

<img src='/CTFRoom/OSINT-Intervarsity/wappalyzer.png' width="640" height="300">

*Flag: 7.4.33*

-----
### Question 4 - So I am website, which year did I likely get published to the internet?(15pts)

For this particular question, we will use "Way Back Machine" and search for our domain name.
Under the calendar tab, we get to see that the first time any actiivity was recorded for the website is actually our needed flag.

<img src='/CTFRoom/OSINT-Intervarsity/calendar.png' width="640" height="360">


*Flag: 2013*

-----
### Question 5 - Before I was, they were. Enter the full URL of my previous site.(20pts)

Under the calendar section, we can open the earliest entry in April 2013 and click on the snapshot to take us to the earliest version of the site and hopefully we come across some valuable information.

Scrolling through the webpage we come across a section that gives us exactly what we need.


<img src='/CTFRoom/OSINT-Intervarsity/oldsite.png' width="640" height="360">

*Flag: http://www.bondo-uni.ac.ke*


-----

### Question 6 - Based on the previous question, enter the mail of the principal.(20pts)

Naviagting to the newly found "Old site", we can scroll about and maybe we can get our mail from the contact page and we find it right there looking at us.

<img src='/CTFRoom/OSINT-Intervarsity/principal.png' width="640" height="360">


*Flag: principal@bondo-uni.ac.ke*

And that marks the end of this quite forward OSINT challenge that was still fun nonetheless.

-----

Nos vemos en mi próximo artículo...
<img src='/favicon.png' width="40" height="40">