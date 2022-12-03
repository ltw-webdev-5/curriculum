---
layout: lesson
title: "Video background"
desc: "Create a video background for the header of a website."

hide_markbot: true

extra_tutorials:
  - title: "Video slide deck"
    url: "/courses/web-dev-5/video/"
  - title: "Video & audio"
    url: video-audio

goal:
  before: |
    We’re going to look at creating a website banner that has a video as the background behind the text.
  no_image: true
  video: "https://videos.learntheweb.courses/playlists/web-dev-5/video-background-goal.mp4"
  video_poster: goal.jpg
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/ltw-webdev-5/video-background"

steps:
  - title: "Set up the project"
    before: |
      The forked & cloned starter repo has the images you need in the `images` folder and the content inside `index.html` that we’ll just wrap some tags around.

      **The CSS inside `main.css` is done for us—it just contains a few colours, and fonts—nothing too complex.**
    folders:
      - label: "video-background"
        type: folder
      - label: "index.html"
        indent: 1
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
      - label: "images"
        type: folder
        indent: 1
      - label: "sol.jpg"
        indent: 2

  - title: "Write some HTML"
    before: |
      Let’s write out the HTML we need to display the video and get it to play properly.

      Here’s the HTML tags we’ll wrap around the content to create the design we’re looking for.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <div>
          <div>
            <video muted loop autoplay poster="images/sol.jpg" src="https://assets.learntheweb.courses/web-dev-5/magnetic-connections.mp4"></video>
          </div>
          <div>
            <h1>The Sun</h1>
            <p>The Sun is the star at the center of the Solar System; a nearly perfect sphere of hot plasma, with internal convective motion that generates a magnetic field via a dynamo process.</p>
            <a href="#">Learn more</a>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "16-17"
        fade: true
      - num: 7
        text: |
          The `<video>` tag has a bunch of attributes on it to look at:

          - `muted` — will prevent the video from playing any sound
          - `loop` — restart the video when it gets to the end
          - `autoplay` — start playing as soon as its ready—doesn’t work on all devices, especially mobiles
          - `poster=""` — a path to an image that will display while the video is buffering

          **Many modern browsers will not auto-play videos unless they’re set to muted—because auto-playing videos with sound are the absolute worst.**
    after: |
      We should see this in the browser:

      ![](html.jpg)

  - title: "Style the video"
    before: |
      Next up we’ll use a bunch of classes from Typografier & Modulifier to make the video background work properly.

      *Remember that `main.css` has a little bit of stuff for us already—specfically a few colours and the `font-family`.*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <div class="banner relative chop pad-t-2">
          <div class="embed embed-4by3 absolute w-1 pin-cl">
            <video class="embed-item" muted loop autoplay poster="images/sol.jpg" src="https://assets.learntheweb.courses/web-dev-5/magnetic-connections.mp4"></video>
          </div>
          <div class="max-length text-center relative zindex-1 pad-t-2 pad-b gutter-1-2">
            <h1 class="yotta push-1-2">The Sun</h1>
            <p class="mega">The Sun is the star at the center of the Solar System; a nearly perfect sphere of hot plasma, with internal convective motion that generates a magnetic field via a dynamo process.</p>
            <a class="btn btn-ghost mega" href="#">Learn more</a>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: "2-3"
        fade: true
      - num: "13-17"
        fade: true
      - num: 8
        fade: true
      - num: 5
        text: |
          The surrounding `<div>` tag will get these classes:

          - `.banner` — defined in `main.css` to add colours
          - `.relative` — makes it `position: relative`
          - `.chop` — adds `overflow: hidden`
          - `.pad-t-2` — for a little spacing
      - num: 6
        text: |
          We want the `<video>` to be responsive so it needs to become an embed container. Plus we’ll add a few classes to get it into the centre behind the text.

          - `.embed`, `.embed-4by3` — the video’s aspect ratio
          - `.absolute` — make this element `position: absolute` so we can move it around
          - `.w-1` — make its width `100%`
          - `.pin-cl` — position the video so it’s in the vertical centre of our banner
      - num: 7
        text: |
          Don’t forget to add `.embed-item` onto the `<video>` tag itself
      - num: 9
        text: |
          This is where much of the positioning is going to happen.

          - `.max-length` — will prevent the line-length from getting too long
          - `.text-center` — align the text and button to the centre
          - `.relative` — make this element `position: relative` so we can bring it to the front
          - `.zindex-1` — bring the element in front of the video
          - `.pad-t-2`, `.pad-b`, `.gutter-1-2` — some nice spacing
    after: |
      That’s it! We should have an autoplaying, looping video banner.

---
