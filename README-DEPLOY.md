# Deploying the new site

Files in this bundle:

    index.html                      the whole site (all pages are sections in one file)
    graphical-abstract-npj.html     standalone page, opens from the npj card
    graphical-abstract-wrr.html     standalone page, opens from the WRR card
    assets/                         images, figures, logos, hero video
    .nojekyll                       tells GitHub Pages to serve files as-is

## Option 1 — GitHub web upload (no command line)

1. Go to https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io
2. Add file -> Upload files
3. Drag in: index.html, both graphical-abstract-*.html, the assets folder, and .nojekyll
4. Commit to `main`

If GitHub hides `.nojekyll` because it starts with a dot, use Add file -> Create new file,
type `.nojekyll` as the name, leave it empty, and commit.

## Option 2 — Git

    git clone https://github.com/MohammadSaeedi-wrm/mohammadsaeedi-wrm.github.io
    cd mohammadsaeedi-wrm.github.io
    git checkout -b new-site
    # copy the contents of this bundle into the repo root
    git add -A
    git commit -m "New site design"
    git push -u origin new-site
    # open a pull request, or merge into main when ready

## Important — the old Jekyll site

`.nojekyll` switches GitHub Pages from Jekyll processing to plain static hosting.
The old `index.md`, `_layouts/`, `_includes/` and `_sass/` are then ignored, but they stay
in the repository, so nothing is lost. Delete them later once you are happy.

Your old `index.md` will no longer render. `index.html` takes over as the homepage.

## Rolling back

Everything is in git history:

    git revert HEAD        # undo the last commit
    git push

## After it is live

- Visit https://mohammadsaeedi-wrm.github.io (allow 1-2 minutes for the first build)
- Check the favicon appears in the browser tab
- Test on your phone
- Submit the URL to Google Search Console so the new description gets indexed

## Notes

- The site loads Inter from Google Fonts; everything else is local.
- The hero video is assets/video.mp4 (~600 KB) and uses preload="none",
  so it only downloads when the visitor reaches it.
- To swap any publication figure later, replace the matching file in assets/
  and keep the same filename.
