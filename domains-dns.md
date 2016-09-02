---
layout: slide-deck

title: "Domains & DNS"

slides:
  - type: super-big-text
    content: |
      **Domains & DNS**

  - content: |
      ## Domains vs. IPs

      - We use domains to access websites — but computers need IP addresses
      - *IP addresses are confusing for humans*

      ```
      127.0.0.1
      2001:0db8:85a3:0000:0000:8a2e:0370:7334
      ```

  - content: |
      ## DNS

      (Domain Name System)

      ### Maps Domains ⬌ IPs

  - type: image
    image: dns-1.svg

  - type: image
    image: dns-2.svg

  - type: image
    image: dns-3.svg

  - type: image
    image: mx.svg

  - content: |
      ## Leasing domains

      - Leasing a domain registers it in the DNS
      - And points the domain to an IP address — the host
      - Also points to where email is sent and received

  - content: |
      ## DNS records

      - `A` — The domain to IP mapping for the host
      - `MX` — The email server location
      - `CNAME` — A subdomain or alias for the `A` record

  - content: |
      ## Don’t buy everything in one place

      *Don’t buy your hosting, email & domains all from the same place!*

      - It may be convenient to start but will get really annoying
      - Difficulty switching — if you want to change host, well, now you likely have to change all services
      - Security — if one is compromised they all are

  - content: |
      ## CloudFlare

      - Becomes our DNS server
      - Provides performance boost
      - Provides great security
      - Provides better DNS solutions for hosting on GitHub

  - content: |
      ## Videos & tutorials

      - [Domains & DNS](/topics/domains/)

---
