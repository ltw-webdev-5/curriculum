---
layout: slide-deck
title: "SEO & metadata"
desc: "A quick overview of important SEO concerns for a website, important tags, and important data."

slides:
  - type: super-big-text
    content: |
      **SEO & metadata**

  - content: |
      ## Google is smart, but only so smart

      - Google is smart about figuring out what content is good
      - And good at determining relevance

      *But with SEO we can give them a little help*

  - content: |
      ## Things that matters

      - Human-friendly text—with minimal, semantic code
      - Clear information hierarchy
      - First line of first paragraph
      - Links to your site from reputable sources
      - Clean, meaningful URLs & filenames
      - Metadata: enhanced semantics, rich information
      - Speed, security & responsiveness

  - content: |
      ## Tags that matter

      - `<title>`
      - `<meta name="description">`
      - `<h1>`, `<h2>`, `<h3>`, etc.
      - First line of the first `<p>`
      - `<a>`
      - `<img alt="">`
      - `<strong>`, `<em>`

  - type: image
    image: "search-results.jpg"
    notes: |
      Google uses information from your website in its search results listings in the following ways:

      1. The `<title>` of your page is the big blue link
      2. The `<meta>` `description` or text from the first `<p>` is the description under the link
      3. The page URLs are used to highlight keywords
      4. Google can pull out important pages and links from navigation or breadcrumbs
      5. Extra info like ratings, votes, times comes from your metadata

  - type: code
    html: |
      <!-- The `<title>` tag is extremely important -->
      <!-- The title must be unique for every single page -->

      <!-- Homepage title pattern -->
      <title>Site/Company Name · Small keyword rich, catchy phrase · City, Country</title>
      <!-- Inside page title pattern -->
      <title>Page Title · Site/Company Name</title>

      <!-- The `<meta>` `description` is sometimes used -->
      <!-- Unique for every single page — max 150 characters -->
      <meta name="description" content="A short sentence describing the purpose and content of this individual page.">

      <!-- Don’t use `<meta>` `keywords` — it’s completely ignored by all search engines -->

  - content: |
      ## Other files

      - `sitemap.xml` — suggest what pages exist and their importance
      - `robots.txt` — used to block search engines — should exist even if blocking nothing
      - `humans.txt` — show who created the site, what tools where used, resources & references

  - content: |
      ## Structured data

      *Have you ever asked Google a question and gotten an answer?*

      - [How far away is the moon?](https://www.google.ca/?gfe_rd=cr&ei=mNj7V9i0BqaC8Qfog4zYDg#q=how+far+away+is+the+moon)

      Google can answer that because websites mark up their content so computers can understand

      - [**Schema.org**](https://schema.org/)

  - content: |
      ## Social media

      When you share something on Facebook or Twitter (*et al.*), the little preview is defined by specific tags

      - [Open Graph](http://ogp.me/)
      - [Twitter Cards](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary)

  - content: |
      ## Videos & tutorials

      - [Search engine optimization ➔](/topics/search-engine-optimization/)
      - [Metadata & enhanced semantics ➔](/topics/metadata-enhanced-semantics/)
      - [Analytics & monitoring ➔](/topics/analytics-monitoring/)
      - [SEO cheat sheet ➔](/topics/seo-cheat-sheet/)
      - [SEO checklist ➔](/topics/seo-checklist/)
      - [Jekyll: unique titles for every page »](https://www.youtube.com/watch?v=ra9Td0DpK0s&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=31)
      - [Jekyll: meta description »](https://www.youtube.com/watch?v=FUL9SSgMZ8Y&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=32)
      - [Jekyll: automatic sitemap.xml »](https://www.youtube.com/watch?v=C49lhiX_JO0&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=33)

---
