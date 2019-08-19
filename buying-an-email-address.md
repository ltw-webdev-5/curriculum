---
layout: lesson
title: "Buying an email address"
desc: "Walk through the process of purchasing an email account from FastMail."

hide_markbot: true

extra_tutorials:
  - title: "Domains & DNS slide deck"
    url: "/courses/web-dev-5/domains-dns/"
  - title: "Email account types slide deck"
    url: "/courses/web-dev-5/email-account-types/"
  - title: "Domains & DNS"
    url: domains

important:
  title: "Delays are allowed"
  text: |
    **You can delay doing this assignment until you get further along in determining your brand—which you’ll be doing in another class.**

steps:
  - title: "Buying email"
    before: |
      It’s best to buy email from a service provider so you can get an email address for your custom domain. I often buy my e-mail services from [FastMail](https://www.fastmail.com/?STKI=12009945)† because they are independent and have great customer service.

      There are two different ways to get a custom email address:

      1. **Buy a forwarder from Hover** — a forwarder will send the email to another address, like Gmail or something. But you can never respond from the custom email address.
      2. **Buy email from a service provider, like FastMail** — this is what I would recommend, it will give you a completely separate, business account tied to your domain.

      - **If you choose the Hover fowarder, [jump to this lesson on Hover forwarding emails ➔](/courses/web-dev-5/forwarding-email-addresses/)**

      If you choose the FastMail option, continue following along…

  - title: "Setting up FastMail"
    before: |
      Go to [**FastMail**](https://www.fastmail.com/?STKI=12009945)† and sign up for an account—you’ll need to pick the **Standard** account to be able to use your custom domain.

      *† The FastMail links are referral links, from me, that will get you 10% off your first year.*

      ![](fastmail-package.jpg)

  - title: "Point your domain"
    before: |
      After you’ve purchased your e-mail service we need to do some domain pointing.

      ![](fastmail-settings.jpg)

      Go to your FastMail “Settings”.

      ![](fastmail-domains.jpg)

      Then go to “Domains”.

      ![](fastmail-add-domain.jpg)

      Then press “Add Domain”.

      ![](fastmail-save-domain.jpg)

      Type in the domain exactly as you purchased in Hover and press “Save”.

  - title: "Configure the DNS"
    before: |
      We now need to take settings from FastMail and put them into Hover to connect the two pieces together.

      ![](fastmail-edit-domain.jpg)

      First, go to FastMail and edit your domain.

      ![](fastmail-dns.jpg)

      Open up the advanced DNS settings for FastMail.

      **Now is where all the fun copying-and-pasting comes in.**

      ![](cloudflare-dns.jpg)

      Make a new tab in Cloudflare and go to the “DNS” tab.

      ![](cloudflare-add-new.jpg)

      *For each of the following items you’ll press the “Add New” button then “Save”.*
    image_steps:
      - url: cloudflare-mx-1.jpg
        text: "Point the first `MX` record. `MX` records tell the DNS system where to find your email server."
      - url: cloudflare-mx-2.jpg
        text: "Point the second, backup, `MX` record"
      - url: cloudflare-cnames.jpg
        text: "Add spam protection with a bunch of `CNAME` records—**Do each of the CNAME records individually.**"
      - url: cloudflare-txt.jpg
        text: "More spam protection with the `TXT` record."

  - title: "Choose your email address"
    before: |
      The last step in this whole process is to actually choose your email address—what comes before the `@` symbol.

      ![](fastmail-alias.jpg)

      Go to FastMail’s “Aliases” page. **You’ll likely have to confirm your password to make changes to the page.**

      ![](fastmail-alias-new.jpg)

      Add a new alias for your email address.

      ![](fastmail-alias-write.jpg)

      *Choose what you want your email address to be by typing in the field.* I would choose something like `hey` or `hello` or `thomas` or something friendly.

      **That’s it—your email should start working any time now, but could take up to 24 hours.**

---
