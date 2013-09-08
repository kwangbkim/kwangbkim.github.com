---
layout: post
title: "Python/Django First Impressions"
date: 2013-03-23 19:49
comments: false
categories: [web, python, django]
---

After a week of coding and a month of banging my head on the table trying to deploy, I finally released [this](http://correylater-kwangbkim.dotcloud.com/correlations/).  Yes, yes, it's not much.  But it feels good to finally get something out there.

Some random thoughts as someone new to Python/Django/Web Development:

####Python, Very Readable
I feel like Python has perhaps the lowest barrier of entry in terms of just learning to code in the language.  Coming from Java/C#, you can pretty much still code in that style using Python's simple syntax.  Of course, you'd be missing out on all of Python's cool and powerful features, but you'd be up and running quickly.

####Libraries and Tools, Everywhere
If there is something you want to do in Python you can place a safe bet that there exists something that already does it.  A couple things I found that were really useful are [pep8](https://pypi.python.org/pypi/pep8) and [virtualenv](https://pypi.python.org/pypi/virtualenv).  Pep8 checks the style of your code because Python is big on good style and readability.  Virtualenv lets you run and test multiple versions of Python.  

####Django 
Using Django is pretty sweet.  Comparing it to Rails, you can probably start up a new project in Rails faster.  But the advantage of Django is being able to use the Python language, which already has lots of stuff specifically for scientific computing, if you're into that.  And it's a lot easier to read than Ruby.

One word of advice, if you're doing Django on your local box, do yourself a favor and set up all your stuff as you would in production.  Meaning if you're running Postgres in production, make sure you install it on your local box.  Don't don't don't use SQLite!  It's a trap as SQLite is incredibly easy to configure, but you will be pulling your hair out later when you want to release something in the real world.

####Deploying
My project uses the Python libraries [SciPy](http://www.scipy.org/) and [matplotlib](http://matplotlib.org/) for graphing and crunching numbers.  I spent a solid three weeks trying to deploy everything to [Heroku](http://www.heroku.com/).  Heroku downloads and installs all the prerequisites for your project.  But it had trouble installing SciPy and matplotlib.  It does offer something called [buildpacks](https://devcenter.heroku.com/articles/buildpacks), which allows you to do pretty much anything before you deploy.  

After trying Heroku for a while I gave up and moved to [dotCloud](https://www.dotcloud.com/).  I'd say it's much more Python friendly and installing everything was a breeze.  It only took a couple lines of code to overcome the issue that Heroku was giving me, namely that I was missing the gfortran and libatlas libraries.

####On Web Development
I think web development can be a little daunting because it requires a large horizontal breadth of knowledge.  Just for this one project I used HTML, CSS, Python, Django, Pip, Virtualenv, matplotlib, scipy, numpy, dotCloud, postgres, nginx, YAML, markdown and probably a bunch of other stuff.  Knowing each individual component is perhaps not very difficult, but understanding everything at once will probably take some time.