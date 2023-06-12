---
layout:       post
title:        "From Start to Finish: A Bash on z/OS Journey"
author:       "Igor Todorovski"
header-style: text
catalog:      true
tags:
    - z/OS
    - Bash
    - Open Source
---

> Bash on z/OS
![image](https://upload.wikimedia.org/wikipedia/commons/8/82/Gnu-bash-logo.svg)

During my 15 year career at IBM, my biggest gripe has been that there hasn't been a supported version of Bash. Sometime in the 2000s, IBM ported Bash, and then another vendor also ported Bash and made it available, but the changes were keep proprietiary and never upstream.

So as part of the z/OS Open Tools initiative, I decided to give a try and rather than keeping it closed source, I wanted to contribute it back.

I'll discuss my journey into Bash and also disclose a few things I learned along the way.

First, what is Bash? Well Bash is short for "Bourne-Again SHell," is a popular command-line interface and scripting language used primarily in Unix-based systems.

Here are some reasons why I like Bash over the default /bin/sh shell on z/OS:

* Tab completion: Bash supports tab completion, which means you can type the first few letters of a command or filename, and then press the Tab key to automatically complete it. This feature can help you save time and reduce typing errors.

* Scripting: Bash is a powerful scripting language that allows you to automate complex tasks and perform operations that are not possible with the Bourne shell. Bash scripts can use variables, loops, conditions, and other programming constructs to perform a wide range of tasks.

* Compatibility: Bash is compatible with the Bourne shell, which means that scripts written for the Bourne shell can run in Bash without modification. This makes it easy to migrate existing scripts to Bash without having to rewrite them.

## Porting Bash to z/OS
Porting Bash to z/OS didn't require as many patches to get it to build as I initially anticipated. In fact, most of the patches were for the tests: https://github.com/ZOSOpenTools/bashport/tree/main/patches.

With the latest Clang compiler on z/OS and by leveraging the zoslib library, we were able to minimize the amount of chagnes required to build Bash on z/OS.

## Contributing the changes back to the Bash community

### Step 1: Identify the community and their contribution policies
After a bit of google searching, I was able to find the Bash community, located here: https://savannah.gnu.org/projects/bash/. Then, I found that Bash had a mailing list https://savannah.gnu.org/mail/?group=bash. 


### Step 2: Introduce the platform and enquire best practices for contributing back.
I decided to post my question about upstreaming to https://lists.gnu.org/archive/html/bug-bash/2023-05/msg00057.html. Fortuantely, the project maintainer, Chet Ramey, quicky responded with helpful advice. 

### Step 3: Clean up the patches
I continued engaging with Chet via direct email and used his guidance to clean up the patches which I had placed 

