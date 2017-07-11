---
layout: post
---

之所以又搭了blog是因为i11r越来越那啥了，几乎上不去（可能github也是如此？），并且用git来写东西十分方便，并且想亲手搭一个试试看。

以下是Theme的介绍

A simple two-column jekyll theme delicated to wrting.

<!-- more -->

## Preview

#### Desktop
![](/images/desktop.png)

#### Mobile
![](/images/mobile.png)

## Features

1. pagination
2. comments
3. google analytics

## Install

1. create a repository named "username.github.io"
2. fork this reporsity to repo in step1, you should see the blog at 'http://username.github.io'
3. configure more below

Similar process with detailed page with gif can be seen [here](https://github.com/barryclark/jekyll-now/blob/master/README.md)


## Configure

In `_config.yml` file

```
title: Xian   # your title
author: Xian # your name
description: Just have some fun here # your description
avatar: /images/avatar.png # change avatar

```

You can uncomment to set disqus and google analytics.

```
# Comments
# disqus:
#   shortname: xxxx-xxxxx-xxx   # your disqus shortname

# Google Analytics
# google_analytics: xx-xxxxxxxx-1  # your google analytics
```

## Writing Blogs

Now you're all set, write articles and add to _posts folder, remember to name it as 'yyyy-mm-dd-your-article-title.md' and always add these lines to the begining your blog file.

```
---
layout: post 
---
```


## Thanks

[Farbtle](https://github.com/YCF/Farbtle) from [YCF](https://github.com/YCF), I steal a lot from him.
