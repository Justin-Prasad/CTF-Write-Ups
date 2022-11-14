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

The first thing I found was a line called ```key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"```. This pretty much let me know that I was on the right track. The idea I had was to alter the code so instead of constantly blocking us, we can bypass it and enter some kind of key to be decrypted. 

Right below these, there were 2 other lines that said ```key_part_dynamic1_trial = "xxxxxxxx"```, ```key_part_static2_trial = "}"```, and ```key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial```

After sifting through the code a bit more I came across a function called ```check_key```. This is what it looks like 

![image](https://user-images.githubusercontent.com/101998961/201789081-cf8defb4-642a-4401-a535-82deb2025ae4.png)

