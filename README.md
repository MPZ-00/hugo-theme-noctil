# noctil
A minimal, terminal-inspired Hugo theme for documenting things I build.

Dark, monospace, and simple. The home page can show a projects section: pinned write-ups on top, everything else as a dated log below. Other sections can be kept off the home page and out of the feed, but still reachable by link.

Inspired by [Terminal](https://github.com/panr/hugo-theme-terminal) by panr.

## Install
```sh
git submodule add https://github.com/MPZ-00/hugo-theme-noctil themes/noctil
```

Then set `theme = "noctil"` in your site config. Needs Hugo 0.147 or newer.

## Example config
```toml
theme = "noctil"
title = "my site"

[params]
logoText = "~/me"
hiddenSections = ["notes"]

[params.intro]
title = "hi"
text = "Things I build, and how."

[[params.footerLinks]]
name = "github"
url = "https://github.com/you"

[[menus.main]]
name = "projects"
url = "/projects/"
```

A project page:
```yaml
---
title: Weather station
date: 2026-09-14
summary: ESP32 sensor node that logs to a small dashboard.
stack: C++
tags: [esp32, iot]
repo: https://github.com/you/weather-station
pinned: true
---
```

## Params
All optional.

| Param | Type | Default | What it does |
|---|---|---|---|
| `logoText` | string | site title | Text in the logo block |
| `subtitle` | string | none | Meta description of the home page |
| `image` | string | none | Link preview image (`og:image`), relative to `static/`. A page's own `image` overrides it and can name a file in its page bundle |
| `dateFormat` | string | `2006-01-02` | Go date layout for displayed dates |
| `showcaseSection` | string | `projects` | Section shown as pinned blocks and log on the home page |
| `hiddenSections` | list | `[]` | Sections kept off the home page and the RSS feed |
| `intro.title` | string | none | Home page heading |
| `intro.text` | string | none | Line under the home page heading |
| `footerLinks` | list of `{name, url}` | none | Links on the right side of the footer |

Page front matter used by the showcase: `summary`, `stack`, `tags`, `repo`, `pinned`, and `dateApprox` (shows `~YYYY` instead of the full date).

## Font
JetBrains Mono is bundled under the SIL Open Font License 1.1 (`static/fonts/OFL.txt`). No external font requests.

## License
MIT, see [LICENSE](LICENSE).
