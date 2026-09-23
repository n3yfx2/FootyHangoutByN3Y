# deploying to github pages

1. create a new repository on github (e.g. `footy-hangout`).
2. upload `index.html` to the root of the repo — that's the only file needed.
3. in the repo, go to **settings → pages**.
4. under "build and deployment", set **source** to `deploy from a branch`, pick the `main` branch and `/ (root)` folder, then **save**.
5. wait a minute or two — github will give you a live url like `https://yourusername.github.io/footy-hangout/`.

## before you deploy

open `index.html` and update `og:url` near the top to your real github pages
link once it's live (search for `yourusername.github.io`).

## a heads up about the embed image

the preview image is baked directly into `index.html` as a data uri, so you
only need to deploy the one file. but discord (and twitter/slack) fetch the
`og:image` as a real url when building a link preview — they can't read a
data uri. so the image looks fine when you open the page yourself, but it
likely won't show up in discord's auto-embed when you paste the link.

if you want that rich discord embed to actually work, the image needs to be
hosted at a real url — e.g. commit an `og-image.png` back into the repo and
point `og:image` at its raw github pages url. happy to set that back up if
you'd rather have the working embed than the single-file version.

## live member widget

the channels section embeds a live discord widget (member count + avatars)
using your server id. this only shows anything if **server widget** is
turned on in discord: server settings → widget → enable server widget.
