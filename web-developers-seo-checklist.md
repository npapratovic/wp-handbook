# Web Developer's SEO Checklist

## Title tag
- [ ] try to keep title length under 60 characters
- [ ] limit title length to 70 characters
- [ ] add unique title to every page of the website
- [ ] include brand name at the end of the title tag

## Meta description
- [ ] try to keep description length under 155 characters
- [ ] limit description length to 160 characters
- [ ] each meta description should be unique
- [ ] if possible write compelling description, otherwise omit it
- [ ] strip double quotation marks or escape them with quot HTML entity

## Img tag
- [ ] use alt attributes
- [ ] limit alt attribute to 125 characters
- [ ] use keyword in image filename and alt attribute

## A tag (hyperlinks)
- [ ] use keywords in anchor text
- [ ] use rel="nofollow" for paid links and untrusted content

## URL Structure
- [ ] use short, human-readable URLs with descriptive keywords
- [ ] use hyphens to separate words
- [ ] URLs should reflect category hierarchy
- [ ] ideally website should have pyramid structure - all pages should be accessible with 3-4 clicks from homepage
- [ ] if applicable, link back from articles to their category and subcategory

## URL Related Tags
- [ ] use link rel="canonical" on all pages to indicate preferred URL
- [ ] don’t chain canonical tags
- [ ] use 301 redirects to redirect duplicate content to new URL, and to migrate old URL structure to new one
- [ ] use link rel="next" and rel="prev" to indicate the relationship between paginated URLs
- [ ] place content on the same subdomain to preserve authority

## www vs non-www
- [ ] both are the same from SEO perspective
- [ ] www has some technical advantages
- [ ] choose one and make sure it is used consistently
- [ ] set 301 redirects from non-preferred domain
- [ ] set preferred domain in Google Search Console

## robots.txt
- [ ] use it to prevent or control crawling
- [ ] specify a crawl delay to prevent crawlers to overload your website, but only if crawlers are causing problems
- [ ] indicate the location of sitemap.xml

## Meta robots tag
- [ ] use it to prevent or control indexing
- [ ] block search indexing with meta robots noindex parameter <meta name="robots" content="noindex" />

## Sitemap.xml
- [ ] use sitemap.xml file with priority, changefreq and lastmod attributes

## Social meta tags
- [ ] include at least following Open Graph meta tags: url, title, description, type, image
- [ ] if possible also add site_name, image:width and image:height
- [ ] prepare optimum image size for Facebook sharing: 1200x630 px
- [ ] add twitter:card tag with summary_large_image property

## Structured Data (Schema.org)
- [ ] add site’s name, logo, contacts and social links
- [ ] add any of the supported content types like Articles, Books, Events, Products...
- [ ] use JSON-LD format
- [ ] follow Google’s recommended procedure for creating new pages: https://developers.google.com/search/docs/guides/prototype#new-page

## HTML5 Sections
- [ ] use HTML5 sectioning elements: header, main, footer, aside and section

## HTTPS Everywhere
- [ ] set up HTTPS everywhere (not just login, payments and other sensitive pages)
- [ ] redirect HTTP to HTTPS

## HTTP Status Codes
- [ ] use 301 redirects rather than 302 redirects to ensure that link juice is passed
- [ ] some 404 pages should be 301 redirects to other web pages if there is a good match: valuable links from external sources, mistyped URLs, those that receive large number of users
- [ ] 404 page should contain: not found notification (heading/text), search box, easy to use navigation system, link to homepage
- [ ] don’t redirect 404 pages to home page

## Mobile Optimization
- [ ] optimize page load time
- [ ] optimize images
- [ ] don’t use pop-ups
- [ ] design for fat finger
- [ ] use Schema.org structured data
- [ ] use responsive web design and serve desktop and mobile clients on the same URL
- [ ] serve the same HTML, CSS and JavaScript to all devices
- [ ] use meta name="viewport" to instruct browsers how to adjust the page to device
- [ ] use HTML5 instead of Flash
- [ ] if website has local element, optimize for local search

## Optimize for local search
- [ ] if a website has a local business element (e.g. a physical shop, restaurant, club, etc.), it should be optimized for local search
- [ ] add your business to Google My Business (https://www.google.com/intl/en/business/)
- [ ] add accurate and appealing pictures
- [ ] add city and state in the title tag, (h1) headings, URL, content, image alt tags and meta description
- [ ] add name, address and phone number to the website, but also to other websites like Yelp, Foursquare, social media sites...
- [ ] embed Google Map that points to your Google My Business Listing
- [ ] encourage customers to leave a review

## Multi Language Websites
- [ ] use a single language for content and navigation on each page
- [ ] add lang attribute to declare the language of a web page
- [ ] use subdirectories or subdomains to separate multilingual content
- [ ] user language switcher (cross-linking each language)
- [ ] avoid automatic redirections
- [ ] use hreflang attribute on each page which has translations

## AJAX
- [ ] develop with progressive enhancement
- [ ] build site’s structure and navigation using only HTML, then spice up the appearance and interface with AJAX
- [ ] use hash fragments - #!
- [ ] avoid iFrames - Google might not index iFrame content

## Page Load Speed
- [ ] optimize Time to Firtst Byte (TTFB)
- [ ] optimize page load speed
- [ ] use CDN
- [ ] optimize database queries
- [ ] alleviate database load with a caching system (e.g. memcached)
- [ ] minify and gzip CSS, HTML and JavaScript files
- [ ] leverage browser caching
- [ ] optimize images
