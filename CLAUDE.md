# baune8d.github.io

Personal resumé site at https://baunegaard.net, in Danish. A Jekyll site with the remote theme [sproogen/resume-theme](https://github.com/sproogen/resume-theme). All content is in `_config.yml`: the about section (`about_content`) and the `content` sections (projects, experience, education).

## Workflow

- Conventional commits (`feat:`, `fix:`, `chore(deps):`, `ci:`, `build:`, `docs:`), one commit per concern, directly on `main`.
- Only push, tag, publish or edit GitHub releases when asked.
- Commit messages must be accurate. If one turns out to be wrong before it is pushed, reword it (replay the commits and check that the tree is unchanged). Never rewrite pushed history.

## Building

- `bundle install`, then `bundle exec jekyll serve` (http://localhost:4000), or `bundle exec jekyll build` to write `_site/`.
- CI builds the site on every pull request and push, and deploys it to GitHub Pages from `main`, so every push to `main` publishes the site.
- The site uses Jekyll 3.10, the version the GitHub Pages branch build used, and fetches the theme from GitHub when it builds (jekyll-remote-theme).
- `url` and `description` in `_config.yml` replace what the github-pages gem filled in from GitHub. jekyll-seo-tag uses them.
- The custom domain is set in the repository's Pages settings. Deployments from Actions don't read the `CNAME` file.
- After changing a dependency or the theme, compare the built `_site/index.html` and `assets/main.css` with the live site.

## Dependencies

- Dependabot runs weekly on Monday with a 7-day cooldown. Minor/patch updates are grouped; security updates have their own group.
- Major versions are ignored by Dependabot and upgraded by hand: read the release notes, update, and build before committing. Jekyll 4 would also move Sass to jekyll-sass-converter 3 (Dart Sass), so check the theme's styles too.
- New exceptions go in `.github/dependabot.yml` with a comment explaining why.

## Content

- The project list mirrors the repositories: their GitHub descriptions as the quote, and the README badges. Update it when a repository is renamed or its description or badges change.
- The profile README (Baune8D/Baune8D) has a project list too; keep both in step.
