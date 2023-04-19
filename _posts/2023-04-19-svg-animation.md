---
layout: post
title:  svg animation
date:   2023-04-19 +0900
categories: [CSS] 
tags: [css, animation]
---

## svg animation

```css
a polyline {stroke-dasharray:1790; stroke-dashoffset:1790; transition:all .5s;}
a:hover polyline {stroke-dashoffset:0;}
```

```html
<a href="javascript:;" onclick="alert('준비중입니다.');">
    <svg width="900" height="170">  
        <polyline points="250,0 0,0 0,170 900,170 900,0 600,0" style="fill:transparent;stroke:#93ebe6;stroke-width:20" />
    </svg>
</a>
```





