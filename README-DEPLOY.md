# Mohammad Saeedi — website. Publish / update guide

## Contents

    index.html                      the whole site (Home, About, Projects, Publications,
                                    Collaborators, CV, Contact are sections in this file)
    graphical-abstract-npj.html     opens from the npj publication card
    graphical-abstract-wrr.html     opens from the WRR publication card
    assets/                         images, figures, logos, hero video, social card
    sitemap.xml                     tells Google what to index
    robots.txt                      points crawlers at the sitemap
    .nojekyll                       serve files as-is instead of building Jekyll

Repo: https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io

## Publish (GitHub website, no command line)

1. Open the repo -> Add file -> Upload files
2. Drag in EVERYTHING: index.html, both graphical-abstract-*.html,
   the assets folder, sitemap.xml, robots.txt, .nojekyll
3. Commit to main

Uploading a file whose name already exists replaces it. That is also how you update later.
If GitHub refuses .nojekyll: Add file -> Create new file -> name it .nojekyll -> leave
empty -> commit.

## Publish (git)

    git clone https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io
    cd mohammadsaeedi-wrm.github.io
    # copy this bundle's contents in, overwriting
    git add -A && git commit -m "New site" && git push

Rollback at any time:  git revert HEAD  &&  git push

## Updating the LinkedIn post on the homepage

The homepage embeds ONE specific post. It does not update by itself.
To swap in a newer post:

1. On LinkedIn, open the post -> "..." menu -> Embed this post
2. Copy the activity id, which looks like  urn:li:activity:1234567890123456789
3. In index.html, search for  urn:li:activity:
4. Replace the number with the new one. There are TWO places (the iframe and the
   "Open the post on LinkedIn" fallback link) - change both.
5. Commit.

Only works for PUBLIC posts. If the post's audience is "connections only" the embed
renders empty.

## IMPORTANT — do these after publishing (this is the SEO half)

1. Google Search Console — https://search.google.com/search-console
   Add property  https://mohammadsaeedi-wrm.github.io
   Verify (easiest: HTML tag -> paste into index.html <head> -> re-upload)
   Submit  sitemap.xml
   Then "URL Inspection" -> "Request indexing" on the homepage.

2. Point every profile back at the site. Google confirms identity through matching links.
   The site declares these as "sameAs"; the links must come back:
   - Google Scholar -> add homepage
   - ORCID          -> Websites -> add
   - ResearchGate   -> add, and change affiliation from UVA to Johns Hopkins
   - LinkedIn       -> add to Contact info, and update affiliation to JHU
   - GitHub profile -> website field
   - X/Twitter bio  -> add link

3. Ask JHU to list you on the departmental people page with a link to this site.
   A .edu link is the strongest single signal available to you.

## Updating one thing later

Text        -> open index.html on GitHub, pencil icon, edit, commit
A figure    -> upload a new image with the SAME filename into assets/
Everything  -> re-upload the bundle
