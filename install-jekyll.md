---
layout: lesson
title: "Install Jekyll"
desc: "Walk through the process of getting Jekyll set up and running on your Mac."

hide_markbot: true
video: oiNVQ9Zjy4o

extra_tutorials:
  - title: "Jekyll"
    url: jekyll
  - title: "Jekyll installation"
    url: jekyll-installation
    highlight: true
  - title: "Jekyll terminal guide"
    url: jekyll-terminal-guide
  - title: "Jekyll cheat sheet"
    url: jekyll-cheat-sheet

steps:
  - title: "Open Terminal"
    before: |
      On MacOS it isn’t too difficult to install Jekyll, but it does require everything to be completed from within Terminal.

      **So first: open “Terminal” on your computer.** It’s in `Applications > Utilities` or you can search with “Spotlight”.

      ![](terminal.jpg)

      *Yours will look different: I have mine super customized.*
    notes:
      - label: "Older MacOS"
        text: |
          If you have an older version of Mac OS X, specifically 10.8 and below, [**☛ See the Older Mac OS X installation guide.**](/topics/jekyll-installation-older-mac/)

  - title: "Install Homebrew"
    before: |
      Homebrew is a package manager for Mac & Terminal—it’s like an app store, but specifically in the terminal and mostly for developer tools.

      ### First go to the [Homebrew website](http://brew.sh/).

      ![](brew.jpg)

      On the page, you’ll see a chunk of code—copy it.

      ![](brew-copy.jpg)

      Paste it into your Terminal and hit return, your computer will go off an install Homebrew.

      ![](brew-paste.jpg)

      **It will prompt you for your computer’s password. As you type it in you won’t see anything—but it is being entered. When you’ve finished typing your password, hit `Return`.**

  - title: "Install Ruby with Homebrew"
    before: |
      First we need to install the programming language Jekyll is written in: Ruby.

      Using `brew` we can install the most recent version of Ruby.

      ![](ruby.jpg)
    code_file: "Terminal"
    code_can_copy: true
    code: |
      brew install ruby

  - title: "Install Jekyll with Ruby Gems"
    before: |
      Next up we need to install Jekyll using Ruby’s package manager, `gem`:

      ![](jekyll.jpg)
    code_file: "Terminal"
    code_can_copy: true
    code: |
      gem install jekyll
    after: |
      *This will go and download a whole bunch of stuff to your computer, when it’s done, you have Jekyll.*

  - title: "Check Jekyll is installed"
    before: |
      Just to confirm that Jekyll is installed we’ll see what version we have.

      *If we get a version number—doesn’t matter what number—it’s installed.* If we get an error message or nothing, then we have a problem.

      ![](jekyll-v.jpg)
    code_file: "Terminal"
    code_can_copy: true
    code: |
      jekyll -v
    after: |
      *As long as you get a version number it doesn’t need to match the one in the screenshot above—it’ll probably be a newer version.*
---
