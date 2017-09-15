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

      1. Go to the “Settings” for your `portfolio` repo
      2. Scroll down to “GitHub Pages” and select “master branch”
      3. Then press “Save”

  - title: "Writing your “Why”"
    before: |
      When writing about yourself for the Web you want the text to follow the standards we discussed at the start to the class—but you also what your text to have personality.

      One way to help reach people and get people to understand your personality—which is really what you want for your portfolio—is to tell them *why* you’re a graphic designer not *what* you are as a graphic designer.

      *Watch this video to see it explained a little more thoroughly:*
    video: "sioZd3AxmnE"
    after: |
      &nbsp;

      You need to write yourself a “why”—to get the right job and work with the right people.

      ### Poor examples of “what” descriptions

      ```
      Thomas J Bradley

      Graphic designer.
      ```

      *Boring…*

      ```
      Thomas J Bradley

      I like to design pretty things!
      ```

      *No duh—so does every other graphic designer.*

      ### Good examples of “why” descriptions

      ```
      Thomas J Bradley, Professor

      Learning new stuff kicks ass. I want to inspire the passion for learning and creating in others—the best way to do that is to teach.
      ```

      *Now you can understand a little bit about who I am and why I do what I do.*

      ```
      elizabeth&jane photography

      Growing up, my father always had a camera in his hand. He captured everything — there are thousands of images from our lives.

      I feel so lucky that I have these moments to look back on: pictures of my parents’ love, images of their happiness, and photos of their joy seeing their kids grow up.

      I believe that capturing life stories and moments is so important, not only for you, but for those to whom you mean the most.
      ```

      *Understanding Liz’s personality & why she’s passionate about photography.*

      **Write your “why” before moving onto the rest of this lesson.** Your “why” should guide every decision you make about your portfolio website.

      *Please call me over and we can read through it and discuss what you’re trying to communicate.*

  - title: "Edit the readme"
    before: |
      We’re going to use [Markdown](/topics/markdown-yaml-cheat-sheet/) to write a simple readme to store in your repository.

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

      © Thomas J Bradley
    notes:
      - label: "Type it, type it real good"
        text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

  - title: "Commit & push"
    before: |
      Once you’re happy with the readme content, commit and push to GitHub.

---
