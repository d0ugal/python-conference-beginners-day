# The Python Ecosystem

This document starts with bullet point notes for presenters, and then at the end has further reading + notes for students


# The origin story

* Free software and Open Source.  MIT hackers, the Mac and PC revolution, Stallman, GNU, Linux, Torvalds



# The world around us

* Programming languages: Assembly, compiled, dynamic. Python's relationship to C. Other similar languages - Ruby, JavaScript, Go.  Mention Java, Lisp?

(insert some examples of assembly etc?  hello world in different languages?)



# Python's journey

* Python -- ramping up to version 2
* the standard library
* Adoption by Google, NASA...
* Python 3
* PEPs
* Pypy
* Adoption in education



# Actually doing stuff (packages!  libraries!)

* Packages.  Pypi.  easy-install, pip.
* Web dev
* Science stuff
* Desktop stuff + mobile, Kivy
* Open source projects, contributing, Github, sprints
* Testing, Agile development, Lean



# Resources and Further reading

History and Free software:
* "In the Beginning was the Command Line" by Neal Stephenson: http://www.cryptonomicon.com/beginning.html 
* "Hackers" by Steve Levy: http://www.stevenlevy.com/index.php/books/hackers 
* The GNU Philosophy articles: https://www.gnu.org/philosophy/philosophy.html 

Programming languages and Python:
* Paul Graham on the advantages that a good language can bring: http://www.paulgraham.com/avg.html
* Guido himself on the history and philosopy of Python: https://www.python.org/doc/essays/foreword/

Open Source and the Python ecosystem
* The Cathedral and the Bazaar: http://www.catb.org/esr/writings/cathedral-bazaar/ 


Science stuff:
* High Performance Python (book): http://shop.oreilly.com/product/0636920028963.do
* Jake Vanderplaas: https://jakevdp.github.io/ 

Web Dev
* the DjangoGirls tutorial - an excellent guide for total beginners, from "how the internet works" up to getting a blog site live on the Internet. http://tutorial.djangogirls.org/ 
* http://www.obeythetestinggoat.com -- a good guide for after you've written your first proper Python project.  TDD, Git, deployments. Focused on web development.  More disclosure:  this was written by the first author of this doc.



# Some definitions and notes to read in your own time (handout)

## Packages:

**package**: is the word for a bundle of Python files that you can use as a tool. A "library".  Sometimes called a "module", although that's probably a less precise use of the term.

