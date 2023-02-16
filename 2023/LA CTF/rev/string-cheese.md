# string-cheese

## Author of writeup

Pat Natali

## Challenge

> I'm something  of a cheese connoisseur myself. If you can guess my favorite flavor of  string cheese, I'll even give you a flag. Of course, since I'm lazy and  socially inept, I slapped together a program to do the verification for  me.
>
> Connect to my service at `nc lac.tf 31131`
>
> Note: The attached binary is the exact same as the one executing on the remote server.

## Solution

I simply took the binary and opened it with a text editor (Notepad++) to find the answer saved in the binary.

![plaintext](..\images\rev\cheese.png)

```
$ nc lac.tf 31131
What's my favorite flavor of string cheese? blueberry
...how did you know? That isn't even a real flavor...
Well I guess I should give you the flag now...
lactf{.....flag....}
```
