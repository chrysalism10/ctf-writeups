# Democracy
Points: 100\
Solves: 505\
Note: This challenge was later shut down and the flag was given out for free by CTF admins due to players attacking each other

## Description
```
I'm tired of all these skill-based CTF challenges. Y'know what we need more of here? Politics! Simply convince (or strongarm) your fellow competitors to vote for you. The top 1% of players who have the most votes (or top 50, whichever is less) will recieve the flag. This voting will occur 5 times per hour. Keep in mind that no matter how many accounts you make, you can only vote once per IP. Good luck, and happy campaigning!
```

## Attachments
```
http://chal.imaginaryctf.org:1339/
```

## Solution
The challenge description tells us that you could only vote once per IP. IP blacklisting is very insecure and can easily be bypassed in many ways, such as by using Tor, which allows you to have a completely different IP address.

By using the Brave browser, which has a Tor integration, we can create a new Tor connection, make a new account, vote for our main account, close Tor, and repeat. After the timer expires, we do in fact get the flag.

```
ictf{i'm_sure_you_0btained_this_flag_with0ut_any_sort_of_trickery...}
```
