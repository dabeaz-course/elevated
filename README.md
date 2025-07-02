# Elevated - The Project

Author: David Beazley (https://www.dabeaz.com)  
Source: https://github.com/dabeaz-course/elevated

Copyright (C) 2025

A somewhat obscure fact about Rust is that an elevator figures into
its origin story.  This [article](https://www.technologyreview.com/2023/02/14/1067869/rust-worlds-fastest-growing-programming-language/) has more detail.  However, I'm struck 
by the following quote from Graydon Hoare:

> "It’s ridiculous, that we computer people couldn’t even make an
> *elevator* that works without crashing!"

That actually sounds like a challenge. Maybe even a throwdown! How
hard could it possibly be to code an elevator?!?  An elevator goes up
and down. Doors open and close.  Maybe it's just a slightly more
advanced version of a toaster.

## Well, How About It "Computer Person"?

The premise of this project is pretty basic, I provide to you a
simulator of low-level elevator hardware in the form of
[Lifty](https://github.com/dabeaz/lifty).  Your task is to write the
control software that makes it do what elevators do--without crashing.

Beyond that, there are very few ground rules.  Although the [Lifty](https://github.com/dabeaz/lifty)
simulator is written in Rust, you can attempt the project in
programming language that you wish.  You can employ any programming
technique that you happen to know about.  At the end of the day, 
your solution will either work like an actual elevator or we'll all
be taking the stairs.

## A Few Desirable Things

In devising a solution, there are a variety of things that
a reasonable software engineer might want to see:

* Code that is easy to read, understand, and debug.
* Appropriate use of abstraction.
* Some kind of testing strategy.
* A coding approach that can adapt to meet new requirements.

Basically, you'd want to write code like your boss is watching--or
maybe a future employer.  Besides, nobody wants to ride on a hack
elevator.

## Approach

With no further guidance, it can be hard to know how to start on
a project like this.  If you want to code it on "beast mode", stop
reading now and get to coding already.

However, if you're looking for a bit more structure, I recommend
tackling the problem in levels as briefly described below.

### Level 1 : Go Somewhere

Using any programming technique you can summon, make the [Lifty](https://github.com/dabeaz/lifty)
simulator do nothing more than the following:

* Issue a reset.
* Wait for a panel button to be pressed.
* Move up to the requested floor.
* Stop and open the door.
* Wait 10 seconds.
* Close the door.

That's it. 

### Level 2 : Hardware Abstraction

In implementing level 1, you probably wrote a lot of code that 
was directly related to the [Lifty](https://github.com/dabeaz/lifty) simulator.   However, what if
you wanted to perform the same tasks on a real elevator?  Or
what if you wanted to make a mock elevator for testing?   To do
that, you probably need to think about an abstraction layer.

Thus, your task is to make some kind of elevator hardware abstraction
layer.  When you're done, modify your solution to level 1 to use it.

### Level 3 : Problem Abstraction and State Machines

What do elevators do anyways?   Spend some time thinking about
the overall execution model of an elevator.  You'll probably
conclude that they operate as a kind of state machine.  Yes,
but at what level of abstraction?

Try to devise some programming abstractions that live in the
high-level problem domain of elevators.  These should allow you to
reason about the overall elevator algorithm without getting too bogged
down in the minutae of low-level hardware details.  

This is also a good time to start thinking about testing.  Does your
approach allow tests to be written?  Can you test parts of your
elevator algorithm without the simulator being attached to it?

When you're done, you should be able to express the basic
problem of level 1 at a high level of abstraction, connect it
to the hardware abstraction layer, and run the [Lifty](https://github.com/dabeaz/lifty) simulator
as before.

### Level 4 : Testing, Verification, and Futher Implementation

So far, you have only coded one basic elevator scenario. However, by
the time you've finished level 3, you should be thinking about how to
expand your work to include more elevator behavior associated with
the standard "elevator algorithm." 

However, what is your overall plan for verifying the correct behavior
of your elevator implementation?  Do you actually understand how the
elevator algorithm works?  Can you write down your understanding in
words?  Can you write your words in some kind of more formal
specification language (e.g., as mathematical assertions)?  Is there a
way for you to verify conformance to the specification in your code?

With your specification of correct elevator behavior in hand, you
should attempt to code the "rest" of the elevator algorithm to the best
of your ability.  Make sure it passes tests. Make sure you can 
connect it to the hardware abstraction layer and run it on [Lifty](https://github.com/dabeaz/lifty). 
Be forewarned--it's probably going to get pretty messy.  However,
messy as it might be, there's a lot to be said for "working."

### Level 5 : Design

Completion of level 4 will probably reveal a lot of things that you'll
want to change about your code.  You might even want to rewrite
everything. Thus, this last level is about refactoring the code to fix
various issues related to code organization, modularity, missing
features, and other such concerns.  This is pretty open-ended, but
here are some possible topics to consider:

* Are there any strategies for simplifying the implementation?
* Can specific design patterns help?
* Is your solution easily extensible to handling new problem requirements?
* Is the code organized in sensible way (files, directories, tests, etc.)
* Have you written any documentation and/or comments?
* Could you show this code to someone else without any cringing being involved?

And last, but not least...

* Does it make [Lifty](https://github.com/dabeaz/lifty) work like a real elevator without crashing?

## Parting Thoughts

Elevators are a lot more complicated than they look.  In fact, many 
job seekers have probably been defeated by some kind of question
related to elevators.  

The elevator algorithm even proved formidable for [Donald
Knuth](https://en.wikipedia.org/wiki/Donald_Knuth) who featured it
as an example in "The Art of Computer Programming, Volume 1." He writes:

> It is perhaps significant to note that although the author had used
> the elevator system for years and thought he knew it well, it wasn’t
> until he attempted to write this section that he realized there were
> quite a few facts about the elevator’s system of choosing directions
> that he did not know. He went back to experiment with the elevator
> six separate times, each time believing he had finally achieved a
> complete understanding of its modus operandi. (Now he is reluctant
> to ride it for fear that some new facet of its operation will
> appear, contradicting the algorithms given.) We often fail to
> realize how little we know about a thing until we attempt to
> simulate it on a computer.  ("The Art of Computer Programming", Volume 1, 3rd Ed., pg. 298).

Personally, I love the challenge of working on this problem because I
like to think about the final deliverable.  If someone came to me to
work on this problem, what would I actually give back to them?  As a
matter of personal pride, I'd probably want to do better than handing
them a giant bag of hacks and an assurance that "it works on my
elevator."

## Questions and Answers

**Q: Do you provide any solution code here?**

A: I do not.  If you want to watch me fail to implement an elevator,
you'll have to [take a class](https://dabeaz.com/courses.html).

**Q: Do you provide any tests?**

A: No. Figuring out how an elevator is supposed to work is part
of the project challenge.

**Q: Can you give me any hints?**

A: Sure.  Open a discussion topic.

**Q: I'm an instructor.  Do you mind if I use this project?**

A: No. Go for it! Everyone will probably learn a lot!  A link
back here is always appreciated. 
