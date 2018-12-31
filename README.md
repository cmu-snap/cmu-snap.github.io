# snap-www

This site is statically generated using [Jekyll](https://jekyllrb.com/).
The source files live in `www`; Jekyll takes these as input and produces a static publishable copy of the site (that can be copied to a web server) in `www/_site`.


## Requirements

To build the site, you'll need a copy of [Jekyll](https://jekyllrb.com/):
```
gem install bundler jekyll
```


## Building the site

After modifying the source files in `www`, use Jekyll to re-compile it:
```
cd www
jekyll build
```

Note: If you see an opaque Ruby error, try prepending `bundle exec` to any Jekyll command. E.g.:
```
cd www
bundle exec jekyll build
```

If you want to check your changes locally before publishing them to the web server, use `jekyll serve` instead (again, use `bundle exec` if needed):
```
cd www
jekyll serve
```
Now go to `localhost:4000` in your browser. 
You can continue to edit the source files while `jekyll serve` is running; it will automatically re-compile the site as you save modifications.


## Publishing the site

TODO


## Adding a person

To add a new person, create a file called `<name>.md` in the `_people` directory.
For exmaple, to add a profile for Harry Bovik, create the file `www/_people/harry-bovik.md`.

The contents of the file should look like this:
```
---
layout: person
name: Harry Q. Bovik
email: bovik@cs.cmu.edu
website: http://www.cs.cmu.edu/~bovik
phone: +1 (412) 123-4567
office: GHC 0000
twitter: harrybovik
github: harrybovik
linkedin: https://www.linkedin.com/in/harry-bovik
position: Faculty
photo: harry-bovik.jpg
---

Harry's bio goes here. Feel free to use markdown syntax.

Multiple paragraphs are also okay.
```

All of the metadata fields between the `---` markers are optional except `layout: person` and `name: ...`.
To include a photo, save the photo to `www/images/people` and give the file name (not the full path) with the `photo: <file name>` tag in the metadata section.
If the photo provided does not already have a square aspect ratio, it will be automatically cropped when displayed.

When you're done, follow the instructions above to build and publish the updated site.


## Adding a blog post

To add a new blog post, create a file called `YYYY-MM-DD-<name>.md` in the `_posts` directory.
`<name>` may be multiple words separated by hypens and the file name will be used to generate the post's URL.
For example, a file named `2018-11-15-mctls-protocol.md` will result in a post with URL `<domain>/blog/2018/11/15/mctls-protocol.html`

The contents of the file should look like this:
```
---
layout: post
title:  mcTLS Specification
author: David Naylor
date:   2018-11-15
categories: ['research']
tags: ['network security', 'privacy', 'tls']
---

Post content goes here. Feel free to use markdown syntax.

Multiple paragraphs are also okay.
```

The `categories` and `tags` fields take arbitrary lists of strings (and can be omitted entirely).

When you're done, follow the instructions above to build and publish the updated site.
