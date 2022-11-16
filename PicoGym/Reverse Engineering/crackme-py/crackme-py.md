# Challenge Rundown #
Category: Reverse Engineering

Points: 30

# Challenge Description #
The description just provides us with this file. [crackme.py](https://github.com/Justin-Prasad/CTF-Write-Ups/blob/main/PicoGym/Reverse%20Engineering/crackme-py/crackme.py)

# Hints #
No hints are provided for this challenge

# Explanation #
Given that the challenge presents us with a python file in a Reverse Engineering category, my first instinct was to inspect the code. So after opening it up in VSCode, the first thing that I noticed was this at the top of the file.

``` # Hiding this really important number in an obscure piece of code is brilliant!
# AND it's encrypted!
# We want our biggest client to know his information is safe with us.
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE02fh3e4a5N" 
```
We see as we scroll down in the file, there is a function called ```decode_secret```. At this point, we know that ```bezos_cc_secret``` should be decoded by ```decode_secret```.

From this point, all we really need to do is add our own print statement to decode the flag using the decoder function provided. 

It should be known that there is another function called ```choose_greatest``` but it's not really that important. We can disregard it, and delete the ```choose_greatest()``` call at the bottom of the file and replace it with a print statement for the decoded string. 

I made mine as ```print(decode_secret(bezos_cc_secret))```

Alternatively, one could also just copy and paste ```A:4@r%uL`M-^M0c0AbcM-MFE02fh3e4a5N``` into an online ROT47 decoder like CyberChef or something of the sort as the ```decode_secret``` function tells rather clearly that it is a ROT47 decoder. We will still end up with the same flag in the end. 

# Flag #
```picoCTF{1|\/|_4_p34|\|ut_a79b6c2d}```


