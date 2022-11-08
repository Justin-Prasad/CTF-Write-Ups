# Challenge Rundown #
Category: General Skills

Points: 5


# Challenge Description #
This file has a flag in plain sight (aka "in-the-clear")
https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag


# Hints #
1.) Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

2.) To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag

3.) $ man cat


# Explanation #
This challenge is really just to make sure you know how to access the terminal, use the ```wget``` command to download it, and then use ```cat``` to view the contents of said file. After using ```wget``` the file provided, and then using ```cat``` on the newly downloaded file in the terminal, the flag can be seen in the terminal 


# Flag #
```picoCTF{s4n1ty_v3r1f13d_4a2b35fd}``` 
