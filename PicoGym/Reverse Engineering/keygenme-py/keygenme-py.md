# Challenge Rundown #
Category: General Skills

Points: 30

# Challenge Description #
The description of this challenge just provides a python file.
https://mercury.picoctf.net/static/5a4198cd84f87c8a597cbd903d92fbf4/keygenme-trial.py

# Hints #
No hints are provided for this challenge.

# Explanation #
As we shall do for most other challenges, we will open up the terminal and ```wget``` the ```keygenme-trial.py``` file. 

![image](https://user-images.githubusercontent.com/101998961/201784266-56b04c2c-145b-475e-8f1b-5e5e47658fa2.png)

It should looks something like this.

We should try to run the python file, and see if there's anything of interest there. Remember to use the ```chmod +x``` command on the file in order to give it permission to run!

![image](https://user-images.githubusercontent.com/101998961/201784535-0f6e49b4-c424-4de4-844e-19e48ab833be.png)

After giving the file permission to run, and then running it, this is what we are met with. I played around with the program for a bit to get a feel of what the basic tasks were. After getting some rather vague answers, I decided to open up nano on my terminal and inspect the code.

One thing that I thought upon first opening the code, was that we were importing Fernet and base64. This is essentially an encryption of some sort such that it cannot be read without some key. So this is what I honed in on.

The first thing I found was a line called ```key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"```. This pretty much let me know that I was on the right track. The idea I had was to look through the code to see if anything stood out.

Right below, there were 2 other lines that said ```key_part_dynamic1_trial = "xxxxxxxx"```, ```key_part_static2_trial = "}"```, and ```key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial```. We should probably go through the program a bit more to see if there's anything else of use.

After sifting through the code a bit more I came across a function called ```check_key```. This is what it looks like. 

![image](https://user-images.githubusercontent.com/101998961/201789326-3db8e270-c9e7-4c6b-a38e-a4516624292a.png)

This was a lovely gift as we know we need to be able to obtain some kind of key. 

We can see that it's using the username defined in the program as "ANDERSON" from the ```username_trial```, which it then encrypts using SHA256 and then puts into hexadecimal using ```hexdigest``` and then check checks a particular character in the inputted key, and then compares it with the actual key.

What we need to do is to encrypt ANDERSON into SHA256, then into hexadecimal, and find the indicated characters in the string as specified in the code. So that is the 4th, 5th, 3rd, 6th, 2nd, 7th, 1st, and 8th characters of the string. You can make a python script to do so if you wish but I just did it with online encoders and picking the characters by hand. 

What I got in the end was the characters ```01582419```. Then all there is to be done now is to add it to what we have in the flag so far and bam! 

# Flag #
```picoCTF{1n_7h3_|<3y_of_01582419```

