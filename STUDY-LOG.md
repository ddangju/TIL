# LOG 📒
## 200731 
<br>p-단락사이여백이 고정되어있어 CSS로 픽셀단위 간격 조절 가능 ;css사용시 (p style ="margin-top:필요한여백px") <br>
<br>br-줄바꾸기 이태그는 닫지 않는다 <br>
<br> ul-순서없는 목록(가운데점), ol-순서있는 목록(숫자,알파벳) 자식관계 li <br>
<br> img src= "이미지링크" with=크기지정 </br>
<br> !doctype html - 문서시작알리는코드 </br>
<br> html </br>
<br> head-본문설명태그 (title-상단탭 이름변경, utf-본문설명) /head </br> 
<br> body- 본문 </br>
<br> /html /body </br>
<br> (a href="링크" target=blank-새창을 엽니다) 이동할까요? (/a) </br>

## 200805
<br> 1-html 복습도중 웹호스팅에서 두시간반이나 걸렸다..💦<br>
사진업로드가 되지를 않았다.. 결국 p(단락나누기)가 문제였다<br>
이미지태그전엔 앞뒤 꼭 확인하기!<br>
첫 웹호스팅 완료 😪<br>


2- 태그과정에서 file:///C:/Users/Hakyeong/Desktop/yeonju/2.html 로 태그걸었더니 표시할수없음으로뜸 <br>
a href=https://ddangju.github.io/myweb/cozyphoto1 로 변경하였더니 페이지가 넘어갔음<br>


## 200817
1. 문자 (character)
a = 'a', "a"
print(a)

2. 문자열 (string)
s = 'apple', "apple"
print(apple)

3. 정수 (decimal)
n = 100
print(100)

4. 실수(=소수)(float)
nn = 3.14
print(nn)

5. 논리형 (boolean) (True or false)
result= True
print(result)

`출력방법`

1. print(변수명입력) or pint (값)

2. c언어의 포맷팅 스타일로 출력을 제공 (%퍼센트 기호 뒤 자료형 약자를 붙이면 포맷)

`약자`

d : decimal   print("%d"%) 숫자 <br>
f : float (소수)  print("%f"%) 소수뒷자리 그대로 노출 or print("%.1f") 소수뒷자리 생략 <br>
int : inteager(정수) (문자열->숫자) <br>
s : string <br>
r : boolean  <br>

`예시`

name = "땅주" <br>
score = 100 <br>
print(name, "의 성적은", score, "점 입니다") <br>
print("%s의 성적은 %d점 입니다."%(name, score)) <br>

`표준입력 하는방법`

1. 내장함수 input() 은 입력을 받고 문자열로 변환시켜주는 함수이다

2. int() 는 문자열을 숫자로 변환시켜주는 함수이다


`예시`

name = (input("이름:"))
age = (input("나이:"))
score = int(input("영어점수"))
score2 = int(input("수학점수"))
avg = (score+score2)/2


print("%s살 %s의 평균은 %.1f점입니다"%(age, name, avg))

`산술연산자`

+더하기 

-빼기

*곱하기

/ 나누기

// 나눈 몫

% 나누기 나머지

`예시`

100초를 1분 40초로 출력

minute = 100 // 60

second = 100 % 60

print("%d분 %d초" % (minute, second))


## 200818

`if-elif-else`
 

* if - 조건이 참일때 실행한다 

* elif - 조건이 참일때 if가 True가 아니면 elif 실행 

* else - 조건이 거짓일때 실행한다 

<u>if가 True 라면 아래 elif,else는 무시하고 넘어가게된다!! </u>


## 200921

#### `head`


웹사이트 환결설정 할 수 있다


[title] tab설명 바뀐다


[meta tag] 구글검색시 보여지는 description. 


[link rel = "shortcut icon" sizes = "16x16 32x32 64x64" href="이미지주소" /] 탭의 이미지가 바뀐다
 
 
#### `body`


외부적 출력된다


'a(anchor)'


(태그name attribute="값")


[a href = "주소링크"  target=" "] go google </a>


target속성 <br>
_blank : 새로운 탭으로 창이 열린다 <br>
_self : 현재 윈도우 <br>


`form tags`

input은 하나or여러개의 type을 가질 수 있다


[input type = "color" type="password" type="text"]


`label`

input과 함께 작동한다


[label for ="first"] my page [/label]

[input id ="first" type="text"]

*for와 id의 값은 동일해야한다

*for과 같은값인 id를 들고있는 input을 작동시킨다 

id의 값은 고유하고 태그는 하나의 id만 가질 수 있다 

`div` 

분할,구분해주는 기능<br>
여러 html 태그들을 블록으로 묶어 컨테이너 역할을 한다<br>
div블록 전체에 동일한 css 스타일을 적용할 수 있다<br>

[div id = "header"] or [header] 둘다 사용 가능하다 <br>
의미를 파악하기위해 div대신 header 사용한다 


## 200924

### css 추가하는방법


같은 HTML파일에 CSS코드 작성하거나 [internal]


HTML와 CSS분리하는 방법.(보편적방법) [external]


block 은 옆요소에 다른요소가 오지 않는다


block의 세가지요소는 `margine, border, padding` 이 있다

ex) box
    box
    box
    
    
inline 은 옆요소에 다른요소가 올 수 있다<br>
너비와 높이는 적용되지 않는다<br>
inline의 요소는 `span, a, image`

ex) hello hello hello


 
 
##### style 작성방법

style태그는 head 안에 있어야한다


```
<style>
selector(태그지정) { 컬러속성 : 색상값; 

                  글씨크기: 크기값;
                     
                  }
                  
div { height: 150px;
        width: 150px;
        }
        
</style>
```                  
                     


방식으로 전개된다 

or

style.css 파일 생성후 head 안에서

[Link href = "style.css" rel = "stylesheets" / ]






###  margine

box의 경계 밖<br>
box생성시 나타나는 margine은 브라우저가 생성한다<br>
margine을 생략할시 margine=margine:0; ,<br>
또한 사방에 마진값을 줄 수 있다


### padding


box의 경계안<br>
div 4개를 각 크기를 다르게 생성하는경우<br>
태그 or id를 주어 id를 가르킨다<br>
id를 가르킬땐 style태그 안에서 #first  이와 같이 할 수 있다 <br>


### border

box의 경계 <br>
경계스타일 적용시 border { 너비 스타일 색상값;} <br>
모든 border 스타일 적용시 * { } 태그 적용한다 <br>
전체 적용된 스타일에서 교체하고 싶은 스타일 적용시, <br>
지정해서 변경 가능하다 <br>
ex) span {border-style : dotted;}


### class


예시 <br>


` 
크기가20px 하는 빨간 토마토,
크기가 20px 하는 노란 바나나 `


```
<style> 

.big{20px} 

.tomato {color : red;} 

.banana {color : yellow;} 

```
 
 
 ```
 <body>
 
 span class = " big tomato" 
 
 span class = " big banana"
 
 ```
 
 
 ## 201007
 
 
 ### position
 
 
#### static

디폴드 배치 방식. 프로퍼티의 값은 위치에 영향을 주지 않는다. 


#### relative (상대배치)

프로퍼티의 값만큼 이동한 '상대위치' 에 배치된다.


#### absolute (절대배치)

프로퍼티값으로 정하며 브라우저크기가 변해도 절대배치 태그위치는 변하지 않는다.

#### fixed (고정배치)

프로퍼티값으로 정하며 특정위치에 고정된다.


