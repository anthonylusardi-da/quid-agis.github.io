---
author: quidagis
---
I have been working on writing a template generator all this week, and the current Technology stack is:

1. [Whiptail](https://linux.die.net/man/1/whiptail)
2. [Bash](https://www.gnu.org/software/bash/)
3. [Vim](https://www.vim.org/)
4. [Nano]( https://www.nano-editor.org/)
5. [Ubuntu](https://ubuntu.com/)

My system is fully configured and capable of using the excellent Microsoft [VS Code Editor](https://code.visualstudio.com/),
complete with the necessary Haskell, Daml, Development code snippets and syntax highlighting. However, since I 
first struggled with installing, or attempting to install, RedHat Linux 7.0 in late 2000, I have had a fascination with
the [Command Line Interface](https://en.wikipedia.org/wiki/Command-line_interface) (CLI).

Quite often with those Linuxes in that era, you could not easily get networking functional as the Graphical User
Interface (GUI) were hit-and-miss, often you *had* to learn (Or as I say 'suffer') using the CLI, enabling modules,
probing modules, compiling kernels for non-supported hardware. Frankly at times it was a nightmare.

Regardless, now I have a fondness for using the various Linux OS that I have, on various architectures; x86_64, x86_32
and ARM5/7, using the CLI.

Want to Google something while using the Firefox browser?
```
$ firefox www.google.co.nz
```

Want to play some music using VLC?
```
$ cd music_directory
$ nvlc *
```

Want to shut a system down?
```
$ sudo shutdown -h now
```

Plus by maintaining key CLI skills, I can use SSH to connect to other systems and execute commands, play music, run
an X Window over TCP, the range is endless.

Anyway, I digress.

While reading through the comprehensive [Daml](https://daml.com/) [documentation](https://docs.daml.com/index.html),
it occured to me that while using Vim on GNU/Linux, there would need to be a lot of code 'Copy & Paste' from examples
or coding from scratch, by hand. While there is nothing wrong with this, it is time consuming and if you are not yet
competent with Daml, it introduces the opportunity for error(s).

Clearly, once you are competent with Daml or not-a-novice then the relevant structure and syntax will be available
from memory and you should be able to build a smart contract, quickly and accurately.

However, what if you are still not competent? What is you are a non-developer? A non-English native speaker? These 
use cases will make the barrier to entry of learning Daml and developing Smart Contracts, higher than it needs be.

Therefore, there are are least two obvious solutions to this;

1. The relevant documentation is 100% relevant to the current codebase at the leading edge, at all times and all the
 examples, code snippets and tutorials cover a wide range of use cases and scenarios.
2. There exists a templating system that is delivered to the user, asks for specific user input, and when complete
generates a complete smart contract, from program header files to the last argument.

With that in mind, I have been working on making a template generator like this for two reasons; the first is that it
helps me. In trying to build a generator that outputs sane and correct code, I learn about the interconnections and
logic for each component (Well in my mind I do). Secondly, once functional, this tool will be available for others
to use and modify, if they see fit.

The use of templating generators has grown substantially over the last 20 years, especially in the web space, where
you can rapidly instantiate a complete web framework with for example Python's Django or Flask frameworks.

Back to Daml Smart Contracts.

The most basic contract that you can write is the self-assigned Token contract, referring to
[1_Token](https://docs.daml.com/daml/intro/1_Token.html)

```
-- Copyright (c) 2021 Digital Asset (Switzerland) GmbH and/or its affiliates. All rights reserved.
-- SPDX-License-Identifier: Apache-2.0

module Token where

template Token
  with
    owner : Party
  where
    signatory owner
```

Why write this out by hand, when you can use Whiptail and Bash to do it for you? To have it correctly commented,
formatted and styled as per Daml guidelines?

To do this in Bash, you take the 7 lines of information (Whitespace Line included), plus the relevant indentations, 
wrap them in a function and reproduce them in a file somewhere.

--------------------------------------------------
```
#!/bin/bash
# Purpose:      Generate Daml Smart Contracts using a build generator
#               with Whiptail, Bash, GNU/Linux
#
# Author:       Quid Agis under GPL v2.0+
# Email:        quidagis [ AT ] keemail.me
# Date:         Fri 02 Apr 2021 20:21:59 NZDT
# Ver:          0.020
# ------------------------------------------


# Daml comment header block
echo "-- Copyright (c) 2021 Digital Asset (Switzerland) GmbH and/or its affiliates. All rights reserved." >> token.daml
echo "-- SPDX-License-Identifier: Apache-2.0" >> token.daml

# 1 line space
echo "" >> token.daml

# Module heading
echo "module token where" >> token.daml

#1 line space
echo "" >> token.daml

# Template body
echo "template Token" >> token.daml
echo "  with" >> token.daml
echo "    owner : Party" >> token.daml
echo "  where" >> token.daml
echo "    signatory owner" >> token.daml
```
--------------------------------------------------

On execution, there will be a file titled 'token.daml' in the local directory, and the contents will look like this:

![Image of generated Daml code](https://raw.githubusercontent.com/quid-agis/quid-agis.github.io/main/assets/images/Screenshot_token_daml-2021-04-04_18-23-56.png)

This was a long post but I wanted to show the context behind creating a template generator. They are flexible, powerful 
and extensible. I will post more template-related code in the next few weeks.

#### # EOF

... my enduring homage to Tron.
