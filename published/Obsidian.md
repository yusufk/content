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

My publish script:
```
#!/bin/zsh

# Check if a commit message was provided
if [ $# -eq 0 ]; then
    echo "Error: Please provide a commit message"
    echo "Usage: publish \"your commit message\""
    exit 1
fi

# Store the commit message
commit_message="$1"

# Change to your repository directory
# Replace the following line with your actual repository path
if ! cd ~/Development/yusufkakacoza_content; then
    echo "Error: Could not change to repository directory"
    exit 1
fi

# Check if we're in a git repository
if ! git rev-parse --is-inside-work-tree >/dev/null 2>&1; then
    echo "Error: Not a git repository"
    exit 1
fi

# Add all changes
if ! git add .; then
    echo "Error: Failed to stage changes"
    exit 1
fi

# Commit with the provided message
if ! git commit -m "$commit_message"; then
    echo "Error: Failed to commit changes"
    exit 1
fi

# Push changes to the remote repository
if ! git push; then
    echo "Error: Failed to push changes"
    exit 1
fi

echo "Successfully published changes"
```