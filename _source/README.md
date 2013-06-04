---
layout: front_page
---
The Basics:
-----------

This page is designed to be used by [Github Pages](http://pages.github.com/),
using[Jekyll](http://jekyllrb.com/), a program written in Ruby
which generates static web-pages from a variety of different
source formats. In particular, we can write pages in 
[Markdown](http://daringfireball.net/projects/markdown/basics)
and generate valid html files. 

Github pages uses a git branch of the project called ```gh-pages```
to serve the project webpage.  To make edits, checkout this branch
in your local working copy:

    $ git checkout gh-pages


Getting Ruby and Ruby-Gems
---------------------------------

To make basic edits, you don't *need* to have
Jekyll installed on your machine, you can simply edit the files,
make a commit and push them to Github; Pages will generate the
webpage, and you can see how it looks live. For more substantial
work, it make sense for us to have a version of Jekyll installed
so that we can preview work, and iron out the kinks before making
changes public.

- __OS X__: This is perhaps the easiest situation, since Ruby comes
preinstalled on OS X. You should update gem though, at a command prompt,
do 

        $ sudo gem update --system
    
- __Linux__: Since many distros don't include ruby by default, you'll need
to install it using your package manager.

    * __apt__ (Ubunutu, Debian etc.), do

            $ sudo apt-get install ruby
            $ sudo apt-get install ruby-gems


Getting Jekyll Using Ruby-Gems
-------------------------------------------------
These instructions should work regardless of your platform

* Open a terminal window, we're going to use ```gem```, Ruby's 
package manager to install Jekyll.
* Type:

        $ gem install jekyll

* And that's it! If you receive an error telling you that you don't
have permission to install the gems, add ```sudo``` to the beginning of
each command.


Building the Site
-----------------

- Now that we have Jekyll installed, open your terminal
and navigate to the melt_mod source directory (the one containing this
README file).
- At the terminal enter

        $ jekyll build

- Some information should be displayed in the terminal, and you should be
returned to a command prompt.
- If everything has gone successfully, there should be a new directory
```_site```, the contents of which are the homepage for the model!
You can now preview the site, make more changes and repeat.

- Jekyll comes with come really handy built-in options.

    * When working, it can get tiresome to rebuild the site
    constantly, the ```--watch``` option tells Jekyll to watch
    the directory, and rebuild the site every time a file is changed.
    * It's also helpful to preview the page as it gets served
      by a real-live webserver. We can do that locally by typing

            $ jekyll serve

      at our command prompt. Stop the server by typing Ctl-C.
      Navigate to ```localhost:4000``` in a web browser to see what the site
      will look like when posted live. 
    * The real gem in this comes when we combine the above, with

            $ jekyll serve --watch

      which lets us make edits and preview them by reloading the
      loaclly served version.

Uploading the Site to GitHub Pages
----------------------------------

Once you're done making changes, you should make a commit to the
branch, so that these changes are tracked in the repository.

- Generate the final page to be uploaded, make sure to preview it just in
case there's some subtle syntax error somewhere.
- Commit the changes to the ```gh-pages``` branch
- Push these changes to the server:

        $ git push origin gh-pages 

- Check the project website and make sure the changes have posted. If not, check
Github's [status page](http://status.github.com) to see if there's an outage.

- The full documentation for Github Pages can be viewed [here](http://help.github.com/pages/)