# JavaScript

- [JavaScript 강의](https://opentutorials.org/course/3085)

본 강의를 통해 JavaScript를 학습하고 정리한 내용입니다.

---
## 1. JavaScript란?
HTML과 CSS로 구성된 웹페이지를 동적으로 만들어 주는 언어.

- 객체(object) 기반의 스크립트 언어이다.
- 웹의 동작을 구현할 수 있다.
- Node.js와 같은 프레임워크를 사용하면 서버 측 프로그래밍에서도 사용할 수 있다.

## 2. 기본 문법
HTML문서 안에서 사용 시 두가지 방법이 있다.

- 내부 자바스크립트

```html
<script>
  자바스크립트 문법
</script>
```

- 외부 자바스크립트

```html
<script src="파일명.js"></script>
```

## 3. 이벤트
자바스크립트가 사용자와 상호작용하는 데 핵심적인 역할.

- 버튼 만들기 - [ex2.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex2.html)

```html
1. hi 버튼 만들기

<input type="button" value="hi">

2. 버튼 클릭 시 경고창 띄우기 

<input type="button" value="hi" onclick="alert('hi')">

3. 텍스트 상자 만들기

<input type="text">

4. 텍스트 상자의 내용이 변했을 때 경고창 띄우기

<input type="text" onchange="alert('changed')">

5. 키를 눌렀을 때 경고창 띄우기

<input type="text" onkeydown="alert('key down!')">
```

## 4. onclick 속성
사용자와 상호작용해서 HTML과 CSS를 프로그래밍적으로, 동적으로 변경하기.

- night & day 버튼 만들기 - [ex3.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex3.html), [colors.js](https://github.com/skagn4929/JavaScript-start/blob/main/colors.js)

```html
1. night 버튼과 day 버튼 만들기

<input type="button" value="night">
<input type="button" value="day">

2. 버튼을 클릭했을 때의 이벤트를 추가하기 위해 onclick 속성을 추가

<input type="button" value="night" onclick="">
<input type="button" value="day" onclick="">

3. night 버튼을 클릭하면 배경색이 검은색이 되도록 onclick 속성 값을 설정

<input type="button" value="night" onclick="
  document.querySelector('body').style.backgroundColor = 'black';
">

4. night 버튼을 클릭하면 글자색이 흰색이 되도록 onclick 속성 값을 추가

<input type="button" value="night" onclick="
  document.querySelector('body').style.backgroundColor = 'black';
  document.querySelector('body').style.color = 'white';
">

5. day 버튼을 클릭하면 배경색이 흰색, 글자색이 검은색이 되도록 완성

<input type="button" value="day" onclick="
  document.querySelector('body').style.backgroundColor = 'white';
  document.querySelector('body').style.color = 'black';
">
```

## 5. 비교 연산자와 불리언
비교 연산자(===)는 왼쪽에 있는 값과 오른쪽에 있는 값이 같은지 판단한다.    
결과는 true or false 중 하나이며, 그 값을 묶어서 불리언이라고 부른다.

- 비교 연산자와 불리언 실습 - [ex4.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex4.html)

```html
<script>
  document.write(1===1);   → 좌우 두 값이 같으므로 true 출력

  document.write(1===2);   → 좌우 두 값이 다르므로 false 출력
</script>
```

## 6. 조건문(if)
조건에 따라 다른 순서의 기능들이 실행되게 하는 것.

- night & day 버튼을 토글 키로 만들기 - [ex3.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex3.html), [colors.js](https://github.com/skagn4929/JavaScript-start/blob/main/colors.js)

```html
1. 버튼에 조건문 형식 추가

<input type="button" value="night" onclick="
  if(night) {
      document.querySelector('body').style.backgroundColor = 'black';
      document.querySelector('body').style.color = 'white';
  } else {
      document.querySelector('body').style.backgroundColor = 'white';
      document.querySelector('body').style.color = 'black';
  }
">

2. 버튼에 id 속성을 추가하고 조건문의 조건을 수정

<input id="night_day" type="button" value="night" onclick="
  if(document.querySelector('#night_day').value === 'night') {
      document.querySelector('body').style.backgroundColor = 'black';
      document.querySelector('body').style.color = 'white';
  } else {
      document.querySelector('body').style.backgroundColor = 'white';
      document.querySelector('body').style.color = 'black';
  }
">

3. 조건에 따라 버튼의 value 값 변경

<input id="night_day" type="button" value="night" onclick="
  if(document.querySelector('#night_day').value === 'night') {
      document.querySelector('body').style.backgroundColor = 'black';
      document.querySelector('body').style.color = 'white';
      document.querySelector('#night_day').value = 'day';
  } else {
      document.querySelector('body').style.backgroundColor = 'white';
      document.querySelector('body').style.color = 'black';
      document.querySelector('#night_day').value = 'night';
  }
">
```

## 7. 리팩터링
코드의 가독성을 높이고, 유지보수를 편리하게 만들고, 중복된 코드를 줄이는 방향으로 코드를 개선하는 작업.

- 리팩터링 실습 - [ex3.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex3.html), [colors.js](https://github.com/skagn4929/JavaScript-start/blob/main/colors.js)

```html
1. this 키워드 사용 : onclick과 같은 이벤트 안에서 실행되는 코드에서 현재 코드가 속해 있는 태그를 가리키도록 약속돼 있는 특수한 키워드

<input type="button" value="night" onclick="
  if(this.value === 'night') {
      document.querySelector('body').style.backgroundColor = 'black';
      document.querySelector('body').style.color = 'white';
      this.value = 'day';
  } else {
      document.querySelector('body').style.backgroundColor = 'white';
      document.querySelector('body').style.color = 'black';
      this.value = 'night';
  }
">

2. <body> 태그를 target 변수에 할당하고, target 변수 사용

<input type="button" value="night" onclick="
  var target = document.querySelector('body');
  if(this.value === 'night') {
      target.style.backgroundColor = 'black';
      target.style.color = 'white';
      this.value = 'day';
  } else {
      target.style.backgroundColor = 'white';
      target.style.color = 'black';
      this.value = 'night';
  }
">
```

## 8. 배열
데이터 중에서 서로 연관된 데이터를 잘 정리 정돈해서 담아두는 일종의 수납상자.   
배열은 대괄호로 시작해서 대괄호로 끝나며 값과 값 사이는 콤마(,)로 구분한다.

- 배열 실습 - [ex6.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex6.html)

```html
1. 배열을 coworkers 변수에 넣기

<script>
  var coworkers = ["egoing", "leezche"]
</script>

2. 배열에서 데이터 꺼내기

<script>
  document.write(coworkers[0]);   → 첫 번째 자리에 있는 값은 0번째라는 뜻  
  document.write(coworkers[1]);
</script>

3. 배열에 들어있는 값이 몇 개인지 확인

<script>
  document.write(coworkers.length);
</script>

4. 배열에 데이터 추가

<script>
  coworkers.push('duru');
  coworkers.push('taeho');
</script>
```

## 9. 반복문(while 문)
순서대로 실행되는 프로그램의 흐름을 제어하는 제어문.   
while : 반복문의 키워드   
while 괄호 안에는 불리언 데이터 타입이 들어오며, 내용이 true인 동안에는 while 문 안의 코드가 false가 될 때까지 반복적으로 실행된다.

- while 반복문 실습 - [ex7.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex7.html)

```html
1. 스크립트 태그안에 임의의 리스트 작성

<script>
  document.write("<li>1</li>");
  document.write("<li>2</li>");
  document.write("<li>3</li>");
  document.write("<li>4</li>");
</script>

2. while 반복문을 이용해 2,3번째 코드를 3번 반복

<script>
  document.write("<li>1</li>");
  var i = 0;
  while(i < 3) {
    document.write("<li>2</li>");
    document.write("<li>3</li>");
    i = i + 1;   → '기존의 i의 값에 1을 더한 결과를 i의 새로운 값으로 준다' 라는 뜻                       
  }
  document.write("<li>4</li>");
</script>
```

## 10. 함수(function)
자신의 외부 코드가 '호출'할 수 있는 하위 프로그램. 함수에 값을 '전달'하면, 함수는 값을 '반환'한다.   
입력에 해당하는 것을 매개변수 또는 인자라고 하며, 출력에 해당하는 것은 return과 관련이 있다.

- 함수의 기본적인 문법 실습 - [ex9.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex9.html)

```html
1. 임의의 코드 리스트 작성

<script>
  document.write('<li>1</li>');
  document.write('<li>2-1</li>');
  document.write('<li>2-2</li>');
  document.write('<li>3</li>');
  document.write('<li>2-1</li>');
  document.write('<li>2-2</li>');
</script>


2. 반복되는 코드를 함수로 바꾸기

<script>
  function two() {
    document.write('<li>2-1</li>');
    document.write('<li>2-2</li>');
  }  
  document.write('<li>1</li>');
  two();
  document.write('<li>3</li>');
  two();
</script>
```

- 매개변수와 인자 실습 - [ex9.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex9.html)

```html
1. 1+1을 출력하는 코드 작성

<script>
  document.write(1+1);  → '2'를 출력
</script>

2. 1+1을 함수로 만들기

<script>
  function onePlusOne() {
    document.write(1+1);
  }
  onePlusOne();
</script>

3. 입력값에 따라 다른 결과를 출력하는 함수로 만들기

<script>
  function oneplusone() {
    document.write(1 + 1 + "<br>");
  }
  oneplusone();
  function sum(left, right) {
    document.write(left + right + "<br>");
  }
  sum(2, 3);   → 이때 함수로 전달하는 2,3이라는 값을 '인자'라고 하며,
  sum(3, 4);     이 값을 받아서 함수 안으로 매개하는 변수(left, right)를 '매개변수'라 한다.
</script>
```

- return 문 실습 - [ex9.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex9.html)

```html
1. sum2() 함수 추가

<script>
  function sum2(left, right) {

  } 
</script>

2. sum2(2,3)에 스타일 추가

<script>
  function sum2(left, right) {

  }
  document.write(sum2(2, 3) + "<br>");
  document.write('<div style="color: red;">' + sum2(2, 3) + "</div><br>");
  document.write('<div style="font-size: 3rem">' + sum2(2, 3) + "</div><br>"); 
</script>

3. return 문 추가

<script>
  function sum2(left, right) {
    return left + right;   → sum2()를 실행한 결괏값을 돌려준다.
  }
  document.write(sum2(2, 3) + "<br>");
  document.write('<div style="color: red;">' + sum2(2, 3) + "</div><br>");
  document.write('<div style="font-size: 3rem">' + sum2(2, 3) + "</div><br>"); 
</script>
```

## 11. 객체
관련된 데이터와 함수의 집합.   
즉, 서로 연관된 함수와 변수를 그루핑해서 정리 정돈하기 위한 수납상자.   
객체에 소속된 함수를 메서드라고 하며, 객체에 소속된 변수를 프로퍼티라 한다.

- 객체의 기본적인 문법 실습 - [ex10.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex10.html)

```html
1. 객체 만들기

<script>
  var coworkers = { }   → 객체를 만들 때 사용하는 기호를 객체 리터럴이라 하며, 중괄호를 쓴다.
</script>

2. 객체에 정보 담기

<script>
  var coworkers = {
    "programmer":"egoing"
    "designer":"leezche"
  }
</script>

3. 객체에서 정보 가져오기

<script>
  var coworkers = {
    "programmer":"egoing"
    "designer":"leezche"
  }
  document.write("programmer : " + coworkers.programmer + "<br>");   → cowrkers 다음에 있는 점(.)은 객체 접근 연산자.
  document.write("designer : " + coworkers.designer + "<br>");
</script>

4. 객체에 정보 추가하고, 가져오기

<script>
  coworkers.bookkeeper = "duru";
  document.write("bookkeeper : " + coworkers.bookkeeper + "<br>");
</script>

5. 이름에 공백이 있는 정보를 추가하고, 가져오기

<script>
  coworkers["data scientist"] = "taeho";   → 이름에 공백이 들어갈 경우 대괄호를 써서 문자열 형태로 넣어야 한다.
  document.write("data scientist : " + coworkers["data scientist"] + "<br>");
</script>
```

- 반복문 for .. in 실습 - [ex10.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex10.html)

```html
1. 반복문 for .. in 사용

<script>
  for(var key in coworkers) { }   → for는 객체에 있는(in) key 값을 가져오는 반복문. key는 가져오고 싶은 정보에 도달할 수 있는 열쇠.
</script>

2. 반복문에서 객체의 키 값 출력

<script>
  for(var key in coworkers) {
    document.write(key + '<br>');
  }
</script>

3. 반복문에서 객체의 키 값에 해당하는 데이터 출력

<script>
  for(var key in coworkers) {
    document.write(coworkers[key] + '<br>');
  }
</script>

4. 반복문에서 객체의 키 값과 데이터 모두 출력

<script>
  for(var key in coworkers) {
    document.write(key + ':' + coworkers[key] + '<br>');
  }
</script>
```

## 12. 라이브러리 
만들고자 하는 프로그램에 필요한 부품들이 되는 소프트웨어들을 잘 정리정돈해 놓은, 재사용하기 쉽게 돼 있는 소프트웨어.

- jQuery : 라이브러리 중에서 가장 유명하며, 안정적이다. 파일을 직접 내려받은 후 프로젝트 디렉터리로 옮겨야 한다.
- CDN : 'Content Delivery Network'의 약자이며, 서버에 파일을 보관해 놓고 사용자는 <script> 태그의 src 속성을 통해 가져가는 방식.

## 13. UI 와 API
- UI : 'User Interface'의 약자이며, 사용자가 시스템을 제어하기 위해 사용하는 조작장치.
  - ex) 웹페이지에 있는 버튼

- API : 'Application Programming Interface'의 약자이며, 애플리케이션을 만들기 위해 프로그래밍할 때 사용하는 조작장치.   
  - ex) alert( ) 함수 : 경고창을 실행하는 조작장치


