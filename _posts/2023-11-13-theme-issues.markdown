---
layout: post
title:  "Issues changing my Jekyll Theme"
date:   2023-11-13 00:01:00 -0300
categories: general
---
I've had a hard time switching to the hacker theme which ultimately ended in my sticking to the ugly but functional Minima Theme.

I started by following the Github Pages tutorial on themes and of course the [Hacker](https://pages.github.com/themes/) name caught my attention. For installation I followed the instructions on the [Github Pages How To](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll) which actually are different from the ones on the [Theme Github Repo](https://github.com/pages-themes/hacker).

Initially it was rendering either only the title like a hyperlink and later only a blank page, google gave this results that were similar to my issue:

[Post 1](https://stackoverflow.com/questions/75393879/why-is-my-completely-new-jekyll-blog-blank-when-i-add-the-supported-hacker-theme)

[Post 2](https://stackoverflow.com/questions/74904492/github-pages-site-will-not-load-any-theme-other-than-minima)

After that I went to bed because I was tired and frustrated.

In the morning after a second and more careful read of the above mentioned posts I noticed that I should look at the build logs and saw this on the `Build with Jekyll` section:

```
Build Warning: Layout 'page' requested in about.markdown does not exist.

Build Warning: Layout 'home' requested in index.markdown does not exist.
```

So I started googling that and arrived at [this](https://www.aleksandrhovhannisyan.com/blog/getting-started-with-jekyll-and-github-pages/)

The solution came from [this link](https://github.com/github/pages-gem/issues/416)

I understood that I should look at what the hacker theme has on the layouts and compare it to the error message, so I made some changes on the about.markdown and index.markdown files:

about:
`layout: page` to `layout: default`

index:
`layout: home` to `layout: post`

Now the build gave no warnings but it wasn't quite working yet:

![hacker-theme](/assets/hacker-theme.png)

So what's going on? As I understand the Hacker Theme does not use the same way of showing the posts as minima and that's why nothing is showing. I'm thinking of maybe creating my own theme? Might be interesting.
