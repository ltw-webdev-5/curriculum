---
layout: lesson
title: "Basic Jekyll site"
desc: "Write the code necessary to make a very basic Jekyll powered website with shared header & navigation."

hide_markbot: true

extra_tutorials:
  - title: "Jekyll"
    url: jekyll
  - title: "Jekyll installation"
    url: jekyll-installation
  - title: "Jekyll terminal guide"
    url: jekyll-terminal-guide
  - title: "Jekyll cheat sheet"
    url: jekyll-cheat-sheet
    highlight: true

goal:
  before: |
    We’re going to look at setting up a small, multi-page website that uses Jekyll layouts to reduce code duplication.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

steps:
  - title: "Set up the project"
    before: |
      There’s a basic starter repo that has the images you need inside it—we’re going to work from that.

      ### [Fork this repo.](https://github.com/acgd-webdev-5/basic-jekyll-site/fork)

      **Then clone it to your computer.**

      You should now have the `basic-jekyll-site` folder and the `images` folder but we still need to make a few **blank** files.
    folders:
      - label: "basic-jekyll-site"
        type: folder
      - label: "index.html"
        indent: 1
      - label: "css"
        type: folder
        indent: 1
      - label: "main.css"
        indent: 2
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "dinosaur.jpg"
        indent: 2
        fade: true
      - label: "flying.jpg"
        indent: 2
        fade: true
      - label: "mammal.jpg"
        indent: 2
        fade: true
    after: |
      1. Drag the `basic-jekyll-site` folder into your code editor
      2. Make a new `index.html` file
      3. Make a new `main.css` in your `css` folder

      *All of these files can remain empty for now.*
    notes:
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Jekyll configuration"
    before: |
      Before we start the Jekyll server system we’ll need to write some configuration.

      First, create a file named `_config.yml`.
    folders:
      - label: "basic-jekyll-site"
        type: folder
      - label: "_config.yml"
        indent: 1
      - label: "index.html"
        indent: 1
        fade: true
      - label: "css"
        type: folder
        indent: 1
        fade: true
      - continue: true
    code_before: "Type the following code in your `_config.yml` to set some defaults for Jekyll."
    code_lang: yaml
    code_file: "_config.yml"
    code: |
      permalink: pretty
      baseurl: "/basic-jekyll-site"
    lines:
      - num: 1
        text: "The `permalink: pretty` setting is going to help make the URLs better looking—and more search engine friendly."
      - num: 2
        text: "The `baseurl` matches the name of our GitHub repo."
    after: |
      Your `_config.yml` should look like this:

      ![](config.jpg)

      And now we’re ready to start Jekyll!

  - title: "Start Jekyll"
    before: |
      Jekyll is a developer tool—and developers **love** the command line (me included). So, that means the interface to start and stop Jekyll is through Terminal.

      We can get to the right place in Terminal using the GitHub Desktop application.
    image_steps:
      - url: github-menu.jpg
        text: "In the GitHub Desktop app go to the menu `Repository > Open in Terminal`—this will open Terminal to the right location."
      - url: jekyll-start.jpg
        text: 'Type `jekyll serve --baseurl=""`'
      - url: return.jpg
        text: "Hit `Return` and Jekyll will start up."
    after: |
      **Leave this window running in the background as long as you’re working on your Jekyll website.**

      If you ever want to stop Jekyll, press `Control-C` or just quit Terminal.
    notes:
      - label: "Keyboard shortcut"
        text: "Press `⌘T` to open the repo in Terminal."

  - title: "Make the homepage"
    before: |
      Now that Jekyll is running we’re ready to start making our website.

      Let’s open our `index.html` and add a little bit of code.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ---
      layout: default
      ---

      <h1>Prehistoric creatures</h1>
    lines:
      - num: 1
        text: |
          These are dashes—not underscores—and they must be the very first line in your HTML.
      - num: 2
        text: |
          This is telling Jekyll which layout (aka master page) to use for this HTML file. Jekyll will automatically merge this HTML file and the master page together into one file.
    after: |
      We intentionally didn’t add all the HTML boilerplate to `index.html` because I want to reduce code duplication—it’s not helpful to repeat code on every page.

      **If you have to copy-and-paste code you’re doing something wrong.**

      *We won’t yet be able to see anything in our browser because we haven’t created the layout yet.*

  - title: "Create the default layout"
    before: |
      Now we’re going to make our new layout, named `default.html`. This is exactly like an InDesign master page, it contains everything that is common to the whole website.

      **Layouts are always saved into the `_layouts` folder.**
    folders:
      - label: "basic-jekyll-site"
        type: folder
      - label: "_config.yml"
        indent: 1
        fade: true
      - label: "_layouts"
        type: folder
        indent: 1
      - label: "default.html"
        indent: 2
      - label: "index.html"
        indent: 1
        fade: true
      - continue: true
    code_before: |
      Next up we’ll add our HTML boilerplate and one other really critical line of code.
    code_lang: html
    code_file: "_layouts/default.html"
    code: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Prehistoric creatures</title>
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <link href="css/main.css" rel="stylesheet">
      </head>
      <body>

        {{content}}

      </body>
      </html>
    lines:
      - num: 7
        text: "Don’t forget to attached the CSS file."
      - num: 11
        text: |
          The `{{content}}` is a placeholder. It’s marking where all the code we write inside `index.html` will be inserted into this layout.
    notes:
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport` & `css`"

  - title: "Preview in the browser"
    before: |
      To see our Jekyll website in the browser we **must** go to a very specific URL:

      ### [http://localhost:4000](http://localhost:4000)

      *Double-clicking `index.html` or right-clicking and pressing `Open in Browser` will not work!*

      What we should see is a pretty generic website:

      ![](preview.jpg)

      **You’ll know it’s working properly if you open up `View Page Source` and see that all the code from `index.html` and all the code from `default.html` is combined together.**

      ![](view-source.jpg)

  - title: "Create a second page"
    before: |
      Next up we’ll look at how simple it is to make a new page to our website.

      Make a brand new HTML file named `dinosaurs.html`
    folders:
      - label: "basic-jekyll-site"
        type: folder
      - label: "_config.yml"
        indent: 1
        fade: true
      - label: "_layouts"
        type: folder
        indent: 1
        fade: true
      - label: "default.html"
        indent: 2
        fade: true
      - label: "index.html"
        indent: 1
        fade: true
      - label: "dinosaurs.html"
        indent: 1
      - continue: true
    code_before: |
      Add the following few lines of code into the file.
    code_file: "dinosaurs.html"
    code_lang: "html"
    code: |
      ---
      layout: default
      ---

      <h1>Dinosaurs</h1>
      <img src="{{site.baseurl}}/images/dinosaur.jpg" alt="">
    lines:
      - num: 6
        text: |
          We’re linking up an image to this page. Notice the `{{site.baseurl}}` part, that’s there to help the website work on our local computer and on GitHub.

          The reason we need it is because on our local computer the URL to our site is just `localhost:4000` but on GitHub there is a folder at the end, like this: `thomasjbradley.github.io/basic-jekyll-site`

          Notice that `{{site.baseurl}}` always has a `/` immediately after it.
    after: |
      We can view this page in the browser only by going directly to its URL, by typing it into the URL bar:

      ### [**http://localhost:4000/dinosaurs/**](http://localhost:4000/dinosaurs/)

      ![](dinosaurs.jpg)

  - title: "Link the pages together"
    before: |
      Let’s add some navigation to our website so we can click around. Nothing too fancy, but it’s a better user experience than having to type the URL directly.
    code_lang: "html"
    code_file: "_layouts/default.html"
    code: |
      ⋮
      <body>

        <header>
          <strong>Prehistoric creatures</strong>
          <nav>
            <ul>
              <li><a href="{{site.baseurl}}/">Home</a></li>
              <li><a href="{{site.baseurl}}/dinosaurs/">Dinosaurs</a></li>
            </ul>
          </nav>
        </header>

        <main>
          {{content}}
        </main>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "18-19"
        fade: true
      - num: 8
        text: |
          We’re using the `{{site.baseurl}}` again here to make the links work on our computer and GitHub.

          Notice that `{{site.baseurl}}` always has a `/` immediately after it.
      - num: 9
        text: "We don’t have to write the `.html` part for `dinosaurs.html` because of the `permalink: pretty` config setting—it automatically strips the `.html` off of files to make the URLs easier to navigate and make them nicer to look at."
      - num: "14-16"
        text: "It’s probably a good idea to wrap the page’s content in a `<main>` tag."
    after: |
      **Since we added this code—only once—to our `default.html` it’ll now show up on all the pages of our website. Thank you, Jekyll.**

      Click around to make sure it works.

      ![](nav.jpg)

  - title: "Add some really basic CSS"
    before: |
      Finally we’re going to add some super basic CSS. Just enough to see how the CSS works.
    code_lang: "css"
    code_file: "css/main.css"
    code: |
      html {
        font-family: Georgia, serif;
      }

      header {
        background-color: #f2f2f2;
      }
    after: |
      If you refresh in the browser you may or may not see the CSS work.

      It works great on the homepage.

      ![](css-home.jpg)

      But if you look at the `/dinosaurs/` page you’ll notice the CSS doesn’t work.

      ![](css-dinos.jpg)

  - title: "Fix the CSS URL"
    before: |
      The CSS error we’re seeing is a combination of a few things:

      1. Because we’re using `permalink: pretty`, Jekyll is actually turning every HTML file into a folder. (You can see this inside the `_site` folder if you have a look.)
      2. The path to our CSS file in the HTML says: “start in this folder and look for a `css` folder”—but inside the `dinosaurs` folder (created by Jekyll) there is no `css` folder.

      So, `{{site.baseurl}}` will fix the problem. *We would have run into exactly the same problem with the image if we didn’t add the `{{site.baseurl}}`*
    code_lang: html
    code_file: "_layouts/default.html"
    code: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Prehistoric creatures</title>
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <link href="{{site.baseurl}}/css/main.css" rel="stylesheet">
      </head>
      <body>
      ⋮
    lines:
      - num: "1-6"
        fade: true
      - num: "8-9"
        fade: true
      - num: 7
        text: |
          Add `{{site.baseurl}}` right before the CSS path.

          Notice that `{{site.baseurl}}` always has a `/` immediately after it.
    after: |
      Now all is good on the “Dinosaurs” page:

      ![](css-dinos-works.jpg)

  - title: "Add the remaining two pages"
    before: |
      This is up to you. Create two more pages:

      1. `mammals.html`
      2. `flying.html`

      Link them into the navigation and link up their images.

---
