# Gallery

A photo gallery built with [Hugo](https://gohugo.io/) and the
[Hugo Gallery theme](https://github.com/nicokaiser/hugo-theme-gallery).

## Run locally

Install Hugo Extended 0.123.0 or later and Go 1.20 or later, then run:

```sh
hugo server
```

Open the local address printed by Hugo.

## Add photos and albums

The easiest option is to drag photos into `content/gallery/`. JPG and PNG are
recommended; the theme advises against WebP. The photos in that folder appear
together in the **Gallery** album.

```text
content/
  landscapes/
    index.md
    mountain.jpg
    lake.jpg
```

To sort photos into albums, make a new folder directly inside `content/` (next
to `gallery`), copy `content/things/index.md` into it, change the `title` and
`description` at the top of the file, then drag the album's photos into that
same folder. For example:

```text
content/
  family/
    index.md
    birthday.jpg
  trips/
    index.md
    beach.jpg
```

The starter **Things** folder is ready to use: just drop photos into it. Empty
albums appear on the site after you add a photo. You can rename this folder or
create your own. Keep each album's `index.md` and photos together. To choose
the cover photo, set `resources.params.cover: true` for that image in the
album's `index.md`.

## Choose a large featured photo

The homepage can show one large featured album above the album cards. In that
album's `index.md`, add `params.featured: true` to the front matter. The large
image uses that album's cover photo (`resources.params.cover: true`). To change
it, mark a different photo as the cover. The theme displays the most recently
updated featured album, so remove `featured: true` from the old album if you
want a different one to be featured. Add `private: true` to an album's front
matter if you want it to appear only as the large featured item, not again in
the album list below.

## Publish

After adding photos or editing album folders, save the changes and push them to
the `main` branch to update the live site. The GitHub Actions workflow builds
and deploys the site automatically. In the repository settings, set **Pages →
Build and deployment → Source** to **GitHub Actions**.
