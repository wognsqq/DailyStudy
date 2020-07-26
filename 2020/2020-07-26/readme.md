## [WEB2 CSS - 8. 박스 모델](https://www.youtube.com/watch?v=MLjCVUspcDo&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=8)
- WEB1에서 가져온 예제에 디자인을 해보자
```html 
 /*
    block level element - 화면 전체를 쓰는 태그
    */
      h1{
      border- width : 5px;
      border- color : red;
      border- style : solid;
      disply:inline;
    }
    /*
    inline -element - 자기 자신의 부피, 컨텐츠만큼 갖는 태그
    */
    a{
    border-width:5px;
    border-color:red;
    border-style: solid;
    disply:block;    
      }
```
- 중복을 제거한 테그
```html
    h1,a{
    border: 5px solid red;   
      }
```

- 이미지 검색 :css box model 
- 웹페이지 오른쪽 - 검사 - style =h1 tag가 어떠한 영향을 받고 있는가 확인
- 개발자 도구를 사용해서 사람과 기계가 같이 일하자
- 화면 전체를 쓰는 것= block level element
- 일부를 쓰는 것 = inline element
- css 를 둘러 싼 것은 padding, 테두리와 테두리 사이는 margin
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      h1{
        border:5px solid red;
        padding:20px;
        margin:20px;
        display:block;
        width:100px;
      }
    </style>
  </head>
  <body>
    <h1>CSS</h1>
    <h1>CSS</h1>
  </body>
</html>
```

## [WEB2 CSS - 9. 박스 모델 써먹기](https://www.youtube.com/watch?v=4ir8XAf7wxI&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=9)
```html
<!doctype html>
<html>

<head>
<title>WEB1 -HTML</title>
<meta charset = "utf-8">
<style>
body{
  margin:0;
}
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
    border-bottom:1px solid gray;
    margin:0;
    padding: 20px;

  }
  ol{
    border-right:1px solid gray;
    width:100px;
    margin:0;
    padding:20px;

  }
```

## [WEB2 CSS - 10. 그리드 소개](https://www.youtube.com/watch?v=M1eQFIBY2vI&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=10)
- 목록과 본문이 나란히 하는 디자인
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #grid{
        border:5px solid pink;
        display:grid;
        grid-template-columns: 150px 1fr;
      }
      div{
        border:5px solid gray;
      }
    </style>
  </head>
  <body>
    <div id="grid">
      <div>NAVIGATION</div>
      <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
    </div>
  </body>
</html>
```
- caniuse.com 태그 사용해도 되는지 안되는지 알려주는 사이트. 매우 중요
## [WEB2 CSS - 11. 그리드 써먹기](https://www.youtube.com/watch?v=AL8RSY8rADY&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=11)
```html
<!doctype html>
<html>
<head>
  <title>WEB - CSS</title>
  <meta charset="utf-8">
  <style>
    body{
      margin:0;
    }
    a {
      color:black;
      text-decoration: none;
    }
    h1 {
      font-size:45px;
      text-align: center;
      border-bottom:1px solid gray;
      margin:0;
      padding:20px;
    }
    ol{
      border-right:1px solid gray;
      width:100px;
      margin:0;
      padding:20px;
    }
    #grid{
      display: grid;
      grid-template-columns: 150px 1fr;
    }
    #grid ol{
      padding-left:33px;
    }
    #grid #article{
      padding-left:25px;
    }
  </style>
</head>
<body>
  <h1><a href="index.html">WEB</a></h1>
  <div id="grid">
    <ol>
      <li><a href="1.html">HTML</a></li>
      <li><a href="2.html">CSS</a></li>
      <li><a href="3.html">JavaScript</a></li>
    </ol>
    <div id="article">
        <h2>CSS</h2>
        <p>
          Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language.[1] Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.
        </p>
      </div>
  </div>
  </body>
  </html>
```
## [WEB2 CSS - 12. 미디어 쿼리 소개](https://www.youtube.com/watch?v=aA4xunvDWU8&list=PLuHgQVnccGMAnWgUYiAW2cTzSBywFO75B&index=12)
- 반응형 디자인의 흐름
- 화면의 크기에 따라서 웹페이지의 각 요소들이 동작하게 된다.
- Media query
- 화면의 크기를 800픽셀보다 크면 보이고, 아니면 안보이고, 하게 하고 싶다면

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      div{
        border:10px solid green;
        font-size:60px;
      }
      @media(max-width:800px) {
        div{
          display:none;
        }
      }
    </style>
  </head>
  <body>
    <div>
      Responsive
    </div>
  </body>
