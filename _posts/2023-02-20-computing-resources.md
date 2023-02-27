---
layout: post
title:  "Shared computing resources"
date:   2023-02-20 18:00:00 +0000
categories: Resources
tags: Starter Servers GPU
---

## GPU servers (Goggins)

There are currently 3 GPU equipped servers available for the lab members:

| Server | Address | CPU | Memory (GB) | GPU(s) |
| :---- | :----: | :----: | :----: | :----: |
| Goggins 01 | decmtcsaiml01.cs.man.ac.uk | Intel Xeon Gold 5217 (16 cores HT) | 188 | 2x Quadro RTX 6000 (24GB VRAM) |
| Goggins 02 | decmtcsaiml02.cs.man.ac.uk | \| \| | \| \| | 1x Quadro RTX 6000 (24GB VRAM) |
| Goggins 04 | decmtcsaiml04.cs.man.ac.uk | \| \| | \| \| | 1x RTX A6000 (48GB VRAM) |

The servers operate on a free time sharing basis, meaning you can use them at any time, unless there is a request for exclusive use, which will be evaluated per case and if approved will be informed on the servers slack channel.

To request access, please contact [Danilo Carvalho](/people.html#danilo.carvalho) (Goggins 01/02) or [Alex Bogatu](/people.html#alex.bogatu) (Goggins 04), providing the following information:
- Full name
- University username (a string of 8 letters and numbers)

Access is done via SSH. 

{% highlight sh %}
ssh <username>@decmtcsaiml<num>.cs.man.ac.uk
{% endhighlight %}

where `<username>` is the university username and `<num>` is the server number.<br/>
The password is the same as your university IT systems one.

#### Storage

The servers have 3 storage spaces available to the users:

* **Home**: Very small space available (~5GB). Use for config files and project/library symlinks.
* **Scratch**: SSD storage, ~100GB p/ user, accessible by *$HOME/scratch/*. Use for code or data files requiring speed.
* **Data**: HDD storage, ~300GB p/ user, accessible by *$HOME/data/*. Use for bigger data files or archival.

While storage quotas are not strictly enforced, exceeding them may result in **loss of data**.

#### Runtimes & Libraries

All servers have the *build-essentials* (C/C++), *python* (>= 3.6) and *OpenJRE 11* (java) packages installed.

To set up a python environment for ML with libraries, we suggest a user install of [Anaconda](https://www.anaconda.com/) with any needed packages in one or more virtual envs.

If you need an application or library that is not available in the server, please contact [Danilo Carvalho](/people.html#danilo.carvalho) (Goggins 01/02) or [Alex Bogatu](/people.html#alex.bogatu) (Goggins 04), with relevant information about the software needed. 


## Idiap Computational Resources

Idiap provides researchers with access to a centralised computational facility.

You can find a complete description of the available resources along with guidelines to use them on the [Idiap Intranet](https://secure.idiap.ch/intranet/system/computing/ComputationGrid).

A very useful documentation on how to setup your working environment (including Pytorch) is available [here](https://lab.idiap.ch/devel/local/sq/practical/env.html).