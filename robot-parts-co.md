---
layout: lesson
title: "Robot Parts Co."
desc: "A quick look at optimizing some content for search engines to make the site show up better in search results."

hide_markbot: true

extra_tutorials:
  - title: "SEO & metadata slide deck"
    url: "/courses/web-dev-5/seo-metadata/"
  - title: "Search engine optimization"
    url: search-engine-optimization

goal:
  before: |
    We’re going to explore a bunch of SEO concepts on a fake website so we can look at the important tags & content and see how to improve the search engine juice.

    **All these techniques will later be applied to your portfolio website.**
  no_image: true

fork:
  url: "https://github.com/acgd-webdev-5/robot-parts-co"

steps:
  - title: "Set up the project"
    before: |
      We’re going to take an mostly complete website and enhance it by adding better SEO and metadata to the code.

      You should see the following files in the folder that you’ve cloned:
    folders:
      - label: "robot-parts-co"
        type: folder
      - label: "css"
        type: folder
        indent: 1
      - label: "main.css"
        indent: 2
      - label: "images"
        type: folder
        indent: 1
      - label: "logo.svg"
        indent: 2
      - label: "products.svg"
        indent: 2
      - label: "index.html"
        indent: 1
      - label: "page2.html"
        indent: 1
      - label: "page3.html"
        indent: 1
    notes:
      - label: "Type it, type it real good"
        text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Rename some files"
    before: |
      One thing that search engines look at when trying to determine the topic and keywords of your page is the URLs, and the words in the URLs.

      We should rename some of these files to be better for search engines.
    folders:
      - label: "robot-parts-co"
        type: folder
      - label: "css"
        type: folder
        indent: 1
        fade: true
      - label: "main.css"
        indent: 2
        fade: true
      - label: "images"
        type: folder
        indent: 1
      - label: "logo.svg"
        indent: 2
        rename: "robot-parts-co.svg"
        notes: "Matches company name"
      - label: "products.svg"
        indent: 2
        rename: "gears-power-cells.svg"
        notes: "More descriptive"
      - label: "index.html"
        indent: 1
        fade: true
      - label: "page2.html"
        indent: 1
        rename: "robot-parts.html"
        notes: "More descriptive"
      - label: "page3.html"
        indent: 1
        rename: "contact.html"
        notes: "More descriptive"
    after: |
      **Don’t forget to change all the references in the HTML.**

  - title: "Improve the <title> tags"
    before: |
      The `<title>` tag is one of the most important pieces of content from an SEO perspective: it’s searched for keywords and it’s used on the search results pages.

      We need to make nice, keyword heavy `<title>` tags that are *completely unique on every page of the website*.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Robot Parts Co. · Every part to conquer the world · Robot Mega City 1, RoboCountry211</title>
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-4"
            fade: true
          - num: 6
            fade: true
          - num: 5
            text: |
              The homepage title follows the format:

              ```
              Site/Company Name · Small keyword rich, catchy phrase · City, Country
              ```
      - code_lang: "html"
        code_file: "robot-parts.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Robot Parts · Robot Parts Co.</title>
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-4"
            fade: true
          - num: 6
            fade: true
          - num: 5
            text: |
              The inside page titles follow the format:

              ```
              Page Title · Site/Company Name
              ```
      - code_lang: "html"
        code_file: "contact.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Contact · Robot Parts Co.</title>
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-4"
            fade: true
          - num: 6
            fade: true
    notes:
      - label: "Keyboard shortcut"
        text: "To create the middot (·) press `⌥⇧9`"

  - title: "Add <meta> descriptions"
    before: |
      The `<meta>` description tag should be included on all websites—and be completely unique on every page.

      Search engines use this as the little description under the link on search results pages. Or sometimes, if it’s better, they’ll use the first few words from the first `<p>` tag.

      Max length for the `<meta>` description is 150 characters.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Robot Parts Co. · Robot parts for robot hearts · Robot Mega City 1, RoboCountry211</title>
            <meta name="description" content="A mega conglomerate corporation selling and servicing all totalitarian robots.">
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-5"
            fade: true
          - num: 7
            fade: true
      - code_lang: "html"
        code_file: "robot-parts.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Robot Parts · Robot Parts Co.</title>
            <meta name="description" content="Every part or piece a destructive robot needs: gears, rotors, manipulators, sensors, power cells and more.">
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-5"
            fade: true
          - num: 7
            fade: true
      - code_lang: "html"
        code_file: "contact.html"
        code: |
          <!DOCTYPE html>
          <html lang="en-ca">
          <head>
            <meta charset="utf-8">
            <title>Contact · Robot Parts Co.</title>
            <meta name="description" content="Send us digital beams or stop by the warehouse to order a part that we’re missing.">
            <meta name="viewport" content="width=device-width,initial-scale=1">
          ⋮
        lines:
          - num: "1-5"
            fade: true
          - num: 7
            fade: true
    notes:
      - label: "Reminder"
        text: "The `<meta>` description tag should be completely unique for every single page on the website."

  - title: "Fix the masthead"
    before: |
      There’s some important information in the `<header>` and top of the website that could be improved for search engine friendliness.
    multi_code:
      - code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
          <header>
            <h1><img src="images/robot-parts-co.svg" alt="Robot Parts Co."></h1>
            <nav>
              <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="robot-parts.html">Robot Parts</a></li>
                <li><a href="contact.html">Contact</a></li>
              </ul>
            </nav>
          </header>
          ⋮
        lines:
          - num: 2
            fade: true
          - num: "4-6"
            fade: true
          - num: "8-11"
            fade: true
          - num: 3
            text: |
              Since the logo is inside the `<h1>` the `alt=""` attribute is extremely important—it should be the name of the company only.
          - num: 7
            text: |
              The titles of pages in the navigation is really important—“Products” is too generic so we’ll change it to “Robot Parts”.
      - code_lang: "html"
        code_file: "robot-parts.html"
        code: |
          ⋮
          <header>
            <strong><img src="images/robot-parts-co.svg" alt="Robot Parts Co."></strong>
            <nav>
              <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="robot-parts.html">Robot Parts</a></li>
                <li><a href="contact.html">Contact</a></li>
              </ul>
            </nav>
          </header>

          <main>
            <h1>Robot Parts</h1>
          ⋮
        lines:
          - num: 2
            fade: true
          - num: "4-13"
            fade: true
          - num: 3
            text: |
              Every page must have a completely unique `<h1>`—that means that the logo cannot be an `<h1>` tag on the inside pages because it would match the homepage.

              So, on inside pages, the logo should probably be a `<strong>` tag.
          - num: 14
            text: |
              Now that the `<h1>` tag has been freed from the logo, we should use it on the most important piece of content on this page: the page title.

              While we’re at it, let’s change the title to be slightly more descriptive than “Products”.
    after: |
      **Go ahead and make the `<h1>` to `<strong>` adjustment on the `contact.html` page too. Then change the `<h2>` to an `<h1>`.**

  - title: "Homepage content fixes"
    before: |
      Looking at the homepage there’s a few adjustments we can do to the content to make it more search engine friendly.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </header>

      <main>
        <p><strong>Every part a destructive robot needs for total world domination.</strong></p>
        <img src="images/gears-power-cells.svg" alt="A selection of the best gears and power cells available to buy">
        <a href="robot-parts.html">Buy robot parts</a>
      </main>

      <footer>
      ⋮
    lines:
      - num: "2-4"
        fade: true
      - num: "8-10"
        fade: true
      - num: 5
        text: |
          The website introductory paragraph was really generic—we changed it to something more relevant.

          Also, since it’s an important paragraph and search engines pay attention to `<strong>` tags we surrounded it with a `<strong>` tag.
      - num: 6
        text: |
          The `<img>` tag should have a really descriptive, keyword laden `alt=""` attribute to help with search results.
      - num: 7
        text: |
          The text inside the `<a>` tag was too generic so we changed it to something more descriptive of the page we’re linking too.

  - title: "Add extra metadata"
    before: |
      The contact page has the address and contact information for the store, it’s a great idea to add extra [Schema.org](https://schema.org/) metadata to help computers (and robots) understand the content better.
    code_lang: "html"
    code_file: "contact.html"
    code: |
      ⋮
      </header>

      <main itemscope itemtype="https://schema.org/Corporation">
        <h1>Contact</h1>

        <strong itemprop="name">Robot Parts Co.</strong>

        <address itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
          <br><span itemprop="streetAddress">1234 Robot Lane</span>
          <br><span itemprop="addressLocality">Robot Mega City 1</span>, <span itemprop="addressRegion">RoboStateB</span>, <span itemprop="addressCountry">RoboCountry211</span>
          <br><span itemprop="postalCode">11001010100101001</span>
        </address>

        <a itemprop="email" href="mailto:parts@robotparts.co">parts@robotparts.co</a>
      </main>

      <footer>
      ⋮
    lines:
      - num: 2
        fade: true
      - num: 5
        fade: true
      - num: 13
        fade: true
      - num: "16-18"
        fade: true
      - num: 4
        text: |
          We first add two attributes to the surrounding HTML element:

          - `itemscope` — defines that this element surrounds all the information
          - `itemtype` — defines what kind of object this is — in this case a `Corporation`
      - num: 7
        text: |
          Define the `<strong>` tag as being the `name` of the corporation.
      - num: 9
        text: |
          Define this paragraph as being a postal address. It’s also an `itemscope` because it surrounds a distinct set of information.
      - num: 10
        text: |
          Define this `<span>` tag as being the `streetAddress` portion.
      - num: 11
        text: |
          There are a few different definitions here, each for a distinct part of a postal address:

          - `addressLocality` — the city or village or hamlet, etc.
          - `addressRegion` — province, territory, state, canton, etc.
          - `addressCountry` — the country of the address.
      - num: 12
        text: |
          Define this chunk of text as the `postalCode`
      - num: 15
        text: |
          Since this is a link to create a new email and it has the email address in it we’ll mark it as the `email` for this corporation.
    after: |
      **The next lesson, [Portfolio metadata](/courses/web-dev-5/portfolio-metadata/), goes into more depth with the extra Schema.org metadata.**

---
