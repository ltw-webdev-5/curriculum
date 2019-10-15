---
layout: lesson
title: "Robot Parts Co."
desc: "A quick look at optimizing some content for search engines to make the site show up better in search results."

hide_show_for_marks: true
markbot_submit: true

extra_tutorials:
  - title: "SEO & metadata slide deck"
    url: "/courses/web-dev-5/seo-metadata/"
  - title: "Search engine optimization"
    url: search-engine-optimization
  - title: "Metadata & enhanced semantics"
    url: metadata-enhanced-semantics

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
      - label: "social.jpg"
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
      - label: "social.jpg"
        indent: 2
        fade: true
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

  - title: "Add location information"
    before: |
      It’s helpful for search engines to know the location of the website, especially if it’s a physical business. They can use that information to plot on maps, etc.

      There are a few tags to define the geographic location using longitude & latitude:
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
        <link href="css/main.css" rel="stylesheet">
        <meta name="ICBM" content="45.41117,-75.69812">
        <meta name="geo.position" content="45.41117;-75.69812">
        <meta name="geo.region" content="ca-on">
        <meta name="geo.placename" content="Ottawa">
      </head>
      <body>
      ⋮
    lines:
      - num: "2,7-8"
        fade: true
      - num: "3,4"
        text: |
          Add the longitude & latitude of the physical location—or even just the city.
      - num: 5
        text: |
          Specify the region’s country code: `ca-on` means “Canada, Ontario”.
      - num: 6
        text: |
          Specify the city, village, town, etc. of the location.
    after: |
      **Make sure to copy this to the `robot-parts.html` & `contact.html`**

  - title: "Add social media tags"
    before: |
      When somebody shares our website on social media we can control what information shows in the share box by adding a few more `<meta>` tags to the head of our document.

      There are primarily 2 chunks of information: [OpenGraph](https://ogp.me/)—used by Facebook, Twitter, Instagram, Pinterest, LinkedIn & more.

      *(Though there are few specific ones for [Twitter](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started). Twitter actually has duplicated many of the OpenGraph tags—but they’re totally optional.)*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
        <meta name="geo.placename" content="Ottawa">
        <meta property="og:type" content="website">
        <meta property="og:title" content="Robot Parts Co. · Every part to conquer the world">
        <meta property="og:url" content="https://robotparts.co/">
        <meta property="og:image" content="https://robotparts.co/images/social.jpg">
        <meta property="og:site_name" content="Robot Parts Co.">
        <meta property="og:description" content="A mega conglomerate corporation selling and servicing all totalitarian robots.">
        <meta property="og:locale" content="en_CA">
        <meta name="twitter:card" content="summary">
        <meta name="twitter:site" content="@robotpartsco">
      </head>
      <body>
      ⋮
    lines:
      - num: "2,12-13"
        fade: true
      - num: "3-9"
        text: |
          These are the OpenGraph tags. They’ll work on just about any social media website, including Twitter.
      - num: "10-11"
        text: |
          Twitter has a few of its own extra tags to add, these are the two that are kind of necessary. The rest of the data will be pulled from OpenGraph.
    after: |
      Copy this to the `robot-parts.html` & `contact.html`. **It’s extremely critical that `og:title`, `og:url` & `og:description` are different for every page.** I usually just copy from the other `<meta>` tags.

  - title: "Humans.txt"
    before: |
      The `humans.txt` file is a place to write the credits of your website: the designers, developers, etc.

      **It’s also a wonderful place to cite the location of where you got assets.** If you downloaded icons from a website you need to specify where, when, etc.—like a bibliography.
    folders:
      - label: "robot-parts-co"
        type: folder
      - label: "css"
        type: folder
        indent: 1
        fade: true
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "index.html"
        indent: 1
        fade: true
      - label: "contact.html"
        indent: 1
        fade: true
      - label: "robot-parts.html"
        indent: 1
        fade: true
      - label: "humans.txt"
        indent: 1
    code_before: |
      Create a new file named `humans.txt` inside the root folder.
    code_lang: "txt"
    code_file: "humans.txt"
    code_can_copy: true
    code: |
      # humanstxt.org

      # TEAM

      (Write all your team members’ information in here)
      (Any format you’d like—I usually use Markdown)

      ---

      # THANKS

      (This is the place where you put sources of things)
      (Locations where you got icons, etc.)

      ---

      # TECHNOLOGY

      ## Software

      (Write what software you’re using)

      ## Hosting

      (Write where the website is hosted & services)
    lines:
      - num: "5-6"
        text: |
          Configure this to specify your team members, their locations & contact information.
      - num: "12-13"
        text: |
          Add the citations & bibliographic entries here. Or thank humans who helped you make the project.
      - num: "21,25"
        text: |
          Use these places to tell about what tools you used: your code editor, version control, where the website is hosted, etc.
    after: |
      Here are a couple examples:

      - [Google](https://www.google.com/humans.txt)
      - [Disqus](https://disqus.com/humans.txt)
      - [New York Times](http://www.nytimes.com/humans.txt)
      - [Netflix](https://www.netflix.com/humans.txt)
      - [Basecamp](https://basecamp.com/humans.txt)
      - [Learn the Web](https://learn-the-web.algonquindesign.ca/humans.txt)
      - [elizabeth&jane photography](https://elizabethandjane.ca/humans.txt)

  - title: "Robots.txt"
    before: |
      The `robots.txt` file is for search engine crawlers—to prevent them from showing certain things in search results. *Remember only honest search engines will follow the specifications.*

      For instance, if you don’t want to have your images show in image search results you could block your images folder.
    folders:
      - label: "robot-parts-co"
        type: folder
      - label: "css"
        type: folder
        indent: 1
        fade: true
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "index.html"
        indent: 1
        fade: true
      - label: "contact.html"
        indent: 1
        fade: true
      - label: "robot-parts.html"
        indent: 1
        fade: true
      - label: "humans.txt"
        indent: 1
        fade: true
      - label: "robots.txt"
        indent: 1
    code_before: |
      Create a new file named `robots.txt` inside the root folder.
    code_lang: "txt"
    code_file: "humans.txt"
    code_can_copy: true
    code: |
      # robotstxt.org

      Sitemap: http://robotparts.co/sitemap.xml

      User-Agent: *
      Disallow:
    after: |
      Here’s the most basic one you should have: it says, “Don’t block anything”.

      Also notice it’s pointing to our `sitemap.xml`—that’s the next step.

  - title: "Search engine sitemap"
    before: |
      The `sitemap.xml` file is used by search engines to help them spider your website. It’s a large list of all the pages on the website.

      **This is different than a user-facing sitemap.** It’s specifically targeted at search engine robots & not humans. The visual sitemap you’ve interacted with previously is another thing that you should probably include.
    folders:
      - label: "robot-parts-co"
        type: folder
      - label: "css"
        type: folder
        indent: 1
        fade: true
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "index.html"
        indent: 1
        fade: true
      - label: "contact.html"
        indent: 1
        fade: true
      - label: "robot-parts.html"
        indent: 1
        fade: true
      - label: "humans.txt"
        indent: 1
        fade: true
      - label: "robots.txt"
        indent: 1
        fade: true
      - label: "sitemap.xml"
        indent: 1
    code_before: |
      Create a new file named `sitemap.xml` inside the root folder.
    code_lang: "xml"
    code_file: "sitemap.xml"
    code: |
      <?xml version="1.0" encoding="UTF-8"?>
      <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

        <url>
           <loc>https://robotparts.co/</loc>
           <lastmod>2027-10-28</lastmod>
           <changefreq>monthly</changefreq>
           <priority>0.6</priority>
        </url>



      </urlset>
    lines:
      - num: 1
        text: |
          This code language is called XML, the structure is similar to HTML with angle brackets, etc.—but significantly more strict.
      - num: "4-9"
        text: |
          Every page on the website should have its own `<url>` entry.

          The only tag within that is required is `<loc>`: the URL of the page itself—the other tags are optional.

          - `lastmod`: The last modification day of the page
          - `changefreq`: How often the page changes
          - `priority`: How important the page is, the default is `0.5`
      - num: 11
        text: |
          Add 2 more `<url>` blocks here for the contact & robot-parts pages.
    after: |
      **Don’t forget to add 2 more `<url>` blocks:**

      1. One `<url>` block for `contact.html`
      1. One `<url>` block for `robot-parts.html`

      Check out [Learn the Web’s sitemap.xml](https://learn-the-web.algonquindesign.ca/sitemap.xml).

      *(Usually humans don’t create these by hand, they’re generated by a tool, like Jeykll.)*

  - title: "Add extra metadata"
    before: |
      The contact page has the address and contact information for the store, it’s a great idea to add extra [Schema.org](https://schema.org/) metadata to help computers (and robots) understand the content better.
    code_lang: "html"
    code_file: "contact.html"
    code: |
      ⋮
          <p>© 2027 Robot Parts Co.</p>
        </footer>

        <script type="application/ld+json">
          {
            "@context": "https://schema.org",
            "@type": "Organization",
            "name": "Robot Parts Co.",
            "email": "parts@robotparts.co",
            "address": {
              "@type": "PostalAddress",
              "streetAddress": "1234 Robot Lane",
              "addressLocality": "Robot Mega City 1",
              "addressRegion": "RoboStateB",
              "addressCountry": "RoboCountry211",
              "postalCode": "11001010100101001"
            }
          }
        </script>

      </body>
      ⋮
    lines:
      - num: "2,3,22"
        fade: true
      - num: 5
        text: |
          Add a new `<script>` tag & set its type to `application/ld+json`

          If we don’t set the `type` attribute the browser will try to execute it as JavaScript.
      - num: 6
        text: |
          The whole thing is a JSON object—so open & close some curly brackets.
      - num: 7
        text: |
          The first entry is `@context` this defines that we’re using the [Schema.org](https://schema.org/) syntax.
      - num: 8
        text: |
          Next up we’ll specify that this JSON-LD object is an `Organization`: one of the types defined on Schema.org.
      - num: 9
        text: |
          Specify the `name` of the corporation.
      - num: 10
        text: |
          Specify the organization’s email address.
      - num: 11
        text: |
          The next entry is a sub-object called address: it has its own set of Schema.org properties we need to implement.
      - num: "13-17"
        text: |
          There are a few different definitions here, each for a distinct part of a postal address:

          - `streetAddress` — the building number & street name.
          - `addressLocality` — the city or village or hamlet, etc. — e.g. “Ottawa”
          - `addressRegion` — province, territory, state, canton, etc. — e.g. “Ontario”
          - `addressCountry` — the country of the address — e.g. “Canada”.
          - `postalCode` — that one’s pretty obvious.
    after: |
      **The next lesson, [Portfolio metadata](/courses/web-dev-5/portfolio-metadata/), goes into more depth with the extra Schema.org metadata.**

---
