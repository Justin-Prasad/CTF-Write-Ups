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

When using ```cat``` on ```message.txt``` in the terminal, I noticed the top of the file had the line ```QWITJSYHXCNDFERMUKGOPVALBZ```. Seeing as how this was a substitution cipher, I assumed it was the substitution values for the standard alphabet ```ABCDEFGHIJKLMNOPQRSTUVWXYZ```. As one naturally does, I made my way to CyberChef and decided to plug it in. After running it with ```QWITJSYHXCNDFERMUKGOPVALBZ``` as my key, I saw a message that looked like this.

```
ABCDEFGHIJKLMNOPQRSTUVWXYZ 

Hjkjpmre Ljykqet qkrgj, axoh q ykqvj qet goqojdb qxk, qet wkrpyho fj ohj wjjodj
skrf q ydqgg iqgj xe ahxih xo aqg jeidrgjt. Io aqg q wjqpoxspd giqkqwqjpg, qet, qo
ohqo oxfj, penerae or eqopkqdxgog—rs irpkgj q ykjqo mkxzj xe q gixjeoxsxi mrxeo
rs vxja. Thjkj ajkj oar krpet wdqin gmrog ejqk rej jlokjfxob rs ohj wqin, qet q
drey rej ejqk ohj rohjk. Thj giqdjg ajkj jlijjtxeydb hqkt qet ydrggb, axoh qdd ohj
qmmjqkqeij rs wpkexghjt yrdt. Thj ajxyho rs ohj xegjio aqg vjkb kjfqknqwdj, qet,
oqnxey qdd ohxeyg xeor iregxtjkqoxre, I irpdt hqktdb wdqfj Jpmxojk srk hxg rmxexre
kjgmjioxey xo.

Thj sdqy xg: mxirCTF{5UB5717U710N_3V0LU710N_03055505}
```

We can see that we have the actual meat of the flag here in ```mxirCTF{5UB5717U710N_3V0LU710N_03055505}``` so all we need to do is remove ```mxir``` and add ```pico```. Alternatively, one could also append all the lower case letters to the plaintext and ciphertext on CyberChef to reveal the flag.

# Flag #
```picoCTF{5UB5717U710N_3V0LU710N_03055505}```
