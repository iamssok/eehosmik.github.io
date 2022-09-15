---
layout: post
title:  Import Video
date:   2022-09-15 14:00:00 +0900
categories: [Javascript] 
---

## Import Video


```html
<div class="video-wrap" data-video="lOQ-BXQhMRY" style="display:block;">
    <img src="images/youtube1.jpg">
</div>
<div class="video-wrap" data-video="o_wc-E_Acr8">
    <img src="images/youtube2.jpg">
</div>
<div class="video-wrap" data-video="mqhrazJcbUc">
    <img src="images/youtube3.jpg">
</div>

<div class="thumbnail">
    <a href="javascript:;" class="thumb1 active"></a>
    <a href="javascript:;" class="thumb2"></a>
    <a href="javascript:;" class="thumb3"></a>
</div>
```

```javascript 
$(document).ready(function() {
    $(".video-wrap").click(function() {
        $(this).append("<div class='video'><iframe width='1024' height='540'src='https://youtube.com/embed/" + $(this).data("video") + "?rel=0&playsinline=0&autoplay=1&mute=1' allow='autoplay; encrypted-media' allowfullscreen></iframe></div>");
    }),
    $(".thumbnail a").click(function() {
        var Element = $(this).index();	
        $(this).addClass("active").siblings().removeClass("active");
        $(".video-wrap").eq(Element).show().siblings(".video-wrap").hide();
        $(".video-wrap .video").remove();	
    });
});
```

```html
<div class="video-wrap2"><img src="images/youtube1.jpg"></div>

<div class="thumbnail2">
    <a href="javascript:;" onclick="popupVideoChange('lOQ-BXQhMRY');" class="thumb1 active"></a>
    <a href="javascript:;" onclick="popupVideoChange('o_wc-E_Acr8');" class="thumb2"></a>
    <a href="javascript:;" onclick="popupVideoChange('mqhrazJcbUc');" class="thumb3"></a>
</div>
```

```javascript 
function popupVideoChange(youtube_code){
    $(".video-wrap2").append("<div class='video'><iframe width='1024' height='540' src='https://youtube.com/embed/" + youtube_code + "?rel=0&playsinline=0&autoplay=1&mute=1' allow='autoplay; encrypted-media' allowfullscreen></iframe></div>");
}
```