---
layout: lesson
title: "Buying a domain & email"
desc: "Walk through the process of leasing a domain from Hover and purchasing an email account from FastMail."

hide_markbot: true

extra_tutorials:
  - title: "Domains & DNS"
    url: domains

steps:
  - title: "Search for domain"
    before: |
      We’re going to be purchasing domains from [**Hover**](https://www.hover.com/), a small Canadian domain registrar with amazing customer service.

      ### [Go to Hover & make an account](https://www.hover.com/)

      ![](search.jpg)

      *Go to the website and search for the domain you want.*

      If the domain you’re looking for doesn’t exist you can search again or find a different TLD.

      ### .ca? — Yes.

      Ideally you want to choose `.ca` because it will give you better search results juice for Canadian searchers.

      If you want, you could also get the `.com` and forward it to the `.ca` so they act as the same website.

  - title: "Add to cart & start checkout"
    before: |
      This is where the money comes in. Depending on what TLD you chose you’ll be charged a different amount—some of the new fancier ones are more expensive.

      ![](add-to-cart.jpg)

      You can add as many domains as you’d like to the checkout and pay for all of them once.

      ![](start-checkout.jpg)

      When you’re ready, start the checkout process.

  - title: "Fill in information"
    before: |
      Create an account at Hover so you can manage your domains at a later time. **Remember your password!**

      ![](create-account.jpg)

      Then fill in all your personal details and pay Hover. *Don’t worry these personal details are not going to be shown publicly unless you want.*

      ![](details.jpg)

      ### Important details

      - **The “Organization” must be exactly the same as your name.**
      - If you have to choose a legal type, choose “Canadian Citizen”.

      *Finalize the checkout and proceed to the next step.*

  - title: "Important settings"
    before: |
      Finally, let’s look at a few important settings to adjust in the Hover domain control panel.

      ![](hover-control-panel.jpg)

      - **Auto Renew** — You probably want to keep this on, then when your domain lease is about to expire your registrar will automatically charge your credit card to register the domain again. You will receive notice e-mails before this happens.
      - **Transfer Lock** — This disables the ability for the domain to be transfered to another registrar. If you want to transfer your domain you’d have to turn this feature off.
      - **Whois Privacy** — This will hide your personal information from WHOIS lookups. So, if someone searched your domain in the WHOIS database they would not be able to see your address and phone number. If your registrar is charging you extra for this you’re getting ripped off.
      - **Forward This Domain** — Allows you to force your domain to be redirected to another location. I use this often if I purchase both the .ca and the .com. I forward the .com to the .ca so that if anyone types .com into their browser it will automatically take them to the primary .ca domain.

  - title: "Buying email"
    before: |
      It’s best to buy email from a service provider so you can get an email address for your custom domain. I often buy my e-mail services from [FastMail](https://www.fastmail.com/?STKI=12009945)† because they are independent and have great customer service.

      There are two different ways to get a custom email address:

      1. **Buy a forwarder from Hover** — a forwarder will send the email to another address, like Gmail or something. But you can never respond from the custom email address.
      2. **Buy email from a service provider, like FastMail** — this is what I would recommend, it will give you a completely separate, business account tied to your domain.

      - **If you choose the Hover fowarder, go ahead and do that right in your Hover account—then you’re done—don’t continue this lesson.**

      If you choose the FastMail option, continue following along…

  - title: "Setting up FastMail"
    before: |
      Go to [**FastMail**](https://www.fastmail.com/?STKI=12009945)† and sign up for an account—you’ll need to pick the **Standard** account to be able to use your custom domain.

      *The FastMail link is a referral link, from me, that will get you 10% off your first year.*

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

      ![](hover-dns.jpg)

      Make a new tab in Hover and go to the “DNS” tab.

      ![](hover-add-new.jpg)

      *For each of the following items you’ll press the “Add New” button then “Save”.*
    image_steps:
      - url: fastmail-mx-10.jpg
        text: "Point the first `MX` record: `@  MX  10  in1-smtp.messagingengine.com`"
      - url: fastmail-mx-20.jpg
        text: "Point the second `MX` record: `@  MX  20  in2-smtp.messagingengine.com`"
      - url: fastmail-dkim-1.jpg
        text: "Add spam protection with a `TXT` record: `mesmtp._domainkey  TXT  v=DKIM1; k=rsa; p=…`"
      - url: fastmail-dkim-2.jpg
        text: "More spam protection: `_adsp._domainkey  TXT  dkim=unknown`"
      - url: fastmail-spf.jpg
        text: "And more spam protection: `@  TXT  v=spf1 include:…`"

  - title: "Choose your email address"
    before: |
      The last step in this whole process is to actually choose your email address—what comes before the `@` symbol.

      ![](fastmail-alias.jpg)

      Go to FastMail’s “Aliases” page.

      ![](fastmail-alias-new.jpg)

      Add a new alias for your email address.

      ![](fastmail-alias-write.jpg)

      *Choose what you want your email address to be by typing in the field.* I would choose something like `hey` or `hello` or `thomas` or something friendly.

      **That’s it—your email should start working any time now, but could take up to 24 hours.**

---
