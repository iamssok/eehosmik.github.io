---
layout: post
title:  calculate
date:   2023-04-28 +0900
categories: [Javascript]
tags: [javascript, calc]
---


```html
<input type="checkbox" id="chk1" name="chk[]" value="20000" data="20000">
<input type="checkbox" id="chk2" name="chk[]" value="20000" data="20000">
<input type="checkbox" id="chk3" name="chk[]" value="30000" data="30000">
<p><span id="price">0</span>원</p>
```

```javascript
$("input:checkbox[name='chk[]']").click(function(){
    calcPrice();
});

function calcPrice(){
    var price = 0;
    var count = $("input:checkbox[name='chk[]']:checked").length;

    for(var i=0; i < count; i++ ){
        price += parseInt($("input:checkbox[name='chk[]']:checked").eq(i).val());  // value
        //price += parseInt($("input:checkbox[name='chk[]']:checked").eq(i).attr("data"));  // data
    }
    $("#price").text(numberWithCommas(price));
}

function numberWithCommas(x) {
    return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}
```