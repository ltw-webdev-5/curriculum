---
layout: lesson
title: "Hosting setup"
desc: "Walk through the process of making a GitHub website live on your own domain."

hide_markbot: true

extra_tutorials:
  - title: "Domains & DNS"
    url: domains

steps:
  - title: "Create a CloudFlare account"
    before: |
      [**CloudFlare**](https://www.cloudflare.com/) is a free service to add an extra level of security and performance to your website. They’re a DNS routing system with the added benefit of stopping security threats to your website and performance enhancements—and SSL.

      ### [Go to CloudFlare & make an account](https://www.cloudflare.com/)

      ![](cloudflare-domain.jpg)

      After creating your CloudFlare account, put in your domain name. CloudFlare will search your domain for DNS records.

      ![](cloudflare-dns.jpg)

      When you get to the DNS configuration page do the following things:

      1. Delete all the `A` records.
      2. Add a new `CNAME` record:
        - `yourdomain.ca`
        - *points to…*
        - `your-github-username.github.io`

      Continue on completing all the steps for CloudFlare’s setup.

      **Make sure you choose the “Free” plan.**

  - title: "Connect Hover to CloudFlare"
    before: |
      Eventually CloudFlare will ask you to change your name servers—this is configuration we need to adjust in Hover.

      ![](cloudflare-hover.jpg)

      Go to “Domain Details” in Hover for your domain, and down to the “Nameservers” section.

      1. Press the “Edit” button.
      2. Delete the 2 nameservers that are currently there.
      3. Copy the 2 cutely named servers that CloudFlare presented to you into Hover.

  - title: "Connect your domain to GitHub"
    before: |
      Using GitHub as a static web host is simple, integrates with our processes—and it’s free.

      On GitHub, create a repository like you normally do. And create a `gh-pages` branch like you normally do. *You can actually avoid the `gh-pages` thing now with GitHub and configure it right in “Settings”.*

      ![](github-settings.jpg)

      Go to the “Settings” for your repository.

      ![](github-domain.jpg)

      Scroll down to the “GitHub Pages” section and enter your “Custom Domain” into the field. Press “Save”.

      **That’s it! Your website should start working any time now but could take up to 24 hours.**
---
