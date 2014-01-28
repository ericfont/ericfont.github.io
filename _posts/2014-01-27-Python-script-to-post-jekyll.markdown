---
layout: post
title: Python script to post jekyll
---

Josh Branchaud has made [a nice simple python script to initialize blog posts for Jekyll](http://joshbranchaud.com/blog/2013/01/11/Jekyll-Post.html).  I made a couple modifications.  First, I set the default to always write to the _posts directory:

    # else condition added by ERF to always default with _posts directory:
    else:
        filename = '_posts/' + filename

Second, at the end of the script, I changed it to always open file in vi (so can immediately start editing and added commmands to build the jekyll site and upload to git:

    # if write flag is on, then try to open file with vi
    # removed by ERF, so always write: if args.write:
    subprocess.call(['vi', filename])

    # ERF added auto commit to git repositorya
    subprocess.call(['jekyll', 'build'])
    subprocess.call(['git', 'commit -a -m "' + filename '"'])
    subprocess.call(['git', 'push' ])

    # print confirmation statement
    print 'New Jekyll post "' + title + '" has been created -- ' + filename ' and committed and pushed git.'

Lastly, instead of putting the python script in my BIN PATH, I simply put it in the root of my github page git folder, so the script is always available on whatever machine I clone my github page repository. You can download my script [here](http://ericfontaine.io/jekyll-post).
