---
category: huntersnightmare
author: RedstoneTim
---
Say, what time is it?  
It's ~~[Howdy Doody Time](https://youtu.be/W1USHuud5i8)~~ time for another blog post!  
Alrighty, now let's see what TheBlockBox has worked on in the last two weeks, shall we?

As you can see from the title, we had issues with a few uninvited "guests" in our code.  
The very attentive readers among you might have already spotted
one of them in the [last post](https://theblockbox.github.io/major-advances/) -
the red cross in the [commits](/assets/images/blog/commits.png).
This basically meant that the mod couldn't even be played, so I set off to fix this:  
Firstly, I found out that there was an issue with the mixins,
which was fixed pretty quickly.  
It basically went like this:

![Akshay Kumar meme where he swaps "CallbackInfo info" and "CompoundTag tag" inside the writeCustomDataToTag method](/assets/images/blog/mixin_parameter_swap.png)

Now, after this was finished, I found myself confronted with yet another problem:
```
[Worker-Main-15/WARN] (Minecraft) Failed to create mob
java.lang.IllegalArgumentException: Duplicate id value for 14!
```
You're wondering what this is supposed to mean? Yeah, I did, too.  
So, I tried to resolve this issue and did fix it, however...

![The colorful remains of a fly on a white wall](/assets/images/blog/fly_on_wall.jpg)

*... when you get rid of one issue, the next one will already be staring right at you.* (And yes, this is *my* wall.)

Finally, I also [found a solution for this](https://pastebin.com/raw/XFR2hgai) and from now on -
if you disregard the fact that IntelliJ Idea decided to crash at least five times -
everything went really smoothly!

As mentioned last time, I continued working on the werewolf infection system and finished the most important parts of it
while also introducing the `MorphableTransformation` interface, which turned out to be completely useless!

We also decided to port the commands from the old versions by rewriting them in [Brigadier](https://github.com/Mojang/brigadier),
so you now get to use the cool autocomplete feature
for `/huntersnightmare <target> [<transformation>]`, which retrieves or changes someone's transformation,
or `/huntersnightmare`, which prints out basic mod information.

![Command outputs and example of autocompletion](/assets/images/blog/commands.png)

*Btw, if anyone has any ideas for making the information command look fancier or more informative, please let us know on our [Discord](https://discord.gg/ttsaFnH)!*

Lastly, as promised, we also started work on the config!  
Although it is currently still being sketched out,
we've mostly decided on using JSON with external documentation (which will most likely be published on this website).  
This means that there will sadly be no easy to read YAML with inline comments,
but also no extra dependency, the file format most Minecraft players are familiar with
and a (hopefully) much nicer looking documentation!

And actually, this is already the end of this post!
We're looking forward to seeing you again on the 30th, so until then, bye!