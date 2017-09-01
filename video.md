---
layout: slide-deck
title: "Video"
desc: "A quick introduction to using video on the web, how to export it, and where to upload it."

slides:
  - type: super-big-text
    content: |
      **Video**

  - content: |
      ## Don’t host video yourself

      Host your video on a dedicated video platform like YouTube or Vimeo as a first choice

      But, hosting video yourself gives you more control

  - content: |
      ## Never, ever (ever, [ever, {ever}]) commit video to GitHub

      *You’ll wreck your repo & won’t be able to sync*

  - content: |
      ## Self-hosted video on a CDN

      If you want to self-host video you need to put it onto a Content Delivery Network

      [**KeyCDN**](https://www.keycdn.com/) is easy to set up and works really well
      <br>(This whole website is on KeyCDN)

  - content: |
      ## Video on the web

      Only one format will work reliably in all browsers:
      <br>**MPEG-4, H.264 encoding**

      *Unlike many web features this isn’t open source—all browsers pay exorbitant fees to let you watch video*

  - content: |
      ## Export from Adobe

      **Adobe Media Encoder**

      - *Format:* **H.264**
      - *Preset:* **Vimeo 1080p HD** or **YouTube 1080p HD**
        <br>The regular “HD 1080p 29.97” should also work but may create larger file sizes.

  - type: interactive
    html: |
      <!-- The <video> tag for self-hosted videos -->

      <video controls src="https://assets.learn-the-web.algonquindesign.ca/web-dev-5/liftoff-of-spacex-crs-5.mp4"></video>

  - type: interactive
    html: |
      <!-- Embed containers make <video> responsive -->

      <div class="embed embed-16by9">
        <video class="embed-item" controls src="https://assets.learn-the-web.algonquindesign.ca/web-dev-5/liftoff-of-spacex-crs-5.mp4"></video>
      </div>
    css_hidden: |
      .embed {
        margin-left: 0;
        margin-right: 0;
        overflow: hidden;
        position: relative;
        width: 100%;
      }
      .embed-16by9, .embed--16by9 {
        padding-top: 56.25%; /* HD TV */
      }
      .embed-item, .embed__item {
        min-height: 100%;
        left: 0;
        position: absolute;
        top: 0;
        width: 100%;
      }

  - type: interactive
    html: |
      <div class="embed embed-16by9">
        <video id="my-video" class="embed-item" src="https://assets.learn-the-web.algonquindesign.ca/web-dev-5/liftoff-of-spacex-crs-5.mp4"></video>
      </div>

      <button id="my-button">Play/Pause</button>
    html_hidden: |
      <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
    js: |
      var myVideo = $('#my-video').get(0);

      $('#my-button').on('click', function () {
        if (myVideo.paused) {
          myVideo.play();
        } else {
          myVideo.pause();
        }
      });
    css_hidden: |
      .embed {
        margin-left: 0;
        margin-right: 0;
        overflow: hidden;
        position: relative;
        width: 100%;
      }
      .embed-16by9, .embed--16by9 {
        padding-top: 56.25%; /* HD TV */
      }
      .embed-item, .embed__item {
        min-height: 100%;
        left: 0;
        position: absolute;
        top: 0;
        width: 100%;
      }
      div {
        margin-bottom: 1em;
      }

  - content: |
      ## Videos & tutorials

      - [Video & audio ➔](/topics/video-audio/)

---
