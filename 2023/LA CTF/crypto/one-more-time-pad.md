# one-more-time-pad

## Author of writeup

Pat Natali

## Challenge

> I heard the onetime pad is perfectly secure so I used it to send an important message to a friend, but now a UCLA competition is asking for the key? I threw that out a long time ago! Can you help me recover it?

## Solution

This one-more-time-pad script is basically just a XOR encryption on each byte. After much trial and error, I realized that `plaintext ^ ciphertext = key` in XOR encryption and since we already had both I could simply derive the key by subtly editing the python script.

```
$ cat llahc.py
pt = b"Long ago, the four nations lived together in harmony ..."
ct = bytearray.fromhex("200e0d13461a055b4e592b0054543902462d1000042b045f1c407f18581b56194c150c13030f0a5110593606111c3e1f5e305e174571431e")
key = ""
for i in range(len(pt)):
    keychar = (pt[i] ^ ct[i])
    print("pt=", pt[i], "ct=", ct[i])
    print("keychar=", keychar)
    # b = (pt[i] ^ next(key))
    key += chr(keychar)
print("key=", key)
```

```
$ python llahc.py
pt= 76 ct= 32
keychar= 108
pt= 111 ct= 14
keychar= 97
pt= 110 ct= 13
keychar= 99
pt= 103 ct= 19
keychar= 116
pt= 32 ct= 70
. . .
keychar= 109
pt= 46 ct= 30
keychar= 48
key= lactf{...flag...}lactf{...flag...
```
