# Programming without the Programming

Ashley M. Clark


Hello! My name is Ashley and I like to anthropomorphize computer programs. The Women Writers 
Project staff calls them “robots,” like they’re tiny metal beings that interface with our files. 
It’s an apt metaphor, because when you write programs or scripts, your “robots” will generally do 
exactly what you tell them to do, and no more. If all goes well, they accomplish your task without 
complaining. But you have to be careful telling your robot what to do. If you’re too vague, or the 
program runs into something unexpected, or you haven't thought out the implications of your 
instructions... Well, the robot will still try to do what you’ve told it to do, but you might not 
like the results.

    https://tinyurl.com/codingWithoutTheCoding2019

Before we get into things, here’s a short link to a Google Drive folder with my slides, and an 
annotated copy of the script I’m using. The script document is editable by anyone with the link. If 
you’re so inclined, feel free to make notes or add comments. I will also be taking pictures of 
anything that ends up on the whiteboard; those will go into the Drive folder as well.

While I have a script, you should absolutely give your hand a wave if you have any questions. Also, 
if you haven’t had a chance yet, please take an index card and write what you would like to be 
called. The link to the Drive folder is on the back for you to take home.

Okay, ready?


## Let’s be robots!

We aren’t actually going to build any robots today. Instead, we’re going to write sets of 
instructions for ourselves pretending to be robots. I’ll cover some common structures and concepts 
that will help you if/when you write your own code. You won’t learn a programming language here, 
but hopefully you’ll learn the basics of how to use one!

Let’s leap in with a dead-simple “program” I wrote.

    SAY "Hello, world!"

And now, pretending that I’m a robot: _“Hello, world!”_

This instruction is an example of “structured natural language”, or “pseudocode”. Pseudocode is 
used in computer science as a way to sketch out the logistics of a program, without getting bogged 
down in the minutiae of any particular programming language. Conveniently, it’s also easy to read 
and write, no matter how much experience with programming you have!

Let’s look at the information we can take from our first program here. We have an _action_: “SAY”. 
This particular action is kinda useless without something _to_ say, and so we also have a string of 
text to use during the action.

There’s one more thing. Because the instruction takes the form of an imperative sentence, the actor 
is the person being commanded. In more traditional programs, the actor is what I’ve been calling a 
robot, with one distinction. The “robot” is _not_ actually the code itself, but the machine that 
takes that code and executes it.

In this example, I was the actor, but it probably could have been anyone here. The instruction is 
general enough; a lot of people could execute this pseudocode (if social conventions didn’t keep 
you from doing it while I’m speaking!).

Which brings us to our next program. Can I have a volunteer to play robot?

    SAY "Hello, Megan!"

Does anyone have any questions or comments about this program?

[ discuss ]

That’s how we can read pseudocode with our programmer hats on. In its simplest form, pseudocode is 
just series of instructions, or actions that should occur one right after another. Writing one of 
these programs is like giving directions, or writing out a recipe.

Let’s brainstorm some routines we could use for example programs.

[ write these on whiteboard, discuss ]

Okay, something else I’d like to point out: As we’re doing these, we’re taking on three roles. We 
are playing the robots, and writing the programs, but we’re also serving as the data. _Because_ we 
are human, we might be considered data, but we’re _complex structures_ of data. We can even 
retrieve or communicate some of it! For example, I as a person know what I prefer to be called. 
[ hold up name card ]

When we put on our robot hats, we have our own human data at our fingertips. We can find out the 
names of the people we’re sitting next to, and we can incorporate that data into our programs. 
Here’s an example.

    SET addressee $name TO "Megan"
    SAY "Hello, $name!"

Let’s take this line by line. So, I’m a robot, and I’ve just been handed this program to execute. I 
read the first line, which has an example of a “variable declaration”. For this first instruction, 
I set some text as the value of a variable called “name”. Then I can use that variable as a 
placeholder, or a symbol, when I execute the second instruction.

Running the program all at once: _“Hello, Megan!”_

If this concept seems familiar, it probably is. In mathematics, variables are used to hold numeric 
data so that you can solve for _y_, or figure out the length of a triangle’s third side, or 
determine the radius of a circle.

| Math            | Pseudocode                    |
| ---             | ---                           |
| _l_ = 10        | `SET $length TO 10`           |
| _w_ = 35        | `SET $width TO 35`            |
| _A_ = _l_ * _w_ | `CALCULATE $length * $width`  |

For example, the area of a rectangle can be found by multiplying its length by its width. The 
equation on the left is how a teacher might expect you to start showing your work. Because of the 
variables _l_ and _w_, it’s easy to see the formula underpinning the calculation, _and_ it’s easy 
to understand how the result might change if the value of _l_ or _w_ were to change.

Does anyone have any questions?

[ optional: walk through example from previous suggestions ]

Up until this point, we’ve been using data that’s been “hard-coded” into the program. Because the 
input data is the same every time, the _results_ will be the same every time, no matter who runs 
the program.

Instead, we can rely on our environment to provide the input, and use variables as placeholders for 
some unknown value.

Anyone want to play robot?

[ hand program to volunteer, flip slide ]

    FIND $neighborOnRight
    GET $name of $neighborOnRight
    SAY "Hello, $name!"

