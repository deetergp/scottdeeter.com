---
layout: post
title: Nuggets from DrupalCamp Atlanta
summary: My thoughts and takeaways from DrupalCamp Atlanta 2013.
---

This past weekend, I came away from DrupalCamp Atlanta with my head over-stuffed with ideas, thanks to their
high-calibre presentations. Before I got too distracted with my day-to-day, I thought I might take a moment to put
some of them here.

[Mike Herchel's](https://twitter.com/mikeherchel) talk,
"[46 Rules and Techniques to Make Drupal Hella-Fast!](https://www.drupalcampatlanta.com/session/46-rules-and-techniques-make-drupal-hella-fast),"
left me with the desire to [be somebody](http://www.youtube.com/watch?v=MAtyiPZUVVg)—somebody that keeps it simple,
checks slow query logs, uses CDNs, and stays in school, fool!. "Reverse proxy caching" and "Varnish" were terms I
had heard thrown around for a while but in his talk, Mike's put them into perspective. Allowing your anonymous users
to get their data without ever even having to dip into Drupal and using resources like [jsperf.com](jsperf.com),
[High Performance on groups.drupal.org](https://groups.drupal.org/high-performance), and [2bits.com](2bits.com) to
tune your code, all seem like great ways to improve user experience on your site.

By now, I am convinced that [Ken Rickard](https://drupal.org/user/20975) could read the phonebook to a crowd and make
it both entertaining and insightful. Knowing Ken's reputation, and appreciating the winking hat-tip to
*[Dr. Strangelove](http://www.amazon.com/gp/product/B000P407K4/ref=atv_feed_catalog?tag=imdb-amazonvideo-20)*, his presentation,
"[How I Learned to Stop Worrying and Love Drupal 8](https://www.drupalcampatlanta.com/session/how-i-learned-stop-worrying-and-love-drupal-8),"
did not disappoint. Ken made it plain that Drupal 8's sights were set plainly on the Enterprise, hence its shift
toward shedding the "not invented here" attitude of the past, adopting OOP code over its Procedural roots, and moving
configuration into the filesystem for better VCS compatibility. I left his presentation now ready to dig into D8 and
with a good idea of what the next steps were for me to do so.

I was particularly interested in [Ryan Szrama](https://drupal.org/user/49344) &
[Josh Miller's](http://commerceguys.com/users/josh) talk on the Commerce Module,
"[Architecting Drupal Commerce Sites](https://www.drupalcampatlanta.com/session/architecting-drupal-commerce-sites),"
for many reasons; one small reason being that I am in the middle of a Commerce project at work. An important but
simple revelation for me was that Commerce was built with the intent of putting SKUs on all the things.
(No, *really*!) SKUing each variation and permutation of the items in your store will make it easier to display
your products, easier to order them, and easier to report on them as you go. And the way the Commerce Card On File
module generates tokens with payment processors to allow recurring payments without having to store credit card
numbers in Drupal is downright impressive! No need to sweat over getting and maintaining PCI-DSS compliance.

This was my second DrupalCamp Atlanta. Last year's was a great camp and this one was even better. The MediaCurrent
folks did a great job making sure the speakers were high-quality, that the subjects were relevant and engaging, and
the event ran buttery-smooth. I would say that, based on their performance this weekend, DC ATL would have a permanent
place on my calendar, but that would be a lie. Last year's camp was that good. DrupalCamp Atlanta is a lock for me
until they decide to stop doing it.
