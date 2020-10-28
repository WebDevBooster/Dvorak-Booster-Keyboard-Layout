# Dvorak-Booster Keyboard Layout

The Dvorak-Booster keyboard layout is better optimized for typing text in English than standard Dvorak and **MUCH better optimized for programming and the command line than Programmer Dvorak**. 

ALL of the special characters for coding or command line are accessible on the two most easily accessible levels and almost all of those special characters are located on the two most easily reachable rows! 

In short: 

> #### With Dvorak-Booster layout switched on, typing code or entering command line instructions feels like walking with an anti-gravity backpack!

Joking aside, typing with Dvorak-Booster layout is ***so easy, effortless and so pleasant***, it almost feels like you are controlling the keyboard keys with your MIND!... Because the difficult, unpleasant and error-prone wrist and finger moves often required with other keyboard layouts have been eliminated on the Dvorak-Booster layout. 

The Dvorak-Booster layout also makes it easy to type in the [dozenal (base 12) system](https://en.wikipedia.org/wiki/Duodecimal) and the general layout of numbers is optimized according to their [frequency distribution](https://en.wikipedia.org/wiki/Benford%27s_law) (unlike standard Dvorak and Programmer Dvorak). In other words, the most frequently typed numbers are the easiest to reach on the numbers row.

And if you occasionally need to type in other languages beside English, you'll love the fact that Dvorak-Booster makes it possible to type in any Latin-alphabet-based (European) language *without switching the keyboard layout*. Although Dvorak-Booster is not optimized for typing in those other languages primarily. So, this is just an additional bonus feature. 

Another great feature of Dvorak-Booster: 

ALL of the arrow keys (left, right, up, down) as well as the delete key as well as the **escape** key are easily reachable from the "home" i.e. default resting position! 

So, if you want to be a command line or `vim` magician, Dvorak-Booster layout will be your trusty magic wand! For example, typing the `!$` combination (to recall the last argument of the previous command in bash) is basically just one fluid and pleasant motion on the Dvorak-Booster layout! Very much like waving a magic wand. 

Overall, Dvorak-Booster makes typing in English and typing for coding, command line and markup languages **MUCH more enjoyable**, reduces the stain on wrists and fingers and cuts down the number of typos to a minimum. That can make you happier and more productive. 

I've put a LOT of time, thought, research and **testing** effort into developing the Dvorak-Booster keyboard layout because being able to type so effortlessly is great fun! And after several iterations of tweaking, challenging and questioning my own assumptions and ideas, throwing out some of my previous assumptions and ideas, re-designing, tweaking, testing, tweaking, testing and tweaking-testing again and again I finally ended up with a keyboard layout that really does feel pretty magical when you use it. This keyboard layout is probably as close to a magic wand as it's possible to get. 


## Table of Contents

### 1 Why
* #### [1.1 The History](#the-history)

* #### [1.2 Layout Rationale](#layout-rationale)

    - ##### [1.2.1 What Would Be The Ideal Layout?](what-would-be-the-ideal-layout)
    
    - ##### [1.2.2 Why Is The Dozenal System Superior?](#what-is-the-dozenal-system-and-why-is-it-superior)

--- 

## The History

When I originally learned to touch type, 
I initially did a research before learning 
(because I like to do things thoroughly) 
and I quickly realized that 
```diff
! the standard keyboard layout i.e. 
! the keyboard layout used on 
! all standard computer keyboards today 
! was specifically developed 
! to SLOW DOWN TYPING!
```

Hard to believe but it's true.

The standard keyboard layout that's being used for computers today is the same that was originally developed for **mechanical typewriters**. 

It was developed to solve a common and very annoying problem with mechanical typewriters:  
The levers for the letters (each letter was attached to an individual mechanical lever) 
would often interlock if you typed too fast. 

I have actually experienced this problem first hand (a very long time ago) when I tried to type on a mechanical typewriter. While I wasn't typing fast, occasionally I would press two adjacent keys together by accident... 

And every time that happened, it was a very annoying and time consuming mess. Getting those levers unstuck wasn't easy and you had to get your fingers dirty etc. etc. It was a mess. 

Long story short, the original (standard) keyboard layouts (for each language) were **specifically developed to slow down typists** in order to minimize those occasions where the typing levers would interlock and get stuck. Typist was actually a profession and companies used to employ large numbers of people whose sole job was to type all day, transcribe from audio recordings etc.

And when computers and computer keyboards got invented (without any mechanical levers attached to the keys), the same old keyboard layouts were copied unchanged. 

Once I learned this simple fact (shortly after I decided to learn touch typing), it became instantly clear to me that I can't possibly waste time on learning a keyboard layout that was designed for SLOW typing. 

Instead, I decided to learn a keyboard layout that was actually... 

* optimized for typing on a computer
* optimized for typing fast
* optimized for being easy on the hands and wrists

That keyboard layout was [**Dvorak**](https://en.wikipedia.org/wiki/Dvorak_keyboard_layout).

Dvorak was the first keyboard layout designed and optimized specifically for making typing easier and faster. 

In other words, Dvorak was the first **sane** keyboard layout for computers. Using the mechanical typewriter layout for computer keyboards is idiotic and insane. And not telling people who want to learn touch typing, not telling them the truth about the 150-year old mechanical typewriter layout is gross negligence. 

Although I suppose most people are just ignorant about those facts and never bother to do a basic research. They never even consider that there might be something wrong with the standard QUERTY layout. 

There were just 2 problems with the Dvorak layout for typing standard English texts: 

1) For reasons unknown to me the "i" key and the "u" key aren't positioned according to their frequency on the Dvorak layout.  
They have to be swapped because the letter "i" is much more common in English than the letter "u". The letter "i" is used around 7.5% of the time while the letter "u" is used [2.758%](https://en.wikipedia.org/wiki/Letter_frequency) of the time on average in written English. And in programming also: The letter "i" (often used as an iterator variable in loops etc.) is much more frequently used than "u".  
Therefore the letter "i" MUST be mapped ([see layout rationale](#layout-rationale)) to one of the "resting position" keys on the keyboard. The most logical way to correct this mistake by August Dvorak (the creator of the original Dvorak layout) is to swap the positions of the "u" and the "i" keys.

2) The numbers (on the number row) aren't positioned in accordance with their [frequency distribution](https://en.wikipedia.org/wiki/Benford%27s_law). So, the most frequently used numbers (1 and 0) are still [hard to reach](#layout-rationale) and thus harder to type on a Dvorak layout. Of course, numbers aren't used as often in normal English texts. This might have been the reason why August Dvorak had neglected the numbers row.

But numbers are used a lot in programming (as well as lots of special characters, brackets and braces). Which brings us to the next point: 

The standard Dvorak layout isn't designed for programming. 

This is why the [**Programmer Dvorak**](https://en.wikipedia.org/wiki/Dvorak_keyboard_layout#Programmer_Dvorak) version was developed. 

BUT:  
While Programmer Dvorak is much more programmer-friendly, it's still what I would call a "half-assed" effort.

### Why do something in a half-assed way if you can do it right?

I really don't have an answer to that question.  
It's always been a mystery to me why people do that.  
And it was painful for me to see that the Programmer Dvorak implementation was done so poorly.

So: 

The Dvorak-Booster keyboard layout is merely just my attempt to "do things right". 

**I hate doing things in a half-assed way.  
I like doing things right.** 


This is WHY I have developed this keyboard layout.

I named it Dvorak-Booster because Dvorak is the primary basis, the starting point and I fully embrace [the philosophy and the rationale of the Dvorak layout](https://en.wikipedia.org/wiki/Dvorak_keyboard_layout#Overview). I'm just adding a few bits and pieces to turn a very good keyboard layout into a GREAT one. Thus, I'm adding my name to it.

#### I just want a keyboard layout that's done RIGHT! 

That's all there's to it! 

Just a keyboard layout where everything's done right. 

No more, no less. 

It's a very simple idea. 

Why can't we have a keyboard layout...  
just one keyboard layout where everything is done right??? 

Why do we have to bend and break our fingers and break our wrists? 

Why can't we just have a keyboard layout that's really **super pleasant** for typing in English and for programming as well??

This is just BEYOND my understanding. 

And this is why I decided to get it done myself. 


## Layout Rationale

In this chapter, I'll detail the rationale (for those who are curious) but first let me tell you: 

### You DON'T need to buy a new keyboard!

And you certainly don't need to put any stickers 
on your existing keyboard. 

Switching a computer keyboard is done via software and **you'll never need to look at the keyboard** because typing without looking at the keyboard is the whole point of **touch typing**.

And the Dvorak-Booster keyboard layout is optimized for touch typing so well and makes touch typing so easy and pleasant that **you'll never want to look at the keyboard** when typing!

So, in case you've been a slave of the computer keyboard until now i.e. forced to look at the keyboard when typing using just one or two fingers, the Dvorak-Booster layout will liberate you from that slavery within 5 days from now and typing will become **unbelievably easy and fun** for you. 

You'll also make much fewer typos/errors because with each key stroke you'll immediately see what you are typing. 

So, those 5 days (that you'll invest to master the Dvorak-Booster layout now) will pay dividends for the rest of your life! And if you are coming from the standard Dvorak or from the Programmer Dvorak layout, you'll only need to invest 2 or 3 days to **master "antigravity" while typing**.


### What would be the ideal layout?

The ideal keyboard layout would be one where your 8 fingers are always resting on the home row and your thumbs are resting on the space bar. 

In other words, with the ideal keyboard layout you'd be able to type everything without ever lifting a finger! 

Of course, that's not feasible but if it was such keyboard layout would be ideal. 

OK. What's the next best thing that IS feasible? 

The next best option is a keyboard layout where 
you'd have to **move the fingers as little as possible to be able to type as much as possible**. And use the strongest fingers as much as possible when you have to move above or below the home row. 

Additionally, it's important to be able to type frequently used character combinations ([bigrams](https://en.wikipedia.org/wiki/Bigram) and [trigrams](https://en.wikipedia.org/wiki/Trigram) such as "the", "and" etc.) "fluently" i.e. on the home row, where the fingers rest and in a way where the hands are alternating rhythmically and the strongest fingers do most of the work. 

The numbers row is the hardest and the bottom row is the second hardest to reach. And the hardest to reach on the numbers row are the outer parts of that row (because you're using the weakest fingers there and the fingers have to travel the farthest to reach there). 

So, the least frequently used characters should be assigned/mapped to the hardest to reach keys.

This means:  
None of the special characters that a frequently used in programming can be mapped to the keys on the numbers row. **Not a single one!**  
The numbers row must be used for numbers only.

And the numbers on the numbers row need be arranged in a way that makes [the most frequently used numbers](https://en.wikipedia.org/wiki/Benford%27s_law) the easiest to reach. Bearing in mind that alternating between hands is desirable. 

That's why I arranged the numbers the way I did. 

The middle key on the numbers row is used for the number `dek` and the number `el` which are the two additional single digit numbers in the dozenal system. 

Huh? Dozenal system??... 

### What is the Dozenal System and why is it superior?

To understand that, you first need to answer the following question: 

**Why aren't we, humans, counting in binary??** 

After all, computers are counting and calculating complex maths problems just fine using only 2 digits ones and zeros. 

So, why don't we, humans, use that binary numeral system? Why do humans usually use the decimal system for counting and doing maths in every day life? Why mess around with 10 digits (0-9) if 2 digits (0 and 1) is all you need for counting and maths? 

That's because the decimal system is a lot easier and more practical in every day life **for humans**. That's why. 

Well, guess what? 

It turns out the **DOZENAL system** (please don't ever use the word "duodecimal" for that) is a lot easier and more practical still! 

For humans. In every day life. 

And while ignorant cavemen can only count up to 10 on two hands (10 in decimal is 1010 in binary by the way), a modern educated person can easily count up to a **dozen dozens** on the same two hands! 

A dozen dozens (better known as one gro - pronounced 'ɡroʊ' - and written as ´100) is 144 in decimal and 10010000 in binary. 

Long story short, it's a ***mathematical fact*** that the [dozenal system is vastly superior](https://en.wikipedia.org/wiki/Duodecimal) when compared to the decimal system.  
For humans.  
In every day life.  
While computers are doing just fine with the binary system.

So, the dozenal system IS the future. And unless you want to live in a cave for the rest of your life (and go back to eating raw meat and spend all day every day hunting for food just to survive), we will be using the dozenal system for counting in the future.  
No ifs, no buts.

The two additional single digit numbers that we use in the decimal system are the number ***dek*** and the number ***el***. 

So, it's zero, one, two, three, four, five, six, seven, eight, nine, dek, el, do (pronounced 'doʊ') or dozen. And as a civilized person, you use your thumb and the dozen [phalanges on the fingers](https://en.wikipedia.org/wiki/Phalanx_bone) of one hand to count to a dozen while using the thumb and the dozen phalanges of the other hand to keep track of the number of dozens you count. That way, counting up to a dozen dozens using two hands is as easy as raspberry pi and if you use your toes, you could go astronomical! :-) 

But the main advantage of the dozenal system over the decimal system is... well... I'll let you to figure that out on your own... 

Suffice to say, we'd already have a working warp drive by now if humans started counting in dozenal two centuries ago... 

Instead of spending one or two hours just to get from one end of a city like London or New York to another, you could zip to [Alpha Centauri](https://en.wikipedia.org/wiki/Alpha_Centauri) (which is 4.4 light-years away) in an afternoon. Imagine that! 

So, if you want to make sure that at least your kids (or grandkids) get to visit Alpha Centauri, you better start using the dozenal system NOW. Don't delay! You don't want your descendants to spit on your grave! 

Anyway, I'm temporarily borrowing the [Cyrillic capital letter HA with hook (&#1276;)](https://en.wiktionary.org/wiki/%D3%BC) for the number `dek` and the ~~Ukrainian capital letter IE (&#1028;)~~ [Latin capital letter open E (&#400;)](https://en.wiktionary.org/wiki/%C6%90) for the number `el`. This is because the dozenal system is not yet fully "fleshed out" but I do want to do my best to help bring it into mainstream use. 

For human use, the dozenal system is vastly superior to the decimal system and I hope that one day dozenal will become the main numeral system for every day use. The Dvorak-Booster keyboard layout can be viewed as a small step or tool contributing to the adoption of the dozenal system. 

The usage of the inverted numbers 2 and 3 for the numbers `dek` and `el` is wrong and should be completely abandoned. Whoever came up with the idea of using those inverted numbers for this purpose doesn't understand even the basics of persuasion. And you'll need a lot of persuasion if you seriously intend to establish a new numeral system in the world.  
Turning the numbers 2 and 3 upside down looks cheap and amateurish. It's instantly obvious that they are just upside down 2 and 3. We need something that looks like **NEW** numbers and something that looks good, not cheap.

Note: I'm not trying to persuade anyone here.  
The above 2 paragraphs are just a side note. 

Here's my draft for what the numbers `dek` and `el` should approximately look like in Arial font (compared to the other numbers): 

![Dozenal numbers](./images/dozenal-numbers-draft2.png)

The number el needs a designer's touch because that modified &#400; that I used in the above image isn't completely straight like the other numbers. There needs to be a normal, a bold and an italic version for both numbers (just like with all other numbers). The number el can't always be italic or "half italic".

Both numbers are extremely easy to write for handwriting, extremely easy to spell out and short i.e. "dek" and "el" and extremely easy to pronounce.

The number `dek` has a resemblance with the Roman numeral X (which is very much desirable because that association works in favor of acceptance). And the number `el` resembles a capital E (which makes it seem logical and easy to remember which once again works in favor of acceptance).

I'm not sure if I'd seen the symbol for `dek` somewhere before. The idea for that glyph just came to me after a nap. I tried to search hoping that this symbol already exists in unicode but couldn't find anything. It's super easy to write on paper because you don't have to lift the pen when writing it. It's just one easy movement (starting from top left).

**Update 9 August 2020:**

Just found that there are mathematical operators [&#8905;](https://en.wiktionary.org/wiki/%E2%8B%89) and [&#8906;](https://en.wiktionary.org/wiki/%E2%8B%8A) that look very similar to what I envision for `dek` except they would need to be turned upright and also would have to be increased in size to match the size of a regular digit. 

---

