# my-chemical-romance

## Author of writeup

Pat Natali

## Challenge

> When I was... a young boy... I made a "My Chemical Romance" fanpage!
>
> [my-chemical-romance.lac.tf](https://my-chemical-romance.lac.tf)

## Solution

There's a header sent to us by the web server saying it's Mercurial-SCM.

![HTTP Header](..\images\web\mcr_headers.png)

 Eventually I got `hg` which is Mercurial SCM and used `hg clone https://my-chemical-romance.lac.tf` which actually worked and downloaded the repo. From there I checked the previous commits by doing `hg log -p`. The flag was deleted in a previous commit and is in the history of the repo itself.
