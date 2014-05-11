---
layout: project
title:  "Various C system-oriented projects"
period: 2012 - 2013
categories: projects school
lang: en
---

A memory allocator, a preemptive process scheduler, synchronization exercises
using mutexes and semaphores, a simplified UNIX shell... Multiple courses
proposed small projects around the C programming language and low-level
programming.

### Simplified shell

Here is an example `ensishell` session, showing redirections, background
processes and time limits. This project was a good opportunity to discover the
standard programming interfaces for pipes, file descriptors and signal
handling.

    $ ./ensishell
    Terminaison asynchrone (sec. 5.4) ; Limitations du temps de calcul (sec. 5.6)
    ensishell>ls
    ensishell.c  présentation_alloc.pdf  readcmd.c	      testshell.expect
    jobs.c	     présentation.odp	     readcmd.h	      trap_sig.sh
    jobs.h	     présentation.pdf	     Shell_print.pdf
    Makefile     présentation_shell.pdf  Sujet_shell.pdf
    ensishell>ls | grep ".c$"
    ensishell.c
    jobs.c
    readcmd.c
    ensishell>
    ensishell>sleep 10 &
    background (&)
    ensishell>liste_ps
    7747	sleep 10 &
    ensishell># Wait 10 seconds
    ensishell: Background process 7747 terminated.
    ensishell>ulimit 1
    ensishell>yes >/dev/null
    out: /dev/null
    # 1 second later, process is terminated
    ensishell>
{:.fullwidth}

### Toy operating system

I remember calculating memory addresses by hand and casting them into
pointers to read and write the contents.
{:.margin.note}

The operating system project, on the other hand, was designed to make us
discover low-level memory manipulation, processor-specific operations such as
registering an interruption handler, saving all register contents before
performing a context switch, and so on. I ended with a process scheduler that
used interruptions to preemptively switch between processes, and time quanta to
know which one to choose. Processes could sleep for some time and be awakened
automatically, and the scheduler could be configured either to do as little
context switches as possible, either to be more interactive by interleaving
active processes.

