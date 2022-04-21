# samaparicio.github.io
For my static pages

This repo is "compiled" by Jekyll and auto-published by Github

To force a recompile, which is sometimes needed for updates, you can curl the Github API like so:

```
curl -X POST -H "Accept: application/vnd.github.v3+json" -U samaparicio https://api.github.com/repos/samaparicio/samaparicio.github.io/pages/builds
```
