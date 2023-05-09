---
layout: post
title:  today close
date:   2023-05-09 +0900
categories: [Javascript]
tags: [javascript]
---


```javascript
function setCookie( name, value, expirehours ) {
    var todayDate = new Date();
    todayDate.setHours( todayDate.getHours() + expirehours );
    document.cookie = name + "=" + escape( value ) + "; path=/; expires=" + todayDate.toGMTString() + ";"
}
function todayclose() {
    setCookie( "popup", "done" , 24 );
    document.getElementById('popup').style.display = "none";
}
cookiedata_popup = document.cookie;
    if ( cookiedata_popup.indexOf("popup=done") < 0 ){
    document.getElementById('popup').style.display = "block";
    } else {
    document.getElementById('popup').style.display = "none";
}
```