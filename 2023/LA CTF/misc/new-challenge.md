# new-challenge

## Author of writeup

Pat Natali

## Challenge

> @bliutech could you push an updated description for this challenge thx
>
> ```
> git clone git://lac.tf:31152/new-challenge.git
> ```

## Solution

First simply clone the repo and look at the prehook to see it's trying to authenticate people by username and email. Change your git username and email locally to get around this with `git config`.

```
~/repos/new-challenge$ git config --get user.name
Benson Liu
~/repos/new-challenge$ git config --get user.email
bensonhliu@lac.ctf
. . .
~/repos/new-challenge$ git log -p
commit 72a7a3ac8b6a36e96cd3cb6471bbdce2f97a6147 (HEAD -> main)
Author: Benson Liu <bensonhliu@lac.ctf>
Date:   Sat Feb 11 04:29:34 2023 +0000

    challenge.yml

    pwned
. . .
~/repos/new-challenge$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 287 bytes | 287.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: lactf{...................flag.........}
remote: don't feel like talking to the disk today, sorry
To git://lac.tf:31152/new-challenge.git
 ! [remote rejected] main -> main (pre-receive hook declined)
error: failed to push some refs to 'git://lac.tf:31152/new-challenge.git'
```
