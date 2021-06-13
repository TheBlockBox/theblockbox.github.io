---
category: huntersnightmare
author: RedstoneTim
---
![Anakin and Padmé meme: RedstoneTim: "I'm going to change the werewolf" TheBlockBox community: "For the better, right?" RedstoneTim: "" TheBlockBox community: "For the better, right?"](/assets/images/blog/werewolf_for_the_better.jpg)

Hey, so you remember how I promised you'd see "some more interesting stuff" next time?

So well, there is some new and interesting stuff...  
... except it's probably not what you were expecting to see.

Okay, so let me elaborate first:  
Quarantine measures have been lifted and school has fully opened again,
so I didn't exactly have much time to code.
On top of this, as you might have seen from the title, we have yet again
been troubled with *a few* nasty bugs which required a while to fix.  
A long while.

So firstly, the model.  
Two weeks ago, I assumed that the model did not work as intended
because I'd modified RebelT's original code quite a lot,
mostly to make it "more modern" or whatever I was thinking at the time.  
Therefore, one would expect that this was the cause of the problem
and that it could easily be fixed by just using the source files
with only the necessary changes applied.

![Minecraft "Werewolf" sitting in water; the model is too small and looks similar to a bear/beaver](/assets/images/blog/bear_beaver_werewolf.png)  
*It's a Bear... It's a Beaver... It's a ... Werewolf???*

I... I mean, it doesn't look as gruesome as last time at least!

So yep, after deciding to postpone that for later,
I tried out the transformation. Surely that would work!  
Yes, no, it did not.  
Basically, transforming did indeed work, except that the entity data was not being saved
(this means that when the werewolf transforms back,
the entity will just be a villager with the default data, including the human transformation).
After [confirming that by initiating a small concert](https://youtu.be/xOyVizMo3zI),
I then found what I believed to be the cause of the issue:
Two keys with the same name, which meant that one of the two values always overrode the other one.

So now, it works, right?

*No.*

I got a `StackOverflowError` and then attempted to fix this by mashing my brain for a good few hours.  
In case you're interested, [here's a rundown of the problem](https://pastebin.com/raw/bwYZtCDT).

Finally, after this was out of the way, I tested the fur color,
which is supposed to be different depending on the spawn biome.  
*But no, not even that wanted to work correctly.*  
I was very close to believing that it was Minecraft's fault
that every biome had a temperature of 0.8 and even the "forest biome" did not have the category "forest", but "plains".  
But then it dawned on me: The entity's position had not yet been set when the fur color was decided.
Therefore, a rewrite was required.  
Please don't get me wrong, the fix was by no means *big*,
but the impact it had on my self-confidence definitely was.

So, as a last resort for receiving at least minimal satisfaction of having accomplished *something*,
I tested whether the other fur colors worked as well and *voilà*:

![The werewolf model with the black and magenta Minecraft error texture](/assets/images/blog/black_magenta_werewolf.png)  
*Reenactment of the sight I was greeted with. (Reenactment because apparently, it works now?)*

***Rage quit*** (and dinner)