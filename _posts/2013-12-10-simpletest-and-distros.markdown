---
layout: post
title: SimpleTest and Distros
summary: Using SimpleTest to run tests against Drupal distributions.
---

A large amount of the Drupal work we do at [Classic Graphics](http://knowclassic.com) is based on distributions and
install profiles, which helps speed up a lot of the work we do by making it easier to manage updates and by having
some uniformity across our various projects. But it recently threw me for a loop when trying to write SimpleTests for
one of our projects. I could not seem to get the test case to enable any modules at all, in spite of the fact that I
had used the same syntax to enable modules for testing on other Drupal sites.

Fortunately for me, [Frippuz](https://drupal.org/user/396517) added
[this little bit of code](https://drupal.org/comment/4909532#comment-4909532) to the
[SimpleTest Tutorial (Drupal 7)](https://drupal.org/simpletest-tutorial-drupal7) describing that little something
extra needed in order to make SimpleTest work for installation profiles:

    <?php
        class MyTestCase extends DrupalWebTestCase
        // Needed to be able to test the module inside an installation profile
        protected $profile = 'my_profile';
        ...
    ?>

That was all that was needed for me to get SimpleTest enabling my modues the way I expected it to.