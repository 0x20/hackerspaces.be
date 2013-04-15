hackerspaces.be
===============

Git backend for the content of http://hackerspaces.be feel free to fork, and to send me updates. Once I know you're not a spammer, you can get commit rights. 

If you just want to add a new space it's easy, look into the *hackerspaces.be/content/spaces* folder, copy one and fill in your details. Editing an exiting space works the same way. The content is formatted with markdown, [tutorial here](http://daringfireball.net/projects/markdown/basics).

This repo gets synched with the site every hour, so if your pull request has been accepted in the master branch, wait till the hour changes to check the site.

You are encouraged to write scripts, for instance, one that would pull a calender feed into git, and displays it nicely on the page. Or a script that checks twitterfeeds for tags and pushes that info to the repo.

## Basic Installation

Get the hyde source by cloning [this repository](https://github.com/hyde/hyde).

The very basic installation of hyde only needs Django, Markdown and pyYAML. More
python goodies are needed based on the features you may use.

    pip install -r requirements.txt
    pip install django-email-obfuscator

OR

	easy_install Django Markdown pyYAML django-email-obfuscator

The script that's triggered on the server does :

	cd ~/hackerspaces.be
	git pull
	cd
	python ./hyde/hyde.py  -g -s /home/hackerspaces/hackerspaces.be -d /home/hackerspaces/staticnew
	rsync -rtu --delete-delay ~/staticnew/ ~/static/

If you are developing use it with the -k option, it'll keep watching the dir for changes and rebuild.

	python ./hyde/hyde.py  -g -s /home/hackerspaces/hackerspaces.be -d /home/hackerspaces/staticnew -k

## Whishlist

* Fancy imageslider on frontpage (every site needs one ;-)
* Logo's of spaces on the page.
	
##More info on Hyde

This document should give enough information to get you up and running. Check
the [wiki](http://wiki.github.com/lakshmivyas/hyde) for detailed documentation.

Hyde is a static website generator with the power of Django templates behind it.
You can read more about its conception, history and features [here][1] and
[here][2].

[1]: http://www.ringce.com/products/hyde/hyde.html
[2]: http://www.ringce.com/blog/2009/introducing_hyde.html
