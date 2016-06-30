---
layout: post
title:  "Using tags and categories with Jekyll"
date:   2016-06-12 18:32:10 -0500
categories:  development
tags: [development, ruby, how to]
---

------------------------------------
                    |
                    |   pic
                    |---------------
      picture       |
                    |   pic
                    |---------------
                    |
                    |   pic



Knowing that I can categorize and tag certain posts i've set out to get a list of all the tags and catigories i use. To then use on other posts and the homepage to make it easier for users to navigate to simplar posts that may interest them. This is a good case of vocabulary meaning different things, becuase as yes you can add tags in the metdatada of each post there are also [ruby tags] (https://jekyllrb.com/docs/templates/#tags) you can insert into the page to populate types of data. I was searching for the former not the latter though google didn't know and provided both. In the end technically both are used.

The google searches:
- jekyll tags
- jekyll catigories
- jekyll tag page
- jekyll liquid tags in markdown

*Sources*
https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/
didn't work on first try, or second *2015*

https://www.chrisanthropic.com/blog/2014/jekyll-themed-category-pages-without-plugins/ *2014*
sort of worked, not really 'all there'

http://christianspecht.de/2014/10/25/separate-pages-per-tag-category-with-jekyll-without-plugins/ *2014*
sort of worked, not really 'all there'

http://charliepark.org/tags-in-jekyll/ *2011*
didn't say where to go to see if it worked or where else to put the code so files are newly made and have stuff that doesn't break the site. But there's no visual list of tags.

http://www.mikeapted.com/jekyll/2015/12/30/category-and-tag-archives-in-jekyll-no-plugins/ *2015*

http://stackoverflow.com/questions/11887929/how-do-i-loop-through-tags-in-a-jekyll-post *1013*
Turns out this lead me down the right path, or a combination of seeing the above and then this one.
what the page had:

```
<tr>
{% for tag in page.tags %}
<td>{{ tag }}</td>
{% endfor %}
</tr>
```

translates to

```
create a table row
- loop through the tags of each page and store it as tag
create a table data, but the thing you stored in 'tag' here
- stop looping
end the table row
```

After changing `tr`'s to `ul`'s I initially put this snippet on the index page, where the list of posts were. It didn't show anything, after further looking it wouldn't because it's referencing looking at tags of a page. So i put the code snippet in a post and looked for the results. It looped through the tags and listed them.


After this success i moved on to produce the result i desired, a list of all the tags used through out the site. I tweaked the code and played with the results.

tried

<img src="/images/codesnippet.png" alt="">

resulted in

<img src="/images/posts_under_catigory.png" alt="">

It repeated each post over 20 times, with header and fooder included on each post but listed under a catigory,so, progress.






