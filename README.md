typelevel.github.com
====================

Web site of typelevel.scala, served under the domain [typelevel.org](http://typelevel.org).


Adding a blog post
------------------

1. Create a new file in the `_posts` directory or copy an existing post. Its name should have the format `YYYY-MM-DD-short_title.md`.
2. Set the `title` (short title of the post, appears as the HTML `<title>`) and `author` (your GitHub user name) in the front matter. If you'd like to use code highlighting in the post, add the field `pygments: true` below `nav`. MathJax is available via `mathjax: true`.
3. If this is your first blog post, please indicate if you want your name and a profile picture to appear on the post. If not, you can remove the `author` field from the front matter.
4. Write your content using Markdown. For code highlighting, use the usual GitHub syntax:

<pre>
```scala
def yourCode: Here
```
</pre>

That's it, we'll take care of the rest. If you wish, you can also submit just a plain Markdown file and we'll be happy to integrate it.


Preview changes locally
-----------------------

This site is built using Jekyll. To preview your changes, you have to install the following things first:

* Ruby
* node.js
* Python 2 and Pygments

  _Note:_ Make sure that `/usr/bin/python` is Python 2 and not Python 3, otherwise you might get weird errors.

Apparently the `coffee-script` gem requires node.js (we don't even use CoffeeScript).
Sorry about that.

Once you've done that, you need to install `jekyll`. Find out if your package manager provides it, and if not, install it via `gem`:

```bash
# don't forget to add the directory where Gem binaries are installed to your `$PATH`
# on my machine, that's `$HOME/.gem/ruby/2.1.0/bin`
gem install jekyll
```

As of this writing, `jekyll` version `2.2.0` and `redcarpet` version `3.1.2` are required.

There's also an official [installation guide](http://jekyllrb.com/docs/installation/). Additionally to `jekyll`, don't forget to install `redcarpet`. 

Everything set up? Great. Now you just have to tell Jekyll to generate the site (the empty quotation at the end is important):

```bash
jekyll serve --watch --baseurl ''
```

This will start a local web server on port 4000 where you can browse the site and which re-generates the site if you change the source files.

_Note:_ The `build.sh` script sets up a Python 2.7 `virtualenv` and starts `jekyll` under the assumption that `jekyll` and Pygments are installed as specified above.
