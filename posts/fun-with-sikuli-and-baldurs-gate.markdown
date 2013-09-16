<!--
.. link:
.. description:
.. tags: Sikuli, Github, Games, python
.. date: 2013/09/16 00:55:24
.. title: Fun with Sikuli and Baldur's Gate
.. slug: fun-with-sikuli-and-baldurs-gate
-->

A few months ago I was playing [Baldur's Gate: Enhanced Edition (BGEE)](http://www.baldursgate.com), and going through the character creation process.  The game chooses the character's initial statistics by simulated random dice rolls.  You can re-distribute points between different attributes as you desire, but you can only increase the total number of points by re-rolling.  You can re-roll as many times as you want, hoping to get a higher total number of points.  You can also "store" and "recall" a single roll.

The lazy programmer in me saw this as an a task begging for automation.

I spent the next several hours developing a [Sikuli](http://sikuli.org) script which automates the process of re-rolling until a desired total roll is reached.  I've finally gotten around to cleaning up the code and releasing it on github as [BGEE_Sikuli_auto_roller](https://github.com/mrabbitt/BGEE_Sikuli_auto_roller).

Here's a video demo (painfully edited in iMovie) of `BGEE_Sikuli_auto_roller` in action:

<iframe width="420" height="315" src="//www.youtube.com/embed/K-0nRvz3z4I" frameborder="0" allowfullscreen></iframe>

Happy dungeon/code hacking!
