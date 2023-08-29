# JavaScript

- [JavaScript 강의](https://opentutorials.org/course/3085)

본 강의를 통해 JavaScript를 학습하고 정리한 내용입니다.

---
## 1. JavaScript란?
HTML과 CSS로 구성된 웹페이지를 동적으로 만들어 주는 언어

- 객체(object) 기반의 스크립트 언어이다.
- 웹의 동작을 구현할 수 있다.
- Node.js와 같은 프레임워크를 사용하면 서버 측 프로그래밍에서도 사용할 수 있다.

## 2. 설정 방법
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
자바스크립트가 사용자와 상호작용하는 데 핵심적인 역할

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

## 4. 제어할 태그 선택하기
사용자와 상호작용해서 HTML과 CSS를 프로그래밍적으로, 동적으로 변경하기

- 주간, 야간 모드 만들기 - [ex3.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex3.html)

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
결과는 true나 false 중 하나이며, 그 값을 묶어서 불리언이라고 부른다.

- 비교 연산자와 불리언 - [ex4.html](https://github.com/skagn4929/JavaScript-start/blob/main/ex4.html)

```html
<script>
  document.write(1===1);  → 좌우 두 값이 같으므로 true 출력

  document.write(1===2);  → 좌우 두 값이 다르므로 false 출력
</script>
```




