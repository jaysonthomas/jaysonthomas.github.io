# al-folio

<!--ts-->

- [al-folio](#al-folio)
  - [Getting started](#getting-started)
  - [Installing and Deploying](#installing-and-deploying)
  - [Customizing](#customizing)
  - [Plugin Ecosystem](#plugin-ecosystem)
  - [Using AI Agents](#using-ai-agents)
    - [Codex](#codex)
    - [Claude](#claude)
    - [Copilot And Other Agents](#copilot-and-other-agents)
  - [Documentation](#documentation)
  - [Features](#features)
    - [Light/Dark Mode](#lightdark-mode)
    - [CV](#cv)
    - [People](#people)
    - [Publications](#publications)
    - [Collections](#collections)
    - [Layouts](#layouts)
      - [The iconic style of Distill](#the-iconic-style-of-distill)
      - [Full support for math &amp; code](#full-support-for-math--code)
      - [Photos, Audio, Video and more](#photos-audio-video-and-more)
    - [Other features](#other-features)
      - [GitHub's repositories and user stats](#githubs-repositories-and-user-stats)
      - [Theming](#theming)
      - [Social media previews](#social-media-previews)
      - [Atom (RSS-like) Feed](#atom-rss-like-feed)
      - [Related posts](#related-posts)
      - [Code quality checks](#code-quality-checks)
      - [GDPR Cookie Consent Dialog](#gdpr-cookie-consent-dialog)
  - [FAQ](#faq)
  - [Contributing](#contributing)
    - [Maintainers](#maintainers)
    - [All Contributors](#all-contributors)
  - [Star History](#star-history)
  - [License](#license)

<!--te-->

## Getting started

**⚠️ Important: Use "Use this template" (not fork)**

When creating your own website with al-folio, you have two options:

- ✅ **Recommended:** Click "[Use this template](https://github.com/new?template_name=al-folio&template_owner=alshedivat)" – This creates a clean copy that is independent from the main al-folio repository. Changes you make to your site won't be accidentally submitted to al-folio as pull requests.
- ❌ **Not recommended:** Forking the repository – This keeps a link to the main al-folio repo, making it easy to accidentally submit your personal site changes as contributions to our project.

**If you already forked:** Don't worry! You can still work with your fork normally. Just make sure to:

1. Make changes on a dedicated branch (e.g., `my-site-updates`)
2. When pushing changes, always verify you're pushing to **your own repository**, not the main al-folio repository
3. Never create pull requests to `alshedivat/al-folio` unless you're intentionally contributing improvements that benefit all users

For quick setup, see [docs/QUICKSTART.md](docs/QUICKSTART.md).

Want to learn more about Jekyll? Check out [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/). Why Jekyll? Read [Andrej Karpathy's blog post](https://karpathy.github.io/2014/07/01/switching-to-jekyll/)! Why write a blog? Read [Rachel Thomas blog post](https://medium.com/@racheltho/why-you-yes-you-should-blog-7d2544ac1045).

## Installing and Deploying

For installation and deployment details please refer to [docs/INSTALL.md](docs/INSTALL.md).

## Customizing

For customization details please refer to [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

## Plugin Ecosystem

`al-folio` is a thin starter in `v1.x`. Runtime features are plugin-owned and published as Ruby gems.

- Ownership boundaries: [docs/BOUNDARIES.md](docs/BOUNDARIES.md)
- Plugin catalog metadata: [`_data/featured_plugins.yml`](_data/featured_plugins.yml)
- Plugin catalog page source: [`_pages/plugins.md`](_pages/plugins.md)

Naming convention:

- Theme-coupled plugins use `al-folio-<feature>` repos and `al_folio_<feature>` gem/plugin ids.
- Reusable plugins can use `al-<feature>` or neutral naming.

Featured plugins and bundled starter plugins are different tracks. Bundling requires explicit updates to [Gemfile](Gemfile) and [\_config.yml](_config.yml).
Plugin-owned changes should be made in the owning `al-org-dev` plugin repository, not by copying runtime assets into this starter.
The bundled v1 plugin repos are:

- [`al-folio-core`](https://github.com/al-org-dev/al-folio-core): shared layouts, includes, style/runtime primitives, and upgrade contracts
- [`al-folio-cv`](https://github.com/al-org-dev/al-folio-cv): CV rendering
- [`al-folio-distill`](https://github.com/al-org-dev/al-folio-distill): Distill layouts and runtime assets
- [`al-folio-bootstrap-compat`](https://github.com/al-org-dev/al-folio-bootstrap-compat): temporary Bootstrap compatibility runtime
- [`al-folio-upgrade`](https://github.com/al-org-dev/al-folio-upgrade): v1 upgrade audit/report/codemods
- [`al-icons`](https://github.com/al-org-dev/al-icons): icon loading
- [`al-search`](https://github.com/al-org-dev/al-search): search runtime
- [`al-citations`](https://github.com/al-org-dev/al-citations): publication/citation helpers
- [`al-ext-posts`](https://github.com/al-org-dev/al-ext-posts): external post ingestion
- [`al-analytics`](https://github.com/al-org-dev/al-analytics), [`al-comments`](https://github.com/al-org-dev/al-comments), [`al-cookie`](https://github.com/al-org-dev/al-cookie), [`al-img-tools`](https://github.com/al-org-dev/al-img-tools), [`al-math`](https://github.com/al-org-dev/al-math), [`al-charts`](https://github.com/al-org-dev/al-charts), and [`al-newsletter`](https://github.com/al-org-dev/al-newsletter): feature-specific runtime and integration behavior

## Documentation

Comprehensive guides for all aspects of your al-folio website:

- **[Documentation index](docs/README.md)** – All user, maintainer, and migration guides
- **[Quick Start](docs/QUICKSTART.md)** – Get running in 5 minutes
- **[Installation & Deployment](docs/INSTALL.md)** – Set up your site on GitHub Pages or other platforms
- **[Customization Guide](docs/CUSTOMIZE.md)** – Personalize your website (CVs, publications, themes, etc.)
- **[Troubleshooting](docs/TROUBLESHOOTING.md)** – Fix common issues (deployment, build, styling, content)
- **[FAQ](docs/FAQ.md)** – Frequently asked questions and solutions
- **[Analytics](docs/ANALYTICS.md)** – Add website analytics and visitor tracking
- **[SEO Guide](docs/SEO.md)** – Optimize for search engines and improve discoverability
- **[Plugin Catalog](_pages/plugins.md)** – Featured and bundled plugin metadata

## Features

### Light/Dark Mode

This template has a built-in light/dark mode. It detects the user preferred color scheme and automatically switches to it. You can also manually switch between light and dark mode by clicking on the sun/moon icon in the top right corner of the page.

<p align="center">
<img src="readme_preview/light.png" width=400>
<img src="readme_preview/dark.png" width=400>
</p>

---

### CV

Your CV can be generated in one of two modern formats: **RenderCV** (recommended, with automatic PDF generation) or **JSONResume** (standardized JSON format). You can use both simultaneously and switch between them, or maintain just the one you prefer.

[![CV Preview](readme_preview/cv.png)](https://alshedivat.github.io/al-folio/cv/)

For setup and customization details, see [Modifying the CV information](docs/CUSTOMIZE.md#modifying-the-cv-information) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

### People

You can create a people page if you want to feature more than one person. Each person can have its own short bio, profile picture, and you can also set if every person will appear at the same or opposite sides.

[![People Preview](readme_preview/people.png)](https://alshedivat.github.io/al-folio/people/)

---

### Publications

Your publications page is generated automatically from your BibTeX bibliography. You can customize publication display, add extra information like PDFs, and control sorting behavior.

[![Publications Preview](readme_preview/publications.png)](https://alshedivat.github.io/al-folio/publications/)

For setup, BibTeX field documentation, and customization options, see [Adding a new publication](docs/CUSTOMIZE.md#adding-a-new-publication) and [Managing publication display](docs/CUSTOMIZE.md#managing-publication-display) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

### Collections

This Jekyll theme implements `collections` to organize content into categories. The theme comes with default collections for `news`, `projects`, `books`, and `teachings`. You can easily create your own collections for apps, stories, courses, or any other creative work.

[![Projects Preview](readme_preview/projects.png)](https://alshedivat.github.io/al-folio/projects/)

For detailed instructions on creating and customizing collections, see [Adding Collections](docs/CUSTOMIZE.md#adding-collections) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

### Layouts

**al-folio** comes with stylish layouts for pages and blog posts.

#### The iconic style of Distill

The theme allows you to create blog posts in the [distill.pub](https://distill.pub/) style:

[![Distill Preview](readme_preview/distill.png)](https://alshedivat.github.io/al-folio/blog/2021/distill/)

For more details on how to create distill-styled posts using `<d-*>` tags, please refer to [the example](https://alshedivat.github.io/al-folio/blog/2021/distill/).

#### Full support for math & code

**al-folio** supports fast math typesetting through [MathJax](https://www.mathjax.org/) and code syntax highlighting using [GitHub style](https://github.com/jwarby/jekyll-pygments-themes). Also supports [chartjs charts](https://www.chartjs.org/), [mermaid diagrams](https://mermaid-js.github.io/mermaid/#/), and [TikZ figures](https://tikzjax.com/).

<p align="center">
<a href="https://alshedivat.github.io/al-folio/blog/2015/math/" target="_blank"><img src="readme_preview/math.png" width=400></a>
<a href="https://alshedivat.github.io/al-folio/blog/2015/code/" target="_blank"><img src="readme_preview/code.png" width=400></a>
</p>

#### Photos, Audio, Video and more

Photo formatting is made simple using Tailwind-first responsive layout utilities. Easily create beautiful grids within your blog posts and project pages, also with support for [video](https://alshedivat.github.io/al-folio/blog/2023/videos/) and [audio](https://alshedivat.github.io/al-folio/blog/2023/audios/) embeds:

<p align="center">
  <a href="https://alshedivat.github.io/al-folio/projects/1_project/">
    <img src="readme_preview/photos-screenshot.png" width="75%">
  </a>
</p>

---

### Other features

#### GitHub's repositories and user stats

**al-folio** displays GitHub repositories and user stats on the `/repositories/` page using [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) and [github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy).

[![Repositories Preview](readme_preview/repositories.png)](https://alshedivat.github.io/al-folio/repositories/)

To configure which repositories and GitHub profiles to display, see [Modifying the user and repository information](docs/CUSTOMIZE.md#modifying-the-user-and-repository-information) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

#### Theming

**al-folio** offers a variety of beautiful theme colors to choose from. The default is purple, but you can customize colors, fonts, spacing, and more to match your style.

For detailed customization instructions, see [Changing theme color](docs/CUSTOMIZE.md#changing-theme-color) and [Customizing fonts, spacing, and more](docs/CUSTOMIZE.md#customizing-fonts-spacing-and-more) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

#### Social media previews

**al-folio** supports Open Graph preview images on social media. When enabled, your site's pages display rich preview objects with images, titles, and descriptions when shared.

For setup and customization, see [Social media previews](docs/CUSTOMIZE.md#social-media-previews) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

#### Atom (RSS-like) Feed

It generates an Atom (RSS-like) feed of your posts, useful for Atom and RSS readers. The feed is reachable simply by typing after your homepage `/feed.xml`. E.g. assuming your website mountpoint is the main folder, you can type `yourusername.github.io/feed.xml`

---

#### Related posts

By default, blog posts display related posts at the bottom. These are selected by finding the most recent posts that share tags with the current post. You can customize this behavior on a per-post or site-wide basis.

For configuration details, see [Related posts](docs/CUSTOMIZE.md#related-posts) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

---

#### Code quality checks

Currently, we run some checks to ensure that the code quality and generated site are good. The checks are done using GitHub Actions and the following tools:

- [Prettier](https://prettier.io/) - check if the formatting of the code follows the style guide
- [lychee](https://lychee.cli.rs/) - check for broken links
- [Axe](https://github.com/dequelabs/axe-core) (need to run manually) - do some accessibility testing

We decided to keep `Axe` runs manual because fixing the issues are not straightforward and might be hard for people without web development knowledge.

---

#### GDPR Cookie Consent Dialog

**al-folio** includes a GDPR-compliant cookie consent dialog provided by the `al_cookie` plugin to ensure your website respects visitor privacy. The dialog is powered by [Vanilla Cookie Consent](https://cookieconsent.orestbida.com/) and integrates seamlessly with all supported analytics providers.

When enabled, analytics scripts are blocked until the user explicitly consents, and user preferences are saved across visits. This is essential for websites serving visitors in the European Union and other regions with strict privacy regulations.

For complete setup and customization details, see [GDPR Cookie Consent Dialog](docs/CUSTOMIZE.md#gdpr-cookie-consent-dialog) in [docs/CUSTOMIZE.md](docs/CUSTOMIZE.md).

## FAQ

For frequently asked questions, please refer to [docs/FAQ.md](docs/FAQ.md).

## Contributing

Contributions to al-folio are very welcome! Before you get started, please take a look at [the guidelines](docs/CONTRIBUTING.md).

If you would like to improve documentation or fix a minor inconsistency or bug, please feel free to send a PR directly to `main`. For more complex issues/bugs or feature requests, please open an issue using the appropriate template.

### Maintainers

Our most active contributors are welcome to join the maintainers team. If you are interested, please reach out!

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://maruan.alshedivat.com"><img src="https://avatars.githubusercontent.com/u/2126561?v=4" width="100px;" alt=""/><br /><sub><b>Maruan</b></sub></a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://rohandebsarkar.github.io"><img src="https://avatars.githubusercontent.com/u/50144004?v=4" width="100px;" alt=""/><br /><sub><b>Rohan Deb Sarkar</b></sub></a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://amirpourmand.ir"><img src="https://avatars.githubusercontent.com/u/32064808?v=4" width="100px;" alt=""/><br /><sub><b>Amir Pourmand</b></sub></a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://george-gca.github.io/"><img src="https://avatars.githubusercontent.com/u/31376482?v=4" width="100px;" alt=""/><br /><sub><b>George</b></sub></a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

### All Contributors

<a href="https://contrib.rocks">
  <img src="https://contrib.rocks/image?repo=alshedivat/al-folio&max=500&columns=24" />
</a>

## Star History

<a href="https://star-history.com/#alshedivat/al-folio&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=alshedivat/al-folio&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=alshedivat/al-folio&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=alshedivat/al-folio&type=Date" />
  </picture>
</a>

## License

The theme is available as open source under the terms of the [MIT License](https://github.com/alshedivat/al-folio/blob/main/LICENSE).

Originally, **al-folio** was based on the [\*folio theme](https://github.com/bogoli/-folio) (published by [Lia Bogoev](https://liabogoev.com) and under the MIT license). Since then, it got a full re-write of the styles and many additional cool features.
