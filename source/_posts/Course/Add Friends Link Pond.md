---
title: Add Friends Link Pond
categories:
  - Course
tags:
  - Hexo
cover: https://i.pinimg.com/originals/92/55/6d/92556dea468c37e1c1ebee41b7537c1b.jpg
abbrlink: d3883050
date: 2024-03-28 08:00:00
recommend: true
update: 2024-03-28 08:00:00
---

{% note 'success simple' %}
Before we begin: Starting from version 1.8.10, the theme will no longer include the Friends Link Pond. If you want to use it, please add it manually.

This tutorial uses the Friends Link Pond style of Hexo.
{% endnote %}

## Introduction

The Friends Link Pond is a way to display your friends' links and their latest articles, making your website more active.

## Tutorial

1. Create a page using the following command:
    ```bash
    hexo new page moments
    ```
2. Copy the following content to source/moments/index.md:
```markdown
---
title: Friends Link Pond
desc: Latest article subscription
date: 2024-01-28 21:29:15
type: "banner"
cover: ''
leftend: Subscribe to the latest articles of your friends' links using Friends Link Pond
---
## 🐟 Pond
<div id="hexo-circle-of-friends-root"></div>
<script>
    let UserConfig = {
        private_api_url: 'http://192.168.31.44:8000/', /* Replace with your API URL */
        page_turning_number: 12, /* Maximum number of articles to load when clicking "Load More", default is 10 */
        error_img: 'https://sdn.geekzu.org/avatar/57d8260dfb55501c37dde588e7c3852c', /* Default avatar URL when loading fails */
        sort_rule: 'created', /* Sorting rule for the first time entering the page */
    };
</script>
   
<style>
    .cf-article-group{
        margin: 0 -8px;
    }   
</style>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/zhheo/JS-Heo@master/mainColor/heoMainColor.css">
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/zhheo/JS-Heo@master/moments5/app.min.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/zhheo/JS-Heo@master/moments5/bundle.js"></script>
```

3. Modify the private_api_url to your API URL.
4. Regenerate your website using the following command:
    ```bash
    hexo clean && hexo g
    ```

## Adding Fishing

1. Add the following code at the top of moments/index.md (below the front-matter):
```markdown
<div class="title-h2-a">
    <div class="title-h2-a-left">
        <h2 style="padding-top: 0;margin:0.6rem 0 0.6rem;">🎣 Fishing</h2>
        <a href="javascript:fetchRandomPost();" id="random-post-start" style="transition-duration: 0.3s; transform: rotate(63000deg); opacity: 1;" data-pjax-state="">
            <i class="solitude st-restart-line"></i>
        </a>
    </div>
    <div class="title-h2-a-right">
        <a href="/links/" data-pjax-state="">All Links</a>
    </div>
</div>
<div id="random-post"></div>

<script>
var fdata = {
    apiurl: "http://192.168.31.44:8000/", /* Replace with your API URL */
    defaultFish: 100,
    hungryFish: 100,
}
</script>

<script type="text/javascript" src="https://cdn.cbd.int/solitude-source@1.0.5/js/moment/random_post.min.js"></script>
```

2. Add the following code inside the style tag in moments/index.md:
```css
#random-post {
  min-height: 32px;
  background: var(--efu-card-bg);
  border: var(--style-border-always);
  box-shadow: var(--efu-shadow-border);
  padding: 20px 30px;
  border-radius: 12px;
  margin-top: 8px;
}
.random-friends-post {
  text-decoration: none;
  border-bottom: 2px solid var(--efu-lighttext);
  color: var(--efu-fontcolor);
  font-weight: 700;
  padding: 0 4px;
}
.random-friends-post:hover {
  text-decoration: none;
  border-bottom: 2px solid var(--efu-none);
  color: var(--efu-white);
  background: var(--efu-main);
  border-radius: 4px;
  box-shadow: var(--efu-shadow-main);
}
.random-post-start {
  transition-duration: 0.3s;
}
.random-post-start:hover {
  color: var(--efu-hovertext);
}
#page .title-h2-a {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 0.5rem;
}
#page .title-h2-a a {
  margin-left: 0.5rem;
  color: var(--efu-secondtext);
  font-weight: 700;
}
#page .title-h2-a a:hover {
  color: var(--efu-main);
}
#page .title-h2-a .title-h2-a-left {
  display: flex;
  align-items: center;
}
#page .title-h2-a .title-h2-a-right {
  font-size: 14px;
  color: var(--efu-secondtext);
}
```

## Complete Code

```markdown
---
title: Friends Link Pond
desc: Latest article subscription
date: 2024-01-28 21:29:15
type: "banner"
cover: ''
leftend: Subscribe to the latest articles of your friends' links using Friends Link Pond
---

<div class="title-h2-a">
    <div class="title-h2-a-left">
        <h2 style="padding-top: 0;margin:0.6rem 0 0.6rem;">🎣 Fishing</h2>
        <a href="javascript:fetchRandomPost();" id="random-post-start" style="transition-duration: 0.3s; transform: rotate(63000deg); opacity: 1;" data-pjax-state="">
            <i class="solitude st-restart-line"></i>
        </a>
    </div>
    <div class="title-h2-a-right">
        <a href="/links/" data-pjax-state="">All Links</a>
    </div>
</div>
<div id="random-post"></div>

<script>
var fdata = {
    apiurl: "http://192.168.31.44:8000/", /* Replace with your API URL */
    defaultFish: 100,
    hungryFish: 100,
}
</script>

<script type="text/javascript" src="https://cdn.cbd.int/solitude-source@1.0.5/js/moment/random_post.min.js"></script>

## 🐟 Pond

<div id="hexo-circle-of-friends-root"></div>
<script>
    let UserConfig = {
        private_api_url: 'http://192.168.31.44:8000/', /* Replace with your API URL */
        page_turning_number: 12, /* Maximum number of articles to load when clicking "Load More", default is 10 */
        error_img: 'https://sdn.geekzu.org/avatar/57d8260dfb55501c37dde588e7c3852c', /* Default avatar URL when loading fails */
        sort_rule: 'created' /* Sorting rule for the first time entering the page */
    }
</script>
<style>
.cf-article-group {
    margin: 0 -8px;
} 
#random-post {
  min-height: 32px;
  background: var(--efu-card-bg);
  border: var(--style-border-always);
  box-shadow: var(--efu-shadow-border);
  padding: 20px 30px;
  border-radius: 12px;
  margin-top: 8px;
}
.random-friends-post {
  text-decoration: none;
  border-bottom: 2px solid var(--efu-lighttext);
  color: var(--efu-fontcolor);
  font-weight: 700;
  padding: 0 4px;
}
.random-friends-post:hover {
  text-decoration: none;
  border-bottom: 2px solid var(--efu-none);
  color: var(--efu-white);
  background: var(--efu-main);
  border-radius: 4px;
  box-shadow: var(--efu-shadow-main);
}
.random-post-start {
  transition-duration: 0.3s;
}
.random-post-start:hover {
  color: var(--efu-hovertext);
}
#page .title-h2-a {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 0.5rem;
}
#page .title-h2-a a {
  margin-left: 0.5rem;
  color: var(--efu-secondtext);
  font-weight: 700;
}
#page .title-h2-a a:hover {
  color: var(--efu-main);
}
#page .title-h2-a .title-h2-a-left {
  display: flex;
  align-items: center;
}
#page .title-h2-a .title-h2-a-right {
  font-size: 14px;
  color: var(--efu-secondtext);
}
</style>
```

## Result

![](https://s3.qjqq.cn/47/66223d41d13b2.webp!color)
