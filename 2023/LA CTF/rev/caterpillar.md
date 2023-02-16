# caterpillar

## Author of writeup

Pat Natali

## Challenge

> -~-~-~-~[]? -~-~-~-~[].

## Solution

They give you a file looking like so:

```const flag = "lactf{XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX}";
if (flag.charCodeAt(-~-~-~-~-~-~-~-~-~-~-~-~-~-~-~-~-~[]) == -~-~-~-~-~-~-~-~-~-~-~-~-~-~-~-~-~- ...
    console.log("That is the flag!");
} else {
    console.log("That is not the flag!");
}
```

This is a Javascript code obfuscation challenge.

Basically each `-~` represents a single `+1` by using a trick via two's complement, so `-~-~-~-~[]?` in the description of the challenge means "4?".

I wrote a perl script called 'butterfly.pl' to solve this one for us.

```
$ cat butterfly.pl 
use strict;
use warnings;

$/ = undef;
open (my $caterpillar, "<", "./caterpillar.js");
my $contents = <$caterpillar>;

warn $contents;
my (%codez) = $contents =~ /flag\.charCodeAt\(([~-]*\[\])\) == ([~-]*\[\])/g;
use Data::Dumper;
warn Dumper \%codez;
my @clean_array = ();
for my $raw_index (keys %codez) {
    my $clean_index = () = $raw_index =~ /(-~)/g;
    my $raw_value = $codez{$raw_index};
    my $clean_value = () = $raw_value =~ /(-~)/g;
    $clean_array[$clean_index] = $clean_value;
}
for my $val (@clean_array) {
   if (!defined $val) {
      next;
   } 
   print chr($val);
}
```

`lactf{th3_hungry_l1ttl3_c4t3rp1ll4r_at3_th3_fl4g_4g41n} `
