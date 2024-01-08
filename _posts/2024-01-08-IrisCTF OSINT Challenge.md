---
layout : page
---

# IRISCTF 2024 OSINT Challenge
-----

### Challenge 1:Czech Where?

#### Description
Iris visited this cool shop a while back, but forgot where it was! What street is it on?

The file provided is the image below.
![ChallengeImage](/_posts/IrisCtf/Chall1/czechwhere.png)
##### Hint
FYI: flag is all lowercase and _ for spaces. Please remove all accent marks if there are any. Wrap your answer in irisctf{}.

##### Solution

The first thing that comes to mind is to check the image metadata for any probable location information, though in most cases it is usually stripped off the image. 

![](/_posts/IrisCtf/Chall1/exif.png)

Just as we thought, the location data has been stripped from the image.


We can now do a reverse search with the image and we see an article with the same image. The article points to Golden Lane,Prague castle. 

![Reverse Search](/_posts/IrisCtf/Chall1/revsearch.png)
![Article](/_posts/IrisCtf/Chall1/blogss.png)

A further google search with the shop name leads us right to the address.
![Address](/_posts/IrisCtf/Chall1/Address.png)

This gives us the flag: *irisctf{zlata_ulicka_u_daliborky}*

-----

### Challenge 2: Away on Vacation

#### Description
Iris and her assistant are away on vacation. She left an audio message explaining how to get in touch with her assistant. See what you can learn about the assistant.

The Audio file was provided and its transcript too

##### Transcript
``` Hello, you’ve reached Iris Stein, head of the HR department! I’m currently away on vacation, please contact my assistant Michel. You can reach out to him at michelangelocorning0490@gmail.com. Have a good day and take care. ```

##### Solution
Out of Curiosity I sent an email to Michel and got the following response.
![](/_posts/IrisCtf/Chall2/Email.png)

We can use ```epieos.com``` and find out what data we can get from there and this gives us the full name of the google account in question.
![Epieos](/_posts/IrisCtf/Chall2/Epieos.png)

A google search with the name shows us two social media accounts i.e LinkedIn and Instagram
![LinkedIn](/_posts/IrisCtf/Chall2/linkedin.png)
![Instagram](/_posts/IrisCtf/Chall2/instagram.png)

We can confirm that the instagram account belongs to him since its all about birds and thats what he hinted towards in his email.
Scrolling through the posts we come across a very interesting one that gives us the flag.

![](/_posts/IrisCtf/Chall2/igflag.png)

This gives us the flag: *irisctf{pub1ic_4cc0unt5_4r3_51tt1ng_duck5}.*

-----

### Challenge 3: Personal Breach

#### Description
Security questions can be solved by reconnaissance. The weakest link in security could be the people around you.

This challenge provides us with a link to a web page where we are required to provide some information.
![Webpage](/_posts/IrisCtf/Chall3/Stein%20Info.png)

##### Solution

Going back to Michel's page, we can check his following which leads us to Iris' Instagram handle.
![following](/_posts/IrisCtf/Chall3/following.png)

Perusing through her feed there isnt much of help apart from a single post where she mentions her mum and also tags a handle.

![mum](/_posts/IrisCtf/Chall3/mum.png)

Searching for that username on Instagram bore no fruits, so i decided to shift my focus to the most obvious platform used by the "Elders" - Facebook.

Searching through facebook gave various accounts but finding the exact one was really easy.

![](/_posts/IrisCtf/Chall3/elaina.png)

Scrolling down through her profile we hit basically a gold mine.

![](/_posts/IrisCtf/Chall3/bday.png)

We have a hit on Iris' Birthdate which gives us her age - 27yrs

In the comments of the birthday post, we basically hit another gold mine as we can now find the hospital she was born in.

![](/_posts/IrisCtf/Chall3/bday%20comment.png)

A revrse search of the image gives us the hospital or alternativley we could search by the leading statement from the mum's comment "best maternity hospital in Manhattan"
This search gives us results from Yelp which leads us to the answer.

![LenoxHill](/_posts/IrisCtf/Chall3/lenoxhill.png)

Now for the final answer, we can do a search on LinkedIn for Iris And we get a hit. Information from the previous question tells us that she works in the HR department and thus we can verify that it indeed is her profile and get her comapny.

![LinkedIn](/_posts/IrisCtf/Chall3/LinkedIn.png)

Using all the details found we can now enter the answers on the web page to get our flag.

![](/_posts/IrisCtf/Chall3/filledwebpage.png)

This gives us the flag: *irisctf{s0c1al_m3d1a_1s_an_1nf3cti0n}*

-----

### Challenge 4: A Harsh Reality of Passwords

#### Description
Recently, Iris's company had a breach. Her password's hash has been exposed. This challenge is focused on understanding Iris as a person.

Hash: $2b$04$DkQOnBXHNLw2cnsmSEdM0uyN3NHLUb9I5IIUF3akpLwoy7dlhgyEC

The flag format is irisctf{plaintextPassword}

##### Hint
Focus on Iris and what she finds important!
There are three words (not letters, but words), and a certain amount of numbers following it.
There's no leet words, proper capitalization nothing like (ExAmPLE), no special characters as well like -,! etc.
If you find a specific date, do not include the month'a name into your word list. Just use the numbers!!

##### Solution
We start with a hash and need to decrypt it for which we shall require a wordlist. This needs us to gather key information to include in the wordlist.
Scouring through her Instagram, she mentioned her Mum's birthday being an important date and we can get this from the mum's facebook. This should be our numbers - as per the hint.
![Mumbday](/_posts/IrisCtf/Chall4/mum.png)

She also mentioned having 'mimosas', and we can add that too.
As we keep scrolling she mentions she has an obsession with 'Tiramisu' and we can take note of this too.

![Tiramisu](/_posts/IrisCtf/Chall4/Tiramisu.png)

In another post, she mentions how 'Portofino' will always be a destination to remember.

![Portofino](/_posts/IrisCtf/Chall4/portofino.png)

Going through all the posts and various things that may be important we now have enough text to create a wordlist.

We can generate the wordlist using a python script

![Python](/_posts/IrisCtf/Chall4/python.png)

We now have a wordlist file that we can run against the hash.
the hash is input in a text file and run against hashcat

```hashcat -m 3200 hash.txt iriswordlist.txt```

This gives us the matching password PortofinoItalyTiramisu0481965

The flag: irisctf{PortofinoItalyTiramisu0481965}

<!-- -----

Overall, this was a very interesting OSINT Challenge that i had fun tackling. Kudos to the team from Iris CTF for setting this up and thanks too... -->

-----
Nos vemos en mi próximo artículo,

@L0rd$ud0