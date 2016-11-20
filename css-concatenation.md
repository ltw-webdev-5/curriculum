---
layout: lesson
title: "CSS concatenation"
desc: "Learn how to automatically combine many CSS files together into a single CSS file for better performance."

hide_markbot: true

extra_tutorials:
  - title: "Performance"
    url: performance
  - title: "Advanced performance"
    url: advanced-performance
  - title: "Advanced performance checklist"
    url: advanced-performance-checklist
    highlight: true
  - title: "Jekyll terminal guide"
    url: jekyll-terminal-guide
  - title: "Jekyll cheat sheet"
    url: jekyll-cheat-sheet
    highlight: true
  - title: "Jekyll: many CSS files"
    url: "https://www.youtube.com/watch?v=H4Fc2xL79nU&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=30"
  - title: "Advanced performance slide deck"
    url: "/courses/web-dev-3/advanced-performance/"

goal:
  no_image: true
  before: |
    We’re going to use Jekyll to combine many CSS files into a single file automatically to improve our website loading time.

    **The method we’re going to use here is slightly different than the one found in the Jekyll videos. Jekyll has a newer feature called `include_relative` that simplifies this process.**
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

steps:
  - title: "Set up the project"
    before: |
      There’s a basic starter repo that has the CSS files we need inside it—we’re going to work from that.

      ### [Fork this repo.](https://github.com/acgd-webdev-5/css-concatenation/fork)

      **Then clone it to your computer.**

      You should now have the `css-concatenation` folder with the basic files.
    folders:
      - label: "css-concatenation"
        type: folder
      - label: "_layouts"
        type: folder
        indent: 1
      - label: "default.html"
        indent: 2
      - label: "css"
        type: folder
        indent: 1
      - label: "grid.css"
        indent: 2
      - label: "main.css"
        indent: 2
      - label: "modules.css"
        indent: 2
      - label: "type.css"
        indent: 2
      - label: "_config.yml"
        indent: 1
      - label: "index.html"
        indent: 1
    after: |
      **Start Jekyll in this folder.** Open the `css-concatenation` into your code editor.
    notes:
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Create new primary CSS"
    before: |
      We need to make a new CSS file that Jekyll is going parse. Generally Jekyll ignores CSS files because they don’t have the `---` at the top.

      So, let’s make a new file named `site.css`:
    folders:
      - label: "css-concatenation"
        type: folder
      - label: "_layouts"
        type: folder
        indent: 1
        fade: true
      - label: "default.html"
        indent: 2
        fade: true
      - label: "css"
        type: folder
        indent: 1
      - label: "grid.css"
        indent: 2
        fade: true
      - label: "main.css"
        indent: 2
        fade: true
      - label: "modules.css"
        indent: 2
        fade: true
      - label: "site.css"
        indent: 2
      - label: "type.css"
        indent: 2
        fade: true
      - label: "_config.yml"
        indent: 1
        fade: true
      - label: "index.html"
        indent: 1
        fade: true
    code_before: |
      In the CSS file we’re going to write this code:
    code_lang: css
    code_file: "css/site.css"
    code: |
      ---
      ---

      {% include_relative modules.css %}
      {% include_relative grid.css %}
      {% include_relative type.css %}
      {% include_relative main.css %}
    after: |
      **The really important thing is that these files are in exactly the same order as inside `default.html`**

  - title: "Link layout to single CSS"
    before: |
      The final step in this process is to link to the single, concatenated CSS file from our `default.html` file.
    code_lang: html
    code_file: "_layouts/default.html"
    code: |
      ⋮
        <title>{{page.title | escape}}</title>
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <link href="css/site.css" rel="stylesheet">
      </head>
      <body>
      ⋮
    lines:
      - num: "2-3"
        fade: true
      - num: "5-6"
        fade: true
      - num: 4
        text: |
          There’s only one CSS file linked from our layout now.
    after: |
      Now our `default.html` only links to a single CSS file. That single CSS file (`site.css`) represents a combined (concatenated) version of all our CSS together.

      *Refresh your browser to make sure everything still works…*

      **And you’re now ready to get much better results on the performance tests.**

---
