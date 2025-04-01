---
kernelspec:
  name: python3
  display_name: Python

title: Template Metrics
subtitle: Use Jupyter Execution to Find the Number of Stars
---

# Template Metrics

This page is an example of an executable document. Here's some code that queries the GitHub API:

```{code-cell} python3
:class: glow

import urllib.request
import json

headers = {
    "Accept": "application/vnd.github+json",
    "X-GitHub-Api-Version": "2022-11-28",
}

request = urllib.request.Request(
    "https://api.github.com/repos/2i2c-org/community-docs-template/stargazers",
    headers=headers,
)

with urllib.request.urlopen(request) as f:
    stargazers = json.load(f)

n_stars = len(stargazers)
star_text = "is 1 star" if n_stars == 1 else "are {n_stars} stars"
```

% Use an eval-expression to compute the number of stars.
There {eval}`star_text` on this template!
