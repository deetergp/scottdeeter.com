---
layout: post
title: Using Drush to Download Repos
summary: I recently found myself in a situation where I needed to programmatically download a module's git repo rather than the module itself.
---

I recently found myself in a situation where I needed to programmatically download a module's git repo rather than the
module itself. We use Jenkins continuous integration at Classic to run a battery of tests against our repos. One such
test is `drush coder` which, when it it passes, is great. But when `drush coder --minor` finds a problem, it ends up
causing Drush to terminate abnormally and throw an error that says as much. Under normal circumstances, this wouldn't
be that big of a problem, since error reporting usually serves as a prompt to address develpers to fix the error and
move on. But in some rare instances, items flagged as errors need to be left in and Coder needs to be told to ignore
them.

Unfortunately, even when those ignore statments are added in the manner proscribed by Coder, and even when Drush
acknowledges the ignores by stating that "x issues were ignored", Drush will still terminate "abnormally". This behavior
causes problems for Jenkins, as it parses the console log, sees the "error" thrown when Drush terminates abnormally and
marks the build as failed.

After some digging, I discovered patch #13 [in this d.o issue](https://www.drupal.org/node/1974654) that allows you to
add the `--ignores-pass` switch and prevents `drush coder --minor` from terminating abnormally. With that solved, the
problem was pushed further down the chain. I needed a way to apply that patch to Coder at build time.

Enter the need to download a git repo.

After still more digging, I found [this post](https://www.drupal.org/node/1728116) which described how to use drush to
download the git repo and check out to the latest stable version of the module. The command looks something like this:

drush dl coder --package-handler=git_drupalorg

After running that command locally, I was able to go into the Coder directory and verify that it was checked out to the
latest stable version and that there was in fact a `.git` directory inside it. Of course, there still are a number of
other issues with this particular Jenkins build that I need to pursue, but I thought this bit was interesting and worth
sharing.