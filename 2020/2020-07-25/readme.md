## [WEB2 CSS - 1. 수업 소개](https://www.youtube.com/watch?v=Ok0bBJPtgJI&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=2&t=0s)

- HTML을 통해 전자문서를 만들 수 있었는데 웹을 통해 문서를 만들 수 있던 것에서 나아가,  웹페이지를 좀더 아름답게 만들 수 있는 방법 =>css

## [WEB2 CSS - 2. CSS가 등장하기 전의 상황](https://www.youtube.com/watch?v=-OWx2vM4tLI&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=2)

- 문서의 글꼴을 변경하게 해주세요, 문서에 색상을 넣게 해주세요, 가운데 정렬을 하고싶어요. 문서에 배경 이미지를 넣고 싶어요
- 쉽지만 한계고 있는 방법
- font
```html
<!doctype html>
<html>

<head>
<title>WEB1 -HTML</title>
<meta charset = "utf-8">
<h1>HTML이란 무엇인가?</h1>
</head>

<body>
<h1><a href="index.html"><font color="red">  WEB<font></a></h1>
<ol>
<li><a href="1.html"><font color="red"> HTML<font></a></li>
<li><a href="2.html"><font color="red">  CSS<font></a></li>
<li><a href="3.html"> <font color="red"> JavaScript<font></a></li>
</ol>
태그들을 빨간색으로 바꾸기

```
- 색깔바꾸는 정도론 만족이 안되, 다만 빨간색으로 표현해야 한다는 디자인을 나타내는 font
- 웹 페이지라는 정보 안에 아무 무관한 font가 들어가면서, 웹 페이지가 정보로서 가치가 현격하게 떨어지기 시작한다.
- a 태그가 1억개일 경우, 색깔을 매일 바꾼다고 생각한다면?? 

- 디자인에 최적화된 완전히 새로운 언어 =>CSS


## [WEB2 CSS - 3. CSS의 등장](https://www.youtube.com/watch?v=L41Zjl7XANI&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=3)

- CSS

```html
<style>
<h3>css문법에 맞게 해석해서 처리해라</h3>
 a {
	color:red;
}
</style>
<body>
<h1><a href="index.html"><font color="red">  WEB<font></a></h1>
<ol>
<li><a href="1.html"> HTML<font></a></li>
<li><a href="2.html"> CSS<font></a></li>
<li><a href="3.html">  JavaScript<font></a></li>
</ol>
```html

- 똑같은 폰트색상바꾸기를 css로 바꾸기
- <style>
<h3>css문법에 맞게 해석해서 처리해라</h3>
-  a {color:red;}</style>
- a {color:black;}</style>
- 코딩 잘하는 방법 => 중복의 제거
- 유지보수 편의성 향상 & 가독성 향상
- 디자인 관련 코드는 '<style>'안에 갇히게 된다. => style 안의 것은 안 건드려도 된다.(HTML은 너무나 중요)
- CSS를 사용해서 웹 페이지를 디자인 하는 것이 훨씬 효율적이다.

[WEB2 CSS - 4. CSS의 기본 문법](https://www.youtube.com/watch?v=h0AlL9YI6bM&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=4)
- <li><a href="2.html" style = "color:red"> CSS<font></a></li>
- style ="" => html의 속성, 
- a{}= 선택자, selector
- color:black; = 효과, declaration 선언
- style태그를 직접사용할 경우에는 직접 효과를 줄 것이기 때문에 선택자를 사용할 필요가 없다. 
- 세미콜론은 하나의 디스크립션이 시작되고 끝나는 것을 구분. 효과 지정 후 세미 콜론

[WEB2 CSS 5 - 혁명적 변화](https://www.youtube.com/watch?v=nC2-nJEXL2U&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=5)
- a{color:red;}
- a = 선택자, selector
- color:red 선언 declaration 효과
- color =속성, property
- red =  property value
- 무엇을 모르는지 알면 검색하고 질문하고 궁금해하라
- 두가지의 여정
1) css를 통해 웹 페이지를 디자인하는 어떠한 property가 존재하는가
2) 그 효과를 더 정확히 선택해서 지정하기 위해서 다양한 선택자를 알아가는 과정

[WEB2 CSS - 6. CSS 속성을 스스로 알아내기](https://www.youtube.com/watch?v=WcED6Ia1IY4&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=6)
- WEB 제목이 더 커졌으면 좋겠다, 가운데 정렬되었으면 좋겠다 
- css text size property, text align center 검색
```html
<!doctype html>
<html>

<head>
<title>WEB1 -HTML</title>
<meta charset = "utf-8">
<style>
a{
  color: black;
  text-decoration: none;
}
  h1{
    font-size:45px;
    text-align: center;
  }
</style>
</head>

<body>
<h1><a href="index.html"> WEB</a></h1>
<ol>
<li><a href="1.html"> HTML</a></li>
<li><a href="2.html" style="color:red;text-decoration:underline">CSS</a></li>
<li><a href="3.html"> JavaScript</a></li>
</ol>

```
[WEB2 CSS - 7. CSS 선택자의 기본](https://www.youtube.com/watch?v=8-rCMmamtDE&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=7)
- css를 지배하는 2가지 효과&선택자
```html 
<!doctype html>
<html>

<head>
<title>WEB1 -HTML</title>
<meta charset = "utf-8">
<style>
a{
  color: black;
  text-decoration: none;
}
.saw{
  color:gray
}
  h1{
    font-size:45px;
    text-align: center;
  }
</style>
</head>
```
- 모든 태그를 검은색 , 방문했던것 = 회색, 방문중= 빨간색
- class 같은 의도로 하나로 그룹핑할 때(회색으로 묶을 것)
- .active{color:red} active 있는 거 red로
- 만약 액티브와saw의 순서를 바꾸면 다 회색으로 나온다. 
- id = "" 
- #active>class>a 태그 선택자
- id 선택자의 값이 active인 태그가 이 웹페이지에서 한번 등장하면 담부터 쓰면 안되.(id의 핵심은 중복되서는 안된다.")
- 태그가 더 포괄적, 구체적인 것이 더 우선순위가 높다.
- css selector 검색
- element= tag

```html
<!doctype html>
<html>

<head>
<title>WEB1 -HTML</title>
<meta charset = "utf-8">
<style>

#active{
  color:red}
.saw{
  color:gray
  
}

  a{
    color: black;
    text-decoration: none;
  }
  h1{
    font-size:45px;
    text-align: center;
  }
</style>
</head>

<body>
<h1><a href="index.html"> WEB</a></h1>
<ol>
<li><a href="1.html" class="saw">HTML</a></li>
<li><a href="2.html" class="saw" id="active">CSS</a></li>
<li><a href="3.html"> JavaScript</a></li>
</ol>
```	
