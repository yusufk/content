<!--
title: Experimenting with Obsidian for content
date: 2025-02-16
--->
It's done. Going forward, I will be using [Obsidian](https://obsidian.md/) for content management on yusuf.kaka.co.za 

To achieve this, I've setup a 2nd Github repo, with only the content for the site, and enabled GitHub pages. I anticipated having weird CORS related issued, but since GitHub applied my custom URL to *all* my repos, I didn't. I just needed to be thoughtful about the path / folder.

Another key step was creating the index file on-the-fly, and for this, I used GitHub actions to add all markdown files to the index.

```
- name: Generate index.json

run: |

cd published

files=$(find . -maxdepth 1 -name "*.md" -type f -exec basename {} \; | jq -R . | jq -s .)

echo $files > index.json
```

The other key step was to use the Obsidian vault as a GIT repo so that updates can be published.