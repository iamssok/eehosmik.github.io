---
layout: post
title:  svg animation
date:   2023-04-19 +0900
categories: [CSS] 
tags: [css, animation]
---

## svg animation

<style>
    a.cls-a {display:block; width:500px; height:150px; border:10px solid #333;}
    a polyline {stroke-dasharray:1300; stroke-dashoffset:1300; transition:all .5s;}
    a:hover polyline {stroke-dashoffset:0;}
</style>
<a href="javascript:;" onclick="alert('준비중입니다.');" class="cls-a">
    <svg width="500" height="150">  
        <polyline points="250,0 0,0 0,150 500,150 500,0 250,0" style="fill:transparent;stroke:#93ebe6;stroke-width:20" />
    </svg>
</a>

```css
a polyline {stroke-dasharray:1300; stroke-dashoffset:1300; transition:all .5s;}
a:hover polyline {stroke-dashoffset:0;}
```

```html
<a href="javascript:;" onclick="alert('준비중입니다.');">
    <svg width="500" height="150">  
        <polyline points="250,0 0,0 0,150 500,150 500,0 250,0" style="fill:transparent;stroke:#93ebe6;stroke-width:20" />
    </svg>
</a>
```





