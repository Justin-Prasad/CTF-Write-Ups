# Challenge
After dinner, Jonah took notes into an online notebook and pushed his changes there. His usernames have been relatively consistent but what country is he going to next? Flag should be in format uiuctf{country_name}

# Hint
forks, trees, pushing, and pulling

# Solution
Within the context of the series, this challenge seems to be one where we're given the least information! Just a description and a hint where this Jonah person could have gone anywhere in the world. Given the lack of routes to take here, I opened the hint and decided to go from there. The hint actually proved to be very helpful, and if you're thinking what I'm thinking, there's only one place to go. An online place where we can fork, push, and pull from trees. You guessed it! It's Github.

Okay so what do we do now? The description says he took to the online notebook and *his usernames have been relatively consistent*. That phrase is very important because now we just need to try to find an account similarly named to the twitter account we found in the "What's for Dinner" challenge.

After a bit of trial and error, I found an account by the username of ```JonahExplorer``` where there exists a public repository called ```adventurecodes```.
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/fcd381bf-fd4a-4ffb-825d-adf24d95fc8a)

Not only that but the date it was created also seemed to line up as well (considering it was made for UIUCTF 2023!)

Looking throught the repo, they says the next place they would like to visit is the "...great wall of china...". You'd think this means they want to go to China right? WRONG. At least that's what the challenge flag submitter said :(

If that wasn't right then what could we do? 

Jonah also mentioned "...not until I get off flight UA5040." Maybe we jumped the gun a bit, got a little trigger-happy with the flag there. Let's see if we can track where this flight is going. Maybe *this* will give us the flag!

Wrong again ;-;

It turns out UA5040 is just a regional flight going from Chicago and Johnstown, Pennsylvania. I even tried to try to find a sort of database of flights because I was so sure this was the way to obtain the flag. That is... until I noticed something else.

The hint said "forks, trees, pushing, and pulling." This prompted me to dive deeper not into the repoistory itself, but githubs features. More so forks and branches (because trees have branches! :o ). After I decided to shift my focus to the features of github itself, I found something very interesting. 
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/8e7eaabd-b904-4210-8b46-a854db6b2e14)

Do you see it too? 

There's a second branch!

Hallelujah! We've found a new lead!

![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/e6f40e77-2975-48dd-b24a-90f9eb6b36d0)

We were just in the main branch, so let's see what's in the active branch. Upon clicking, we see the following screen.

![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/4dc1de0c-35a5-43fa-a34e-79fa650fb25a)

There's 4 commits in this branch! Let's open it up a bit more and see what's inside. 

The initial commit isn't very exiciting.
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/a70484f2-7fb6-4b77-80da-47f37ebfd119)

The second one is just what we saw in the main branch
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/f6a56f60-6ea6-4a42-a2ab-7e9b1e522e2a)

The third one is especially exciting. We find out Jonah is going to Italy before China!
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/3b5847cd-543f-4851-b451-edc2c6d7302c)

## Flag
Adhering to the flag format specified in the description, we get ```uiuctf{italy}```







