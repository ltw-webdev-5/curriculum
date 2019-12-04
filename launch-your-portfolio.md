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
      ## Enable portfolio

      1. Go to [Netlify](https://www.netlify.com/) & sign in
      2. Select your portfolio website
      3. Press “Domain settings”
      4. Press the “Add domain alias” button
      5. Type your domain into the URL
      6. Pop into [Cloudflare](https://www.netlify.com/) & sign in
      7. Find the `CNAME` record that points to GitHub
      8. Replace the GitHub URL with your Netlify URL
      9. Make sure the Cloudflare orange cloud is greyed out
    col2: |
      ## Disable coming soon

      1. Go to [GitHub.com](https://github.com/)
      2. Go to your “coming soon” repo’s “Settings”
      3. Scroll down to “Custom domain” under “GitHub Pages”
      3. Delete the domain & save

---
