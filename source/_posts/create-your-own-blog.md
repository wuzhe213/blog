---
title: Create Your Own Blog
tags: [blog, hexo]
categories: []
date: 2018-07-02 
---

# Create your own blog with hexo

create a repo on github
my repo: wuzhe213/blog

create a hexo blog on local
```bash
create blog
cd blog

npm install hexo-cli -g
hexo init
hexo server  # to test <br/>

```

push your blog to github
```bash
git init
git remote add origin https://github.com/wuzhe213/blog.git

git add .
git commit -m "init blog"
git push -u origin master
```

customize your blog
I want my blog can have search function.
So searched on https://hexo.io/themes/, and found a theme called "aria"
the instruction below is following https://github.com/AlynxZhou/hexo-theme-aria

In order to customize theme aria, and record modification, fork repo https://github.com/AlynxZhou/hexo-theme-aria on github,
So, I will have a repo named https://github.com/wuzhe213/hexo-theme-aria.git

```bash
cd blog  # if you not in root directory of your blog
npm install --save hexo-renderer-njucks hexo-renderer-stylus hexo-generator-search hexo-generator-feed
git add .
git commit -m "add dependencies which theme aria needed"
git push -u origin master

git clone https://github.com/wuzhe213/hexo-theme-aria.git themes/aria
cd themes/aria
```
 
customizing in blog's _config.xml
open _config.yml, and change line:
```yaml
theme: aria
language: en
search:
  path: search.xml
  field: all
highlight:
  enable: true
  hljs: true # Add this line!
  line_number: true
  auto_detect: true
  tab_replace:
```

create aria's configuration
```bash
cp themes/aria/_config.yml.example themes/aria/_config.yml
```

customize themes/aria/_config.yml
```yaml
highlight: solarized-dark
sidebar: left
auto_excerpt: 400
social:
  enable: false
blogroll:
  enable: false
reward:
  enable: false
info:
  enable: false
```

in layout/post.njk
```diff
-  {% if theme.reward %}
+  {% if theme.reward.enable %}
```

in layout/sidebar.njk
```diff
-  {% include "info.njk" %}
+  {% if theme.info.enable %}
+    {% include "info.njk" %}
+  {% endif %}
```

in source/css/normalize.css
```diff
 kbd,
 samp {
   font-family: monospace, monospace; /* 1 */
-  font-size: 1em; /* 2 */
+  font-size: 0.8em; /* 2 */
 }
```

Down, 



