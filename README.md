# [A blog I can run from a github codespace](https://yordan.llc)
[![Deploy Hugo site to GitHub Pages](https://github.com/fyordan/blog-from-codespace/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/fyordan/blog-from-codespace/actions/workflows/gh-pages.yml)

## Known Issues
* RSS Feed is not working

## Steps taken to reproduce this project

1. Created a Codespace in github to be able to run these commands on the cloud.
2. Installed library: [hugo](https://gohugo.io/installation/linux/)
   1. `sudo apt update`
   2. `sudo apt install hugo`
   3. Note: In my case I had to install hugo using wget and copying the binary into usr/local/bin/hugo in order to get hugo_extended
3. Use hugo and git to create the site directory
   1. `hugo new site hugo-site`
   2. `cd hugo-site`
4. Install Theme
   1. I looked at hugoplate and xmin but ended up with [hello-friend](https://themes.gohugo.io/themes/hugo-theme-hello-friend-ng/)
   2. `git submodule add https://github.com/rhazdon/hugo-theme-hello-friend-ng.git themes/hello-friend-ng`
6. Commit to git
   1. Make sure .gitignore will ignore the files you do not care about.
      1. hugo-site/public/
      2. hugo-site/resources/_gen/
   2. .github/workflows/gh-pages
      1. Make sure settings for gh-pages and actions are correct.
   3. Badge for workflow
7. Add new content
   1. `hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>`
   2. `hugo server --buildDrafts`
8. TODO:
   1. [X] Set github actions for releases
   2. [X] Confirm that I am able to add new content and preview from Ipad
   3. [x] Migrate content from wordpress
   4. [X] Set up DNS in Namecheap
   5. [ ] Deploy "preview" branches
   6. [ ] Create new themes

### Installing hugo+extended+withdeploy in codespaces
1. Find the release version in the official github [here](https://github.com/gohugoio/hugo/releases)
2. Find your architecture using `sudo uname -i`
3. Remove old versions of hugo (use `which hugo` to find the existing one)
4. Based on architecture and version number, run the following commands:
   1. `mkdir tmp && cd tmp`
   2. `wget https://github.com/gohugoio/hugo/releases/download/v<latest-version>/hugo_extended_<latest-version>_Linux-64bit.tar.gz`
   3. `tar -xzf hugo_extended_<latest-version>_Linux-64bit.tar.gz`
   4. `sudo mv hugo /usr/local/bin/`
   5. `cd .. && rm -r tmp`

### Recommended plugins for vscode
1. Vim
2. GitHub Actions
3. Hugo Language and Syntax Support
4. Markdown All in One

## Reproducing on nix
1. System-wide dependency: git
2. Project dependencies in shell.nix
3. Needs to run `git submodule update --init --recursive`
4. Can run `hugo server -D` after running `nix-shell` on root