**PyPI**: the Python Package Index.  Used to be known as the Cheese Shop (because http://www.youtube.com/watch?v=PPN3KTtrnZM).  A public directory of python packages, including links to their source code.  Anything on PyPI can be pip installed.  Anyone can upload a package to Pypi, all you need is to read the docs and create a special installation file called *setup.py*.

**pip**: the standard Python command-line package installer.  "pip install package-name" is the basic command.  There used to be one called `easy_install`, essentially the same, now is less used.  You can also manually download the source code for a package and install it by running the setup.py file, `python setup.py install`.


## Web dev:

**HTML** Hypertext Markup Language is the code for web pages.  What you see when you click "view source" in your browser.  You know, `<html></html>` and all that stuff.

**JavaScript** a hideous car crash of a language that everyone looks down on, partially for good reasons, and partially because they're jealous that it's so popular, because it's the only language you can use in a browser.  It's not that bad, really.

**REST** "Representational State Transfer" is a standard for structuring URLs and how to do HTTP requests for data structures over the Internet.  Used for APIs.  A common pattern these days is to have a basic HTML site which does most of its interaction with your database via javascript and a REST API, instead of doing "normal" browser form interactions...

**WSGI** the Web Server Gateway Interface is the standard protocol or API for request/response (traditional HTTP, ie not websockets/webrtc etc) web apps.  Django, Flask etc all use WSGI.  You could write your own web app that complies with the WSGI standard without using any of them, but it would be a little pointless.

**websockets** are an alternative to the traditional request/response protocol for the web.  They let you open a 2-way, "real-time" conduit between your web page and the server, so you can do real-time updates without needing to refresh the browser or use javascript.  Think chat apps, notifications, etc.  lots of websockets in twitter and facebook...

**Django** is probably the most popular framework.  It comes with lots of built-in tools like the "admin", a web ui for admin users to create database entries, a templating language for generating HTML, an "ORM" to make it easy to work with the database, and so on.

**Flask** is a more "lightweight" alternative -- it doesn't include an ORM or a templating language, and its way of dealing with URLs is simpler, and you can use other ORMs (sqlalchemy is popular) and templating languages (jinja2 usually), but after a while, if your project is going to be complex, the third-party tools start to have inter-dependencies that do end up constraining your choices.   Best for smaller projects, microservices etc.

**bottle** is a micro-micro-micro framework.  It's a single file!

**web2py** is super beginner-friendly, but scorned by more experienced programmers, perhaps unfairly.

**Pyramid** is very flexible and based on components you can choose to use or not.  The slightly intimidating, harcore user's choice. Also, they have the coolest t-shirts.

**Tornado** is the first non-wsgi web app framework in our list.  It's often used to do websockets, but it can also do traditional request/response stuff.

**Twisted** is the second, it's been around for ages, it actually does all sorts of network stuff, from serial port connections all the way up to being its own web server. Requires a slightly "twisted" way of thinking about programming (callbacks, "deferred" objects...).

**Virtual Machine providers** - people who will host virtual servers for you. **Amazon Web Services (AWS)** is the biggest; Amazon rents out virtual machines and server services -- VMs, but also storage (S3), load balancing, databases...  They have lots of competitors, like **Rackspace**, **Linode**, **Digital Ocean** and more (with varying level of capabilities)

**PaaS (Platform-as-a-Service) providers** - people who want to rent you a service rather than a virtual machine.  Usually you trade off convenience (eg, not having to worry about sysadmin, OS updates, load balancing) against flexibility (you may not be able to do everything you could do on your own server).  The biggest is **Heroku**, see also **PythonAnywhere** for a Python-focused one [1]

* [1] disclosure: original author works for PythonAnywhere.

**Docker** is the trendy technology of the month.  It's a lightweight alternatives to a VM - instead of one physical server running lots of virtual servers, you have one physical or virtual server running lots of "containers", which are little sandboxes that pretend to the process that runs inside them that they are all alone on a server, when in fact they are not.  You can start a VM in 20-60s, but you can start a container in less than a second.



## Science stuff:

**numpy & scipy** are two of the most popular scientific python libraries.  Numpy has lots of tools for doing maths on big arrays of numbers, and scipy has lots of stats and ananalysis functions.  scipy depends on numpy.  If you're on windows, they may not "pip install" cleanly, so go to the scipy website and download installers, or look into Conda.

**IPyton and the IPython Notebook** - as we saw earlier, Ipython is an enhanced Python interpreter.  The Ipython Notebook is the real darling of the scientific Python world though, it gives you a sort of interactive notebook interface, a bit like matlab I'm told.

**pandas** is popular for dealing with tables of data.  Lets you do excel-style pivottables, for example

**matplotlib** is a well-revered tool for drawing graphs





## Open source, version control

**Version control system (VCS)** - a system for managing snapshots of your source code.  Popular ones these days are git and mercurial.  In the bad old days you had subversion and CVS.

**Git** - probably the most popular version control system (it was built by Linus and the other kernel developers to manage the Linux source code).  It's also probably the least user-friendly!  
(link to that git-emailing-patches guide?)

**Mercurial (hg)** - is a slightly friendlier version of git, written in Python.  It's used to manage the Python source code.

**GitHub** is the world's most popular code sharing site, and centralised git hosting tool.  You can also put mercurial repos on there.  There used to be **Google code**, but that's been retired, and there's sourceforge, which almost everyone has downloaded something off at some point.  GitHub is like sourceforge but more focused on nerds, and with less random adware all over everything.

**Bitbucket** is the plucky underdog to GitHub's thousand-pound gorilla

**GitLab** lets you host your own github

**Maintainer** is a person who decides what commits to accept into an open source project.  They may not do the bulk of the work, or be a single person...

**Patches** are a syntax showing changes to a file.  Also (more or less) called a **diff**.  The `patch` command can apply a patch to a file.  Git is essentially a big complicated system for managing patches.

**Fork**  refers to the idea of taking a copy of an open source project, and maybe taking it off in a new direction -- either permanently (MariaDB is a fork of the Oracle version of MySQL, LibreOffice is a fork of OpenOffice), or maybe just in the very short term, while a developer tries out a new idea, before submitting patches to merge back into the main project

**Pull Request** is Github's way of managing contributions from random developers to open source projects.  Developer forks the main repo, makes a few commits, then does a "pull request" to ask the owner of the main repo to merge her changes.

**Sprints** are focused periods of contributions to an open-source project, usually where people get together physically in a single room, and new contributors can get advice directly in person from the maintainer(s).  There are usually sprints at the end of a conference!  They're usually very welcoming to beginners...


## Development methodologies

**Agile software development**  Traditionally, software was developed in the "waterfall" model: requirements gathering first, then design, then build, then test.  In the 90s, people started to try a different mode, with much shorter development cycles (weeks rather than months), aiming to get new features out in front of users as fast as possible, in smaller chunks.  **Extreme Programming (XP)** was the first, and **Scrum** is now quite popular with corporations.  **Kanban** has something to do with this too.

**Lean Startup** is a counterpart to the agile model, where rather than taking months or years to build a fully-featured product and then trying to sell it to consumers, you instead try to build a **Minimum Viable Product**, the simplest, smallest thing that could possibly be useful, show it to users asap, and then iterate on it

**Automated Testing** is a practice that grew out of XP, which is the idea that you can have automated tests for your software.  **unit tests** are small tests for individual little bits of your code, although you can also write end-to-end tests for the whole programming.  **TDD** (Test-Driven-Development) is the crazy idea that you can actually write tests *before* you write the actual code...

