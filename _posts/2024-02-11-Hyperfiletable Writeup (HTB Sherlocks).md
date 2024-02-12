---
layout : page
---

<img src='/Sherlocks/Hyperfiletable/hyperfilebanner.png' width="640" height="140">

# HTB SHERLOCKS - HYPERFILETABLE
-----

## Description

There has been a new joiner in Forela, they have downloaded their onboarding documentation, however someone has managed to phish the user with a malicious attachment. We have only managed to pull the MFT record for the new user, are you able to triage this information?

<!-- ## Files Attached

<img src='/Sherlocks/Hyperfiletable/files.png' width="640" height="200"> -->

-----

## Solution
We will start by unzipping the file and then parsing it using analyzeMFT to get an output in CSV format.

<img src='/Sherlocks/Hyperfiletable/unzip.png' width="640" height="140">

We have the output in CSV format now and we can proceed with the analysis.

<img src='/Sherlocks/Hyperfiletable/parsedmft.png' width="640" height="90">

-----
### Task 1 - What is the MD5 hash of the MFT?

We use the md5sum command to get this.

*Flag: 3730c2fedcdc3ecd9b83cbea08373226*

<img src='/Sherlocks/Hyperfiletable/md5sum.png' width="640" height="100">

-----

### Task 2 - What is the name of the only user on the system?

We can filter for Users in the csv file and we get the answer.

*Flag: Randy Savage*

<img src='/Sherlocks/Hyperfiletable/username.png' width="640" height="360">

-----

### Task 3 - What is the name of the malicious HTA that was downloaded by that user?

Staying in the CSV file we can search for .HTA to see if any such file exists.
This gives us the name of the malicious HTA that was downloaded.

*Flag: Onboarding.hta*

<img src='/Sherlocks/Hyperfiletable/hta.png' width="640" height="300">

-----
### Task 4 - What is the ZoneId of the download for the malicious HTA file?

For this particular question, we will analyse the mft.raw file using MFTEplorer.

<img src='/Sherlocks/Hyperfiletable/mftexplorer.png' width="640" height="360">

We can now navigate to the directory where the HTA file is located and in the data interpreter section we can identify the ZoneId.

*Flag: 3*

<img src='/Sherlocks/Hyperfiletable/zoneid.png' width="640" height="360">

-----
### Task 5 - What is the download URL for the malicious HTA?

In the same data interpreter section, scrolling down we can identify the Download URL used.


<img src='/Sherlocks/Hyperfiletable/downloadurl.png' width="640" height="360">

-----

### Task 6 - What is the allocated size for the HTA file? (bytes)

In the overview tab we can see some information about the file size.
Physical size is what is referred to as allocated size.

<img src='/Sherlocks/Hyperfiletable/size.png' width="640" height="360">

The Physical size identified is 0x1000 which when converted equals 4096bytes.

*Flag: 4096*

-----

### Task 7 - What is the real size of the HTA file? (bytes)

From the overview tab, we have already have the required information. In the case of real size it is being referred to here as logical size.

<img src='/Sherlocks/Hyperfiletable/size.png' width="640" height="360">

The logical size identified is 0x478 which when converted equals 1144bytes.

*Flag: 1144*

-----

### Task 8 - When was the powerpoint presentation downloaded by the user?
Sifting through the directories, we find the powerpoint file in the Documents directory.

<img src='/Sherlocks/Hyperfiletable/pptx.png' width="640" height="360">

The date is found under the created on column.

*Flag: 05/04/2023 13:11:49*

-----

### Task 9 - The user has made notes of their work credentials, what is their password?
In the same Work Directory, there is a file called notes.txt and upon examining the data interpreter section, we can find the credentials.

*Flag: ReallyC00lDucks2023!*

<img src='/Sherlocks/Hyperfiletable/password.png' width="640" height="360">

-----
### Task 10 - How many files remain under the C:\Users\ directory? (Recursively)

You have to check for all the files that have C:\Users as the parent directory.


*Flag: 3471*

-----

Nos vemos en mi próximo artículo...