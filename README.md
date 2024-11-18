## Steps taken to reproduce this project

1. Created a Codespace in github to be able to run these commands on the cloud.
2. Installed library: [hugo](https://gohugo.io/installation/linux/)
   1. `sudo apt update`
   2. `sudo apt install hugo`
3. Use hugo and git to create the site directory
   1. `hugo new site hugo-site`
   2. `cd hugo-site`
4. Install Theme
   1. I looked at hugoplate and xmin but ended up with [hello-friend](https://themes.gohugo.io/themes/hugo-theme-hello-friend-ng/)
   2. `git submodule add https://github.com/rhazdon/hugo-theme-hello-friend-ng.git themes/hello-friend-ng`
5. Commit to git
6. Add new content
   1. `hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>`
   2. `hugo server --buildDrafts`
7. TODO:
   1. [ ] Set github actions for drafts and final releases
   2. [ ] Confirm that I am able to add new content and preview from Ipad
   3. [ ] Migrate content from wordpress
   4. [ ] Set up DNS in Namecheap
   5. [ ] Create new themes
