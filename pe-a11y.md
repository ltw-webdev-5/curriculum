---
layout: slide-deck

title: "PE & a11y"

slides:
  - type: super-big-text
    content: |
      **PE & a11y**


  - content: |
      ## Progressive enhancement

      *Javascript is a powerful tool to enhance your website*

      - What happens if it fails to load?
      - What happens if their ad blocker blocks it?
      - What happens if your user has it disabled?

      **Your portfolio should still work.**

  - content: |
      ## Provide a base-level experience

      - Your portfolio, up to this point, should be fully functional without Javascript
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
      ## Javascript doesn’t make your website inaccessible

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
      - [Javascript & accessibility ➔](/topics/javascript-accessibility/)

  - content: |
      ## Helpful links

      - [ARIA role definitions](https://www.w3.org/TR/wai-aria/roles#role_definitions)
      - [ARIA states & properties](https://www.w3.org/TR/wai-aria/states_and_properties#state_prop_def)
      - [MDN: ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

---
