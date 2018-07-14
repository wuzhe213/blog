---
title: hexo Next theme configuration
categories: 
tags: [hexo, Next]
date: 2018-07-14 07:23:12
---

# Install Next Theme  
```bash
cd blog/
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

# set theme to Next
open blog configuration file _config.yml
```yaml
theme: next
```

# Configuration
Edit Next's theme configuration file: themes/next/_config.yml 

<!--more-->

```yaml
rss: false
scheme: Pisces
motion:
  enable: false
local_search:
  enable: true
sidebar:
  position: left
  display: always

menu:
  home: / || home
  tags: /tags/ || tags
  categories: /categories/ || th
  archives: /archives/ || archive
```


## create link for tags and categories
```bash
hexo new page tags
hexo new page categories
```

### edit file source/categories/index.md
set type to categories, like below:
```markdown
---
title: categories
date: 2018-07-14 07:38:13
type: categories
---
```

### edit file source/tags/index.md
set type to tags, like below:
```markdown
---
title: tags
date: 2018-07-14 07:38:07
type: tags
---
```


