---
layout: post
title:  svg animation
date:   2023-04-19 +0900
categories: [CSS] 
tags: [css, animation]
---

## svg animation

<style>
    a.cls-a {display:block; width:400px; height:100px; margin:50px auto; background:url('/eehosmik.github.io/assets/img/btn-line.png') no-repeat; border-bottom:0 !important;}
    a polyline {stroke-dasharray:1000; stroke-dashoffset:1000; transition:all .5s;}
    a:hover polyline {stroke-dashoffset:0;}
</style>
<a href="javascript:;" class="cls-a">
    <svg width="400" height="100">  
        <polyline points="200,0 0,0 0,100 400,100 400,0 200,0" style="fill:transparent;stroke:#93ebe6;stroke-width:20" />
    </svg>
</a>

```css
a polyline {stroke-dasharray:1000; stroke-dashoffset:1000; transition:all .5s;}
a:hover polyline {stroke-dashoffset:0;}
```

```html
<a href="javascript:;" class="cls-a">
    <svg width="400" height="100">  
        <polyline points="200,0 0,0 0,100 400,100 400,0 200,0" style="fill:transparent;stroke:#93ebe6;stroke-width:20" />
    </svg>
</a>
```





