# ECONS 431 course website

Source for the course site at https://wsu-econs431.github.io/site/ ,
built with [Quarto](https://quarto.org).

## Work on the site

```
uv sync                      # once: build the course Python environment
uv run quarto preview        # live preview in your browser; refreshes on save
```

`uv run` makes Quarto run notebook code with the course environment (the same
`pyproject.toml` and `uv.lock` the students use). A "Kernel is running over TCP
without encryption" warning while rendering is harmless.

## Publish

```
git add .
git commit -m "Describe the change"
git push                     # saves the source
uv run quarto publish gh-pages   # updates the live site
```

The first time, confirm under the repo's Settings > Pages that the site is
served from the `gh-pages` branch.

## Files

- `_quarto.yml`: site settings and navigation bar
- `index.qmd`, `schedule.qmd`, `setup.qmd`, `setup-faq.qmd`, `policies.qmd`: pages
- `weeks/`: lecture notebooks, one per week
- `_freeze/`: saved notebook results (commit this; Quarto re-runs a notebook only when it changes)
