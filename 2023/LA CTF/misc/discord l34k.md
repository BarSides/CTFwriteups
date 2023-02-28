# discord l34k

## Author of writeup

Pat Natali

## Challenge

> My friend sent me [this](https://discord.com/channels/1060030874722259057/1060030875187822724/1060031064669700186) message link that apparently links to a "flag", but discord says "You  don't have access to this link"! They did mention something about them  being able to embed a list of online users on their own website, and  sent me this image. Can you figure out how to join the server?
>
> Note: Discord phone verification is NOT required for this challenge.

They attached an image named "embed.png".

## Solution

The key here is to make the same widget that they show you as their example and then substitute in the right values from the discord link.

Using this message link `https://discord.com/channels/1060030874722259057/1060030875187822724/1060031064669700186` and the embed widget from my own personal Discord server:

```
<iframe src="https://discord.com/widget?id=----->SERVER ID GOES HERE<------&theme=dark" width="350" height="500" allowtransparency="true" frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"></iframe>
```

The first number in the URL from the discord server given to us is the server id (`1060030874722259057`). If we just paste in that server id to the widget's id parameter, we can fabricate our very own discord invite link. Clicking this brings us to the discord server containing the flag.
