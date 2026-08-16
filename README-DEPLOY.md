# Publishing / updating the site

Contents of this bundle — this is the WHOLE site:

    index.html                      every page (Home, About, Projects, Publications,
                                    Collaborators, CV, Contact are sections in this one file)
    graphical-abstract-npj.html     opens from the npj card
    graphical-abstract-wrr.html     opens from the WRR card
    assets/                         all images, figures, logos, hero video
    .nojekyll                       tells GitHub Pages to serve files as-is

Repo: https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io

--------------------------------------------------------------------
OPTION 1 — GitHub website (no command line)
--------------------------------------------------------------------
1. Open the repo, click  Add file -> Upload files
2. Drag in: index.html, both graphical-abstract-*.html, the assets folder, .nojekyll
3. Scroll down, write a message like "Update site", click Commit changes

Uploading a file with a name that already exists REPLACES it. That is how you
update later too - just drag the new file in again.

If GitHub will not accept .nojekyll (files starting with a dot):
   Add file -> Create new file -> name it  .nojekyll  -> leave empty -> Commit

--------------------------------------------------------------------
OPTION 2 — Git command line
--------------------------------------------------------------------
    git clone https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io
    cd mohammadsaeedi-wrm.github.io

    # copy this bundle's contents into the repo folder, overwriting

    git add -A
    git commit -m "Update site"
    git push

To try it on a branch first instead of going straight live:

    git checkout -b new-site
    git push -u origin new-site

--------------------------------------------------------------------
UPDATING JUST ONE THING LATER
--------------------------------------------------------------------
Text change      -> open index.html on GitHub, click the pencil icon, edit, commit
Replace a figure -> upload a new image with the SAME filename into assets/
Everything       -> re-upload the whole bundle

--------------------------------------------------------------------
ABOUT THE OLD JEKYLL SITE
--------------------------------------------------------------------
.nojekyll switches GitHub Pages from building Jekyll to plain static hosting.
Your old index.md, _layouts/, _includes/, _sass/ stop being used, but they stay
in the repository and in git history. Nothing is lost. Delete them later if you like.

Rollback:  git revert HEAD  then  git push
Or on the website: Commits -> open the previous commit -> Revert

--------------------------------------------------------------------
AFTER IT IS LIVE
--------------------------------------------------------------------
- https://mohammadsaeedi-wrm.github.io  (first build takes 1-2 minutes)
- Hard refresh if you see the old page: Ctrl+Shift+R / Cmd+Shift+R
- Check the favicon in the browser tab, and open it on your phone
- Submit the URL to Google Search Console so the new description gets indexed