Here we’re starting to use programming as a tool for exploration and inquiry. We _identify_ the 
person who is on our right; we _retrieve_ a specific attribute from them; and then we _do_ 
something with that information.

What do you think would happen if someone ran this program and there wasn’t anyone on their right?

[ discuss/try it ]

    IF there is someone on your right THEN
      FIND $neighborOnRight
      GET $name of $neighborOnRight
      SAY "Hello, $name!"
    ELSE
      SET $name TO "world"
      SAY "Hello, $name!"
    END-IF

Here’s an alternative program. Let’s go line by line. First, I have a test to determine whether or 
not there is someone on my right. That is true for me, so I proceed to identify my neighbor and 
greet them. The other condition, marked by the ELSE, does not apply to me, so now I’m done. What 
happens if there _isn’t_ someone on my right? [ ... ]

In programming, this construct, or pattern of code is usually called an “if statement”, or a 
“conditional”. It’s like drawing out branches in a flowchart: the robot will follow the first path 
that applies. Among other things, the IF statement can let you perform tests on the input data 
_before_ it’s used, letting your robot recover from unforeseen use cases, or just plain bad data.

[ optional: use a suggestion from earlier ]

You might have noticed that there’s some repetition in this slide, what with the “Hello, $name!”. 
It’s not a big deal because the program is so short. However, the longer the program, the more 
necessary it becomes to reduce repetition. The more times you have to write out the same 
instructions, the more likely it is that there will be small variations, like mistakes or typoes. 
And even if you can reduce errors by copy-pasting, if you decide that the code snippet needs to 
change in one place, you will have to change it _everywhere_, or let the copies go out of sync. Too 
much repetition makes it harder to maintain code.

_That_ said: repetition is _very_ helpful when writing pseudocode! Pseudocode is useful for letting 
you build out the structure of a program in your head. It’s absolutely fine to let yourself step 
through a process by repeating instructions. You can always abstract steps out later, just like 
we’re going to do now.

    DEFINE routine PerformGreeting AS
      GET $name
      SAY "Hello, $name!"
    END-DEFINE

Here’s an example of defining a subroutine for your pseudocode. We’re not actually running these 
instructions, but declaring that they are a set, and assigning the set a name.

Then we can use the routine’s name “PerformGreeting” as a shortcut to the instructions for 
expressing the greeting. Saves us a lot of writing!

    DEFINE routine PerformGreeting AS
      GET $name
      SAY "Hello, $name!"
    END-DEFINE
    
    SET $name TO "Ashley"
    PerformGreeting

Anyone want to try running this? [ … ]

Note that the routine assumes that the value of the variable $name has been set beforehand. 
However, we can build in our IF statement test from earlier. This way, we don’t have to check $name 
every time we call PerformGreeting.

    DEFINE routine PerformGreeting AS
      GET $name
      IF there is not a value for $name THEN
        SET $name TO "world"
      END-IF
      SAY "Hello, $name!"
    END-DEFINE
    
    PerformGreeting

Let’s do that. In this variation, PerformGreeting still tries to find a pre-set variable called 
$name. But instead of continuing straight to the greeting, there’s a test. When it is true that 
$name has not been set, PerformGreeting will set the variable itself, using the text string "world" 
as its default.

Does anyone have any questions?

[ … ]

    FIND group of $fellowParticipants
    FOR each $person IN $fellowParticipants
      GET $name of $person
      PerformGreeting
    END-FOR

Okay. There’s one more programming construct I’d like to show you today: a “for loop”.

First, I use a variable $fellowParticipants as a symbol for all of you. Then I enter the FOR loop. 
For each of you, I will get your name, and then call PerformGreeting. When there are no more 
$fellowParticipants, I will stop.

Anyone want to try running this? We can use a smaller group for $fellowParticipants.

[ if not, I’ll do it ]

## Where to go from here

Congratulations! You have just worked through the programming exercise “Hello, world”. 
Traditionally, this is one of the first things people write when they begin learning a new 
programming language. The goal is simple—just output the words “Hello, world” to the screen—but as 
you can see, you can build on this program as you learn more about the language.

If you want to pick up a programming language, I encourage you to use this or some other exercise 
as a way to explore the features of the language. Play with it! Set yourself small, accomplishable 
goals. Challenge yourself with “what if”s. Skim through the documentation; Google any errors; talk 
out the problem with someone. Write pseudocode!

Speaking of pseudocode, I’ve intentionally used an extremely structured syntax today. I chose to do 
that for the sake of showing the patterns that crop up repeatedly in programming. Unlike actual 
programming languages, pseudocode has all the limits of a natural language—which is to say, _none_. 
Pseudocode does not have to be good, or consistent in how things are expressed. It does not have to 
be perfect on the first try. If something doesn’t work, rewrite it later.

This workshop is a pretty unconventional way of introducing the topic of programming. If you’re 
looking for a more traditional experience, I have a list of websites and books I consulted when 
writing this script. You’ll find it in the Drive folder.

## Questions? <br />Examples!

That’s all I have! We can use the rest of the time to do some group programming, and answer any 
questions you all have. But first, thank you to Megan Barney for her persistence and enthusiasm in 
getting me here. And thank you all so much for being here. I really hope you had fun!
