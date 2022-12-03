This page has a number of tips, common pitfalls, and other things that may be
useful as you do the labs in this course.

## Before putting your name on the queue...
As the labs get more and more complicated, queue times will get longer and
longer. To be as efficient as possible, please make sure you address the
following points **before** you enter the queue. That way you can avoid having
to wait a long time for an extremely simple solution, and avoid exasperating
your TAs.

#### Did *you* try diagnosing the problem?
Before asking for help, it is both more valuable for your learning as well as
better use of your time and your TA's time if you try to diagnose the issue,
whether it's with the tools, your code, etc. If you can tell us what you tried,
and what you suspect is going on, then we can dive right in to helping you
without starting from Square 1. It's frustrating for both parties when the
problem is, "It doesn't work."

#### Did you try the waveform viewer?
This cannot be stressed enough. Print statements can only get you so far with
complex systems. If you haven't tried opening the waveform viewer for debugging
then **please do so**. Extremely obvious errors like off-by-one cycle bugs can
be spotted immediately with even the slightest use of the waveform.

#### Did you read the error messages?
Error messages are (for the most part) super helpful. That's what they're there
for. More often than not you can figure out what's wrong by reading them (go
figure). Of course if the error doesn't make sense to you then by all means ask.

#### Did you add all of the files needed?
When compiling with VCS, ensure that all of the files with your module
descriptions are included.

#### Is the name of the top-level entity the same as your SV module?
It should have the same name as whatever you defined your top level module to
be. More often than not this would be your `ChipInterface` module.

#### Did you select the right device in Quartus?
Make sure the device for your Quartus project is the **Cyclone IV E** family,
device number **EP4CE115F29C7**.

#### Did you import pin assignments?
Grab the `DE2_115.qsf` file from Canvas, then click Assignments &rarr; 
Import Assignments and select this file.

## General tips for success in lab
1. **Read the handout**: There are a lot of details and nuances that may be
   easily missed in the first skim. Make sure you understand *everything* that
   is expected of you to avoid pains down the road.
2. **READ the handout**: Lots of questions have their answers in the handout.
3. **Read the HANDOUT**: You get the point.
4. **Start early**: The later labs simply cannot be done in the (relatively)
   short three hours for your lab section. You are expected to meet with your
   partner outside of lab to do a not-insignificant portion of it. Which brings
   us to...
5. **Communicate with your partner**: Figure out things like when to meet, what
   tasks to do (should you wish to divide & conquer), what the handout means,
   etc. *If your partner isn't the first to contact you, then you should be the
   first to contact them*.
6. **Don't stop at what's due for that day**: Some labs will have parts of the
   lab due at different dates. You may notice that not all parts are created
   equal, and some will give you *significantly* more trouble than others. If
   you finish a part early and still have time in lab, **don't leave early**.
   Get as far as you can. Trust me, your future self will thank you.
7. **Try to understand what's going on**: You may find that you "lucked out" and
   found a partner that can do the whole lab. You may be tempted to let them
   carry you through it. Don't fall for that temptation. You're here to *learn*
   so if there's something you don't understand make sure to *ask*.
