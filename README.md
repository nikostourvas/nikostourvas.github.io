# nikostourvas.github.io

Personal website of Nikos Tourvas, live at <https://nikostourvas.github.io>.

Built with [Jekyll](https://jekyllrb.com/) from the [Academic Pages](https://github.com/academicpages/academicpages.github.io)
template (copied in December 2024, not synced with it since). GitHub Pages rebuilds the site
automatically on every push to `master`; build status is in the repository's **Actions** tab.

## Where things are

| To change…                                   | Edit                                      |
|----------------------------------------------|-------------------------------------------|
| Name, bio, sidebar links, site description   | `_config.yml` (`author:` section)         |
| Top menu                                     | `_data/navigation.yml`                    |
| Home page text and photo                     | `_pages/about.md`                         |
| Software entries                             | one `.md` file per tool in `_software/`   |
| CV and other downloadable files              | `files/` (served at `/files/<name>`)      |
| Images                                       | `images/`                                 |

The other folders (`_includes`, `_layouts`, `_sass`, `assets`) are the template's internals.

## Preview locally

Needs Docker. Build the image once:

```bash
docker build -t academic-pages .
```

Then, from this folder:

```bash
docker run -p 4000:4000 --rm -v "$PWD":/usr/src/app academic-pages
```

Open <http://localhost:4000>. Pages refresh on save; restart after editing `_config.yml`.
If it fails with `Could not find jekyll-…`, delete `Gemfile.lock` (it is regenerated) and try again.

## Publish

```bash
git add -A
git commit -m "what changed"
git push
```
