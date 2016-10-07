---
layout: slide-deck

title: "Jekyll: web master pages"

slides:
  - type: super-big-text
    content: |
      **Jekyll: web master pages**

  - content: |
      ## What does Jekyll solve?

  - content: |
      ## Master pages for the web

  - content: |
      ## Automatically populating data

  - content: |
      ## Developer tool

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
        notes: "The generated files output in here—it’s temporary"
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
