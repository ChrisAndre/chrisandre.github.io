---
layout: post
title: "Minimal Travis CI LaTeX Builder"
date: 2015-08-04 19:30:00 -0400
comments: false
---
# Minimal example - setup Travis-CI to emit a .pdf from a .tex source in a Github repo
Create a repo on Github

From travis-ci.org, toggle your Github repo on

Locally, create a git repo:

{% highlight bash %}
git init repo
cd repo
git remote add origin https://github.com/user/repo.git
{% endhighlight %}

Add a test LaTeX source root.tex

And add a .travis.yml:

{% highlight yaml %}
before_install:
- sudo apt-get update -qq
- sudo apt-get install texlive-latex-base
script:
- mkdir build
- pdflatex -output-directory build root.tex
deploy:
  provider: releases
  api_key:
    secure:
  file:
    - build/root.pdf
  skip_cleanup: true
  on:
    tags: true
{% endhighlight %}

On your command line:

{% highlight bash %}
sudo apt-get install ruby-dev && gem
gem install travis
travis setup releases
{% endhighlight %}

This will populate the api_key field so that it may autodeploy a release.

On your command line:

{% highlight bash %}
git add --all
git commit -m "message"
git tag tagname
git push -u origin --tags
{% endhighlight %}

On Github, a new release will appear. Once Travis-CI finishes the build, root.pdf will appear in the downloads section beside the tarballs.
