## WEB1 - 12. 부모자식과 목록
[WEB1 - 12. 부모자식과 목록](https://www.youtube.com/watch?v=aUtnyev_1vg&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=12)
- Unordered list ,<ul>
```html
<ul>
<li>1. HTML</li>
<li>2. CSS</li>
<li>3. JavaScript</li>
</ul>
```  
- li 는 list up을 해준다. 목차답게 표현하게
- ul은 li의 부모로써 무조건 붙여야 한다

- Ordered list
```
<ol>
<li> HTML</li>
<li> CSS</li>
<li> JavaScript</li>
</ol>
```
- ol은 번호를 자동으로 지정해준다. 

## WEB1 - 13. 문서의구조와 슈퍼스타들
[WEB1 - 13. 문서의구조와 슈퍼스타들](https://www.youtube.com/watch?v=sVt5nyz3Gdo&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=13)
- 정보가 많아짐에 따라 정보를 잘 정리하기 위한 구조가 필요하다
- 1,2,3,4위를 살펴보자
```html
 <title>WEB1 - html</title>
```
위 태그를 사용하여 명시적으로 사용자에게 보여줄 뿐 아니라, 웹 페이지에서 책 표지와 같은 역할을 하므로 검색이 잘 된다. 
- <h1>HTML이란 무엇인가?</h1> utf8로 작성했는데, 웹페이지도 utf8로 열라고 할때는 
- <meta charset = "utf-8">
- 띄어쓰기 , 밑에있는 건 본문, <title>과 <metacharset은 이 웹페이지는 utf8로 저장되 있다> 제목은 <!doctype html> <html>을 최상단에. <head></head>본문은 <body>
- 위키피디아 -  페이지소스보기에서 html 태그 확인해보자
  
```html

<!doctype html>
<html>

<head>
<title>WEB1 - html</title>
<meta charset = "utf-8">
<h1>HTML이란 무엇인가?</h1>
</head>


<body>
<ul>
<li>1. HTML</li>
<li>2. CSS</li>
<li>3. JavaScript</li>
</ul>

<h1>HTML</h1>
Hypertext Markup Language (HTML) is the standard markup Language for creating
web pages and<br><br><br>web applications.

Hypertext Markup Language (HTML) is the standard markup Language for creating
web pages and web applications.
Hypertext Markup Language (HTML)</p><p> is the standard markup Language for creating
web pages and web applications.

Hypertext Markup Language (HTML) is the standard markup Language for creating
web pages and web applications.
Hypertext Markup Language (HTML) is the standard markup Language for creating
web pages and web applications.
Hypertext Markup Language (HTML)</p><p style = "margin - top:45px;"> is the standard markup Language for creating
web pages and web applications.

<img src="covid19.jpg" width = '100%'>

```

