hackerspaces.be
===============

Git backend for the content of hackerspaces.be feel free to fork, and to send me updates. Once I know you're not a spammer, you can get commit rights. 

#SETUP

This document should give enough information to get you up and running. Check
the [wiki](http://wiki.github.com/lakshmivyas/hyde) for detailed documentation.

Hyde is a static website generator with the power of Django templates behind it.
You can read more about its conception, history and features [here][1] and
[here][2].

[1]: http://www.ringce.com/products/hyde/hyde.html
[2]: http://www.ringce.com/blog/2009/introducing_hyde.html


## Basic Installation

Get the hyde source by cloning [this repository](https://github.com/hyde/hyde).

The very basic installation of hyde only needs Django, Markdown and pyYAML. More
python goodies are needed based on the features you may use.

    pip install -r requirements.txt

OR

	easy_install Django Markdown pyYAML
