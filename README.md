# syskasnippets

<!-- badges: start -->
[![Travis build status](https://travis-ci.org/murraycadzow/syskasnippets.svg?branch=master)](https://travis-ci.org/murraycadzow/syskasnippets)
<!-- badges: end -->

The source files that are used with the blogdown R package to create the blog site https://otagostudygroup.github.io/syskasnippets/

Currently the blog is compiled using tavis-ci which enables others to add posts by following a few steps:

Some familiarity with using github is assumed for this process

You don't need to have `blogdown` installed locally but it makes it much easier,

0. (If you don't already have it) install the R package blogdown `install.packages("blogdown")`
1. Fork the repo and then clone your copy to make it local for you
2. Open the project up in RStudio
3. - easiest: Use the "New Post" rstudio addin to open a dialog box to fill in the details
      - see https://bookdown.org/yihui/blogdown/rstudio-ide.html for extra details 
   - harder: create a new Rmd or md post with `blogdown::new_post()` or copy and rename an old post and alter the details
      - source files for posts are stored in `content/post/`
4. Preview your post with `blogdown::build_site(local = TRUE)`
5. When happy with content and successfully building do the following on the **master** branch:
  - `git add` your post .Rmd, .Rmarkdown or .md file
  - `git commit`
  - `git pull` 
  - `git push`
6. On github create a pull request for your repo to send the changes to otagostudygroup/syskasnippets


An excellent reference for creating blogdown posts is https://bookdown.org/yihui/blogdown/

For reference on RMarkdown refer to https://bookdown.org/yihui/rmarkdown/
