---
layout: lesson
title: "Video controls"
desc: "A lesson on making a custom play/pause button for an embedded video."

hide_markbot: true

extra_tutorials:
  - title: "Video & audio"
    url: video-audio

goal:
  before: |
    We’re going to look at creating a custom play/pause button for a website video.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

steps:
  - title: "Set up the project"
    before: |
      There’s a basic starter repo that has the files hooked up—we’re going to work from that.

      ### [Fork this repo.](https://github.com/acgd-webdev-5/video-controls/fork)

      **Then clone it to your computer.**

      *The content is already inside `index.html` we just need to wrap some tags around it.*
    folders:
      - label: "video-controls"
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
      - label: "js"
        type: folder
        indent: 1
      - label: "main.js"
        indent: 2

  - title: "Write some HTML"
    before: |
      Let’s write out the HTML we need to display the video and a button for controlling the video.

      Here’s the HTML tags we’ll wrap around the content to create the design we’re looking for.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      </head>
      <body>

        <div class="wrapper">
          <div class="relative" id="video-wrap">
            <div class="embed embed-16by9">
              <video class="embed-item" id="the-video" src="https://assets.learn-the-web.algonquindesign.ca/web-dev-5/liftoff-of-spacex-crs-5.mp4"></video>
            </div>
            <button class="btn btn-light giga absolute pin-c" id="btn-play-pause">Play</button>
          </div>
        </div>

        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
        <script src="js/main.js"></script>

      </body>
    lines:
      - num: "2-3"
        fade: true
      - num: "14-17"
        fade: true
      - num: 6
        text: |
          We’ll use the IDs on these lines for interfacing with Javascript.
      - num: 8
      - num: 10

  - title: "Make the play button work"
    before: |
      Let’s move into Javascript to make the play button work.

      *jQuery is already included in our `index.html` file so we’ll be able to use its functions.*
    code_lang: "js"
    code_file: "js/main.js"
    code: |
      var $video = $('#the-video');
      var $btn = $('#btn-play-pause');

      $btn.on('click', function () {
        if ($video.get(0).paused) {
          $video.get(0).play();
          $btn.html('Pause');
        } else {
          $video.get(0).pause();
          $btn.html('Play');
        }
      });
    lines:
      - num: "1-2"
        text: |
          Make variables that refer to the video and button in our HTML.
      - num: 4
        text: |
          Add an event listener so we can execute some code whenever somebody clicks on the button.
      - num: 5
        text: |
          Check to see if the video is currently paused:

          - If the video is paused — we’ll play it
          - If the video isn’t paused — we’ll pause it
      - num: 7
        text: |
          Change the text inside the button to match the action that will happen when it’s clicked again—the opposite of what the video currently doing.
    after: |
      Try it out—the button should play and pause the video.

      *But the button is annoyingly in the way—we’ll fix that next.*

  - title: "Hide & show the button"
    before: |
      Most video players hide the pause button when the video is playing and the mouse isn’t hovering. So let’s add some Javascript and CSS to do just that.
    multi_code:
      - code_lang: "js"
        code_file: "js/main.js"
        code: |
          var $videoWrap = $('#video-wrap');
          var $video = $('#the-video');
          var $btn = $('#btn-play-pause');

          $btn.on('click', function () {
            if ($video.get(0).paused) {
              $video.get(0).play();
              $btn.html('Pause');
              $videoWrap.attr('data-state', 'playing');
            } else {
              $video.get(0).pause();
              $btn.html('Play');
              $videoWrap.attr('data-state', 'paused');
            }
          });
        lines:
          - num: "2-8"
            fade: true
          - num: "10-12"
            fade: true
          - num: "14-15"
            fade: true
          - num: 1
            text: |
              Create a variable that references the `#video-wrap` element in our HTML.
          - num: 9
            text: |
              Add a `data-state="playing"` attribute to the `#video-wrap` element that we can use to hide & show the button in CSS.
          - num: 13
            text: |
              Set the `data-state` attribute to `paused` for CSS also.
      - code_before: |
          Now a little CSS to control the hiding and showing of the button.
        code_lang: "css"
        code_file: "css/main.css"
        code: |
          html {
            font-family: sans-serif;
          }

          [data-state="playing"] .btn {
            display: none;
          }

          [data-state="playing"]:hover .btn {
            display: inline-block;
          }
        lines:
          - num: "1-3"
            fade: true
          - num: "5-7"
            text: |
              When the `data-state` attribute is set to `playing` the `.btn` should be hidden.
          - num: "9-11"
            text: |
              When the `data-state` attribute is set to `playing` and we hover over `#video-wrap` we should show the pause button.
    after: |
      That’s it. When playing and the mouse isn’t hovering the button should hide. And become visible again when we hover on the video.

---
