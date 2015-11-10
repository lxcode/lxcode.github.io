---
layout: post
title: More useful console apps
---

On my software (<http://grumplicio.us/software.html>) page, I mention a few
console applications that I use regularly, like tmux, mutt, w3m, cmus, and
calcurse. I've recently discovered a couple more applications that are worth
knowing about if you prefer to do most of your work in a terminal-based
environment.

Taskwarrior
-----------

<http://taskwarrior.org/projects/show/taskwarrior>

On the face of it, this project appears to be absurd: "It's a list of TODOs. I
already have a list of TODOs", you might say. However, after giving it a shot,
I've found it to be actually quite useful. The reasons why I like it better
than my previous flat file approach are:

    * Easy tagging and filtering. I primarily use +home and +work to keep my
      full task list easily filterable.

    * Automatic urgency calculation. Taskwarrior is smart about figuring out
      which stuff you actually need to work on next --- it looks at the age of
      the task, your chosen priority, the due date and other metrics to
      determine how tasks are sorted. I've found this to be quite useful.

    * It handles things like projects, dependencies, notes and annotations
      attached to tasks. It knows that your blocking dependencies have higher
      priority.

    * Lots of shortcuts. I just have to say that something is due at "eom", and
      it'll do the right thing.

    * It keeps things together. Tasks are easy to synchronize between a remote
      server and your local machine, using the "merge" command. 

Anyway, it's worth a try to see if it works for you. The only thing that it
really lacks is a modern way to integrate to calendaring applications, but I'm
sure that will come before too long.


Newsbeuter
----------

<http://newsbeuter.org>

On OS X, there's not really a decent non-commercial RSS reader available,
unless you want to run Thunderbird all the time. I'd been using Liferea under
X, but it wasn't a terribly great solution. Newsbeuter aspires to be the mutt
of RSS readers, and it pretty much is. You define your URLs in a simple flat
file, spawn the reader, and it will handle updating them, downloading
summaries, and plenty of other stuff I'll never use. From the summary view, you
can have the actual article links launched in an external browser --- I use
w3m, as I run it under tmux on a remote server. That approach also means that
your read and unread items are pretty well tracked regardless of where I am. 

