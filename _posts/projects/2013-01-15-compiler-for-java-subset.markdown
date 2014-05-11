---
layout: project
title:  "Projet Génie Logiciel: a compiler for Deca, a subset of Java"
period: January 2013
categories: projects school
lang: en
---

All Ensimag engineers have at least one project in common: the "Software
Engineering Project", in French *Projet Génie Logiciel*, which consists of
three dedicated weeks of work in teams of five students. Goal: build a
full-blown compiler for a small object-oriented language. The target language
is jokingly called *Deca*, and looks like a subset of Java. Our compiler,
`decac`, must be written in Ada, and should output assembly code targeted at a
small virtual machine, built on purpose for this project.

Every good project should have an ASCII art banner. (Unfortunately that's all I
can put here, school policy forbids giving away project sources).
{:.margin.note}

                           /
                           \
                            \        \
                            |        /
                            /       /
                   ||      /       /       ||
                   ||______________________||______
                   ||  __   ___  __   ___  ||  __  \
                   || |  \ |    /  \ /   \ || /  \ |
                   || |  | |_   |    |___| || |    |
                   || |  | |    |    |   | || |    |
                   || |__/ |___ \__/ |   | || \__/ |
                   ||______________________||______/
                   \\     _                //
                    \\   |   |  |_| |_|   //
                     \\  |_| |_   |   |  //
                      \\________________//
                       

During this project, **I learned how to write Flex rules, how to build a syntax
tree with Yacc and to decorate it**. For this specific part, I had to implement
and to test the rules of float propagation in numerical computations. I also
wrote the data structure that took track of scope contexts during the parsing
of class and method declarations. 

I also learned how to generate assembly code that implemented **dynamic linking
of methods** and used at most an arbitrary number of registers. Even if I did not
code this part, I helped debugging it.

But the most interesting part for me was the **implementation of the included
math functions**, proposed in a way similar to Java's `Math` utility class. We
had to provide sine, cosine, tangent and square root. This part was both
interesting and challenging, because we decided to write the math class in Deca
itself.  It meant we had to compile our compiler without support for the math
class in a first time, then compile our math class to bytecode using our
compiler, and then recompile our compiler including support for our math class.

In the end, our compiler was considered by the professors to be of very good
quality (except for a few bugs in lexical analysis - bad handling of case
sensibility) and especially, our math class was pointed out as **one of the most
precise implementations**.



