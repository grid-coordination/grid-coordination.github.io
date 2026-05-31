# Grid Coordination

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Grid%20Coordination-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/company/grid-coordination)
[![Slack](https://img.shields.io/badge/Slack-Grid%20Coordination-4A154B?logo=slack&logoColor=white)](https://grid-coordination.slack.com)
[![GitHub](https://img.shields.io/badge/GitHub-grid--coordination-181717?logo=github&logoColor=white)](https://github.com/grid-coordination)

Source for the [Grid Coordination](https://grid-coordination.energy) website — an initiative defining the architecture of the future electric grid through open standards, policy advocacy, and working software.

## Connect

- [LinkedIn](https://www.linkedin.com/company/grid-coordination)
- [Slack](https://grid-coordination.slack.com)
- [GitHub](https://github.com/grid-coordination)
- [Email](mailto:grid-coordination@clark-communications.com)

## Live site

- Production: <https://grid-coordination.energy>
- Live OpenADR 3 price server: <https://price.grid-coordination.energy/openadr3/3.1.0/>

## How it's built

Static site rendered by [Jekyll](https://jekyllrb.com/) and deployed via GitHub Pages. The site is the Markdown files at the repo root (`index.md`, `vision.md`, `software.md`, …) plus the layout in `_layouts/default.html`. Presentations live under `presentations/` and the placeholder logo under `images/`.

Local preview:

```bash
bundle exec jekyll serve
```
