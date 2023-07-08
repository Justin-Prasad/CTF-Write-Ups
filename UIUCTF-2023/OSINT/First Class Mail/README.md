# First Class Mail

## Challenge
Jonah posted a picture online with random things on a table. Can you find out what zip code he is located in? Flag format should be uiuctf{zipcode}, ex: ```uiuctf{12345}```

## Hint 
I think code is cool

## Solution
In the final part of the Jonah series, we are given another jpg file! 
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/53feb8a2-84f8-4ed6-9bc9-75c9a8c8428c)

Now at first glance, this picture looks extremely cluttered. There's a lot of stuff going on, and it's honestly a little overwhelming. Let's try to take this one step at a time shall we?

So we see in the challenge description, we want to find the zipcode Jonah is located in. What better way to get that than from the gps coordiantes? And what better way to get the gps coordinates than by going through the exif data? :D

Chucking this into [aperisolve](https://www.aperisolve.com/) however yields nothing I can really use unfortunately. Back to square one we go!

Looking at the picture, the next best lead I was able to obtain was an insurance form!

![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/3a70081b-aeda-4cef-9d87-c6d1b69fbcc2)

Looking at this form, I decided to search up where the company was located, and possible zipcodes I could try. Because the form mentioned that it was sent to us "courtesy of your local Erie Insurance agent Lanyi Insurance Agency Inc." So searching up where this was led me to Irwin, Pennsylvania. I kid you not, I tried nearly every zip-code in the god dang county. The reason I'm sharing this with you is because I believe it's important to share when I too get lost in a red-herring and to learn from it! Anyways, it was definitely not the right path to take, but I was so deadset on this zipcode being from the state of Pennsylvania that it clouded my judgement from an even bigger piece of information. 

This challenge name is "First Class Mail." The phrase is a reference to the United States Postal Service offering a way to send envelopes and lightweight packages that is easy and affordable. Not only that but the hint itself is saying "I think code is cool." What if this is some sort of cryptographic code related to the United States Postal Service? 

A quick google search will lead us to a wikipedia article describing the [Intelligent Mail Barcode](https://en.wikipedia.org/wiki/Intelligent_Mail_barcode)(IMB)

Going back to the image, there's something on one of the papers in plain sight. It seems like a barcode that's inline with what the article is describing!
![image](https://github.com/Justin-Prasad/CTF-Write-Ups/assets/101998961/379c5586-7c78-4bad-bf19-a83af5b330fa)

Looking at how to decode the IMB however shows us that the code in the picture does not match. The reason for this is because the IMB requires us to have 65 bars, but we only have 52! 

Alas our plans have been foiled again... Or have they? 

Reading the wikipeida article again, it mentions that the IMB has a predecessor code known as [POSTNET](https://en.wikipedia.org/wiki/POSTNET). Maybe that could help! We see that the code reveals a zipcode, a 4 digit extension, AND start and stop code! Because each digit takes 5 bars with a check digit and a start/stop of 1 bar each, mathematically this means we need 52 bars, which is what we have! Hallelujah we've done it! 

Decoding the barcode using the POSTNET encoding scheme yields our flag

## Flag
```uiuctf{60661}```






