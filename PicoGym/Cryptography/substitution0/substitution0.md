# Challenge Rundown #
Category: Cryptography

Points: 100

# Challenge Description #
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://github.com/Justin-Prasad/CTF-Write-Ups/blob/main/PicoGym/Cryptography/substitution0/message.txt)

# Hints #
Try a frequency attack. An online tool might help.

# Explanation #
This challenge didn't have much to it. From the name alone I inferred that it was a substitution cipher. 

A substitution cipher is a cipher in which alpha-numeric characters are... well... substituted, most often with other letters or numbers.

When using ```cat``` on ```message.txt``` I noticed the top of the file had 
