---
layout: slide-deck
title: "PE & a11y"
desc: "A quick introduction to progressive enhancement with JavaScript and applications and how to detect browser features."

slides:
  - type: super-big-text
    content: |
      **PE & a11y**


  - content: |
      ## Progressive enhancement

      *JavaScript is a powerful tool to enhance your website*

      - What happens if it fails to load?
      - What happens if their ad blocker blocks it?
      - What happens if your user has it disabled?

      **Your portfolio should still work.**

  - content: |
      ## Provide a base-level experience

      - Your portfolio, up to this point, should be fully functional without JavaScript
      - Now add JS touches to enhance the user experience

  - content: |
      ## Detect CSS features

      ```css
      /* Work without parallax here */

      @supports (transform-style: preserve-3d) {
        /* Put parallax code in here */
      }
      ```

  - content: |
      ## Or from with JS

      ```js
      if (CSS.supports('filter', 'greyscale(1)')) {
        // Make all things grey-scale
      }
      ```

  - content: |
      ## JavaScript doesn’t make your website inaccessible

      With a little care it enhances your website—making it even more usable & accessible

  - content: |
      ## Use proper semantics

      - Don’t use `<div>` when something else is better
      - If it goes to another page use an `<a>` tag
      - If it controls something on the same page use a `<button>` tag
      - *etc.*

  - content: |
      ## Consider adding ARIA

      - `aria-label="…"`<br>— for more accessible text
      - `aria-hidden="true"`<br>— to hide things from screen readers
      - `aria-controls="…"` + `id="…"`<br>— to coordinate elements
      - `role="…"`<br>— to help define purpose
      - *etc.*

  - content: |
      ## Video & tutorials

      - [Progressive enhancement ➔](/topics/progressive-enhancement/)
      - [Accessibility ➔](/topics/accessibility/)
      - [Accessibility checklist ➔](/topics/accessibility-checklist/)
      - [JavaScript & accessibility ➔](/topics/javascript-accessibility/)
---
