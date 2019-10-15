---
layout: lesson
title: "Portfolio metadata"
desc: "Look at writing the code necessary for describing portfolio piece using MicroData and Schema.org."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "SEO & metadata slide deck"
    url: "/courses/web-dev-5/seo-metadata/"
  - title: "Metadata & enhanced semantics"
    url: metadata-enhanced-semantics

goal:
  before: |
    We’re going to explore how to write MicroData for a CreativeWork on a fake website so we can look at the important concepts and how to implement them.

    **All these techniques will later be applied to your portfolio website.**
  no_image: true


fork:
  url: "https://github.com/acgd-webdev-5/portfolio-metadata"

steps:
  - title: "Set up the project"
    before: |
      We’re going to write the HTML necessary for marking up a [WebSite](https://schema.org/WebSite) portfolio piece using Schema.org.
    folders:
      - label: "portfolio-metadata"
        type: folder
      - label: "content.txt"
        notes: "For copying-and-pasting"
        indent: 1
        fade: true
      - label: "index.html"
        indent: 1
    after: |
      1. Make a new `index.html` file
      2. Populate the `index.html` with the boilerplate code
    notes:
      - label: "Type it, type it real good"
        text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport`"

  - title: "Add the basic HTML"
    before: |
      Before we start adding the metadata, let’s add the basic HTML markup for a portfolio piece. **Copy the text from `content.txt` to save some time.**

      *For this we’re concentrating on a `WebSite`—if it was a [visual artwork](https://schema.org/VisualArtwork) or a [photograph](https://schema.org/Photograph) there would be other specific properties.*

      **You may also want to check out the generic [CreativeWork](https://schema.org/CreativeWork) that can be applied to non-specific portfolio pieces.**
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <figure>
          <img src="https://placehold.it/1600x900" alt="">
          <figcaption>
            <h2>Dinos ’R’ Us</h2>
            <p>A shop-at-home website dedicated to the many amazing dinosaur products.</p>
            <p>The goal of the project was create a pattern library for a large-scale website and show pattern examples on a few sample pages.</p>
            <p><em>Won the RGD Student Award 2015</em></p>
            <a href="https://thomasjbradley.ca/work/dinos-r-us/">View website</a>
            <aside>Web, Responsive, CSS, Mobile, Dinosaurs</aside>
          </figcaption>
        </figure>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "16-17"
        fade: true
    after: |
      This is an example of a really basic portfolio piece you might see on your website.

      *It intentionally doesn’t include case-study related information to simplify the code in this lesson.*

  - title: "Add the portfolio piece JSON-LD"
    before: |
      We’re now going to add JSON-LD to the website to help search engines understand the content and display better results.

      *All of the properties we’re adding are documented under the [WebSite type on Schema.org](https://schema.org/WebSite).*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          </figcaption>
        </figure>

        <script type="application/ld+json">
          {
            "@context": "https://schema.org",
            "@type": "WebSite",
            "name": "Dinos ’R’ Us",
            "description": "A shop-at-home website dedicated to the many amazing dinosaur products.",
            "image": "https://placehold.it/1600x900",
            "award": "Won the RGD Student Award 2015",
            "url": "https://thomasjbradley.ca/work/dinos-r-us/",
            "keywords": "Web, Responsive, CSS, Mobile, Dinosaurs"
          }
        </script>

      </body>
      </html>
    lines:
      - num: "2-3,18-19"
        fade: true
      - num: 5
        text: |
          Don’t forget to add the `<script>` tag.
    after: |
      All the above properties are fairly self-explanatory—but only the most basic ones. Check out the [Schema.org WebSite type](https://schema.org/WebSite) for all the possibilities.

  - title: "Denote the author"
    before: |
      The major thing missing from the above metadata is the author of this creative work—the person who designed it.

      Most likely we’ll have all the necessary author information in the `<footer>` of the website. But we want to link the same information into the JSON-LD.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          </figcaption>
        </figure>

        <footer role="contentinfo">
          <p>© Thomas J Bradley</p>
          <a href="mailto:hey@thomasjbradley.ca">hey@thomasjbradley.ca</a>
          <address>
            Ottawa, Ontario
            <br>Canada
          </address>
        </footer>

        <script type="application/ld+json">
          {
      ⋮
    lines:
      - num: "2-3,14-15"
        fade: true

  - title: "Link the author"
    before: |
      Now we can write another chunk of JSON-LD linking the author with the creative work.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
          </address>
        </footer>

        <script type="application/ld+json">
          {
            "@context": "https://schema.org",
            "@type": "WebSite",
            "name": "Dinos ’R’ Us",
            "author": {
              "@type": "Person",
              "@id": "#thomasjbradley"
            },
            "description": "A shop-at-home website dedicated to the many amazing dinosaur products.",
            "image": "https://placehold.it/1600x900",
            "award": "Won the RGD Student Award 2015",
            "url": "https://thomasjbradley.ca/work/dinos-r-us/",
            "keywords": "Web, Responsive, CSS, Mobile, Dinosaurs",
          }
        </script>

        <script type="application/ld+json">
          {
            "@context": "https://schema.org",
            "@type": "Person",
            "@id": "#thomasjbradley",
            "name": "Thomas J Bradley",
            "email": "hey@thomasjbradley.ca",
            "url": "https://thomasjbradley.ca"
          }
        </script>

      </body>
      </html>
    lines:
      - num: "2-9,14-20,33-34"
        fade: true
      - num: "10-13"
        text: |
          Add a new blocked named `author`, it doesn’t have any specific information, it just links to another JSON-LD block.
      - num: "22-31"
        text: |
          The new “author” JSON-LD block. Notice the schema-type is `Person`.

  - title: "Validate"
    before: |
      Before getting this checked by the teacher it’s a good idea to validate it. Google’s Rich Snippets Testing Tool allows you to paste the metadata enhanced HTML and it will extract the information out of it. If the tool finds any errors they’ll be displayed on the side.

      ### [Google Rich Snippets Testing Tool.](https://search.google.com/structured-data/testing-tool)

      ![](validate.jpg)

      Copy and paste your HTML into the “Code Snippet” box and make sure there are no red errors.

      It should look like this if everything is okay:

      ![](validate-pass.jpg)

  - title: "Don’t repeat yourself"
    before: |
      **Using Jekyll & pattern libraries we can very easily generate the JSON-LD information for every portfolio piece at the same time we generate the pages themselves.**

---
