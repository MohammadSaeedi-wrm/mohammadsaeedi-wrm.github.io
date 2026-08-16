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

## IMPORTANT — do these after publishing (this is the SEO half)

1. Google Search Console — https://search.google.com/search-console
   Add property  https://mohammadsaeedi-wrm.github.io
   Verify (easiest: HTML tag -> paste into index.html <head> -> re-upload)
   Submit  sitemap.xml
   Then use "URL Inspection" -> "Request indexing" on the homepage.

2. Point every profile at the site. Google confirms identity through matching links.
   The site already declares these as "sameAs"; the links must come back:
   - Google Scholar -> add homepage in profile
   - ORCID          -> Websites -> add
   - ResearchGate   -> and change affiliation from UVA to Johns Hopkins
   - LinkedIn       -> Featured/Contact info -> add, and update affiliation to JHU
   - GitHub profile -> website field
   - X/Twitter bio  -> add link

3. Ask JHU to list you on the departmental people page with a link to this site.
   A .edu link is the single strongest signal available to you.

## Updating one thing later

Text        -> open index.html on GitHub, pencil icon, edit, commit
A figure    -> upload a new image with the SAME filename into assets/
Everything  -> re-upload the bundle
