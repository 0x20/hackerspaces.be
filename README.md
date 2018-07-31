hackerspaces.be
===============

Git backend for the content of https://hackerspaces.be feel free to fork, and to send me updates. Once I know you're not a spammer, you can get commit rights.

If you just want to add a new space it's easy, look into the `hackerspaces.be/content/spaces` folder, copy one and fill in your details. Editing an exiting space works the same way. The content is formatted with markdown, [tutorial here](http://daringfireball.net/projects/markdown/basics).

This repo gets synced with the site every hour, so if your pull request has been accepted in the master branch, wait till the hour changes to check the site.

You are encouraged to write scripts, for instance, one that would pull a calender feed into git, and displays it nicely on the page. Or a script that checks twitterfeeds for tags and pushes that info to the repo.

## Basic Installation
The main requirement, hyde, requires python 2.7 or above. Python3 and above are not yet supported.

    pip install -r requirements.txt

# Usage
The only command to execute is `hyde gen`. The static result will be in `deploy/`.
If you copy it to another location make sure to also copy the `media/` directory since it contains the stylesheet and images.

While developping, it may be usefull to use the integrated server with `hyde serve -a localhost -p 8000`

Or by using Docker (and access it via http://localhost:8080):
```bash
docker run -it  -p 8080:8080 -v $(pwd):/code nyxcharon/docker-hyde bash
hyde serve -a <ip of container>
```

## Deployment

The script that's triggered on the server does :

	cd ~/hackerspaces.be && git pull
	hyde gen
	rsync -rtu --delete-delay ~/staticnew/ ~/static/

## Wishlist

* Fancy imageslider on frontpage (every site needs one ;-)
* Logo's of spaces on the page.
