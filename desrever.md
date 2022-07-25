# Desrever
Points: 100\
Solves: 430

## Description
```
?galf eht teg uoy naC
```

## Attachments
```
https://imaginaryctf.org/r/0m7ei#desrever.py
```

## Solution
When we open `desrever.py`, we see the following Python code:

```python
#!/usr/bin/env python3

cexe = exec
cexe(')]"}0p381o91_flnj_3ycvgyhz_av_tavferire{sgpv"==)]pni ni _ rof _ esle "9876543210_}{" ni ton _ fi ]_[d.siht[(nioj.""[)"tcerroc","gnorw"((tnirp;)" >>>"(tupni=pni;)"?galf eht si tahW"(tnirp;siht tropmi'[::-1])
```

The two main things that we can notice at first glance are:
1. The text string passed into `cexe` (particularly at the end) seems to be reversed
2. At the end of the string is `[::1]`, which  is slice notation in Python to reverse a string

With this knowledge, we can plug the string into an [online text reversal tool](https://textreverser.com/), which returns:

```
import this;print("What is the flag?");inp=input(">>> ");print(("wrong","correct")["".join([this.d[_] if _ not in "{}_0123456789" else _ for _ in inp])=="vpgs{erirefvat_va_zhygvcy3_jnlf_19o183p0}"])
```

Now, we can clearly recognize the ImaginaryCTF flag format `ictf{...}` at the end of the string, however it seems to be encrypted somehow. When I was solving this, I initially tried plugging the encrypted flag into [CyberChef](https://cyberchef.org/), but to no avail. I then thought the seemingly random scrambling of characters could be a result of the Caesar cipher, so I tried plugging it into a [decoder](https://www.dcode.fr/caesar-cipher), which gives us the flag.

```
ictf{reversing_in_multipl3_ways_19b183c0}
```
