# Example Static Content Repo For Wiki Instances
![Arcetypal Repo](archetypal-heading.jpg)
1. Sync Markdown content into `content` directory to be consumed by private Wiki Instance.
2. Markdown can be Frontmatter decorated.
3. Ensure Repo emits `dispatch.yml` to trigger workflow in order to rebuild site once content updates.
    * create repo secret: `REPO_PAT` : `paste in org PAT - github_pat_***`
      * requires Organisaztion PAT
      * Read access to metadata
      * Read & Write to Contents
    * create repo variable: `REPO_OWNER`
    * create repo variable: `REPO_NAME`
    * create repo variable: `EVENT` and use value: `TRIGGER_BUILD`
4. Connect workflows with other REPO by having a consuming end:
*workflow*
```
on:
    repository_dispatch:
        types:
            - TRIGGER_BUILD
```
### Frontmatter
Current available fields:
```
---
description: SEO powers for wiki specific page
published: true # also defaults to true (sets visibility)
pin: 1111 # will lock page privately behind a hash
tags: ['blog']
---
```

---
## Welcome to Community content

This would be a community facing **public** repo.
Rules and regs in order to submit PRs
