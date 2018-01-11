---
layout: slide-deck
title: "Launch your portfolio"
desc: "Look at how to launch your portfolio on your domain to replace the coming soon page."

slides:
  - type: super-big-text
    content: |
      **Launch your portfolio**

  - type: two-col
    col1: |
      ## Disable coming soon

      1. Go to [GitHub.com](https://github.com/)
      2. Go to your “coming soon“ repo’s “Settings”
      3. Scroll down to “Custom domain” under “GitHub Pages”
      3. Delete the domain & save
    col2: |
      ## Enable portfolio

      1. Change the `baseurl` inside `_config.yml`:
        <br>`baseurl: ""`
      2. Commit and push
      3. Go to your portfolio repo’s “Settings”
      3. Scroll down to “Custom domain” under “GitHub Pages”
      4. Add your domain & save
      5. Press the “Pull” button on the GitHub app

---