</html>
```
[WEB2 CSS - 13. 미디어 쿼리 써먹기](https://www.youtube.com/watch?v=qe3nSIg2k3Y)
- 화면을 바꿈에 따라 화면크기에 맞춰서 글자 보이기
```html
<!doctype html>
<html>
<head>
  <title>WEB - CSS</title>
  <meta charset="utf-8">
  <style>
    body{
      margin:0;
    }
    a {
      color:black;
      text-decoration: none;
    }
    h1 {
      font-size:45px;
      text-align: center;
      border-bottom:1px solid gray;
      margin:0;
      padding:20px;
    }
    ol{
      border-right:1px solid gray;
      width:100px;
      margin:0;
      padding:20px;
    }

    #grid{
      display: grid;
      grid-template-columns: 150px 1fr;
    }
    #grid ol{
      padding-left:33px;
    }
    #grid #article{
      padding-left:25px;
    }
  screen width <800px
  @media(max-width:800px){
    #grid{
    display: block;
  }
  ol{border-right:none;
  }
  h1{
    border-bottom:none;
}
  }

  </style>
</head>

<body>
  <h1><a href="index.html">WEB</a></h1>
  <div id="grid">
    <ol>
      <li><a href="1.html">HTML</a></li>
      <li><a href="2.html">CSS</a></li>
      <li><a href="3.html">JavaScript</a></li>
    </ol>
    <div id="article">
        <h2>CSS</h2>
        <p>
          Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language.[1] Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.
        </p>
      </div>
  </div>
  </body>
  </html>
```
[WEB2 CSS - 14. CSS 코드의 재사용](https://www.youtube.com/watch?v=djBrHjeitUo)
- 위css코드를 다른 페이지에도 전파하세요
- style tag는 따로 빼서 링크걸어서 css파일과 연결하여, 코드를 더 깔끔하게 짠다.
- 완전 구현이 달라지며 효율적으로 동작하게 된다. 
```html
<!doctype html>
<html>
<head>
  <title>WEB - CSS</title>
  <meta charset="utf-8">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1><a href="index.html">WEB</a></h1>
  <div id="grid">
    <ol>
      <li><a href="1.html">HTML</a></li>
      <li><a href="2.html">CSS</a></li>
      <li><a href="3.html">JavaScript</a></li>
    </ol>
    <div id="article">
        <h2>CSS</h2>
        <p>
          Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language.[1] Although most often used to set the visual style of web pages and user interfaces written in HTML and XHTML, the language can be applied to any XML document, including plain XML, SVG and XUL, and is applicable to rendering in speech, or on other media. Along with HTML and JavaScript, CSS is a cornerstone technology used by most websites to create visually engaging webpages, user interfaces for web applications, and user interfaces for many mobile applications.
        </p>
      </div>
  </div>
  </body>
  </html>
```
-style.css
```html
body{
  margin:0;
}
a {
  color:black;
}
h1 {
  font-size:45px;
  text-align: center;
  border-bottom:1px solid gray;
  margin:0;
  padding:20px;
}
ol{
  border-right:1px solid gray;
  width:100px;
  margin:0;
  padding:20px;
}
#grid{
  display: grid;
  grid-template-columns: 150px 1fr;
}
#grid ol{
  padding-left:33px;
}
#grid #article{
  padding-left:25px;
}
@media(max-width:800px){
  #grid{
    display: block;
  }
  ol{
    border-right:none;
  }
  h1 {
    border-bottom:none;
  }
}
```
- 그냥 웹페이지 안에 css코드를 내장하는 것이 네트워크 자체로는 효율적.
- 캐싱 : 저장하다 => style.css 를 다운받았으면 저장된 결과를 가져와서 속도를 높일 수 있고, 경제적인 효과를 얻게 되는 것
- 가급적 css파일을 만들었다면 꺼내서 중복을 제거하는 것이 좋을 것이다.

## [WEB2 CSS - 15. 수업을 마치며](https://www.youtube.com/watch?v=42Bps7nCx8I&list=PL2Mkwvh6s7KIwNdw3--NJxAkiFnx2RoUX&index=15)
- 속성과 선택자, 주어와 서술어 처럼, 저 두개를 좀 잘 알아두자
- 그만두기 좋은 타이밍이면서 써먹기에 좋은 타이밍, 수단과 방법을 가리지 않고 공부와 멀어지려한다 ㅋㅋ
- 써먹으면 뇌가 감탄하고, 뇌는 공부를 하고 싶어해
- 내 웹 사이트를 꾸며보면 어떨까요, 디자인적으로나 기술적으로 부족한 부분을 검색, 질문, 고민하다보면
- 무관한 개념들이, 연결되고, 내부로 깨달아서 알게되는 배움을 얻게 될 것이다.

