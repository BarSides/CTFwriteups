# Old Habits Die Hard

## Author of writeup

Justin Forbes [@justinforbes](https://twitter.com/justinforbes)

## Challenge

> We found this zip file but its encrypted so we can't read the contents. Do you think you could crack it?

## Attachements

![Encryptedfile.zip](../images/Encryptedfile.zip)
![wordlist.txt](../images/wordlist.txt)

## Solution

Using the tool zip2john we created a hash file that can be used with John the ripper.

![zip2john](../images/zip2john.png)

Then we used John the Ripper to crack the hash and retrieve the password.

![john](../images/cracked.png)

Finally we used the password to unzip the archive and retrieve the flag.

![flag](../images/unzip.png)
