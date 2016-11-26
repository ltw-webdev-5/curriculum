---
layout: lesson
title: "Lazy-loading images"
desc: "Look at creating a fast website with lots of images, some loaded without Javascript & more loaded with Javascript."

hide_markbot: true

extra_tutorials:
  - title: "Progressive enhancement"
    url: progressive-enhancement
    highlight: true
  - title: "Accessibility"
    url: accessibility
  - title: "Accessibility checklist"
    url: accessibility-checklist
  - title: "Javascript & accessibility"
    url: javascript-accessibility
  - title: "PE & a11y slide deck"
    url: "/courses/web-dev-5/pe-a11y/"

goal:
  no_image: true
  before: |
    We’re going to look at making a basic gallery user experience without Javascript then enhance it with some Javascript to substantially improve the loading and rendering performance.

    The idea is to make the website load really quickly—by default only showing a few images.

    - When Javascript isn’t enabled we use the `<noscript>` tag to show more images.
    - When Javascript is enabled we go and download more images to the page after it has already loaded.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

steps:
  - title: "Set up the project"
    before: |
      There’s a basic starter repo that has the CSS files & images we need inside it—we’re going to work from that.

      ### [Fork this repo.](https://github.com/acgd-webdev-5/lazy-loading-images/fork)

      **Then clone it to your computer.**

      You should now have the `lazy-loading-images` folder with the basic files.
    folders:
      - label: "lazy-loading-images"
        type: folder
      - label: "_data"
        indent: 1
      - label: "images.yml"
        indent: 2
      - label: "css"
        type: folder
        indent: 1
        notes: "Lots of CSS in this folder—we’re not going to touch it"
      - label: "_config.yml"
        indent: 1
      - label: "images"
        type: folder
        indent: 1
        notes: "Lots of images in this folder"
      - label: "index.html"
        indent: 1
    after: |
      **Start Jekyll in this folder.** Open the `lazy-loading-images` into your code editor.
    notes:
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Prioritize the images"
    before: |
      To start we need to group the images into 3 categories:

      1. **Critical images** — these images will always load
      2. **Must-have images** — these images should always load
      3. **Non-critical images** — it’d be nice if these images loaded

      *Of course—the images themselves may just fail to load because of slow Internet—there’s nothing we can do to mitigate that.*

      For this exercise, we’ll say the first 2 images are critical, the next 2 are must-have, and the rest are non-critical images.

      Let’s adjust our HTML to group the images into our three categories.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

         <div class="grid">
          {% for img in site.data.images limit:2 %}
            <div class="critical-img unit xs-1 m-1-2">
              <div class="embed embed-16by9">
                <img class="embed-item" src="images/{{img}}" alt="">
              </div>
            </div>
          {% endfor %}
          {% for img in site.data.images offset:2 limit:2 %}
            <div class="non-critical-img unit xs-1 m-1-2">
              <div class="embed embed-16by9">
                <img class="embed-item" data-src="images/{{img}}" alt="" hidden>
                <noscript>
                  <img class="embed-item" src="images/{{img}}" alt="">
                </noscript>
              </div>
            </div>
          {% endfor %}
          {% for img in site.data.images offset:4 %}
            <div class="non-critical-img unit xs-1 m-1-2" hidden>
              <div class="embed embed-16by9">
                <img class="embed-item" data-src="images/{{img}}" alt="">
              </div>
            </div>
          {% endfor %}
        </div>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "32-33"
        fade: true
      - num: 6
        text: |
          In this loop we’re limiting the output to the first two images.

          These are the “critical” images—they will always be shown.
      - num: 7
        text: |
          There’s a new class here, `.critical-img`, to help us remember the importance of this image.
      - num: 13
        text: |
          This is a duplicate of the previous loop with a few small modifications:

          - It has `offset:2`, meaning it will start at the item with the index of 2, aka the 3rd item.
          - It has `limit:2`, again, here we only want to spit two images out—these are our “must-have” images.
      - num: 14
        text: |
          There’s new class here, `.non-critical-img`, to denote these as being “non critical” images—we’ll be using this in Javascript later.
      - num: 16
        text: |
          Notice how the `src="…"` attribute doesn’t exist any more, now it’s `data-src="…"`, this is to prevent the image from downloading. It can’t download unless it has an `src="…"` attribute.

          It also has the `hidden` attribute so that it doesn’t accidentally get shown.
      - num: "17-19"
        text: |
          The `<noscript>` tag is here to force the image to be visible if Javascript isn’t available.

          Inside the `<noscript>` tag is a standard `<img src="…">` tag that will only get triggered if Javascript is disabled in the browser.
      - num: 23
        text: |
          We’ll start outputting the images with the fifth one.
      - num: 24
        text: |
          Here we have a `hidden` attribute so this whole grid unit isn’t shown until the Javascript executes.
      - num: 26
        text: |
          Again we’re using the `data-src="…"` attribute to prevent these images from loading.
    after: |
      In the code above we have three loops, each has a specific purpose and ties to the our image categories:

        1. The images in the first loop will always show.
        2. The images in the second loop will show with or without Javascript, essentially they will also *always* show.
        3. The images in the third loop will only show when the Javascript is triggered.

        **Why bother having the second loop at all if they’re always going to show?** To help the page load faster. Most (almost all) browsers have Javascript enabled, so these images can be triggered later with Javascript. The page will load super quick, showing only the images in the first loop, then the Javascript will kick in and start downloading the rest—but our user will already have a nice, complete page.

  - title: "Lazy load non-critical images with Javascript"
    before: |
      Now for a little titch of Javascript to make the whole thing work together.
    multi_code:
      - code_before: |
          First make a new JS file: `js/image-loader.js`

          *We’re not going to use jQuery for this code because it will just slow our website down. There’s so little Javascript that jQuery adds a massive, unnecessary overhead.*
        code_lang: "js"
        code_file: "js/image-loader.js"
        code: |
          window.addEventListener('load', function (e) {
            var imgs = document.querySelectorAll('.non-critical-img');

            [].forEach.call(imgs, function (img) {
              var imgTag = img.querySelector('img');

              imgTag.src = imgTag.dataset.src;
              imgTag.removeAttribute('hidden');
              img.removeAttribute('hidden');
            });
          });
        lines:
          - num: 1
            text: |
              Wait for the website to finish loading before this Javascript is triggered.
          - num: 2
            text: |
              Find all the elements on the page with the class `.non-critical-img`
          - num: 4
            text: |
              Start a loop, that will traverse over all those non-critical images that Javascript found.
          - num: 5
            text: |
              Inside the “non-critical” element, find the `<img>` tag itself.
          - num: 7
            text: |
              Convert the `data-src="…"` attribute into a `src="…"` attribute so the image will start downloading.
          - num: "8-9"
            text: |
              Remove the `hidden` attributes from the `<img>` and the surrounding `<div>` tags.
      - code_before: |
          Now we need to connect the Javascript to our HTML file.

          Instead of using the standard `<script src="…">` tag, we’re going to embed the Javascript right on the page. This will help mitigate the possibility of the external Javascript file not downloading.
        code_lang: "html"
        code_file: "index.html"
        code: |
          ⋮
              {% endfor %}
            </div>

            <script>{% include_relative js/image-loader.js %}</script>
          </body>
          </html>
        lines:
          - num: "2-3"
            fade: true
          - num: "6-7"
            fade: true
          - num: 5
            text: |
              We’ll use Jekyll’s `include_relative` function to read all the Javascript from our file and output it into the page itself.
    after: |
      **That’s it. Give it a try in your browser with Javascript on & off and with the network speed throttle to see how it significantly improves performance.**

---
