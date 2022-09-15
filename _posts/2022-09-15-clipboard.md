---
layout: post
title:  Clipboard
date:   2022-09-15 10:00:00 +0900
categories: [Javascript] 
---

## Clipboard
현재 페이지 주소나 특정 문자를 복사하기 위한_ 


```html
<a href="javascript:;" onclick="clip(1);" alt="현재 페이지 링크 복사">링크 복사</a>
<a href="javascript:;" onclick="clip(2);" alt="필수 해시태그 복사">해시태그 복사</a>
```

```javascript
function clip(type){
    var textarea = document.createElement("textarea");		
    document.body.appendChild(textarea);
    if (type == 1) {
        url = window.document.location.href;
        textarea.value = url;
    } else if (type == 2) {
        hashtag = '#html #css #javascript #jquery #vue #react #git';
        textarea.value = hashtag;
    }
    textarea.select();
    document.execCommand("copy");
    document.body.removeChild(textarea);
    if (type == 1) {
        alert("URL이 복사되었습니다.");
    } else if (type == 2) {
        alert("해시태그가 복사되었습니다.");
    }
}
```

## select()
`input text`나 `textarea`의 text field 내용을 선택

## execCommand()

### copy :
현재 선택 영역의 내용을 복사
