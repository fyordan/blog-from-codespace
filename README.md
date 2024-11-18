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
7. Add new content
   1. `hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>`
   2. `hugo server --buildDrafts`
8. TODO:
   1. [ ] Set github actions for drafts and final releases
   2. [ ] Confirm that I am able to add new content and preview from Ipad
   3. [ ] Migrate content from wordpress
   4. [ ] Set up DNS in Namecheap
   5. [ ] Create new themes
