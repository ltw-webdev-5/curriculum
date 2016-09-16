---
layout: lesson
title: "Writing a readme"
desc: "A quick look at writing the correct readme for your portfolio website that’s hosted on GitHub."

hide_markbot: true

extra_tutorials:
  - title: "Writing for the Web"
    url: writing-for-the-web
  - title: "Writing checklist"
    url: writing-checklist
  - title: "Markdown"
    url: markdown
    highlight: true
  - title: "YAML"
    url: yaml
  - title: "Markdown & YAML cheat sheet"
    url: markdown-yaml-cheat-sheet
    highlight: true
  - title: "Writing a readme"
    url: writing-a-readme
    highlight: true

steps:
  - title: "Create your portfolio repo"
    before: |
      Go to GitHub and make a brand new repository. *We’re leaving our `coming-soon` repo alone so the page stays online.*

      Name your repository something like `portfolio` or `thomasjbradley.ca` (subbing for your domain).

      **Make sure to choose “Initialize this repository with a README” when creating the repository.**

      *Clone to your desktop when you’re ready.*

  - title: "Set it up as a hosted website"
    before: |
      There are now two ways you can set your repository up to be hosted on GitHub.

      ![](gh-pages.jpg)

      1. Do the whole `gh-pages` rigmarole,
        <br>*or*
      2. Go to the “Settings” for your `portfolio` repo, scroll down to “GitHub Pages” and select “master branch”—then press “Save”.

  - title: "Edit the readme"
    before: |
      We’re going to use Markdown to write a simple readme to store in your repository.

      The readme should contain this information:

      - Your name
      - Your “Why”
      - Contact information: email, social media, etc.
      - Link to Behance, Dribbble, etc.
      - Your copyright notice to denote everything is yours.
      - Putting an avatar or logo would be good too.

      *Basically all the same information that you put on your coming soon page.*

      Here’s an example of what your readme should look like:
    code_lang: "markdown"
    code_file: "README.md"
    code: |
      # Thomas J Bradley

      #### [☛ thomasjbradley.ca](https://thomasjbradley.ca)

      ![](photo.jpg)

      Thomas J Bradley is a Professor, Developer, and Author of The Open Web.
      I believe that everybody should perpetually learn, try, build, break, & fix things.

      - **[hey@thomasjbradley.ca](mailto:hey@thomasjbradley.ca)**
      - [GitHub](https://github.com/thomasjbradley)
      - [Keybase](https://keybase.io/thomasjbradley)

      ---

      © 2016 Thomas J Bradley
    notes:
      - label: "Type it, type it real good"
        text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

  - title: "Commit & sync"
    before: |
      Once you’re happy with the readme content, commit and sync to GitHub.

---
