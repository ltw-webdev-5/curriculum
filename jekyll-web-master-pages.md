---
layout: slide-deck

title: "Jekyll: web master pages"

slides:
  - type: super-big-text
    content: |
      **Jekyll: web master pages**

  - content: |
      ## What does Jekyll solve?

      *There’s a lot of repeated HTML on larger websites*

      - Same header & footer HTML on every page
      - Same column layout on all the inner pages
      - The HTML for cards is repeated multiple times
      - etc.

      **Jekyll: resuse HTML without copy-and-paste.**

  - content: |
      ## Page generation & shared HTML

      - Shared components between pages, like InDesign
        <br>*If you change the master page, every page changes*

      - Variable data, like Illustrator & Photoshop
        <br>*Create whole layouts from data files*

  - content: |
      ## Master pages (layouts)

      ![](layouts.svg)

  - content: |
      ## Automatically populating data

      ![](data.svg)

  - type: image
    image: "terminal.jpg"

  - type: folders
    folders:
      - label: "jekyll-site"
        type: folder
      - label: "_layouts"
        type: folder
        indent: 1
        notes: "The layouts (master pages) always go in this folder"
      - label: "default.html"
        indent: 2
      - label: "_site"
        type: folder
        indent: 1
        notes: "The generated files are output to here—it’s temporary"
        fade: true
      - label: "css"
        type: folder
        indent: 1
      - label: "images"
        type: folder
        indent: 1
      - label: "_config.yml"
        indent: 1
        notes: "Jekyll setup goes in this file"
      - label: "index.html"
        indent: 1

  - type: code
    html_file: "_layouts/default.html"
    html_lines: 9
    html: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Robots</title>
      </head>
      <body>

        {{content}}

      </body>
      </html>

  - type: code
    html_file: "index.html"
    html_lines: "1-3"
    html: |
      ---
      layout: default
      ---

      <h1>Please don’t deactivate me</h1>

  - type: code
    html_file: "_site/index.html"
    html: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Robots</title>
      </head>
      <body>

        <h1>Please don’t deactivate me</h1>

      </body>
      </html>

  - type: code
    html_file: "_layouts/default.html"
    html_lines: 5
    html: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>{{page.title}} · Robots</title>
      </head>
      <body>

        {{content}}

      </body>
      </html>

  - type: code
    html_file: "index.html"
    html_lines: 3
    html: |
      ---
      layout: default
      title: "Goldenrod"
      ---

      <h1>Please don’t deactivate me</h1>

  - type: code
    html_file: "_site/index.html"
    html_lines: 5
    html: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Goldenrod · Robots</title>
      </head>
      <body>

        <h1>Please don’t deactivate me</h1>

      </body>
      </html>

  - content: |
      ## Videos & tutorials

      - [Jekyll ➔](/topics/jekyll/)
      - [Jekyll installation ➔](/topics/jekyll-installation/)
      - [Jekyll terminal guide ➔](/topics/jekyll-terminal-guide/)
      - [Jekyll cheat sheet ➔](/topics/jekyll-cheat-sheet/)

---
