---
layout: lesson
title: "Content microdata"
desc: "Look at writing the code necessary for describing portfolio piece using Microdata and Schema.org."

hide_markbot: true

extra_tutorials:
  - title: "Metadata & enhanced semantics"
    url: metadata-enhanced-semantics

steps:
  - title: "Set up the project"
    before: |
      We’re going to write the HTML necessary for marking up a [WebSite](https://schema.org/WebSite) portfolio piece using Schema.org.
    folders:
      - label: "portfolio-piece-metadata"
        type: folder
      - label: "index.html"
        indent: 1
    after: |
      1. Drag the `portfolio-piece-metadata` folder to your code editor
      2. Make a new `index.html` file
      3. Populate the `index.html` with the boilerplate code
    notes:
      - label: "Type it, type it real good"
        text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport` & `css`"

  - title: "Add the basic HTML"
    before: |
      Before we start adding the microdata, let’s add the basic HTML markup for a portfolio piece.

      *For this we’re concentrating on a `WebSite` if it was a [visual artwork](https://schema.org/VisualArtwork) or a [photograph](https://schema.org/Photograph) there would be other specific properties.*
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
            <p itemprop="award"><em>Won the RGD Student Award 2015</em></p>
            <a href="#">View website</a>
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

  - title: "Add the MicroData"
    before: |
      We’re now going to add MicroData to the website to help search engines understand the content and display better results.

      We’re specifically going to use the *MicroData* format but there are other formats like *RDFa* and *JSON-LD*.

      **On the HTML tags that represent specific information we’re going to add a new property: `itemprop="…"`.**

      *All of the properties we’re adding are documented under the [WebSite type on Schema.org](https://schema.org/WebSite).*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <figure itemscope itemtype="https://schema.org/WebSite">
          <img itemprop="image" src="https://placehold.it/1600x900" alt="">
          <figcaption>
            <h2 itemprop="name">Dinos ’R’ Us</h2>
            <p itemprop="description">A shop-at-home website dedicated to the many amazing dinosaur products.</p>
            <p>The goal of the project was create a pattern library for a large-scale website and show pattern examples on a few sample pages.</p>
            <p itemprop="award"><em>Won the RGD Student Award 2015</em></p>
            <a itemprop="url" href="#">View website</a>
            <aside itemprop="keywords">Web, Responsive, CSS, Mobile, Dinosaurs</aside>
          </figcaption>
        </figure>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: 6
        fade: true
      - num: 9
        fade: true
      - num: "13-17"
        fade: true
      - num: 4
        text: |
          On the element that surrounds all the content we’re adding two properties:

          - `itemscope` — defines that this element surrounds all the information
          - `itemtype` — defines what kind of object this is — in this case a `WebSite`
      - num: 5
        text: "Define the `<img>` tag as the `image` property."
      - num: 7
        text: "Define the `<h2>` tag as the `name` of this website."
      - num: 8
        text: "Define the first `<p>` tag as the `description` for this website."
      - num: 10
        text: "Define this `<p>` tag as containing information about what awards this work won."
      - num: 11
        text: "This `<a>` tag represents the `url` of where to view this website."
      - num: 12
        text: "Define the `<aside>` as being keywords related to this website."
    after: |
      In most cases the HTML tag is irrelevant, the `name` could be an `<h1>` or `<h2>` or `<strong>` or `<span>` microdata doesn’t necessarily care.

      But some tags are important:

      - `itemprop="image"` should always be on an `<img>` tag.
      - `itemprop="url"` should always be on an `<a>` tag.
      - Any of the time related properties should always be on `<time>` tags.

  - title: "Denote the author"
    before: |
      The major thing missing from the above metadata is the author of this creative work—the person who designed it.

      We could definitely include the `itemprop="author"` above in the code—but you know that I don’t like to repeat code if I don’t have to.

      Most likely we’ll have all the necessary author information in the `<footer>` of the website and we can use link it back up to the portfolio piece.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <figure itemref="data-author" itemscope itemtype="https://schema.org/WebSite">
          <img itemprop="image" src="https://placehold.it/1600x900" alt="">
          <figcaption>
            <h2 itemprop="name">Dinos ’R’ Us</h2>
            <p itemprop="description">A shop-at-home website dedicated to the many amazing dinosaur products.</p>
            <p>The goal of the project was create a pattern library for a large-scale website and show pattern examples on a few sample pages.</p>
            <p itemprop="award"><em>Won the RGD Student Award 2015</em></p>
            <a itemprop="url" href="#">View website</a>
            <aside itemprop="keywords">Web, Responsive, CSS, Mobile, Dinosaurs</aside>
          </figcaption>
        </figure>

        <footer id="data-author" itemprop="author" itemscope itemtype="https://schema.org/Person">
          <p>© 2016 <span itemprop="name">Thomas J Bradley</span></p>
          <a itemprop="email" href="mailto:hey@thomasjbradley.ca">hey@thomasjbradley.ca</a>
          <p itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
            <span itemprop="addressLocality">Ottawa</span>,
            <span itemprop="addressRegion">Ontario</span>,
            <span itemprop="addressCountry">Canada</span>
          </p>
        </footer>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "5-14"
        fade: true
      - num: "26-27"
        fade: true
      - num: 4
        text: |
          Add a new property to the portfolio piece named `itemref`. In `itemref` we write the IDs of other elements on the page that add properties to this `itemscope`
      - num: 16
        text: |
          Lots of properties on the `<footer>` tag:

          - `id` — to associate with the `itemref` attribute above.
          - `itemprop` — to define this as being an `author` for something else on the page.
          - `itemscope` — group all this information together.
          - `itemtype` — define this as a `Person`
      - num: 17
        text: "Define my name as the `name` of this person."
      - num: 18
        text: |
          Define the email address for this person with `itemprop="email"`
      - num: "19-22"
        text: |
          Define this `<p>` tag as being a `PostalAddress`, with a bunch of sub-properties:

          - `addressLocality` — the city or village or hamlet, etc.
          - `addressRegion` — province, territory, state, canton, etc.
          - `addressCountry` — the country of the address.
    after: |
      So we can put the `author` information somewhere else on the page and link each portfolio piece to the author without having to duplicate the code.

  - title: "Validate"
    before: |
      Before getting this checked by the teacher it’s a good idea to validate it. Google’s Rich Snippets Testing Tool allows you to paste the metadata enhanced HTML and it will extract the information out of it. If the tool finds any errors they’ll be displayed on the side.

      ### [Google Rich Snippets Testing Tool.](https://search.google.com/structured-data/testing-tool)

      ![](validate.jpg)

      Copy and paste your HTML into the “Code Snippet” box and make sure there are no red errors.

      It should look like this if everything is okay:

      ![](validate-pass.jpg)

---
