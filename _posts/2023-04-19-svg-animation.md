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

<style>
    .chk-wrap {position:absolute; top:400px; left:50%; width:200px; height:30px; margin-left:-100px;}
	.chk-wrap input {display:none;}
	.chk-wrap svg {border:1px solid #333;}
	.st0 {fill:#000; stroke:#fff; stroke-width:6px; stroke-miterlimit:10;}
	.st1 {fill:none; stroke:#000; stroke-width:6px; stroke-miterlimit:10; stroke-dashoffset:0; stroke-dasharray:90;}
	input:checked ~ label .st1 {stroke:#fff; animation:dash 0.3s linear alternate 1;}
	label span {position:relative; top:-5px; margin-left:2px; color:#fff;}
	@keyframes dash {
	  from {stroke-dashoffset:90;}
	  to   {stroke-dashoffset:0;}
	}
</style>
<div class="chk-wrap">
    <input type="checkbox" name="chk" id="chk"> 
    <label for="chk">
        <svg width="20" height="20" viewbox="0 0 80 40">
            <polyline class="st1" points="15,15 35,38 65,2" />
        </svg>
        <span>체크하려면 클릭하세요</span>
    </label>
</div>



