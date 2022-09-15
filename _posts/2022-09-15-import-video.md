---
layout: post
title:  Import Video
date:   2022-09-15 14:00:00 +0900
categories: [Javascript] 
---

## Import Video
썸네일 클릭에 따른 각각의 유튜브 영상 가져오기

```html
<div class="video-wrap" style="display:block;">
    <a href="javascript:;" data-video="lOQ-BXQhMRY"></a>
    <div class="video-cont"></div>
    <img src="images/youtube1.jpg" alt="우다희 CTA">
</div>
<div class="video-wrap">
    <a href="javascript:;" data-video="o_wc-E_Acr8"></a>
    <div class="video-cont"></div>
    <img src="images/youtube2.jpg" alt="이주용 CTA">
</div>
<div class="video-wrap">
    <a href="javascript:;" data-video="mqhrazJcbUc"></a>
    <div class="video-cont"></div>
    <img src="images/youtube3.jpg" alt="이원준 CTA">
</div>

<div class="thumbnail">
    <a href="javascript:;" class="thumb1 active"></a>
    <a href="javascript:;" class="thumb2"></a>
    <a href="javascript:;" class="thumb3"></a>
</div>
```

```javascript 
$(document).ready(function() {
    $(".video-wrap a").click(function() {
        $(".video-cont").addClass("reveal");
        $(".video-cont").append("<div class='video'><iframe width='1024' height='540' src='https://youtube.com/embed/" + $(this).data("video") + "?rel=0&playsinline=0&autoplay=1&mute=1' allow='autoplay; encrypted-media' allowfullscreen></iframe></div>");
    }),
    $(".thumbnail a").click(function() {
        var Element = $(this).index();	
        $(this).addClass("active").siblings().removeClass("active");
        $(".video-wrap").eq(Element).show().siblings(".video-wrap").hide();
        $(".video-cont").removeClass("reveal");
        $(".video-cont .video").remove();		
        $(".fullCnt1").css("background","url(images/bg_cnt_01-" + Element + ".jpg)");
    });
});
```