---
layout: post
title:  svg animation
date:   2023-04-19 +0900
categories: [Html]
tags: [html]
---

## svg animation

<style>
    .arcc_wrap a {position:relative; width:780px; height:50px; background:#eee; border-top:2px solid #fff; border-bottom:1xp solid #000;}
</style>
<div class="arcc_wrap">
    <a href="javascript:;" class="open">Installing Dependencies</a>
    <a href="javascript:;" class="close" style="display:none;">Customing Static Assets</a>
    <div class="arcc_cont" style="display:none;">
        <p>Before running for the first time, go to the root directory of your site, and install dependencies as follows</p>
    </div>
</div>
<div class="arcc_wrap">
    <a href="javascript:;" class="open">Customing Stylesheet</a>
    <a href="javascript:;" class="close" style="display:none;">Running Local Server</a>
    <div class="arcc_cont" style="display:none;">
        <p>Removes some files or directories from your repository</p>
    </div>
</div>
<script>
    /*
    $('.arcc_wrap').click(function(){
        $(this).toggleClass('on');
        if( $(this).hasClass('on') == true ){
            $(this).siblings('.arcc_wrap').removeClass('on');
            $(this).siblings('.arcc_wrap').children('.arcc_cont').slideUp(250);
            $(this).siblings('.arcc_wrap').children('.open').show();
            $(this).siblings('.arcc_wrap').children('.close').hide();	
            $(this).children('.arcc_cont').slideDown(250);
            $(this).children('.open').hide();
            $(this).children('.close').show();				
        }else{
            $(this).children('.arcc_cont').slideUp(250);
            $(this).children('.open').show();
            $(this).children('.close').hide();
        }
    });
    */
</script>

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