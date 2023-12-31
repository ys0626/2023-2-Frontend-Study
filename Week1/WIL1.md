# 1장 자바스크립트의 개요
=======
# Week1 모던 자바스크립트 정리

# 1장 자바스크립트의 개요
[1장 자바스크립트의 개요](https://ys0626.notion.site/1-5ba76e1bcb094c56b203c6f4de3b3f2d?pvs=4)

## 1. 프로그래밍 언어로서의 자바스크립트

### 컴파일 언어 vs 인터프리터 언어

 소스 코드를 컴퓨터가 읽을 수 있도록 기계어로 번역하는 것을 **컴파일**, 이를 수행하는 소프트웨어를 **컴파일러**라고 한다. 소스 코드 여러 개를 하나로 묶어 컴파일 해 실행하는 언어를 컴파일 언어라고 한다. 빠르지만 컴파일 시간이 오래 걸린다. (ex. C, C++, Java)

 반면에 인터프리터 언어는 소스 코드를 한 줄씩 읽고 해석하며 동시에 실행하는 방식이다. 이를 수행하는 소프트웨어를 **인터프리터**라고 한다. 인터프리터 언어는 소스 코드를 수정하고 실행할 때마다 번역 과정이 필요하지 않아 편리하지만 느리다. (ex. Python, JavaScript)

- 절차적 언어, 객체 지향 언어, 함수형 언어, 논리형 언어가 있다.

### 자바스크립트의 특징

1. 인터프리터 언어다.  - JIT 컴파일러가 내장 되어 있어 속도가 빠름
2. 동적 프로토타입 기반 객체 지향 언어다. - 동적으로 추가 혹은 삭제 가능
3. 동적 타입 언어다. - 변수 타입이 없음, 실행 도중에 저장
4. 함수가 일급 객체다. - 고차 함수 구현 가능
5. 함수가 클로저를 정의한다. - 변수를 은닉하거나 영속성 보장 가능한 함수형 프로그래밍 가능

### 자바스크립트의 기술적 요소

1. ECMAScript(코어 언어) 
2. 클라이언트 측의 고유한 기술 요소 (Window, DOM, XMLHttpRequest, HTML5)
3. 서버 측 자바스크립트의 고유한 기술 요소 (Node.js, Rhino, Aptana Jaxer)

### ECMAScript 6 (ECMAScript 2015)

2009년에 권고된 ECMAScript 5 이후 다양한 프로그래밍 기능이 추가되어 발표된 2015년 버전 ECMAScript. 주요 기능들을 뒷장에서 다룬다.

## 2. 자바스크립트의 역사

 자바스크립트는 1995년 브렌던 아이크가 개발했다. 초반에는 브라우저 간의 호환성이 낮았으나 1997년부터 ECMAScript를 따르는 표준화가 이루어져 오래된 브라우저를 제외한 대다수의 브라우저가 서로 호환된다.

 오랫동안 웹 브라우저용 하급 스크립트 언어라고 오해가 있었으나 기능이 많은 어플리케이션(ex. 구글 지도)가 등장하면서 사라졌다. 고성능의 웹 애플리케이션을 제작할 수 있는 객체 지향 언어이다. HTML5 사양이 정해진 이후로 웹 애플리케이션을 만들 수 있는 다양한 API가 등장했다. 웹 브라우저 성능도 향상되면서 더 대중적인 언어가 되었다.


 # 2장 프로그램의 작성법과 실행법
[2장 프로그램의 작성법과 실행법](https://ys0626.notion.site/2-59e7f2b6e2c2406482cc1341519ecfea?pvs=4)


- 웹 브라우저, Node.js을 설치하고 메모장으로 코드를 입력해 편집할 수 있다. 메모장 대신 비주얼 스튜디오 코드를 사용할 수 있다.

### 간단한 예제 (팩토리얼 계산)

```jsx
function fact(n) {
	if (n <= 1) return n;
  return n * fact(n - 1);
}
for (var i = 1; i < 10; i++) {
	console.log(i + "!= " + fact(i));
}
```

 tab으로 들여쓰기를 한다. 들여쓰기를 안 해도 오류가 발생하지는 않는다. 저장할 때 확장자를 붙인다. (.js or .html)

 화면에 표시하라는 명령어는 console.log(…) 이다.

### 프로그램 실행

1.  웹 브라우저의 콘솔로 실행
    
    웹 브라우저는 개발자 도구를 제공한다. HTML과 CSS로 설정한 내용을 확인, 편집할 수 있다. 크롬을 예로 들자면 “ctrl + shift + i”로 개발자 도구를 열 수 있다. 사용자 정의 버튼을 누르면 배치를 바꿀 수도 있다. console 탭을 선택해 프롬프트를 열어 자바스크립트 코드를 입력해 실행한다. 
    

(단축기가 많으며 책에서 표 참고)

1. HTML 문서에 삽입해 웹 브라우저로 실행
    
    HTML 요소와 CSS 스타일을 제어해 대화형 웹을 만들 때 사용한다. 상호작용 없는 순수 프로그램을 실행시킬 때도 이용 가능하다. HTML 문서에 script 요소를 배치한 다음 script 요소 안에 js 코드를 작성한다. 
    

위의 팩토리얼 프로그램을 HTML 문서에 삽입하면 이렇게 된다.

```jsx
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<title>팩토리얼 계산</title>
</head>
<body>
	<script>
		function fact(n) {
				if(n<=1) return n;
				return n*fact(n-1);
		}
		for(var i=1; i<10; i++){
				console.log(i + "! = " + fact(i));
		}
	</script>
</body>
</html>
```

 console.log(…) 부분을 document.write(…)로 바꾸면 출력 결과를 웹 페이지의 창에서 확인할 수 있다. 따라서 콘솔 화면을 켤 필요가 없어진다. 그러나 실무에서는 쓸 일이 별로 없다. “<br />”는 줄 바꿈 표시이다.

 js 코드를 script 요소 안에 작성하면 프로그램이 길어졌을 때 전체 HTML을 읽기 힘들다. 따라서 다른 파일에 저장한 것을 읽어 들이도록 구현하면 편하게 읽을 수 있다.

```jsx
<script src="다른 파일의 경로"></script>
```

 위의 두 번째 예제가 첫 번째 예제의 factorial.js를 읽어 들이도록 한 것.

1. Node.js에서 실행
    
    크롬은 자바 스크립트 실행 엔진으로 V8 엔진을 탑재하고 있어 실행 속도가 빠르다. Node.js를 실행시키려면 윈도우 기준으로 명령 프롬프트를 사용한다.
    
    (윈도우 기준)
    
    디렉토리 이동 명령어: cd
    
    ex. $ cd js_study
    
    현재 디렉토리를 표시하는 명령어: 윈도우에서는 cd
    
    디렉토리 내의 파일 목록 보기 명령어: dir
    
    Node.js에서 파일을 읽어 실행하기 위한 명령어: node 파일 이름.확장자
    

### 프로그램 작성법

1. JS는 유니코드로 작성한다. ECMAScript 6에는 유니코드 5.1.0 이상 필요.
2. 대문자와 소문자 구별이 필요하다. 다른 문자로 인식한다.
3. 프로그램을 구성하는 최소 단위를 **토큰**이라고 한다. 프로그램 실행 전 JS 구문 규약에 맞는 올바른 프로그램인지 판정하는 것이 구문 분석(파싱)이다. 문제가 없다고 판단되면 실행한다.
    
    ex) 영어는 단어와 문장 부호가 토큰 기준이다. 최소한의 문자 덩어리
    
4. 공백 문자가 있어야 토큰을 판별할 수 있다.
5. 공백 문자가 없어도 판별할 수 있는 경우
    
    ex) a=1+2*3; 공백 없어도 토큰 분리가 된다. 따라서 **분리자, 구분자**로 불린다.
    
6. 가독성을 높이기 위해 공백, 탭, 개행을 적절히 추가하는 게 좋다.
7. 한 줄에 한 문장만, 문장 끝에 세미콜론을  붙이고 다음 줄로 바꾸자. 
8. 중괄호로 감싼 복합문은 세미콜론을 붙이지 않는다.
9. 빈 문장은 세미콜론으로 작성한다. 필요할 때가 있다.
10. JS 엔진이 자동으로 세미콜론을 추가한다. 줄이 달라도 이어진다고 판단이 되면 자동으로 세미콜론을 추가하지 않기도 한다. 그러나 예기치 못한 오류가 생길 때도 있을 테니 끝에 직접 써주는 게 좋다.

### 주석 쓰는 법

여러 문장을 쓸 때: /* 주석문 */

한 문장으로 끝날 때: // 주석문


# 3장 변수와 값
[3장 변수와 값](https://ys0626.notion.site/3-da4c26830b2747a4a865ed39c3f84cfb?pvs=4)

## 1. 변수와 선언

var sum; 과 같이 변수를 선언한다.

var은 변수를 선언하기 위한 선언자이다. sum은 변수 이름이다.

JS는 변수 타입이 없으므로 변수 선언자가 var 하나뿐이다.

쉼표를 사용해 변수 여러 개를 한 개의 문장으로 선언하는 것도 가능하다.

함수를 선언하기만 하면 변수 안에는 정의되지 않았다는 undefined라는 값이 들어간다.

선언하면서 초깃값 설정도 가능하다. 이때에도 쉼표로 한 문장에 가능하다.

변수 선언을 생략하고 읽으려고 시도하면 참조 오류가 발생한다. (ReferenceError)

 그러나 var로 선언하지 않은 변수에 값을 대입할 때는 오류가 발생하지 않는다. 엔진이 자동으로 그 변수를 전역 변수로 선언하기 때문이다. 그러나 **선언을 하지 않고 변수를 사용하면 버그**가 생길 수 있다. 선언을 해주자.

### 변수 끌어올림과 중복

 변수 선언을 먼저 하지 않아도 된다. 먼저 코드를 작성하고 뒤에 선언을 해도 문장이 제대로 해석된다. 이를 변수 선언의 끌어올림(호이스팅, hoisting)이라고 한다.

**단, 선언과 동시에 값을 대입하는 코드는 끌어올리지 않는다.**

같은 이름을 가진 변수를 여러 개 선언해도 문제 없다. 모두 끌어올린 후에 하나의 영역에만 할당된다. 이러한 끌어올림은 JS에만 있는 고유한 특징이다. 

- 변수 명명 규칙
    - 알파벳, 숫자, 밑줄, 달러 기호를 사용할 수 있다.
    - 첫 글자로는 숫자를 사용할 수 없다.
    - 예약어를 식별자로 사용할 수 없다. (식별자 명명 규칙을 따르는 건 사용 가능)
    
- 표기법
    - 캐멀: 두 번째 단어부터 첫 글자를 대문자로 표기, 나머지 소문자
    - 파스칼: 각 단어의 첫 글자를 대문자, 나머지는 소문자
    - 밑줄: 모든 단어를 소문자로 표기하고 단어 사이를 밑줄로 구분
    - 상수는 대문자로 표현한다.
    - 논리값 변수 앞은 is로
    - 생성자 이름은 파스칼로 표현

### 예약어

예약어란 JS 문법을 규정짓기 위해 JS 언어 사양에서 사용하는 특수한 키워드를 말한다. (ex. break, case, catch, class, const 등)

차후에 추가될 예약 키워드가 있으므로 이것을 식별자로 쓰는 것은 지양하자. (ex. await, enum, protected, private, public 등)

미리 정의된 전역 변수와 전역 함수 또한 피하자. (ex. Error, NaN, Array 등)

window 객채의 이름과 DOM에서 사용하고 있는 객체 이름도 식별자 이름으로 쓰지 않는 게 좋다.

## 2. 데이터 타입

 데이터 타입이란 숫자나 문자열처럼 변수에 저장하는 데이터 종류를 말한다. 변수에 타입이 있는 언어를 가리켜 정적 타입 언어(static typed language)라고 부른다.

 반면에 JS에서는 변수에 저장된 데이터 타입을 동적으로 바꿀 수 있는데 이러한 언어를 동적 타입 언어(dynamic typed language)라고 부른다.

 JS가 처리할 수 있는 데이터 타입은 원시 타입(primitive type)과 객체 타입이다.

원시 타입: 숫자, 문자열, 논리값, 특수한 값(undefined, null),  심벌이 있다.

데이터를 구성하는 기본적인 요소로 불변 값으로 정의되어 있다. 따라서 원시 값이라고 불린다.

객체: 원시 타입에 속하지 않는 값. 변수 여러 개가 모여서 만들어진 복합 데이터 타입이다. 안에 지정된 값을 바꿀 수 있으며 참조 타입이다. 따라서 값을 대입하면 그 객체에 대한 참조(메모리에서의 위치 정보)가 할당된다.

### 숫자

 JS에는 타입이 없으므로 숫자를 모두 64비트 부동소수점으로 표현한다. double 타입에 해당된다. 배열 인덱스와 비트 연산은 32비트 정수로 처리한다.

  프로그램에 직접 작성할 수 있는 상수 값은 리터럴(literal)이라고 한다.

 정수 리터럴과 부동소수점 리터럴이 있다.

 정수 리터럴: 말 그대로 정수 표현. 10진수, 16진수(0x2a), 8진수(0o73), 2진수(0b101)가 있다.

 부동소수점 리터럴: 정수 소수, 소수, 가수부e지수부, 가수부E지수부로 나뉜다. (사실 e와 E는 어느 쪽을 사용해도 같다.)

 NaN은 0을 0으로 나눈 값, Infinity를 Infinity로 나눈 값, 음수의 제곱근 등 숫자로 표현할 수 없는 부정 값을 뜻한다.

### 문자열

JS의 문자열은 길이가 16비트인 유니코드 문자(UTF-16 코드)를 나열한 것이다. 문자열 리터럴은 작은따옴표나 큰따옴표를 붙여 표현한다. 아무것도 없는 문자열도 가능하다.

JS를 HTML 요소에 끼워 넣을 때 프로그램을 문자열로 작성한다. 이때 HTML 코드에는 큰따옴표, JS 코드에는 작은따옴표를 사용해 구분하는 게 좋다.

줄 바꿈과 탭은 이스케이프 시퀀스로 표현해야 한다. 역슬래쉬(\)를 사용한 것을 뜻한다. (ex. \b, \n 문자)

### 논리값

조건식이 참인지 거짓인지 표현하기 위해 사용하는 값이다. true, false 두 가지 종류가 있다. 주로 제어 구문에 사용한다.

### 특수한 값

값이 없음을 표현하기 위한 특수값에는 null과 undefined가 있다.

undefined: 값이 정의되지 않은 상태

- 값을 할당하지 않은 변수의 값
- 없는 객체의 프로퍼티를 읽으려고 시도했을 때의 값
- 없는 배열의 요소를 읽으려고 시도했을 때의 값
- 아무것도 반환하지 않는 함수의 값
- 함수를 호출했을 때 전달받지 못한 인수의 값

이처럼 코드에 undefined를 대입한 것이 아니라 값이 할당되지 않은 결과이다. 전역 변수에도 undefined가 있다.

null: 아무것도 없음. 말 그대로 프로그램에서 검색을 했지만 찾지 못했을 때 아무것도 없음을 표현한 값이다.

### ECMAScript 6부터 추가된 타입

1. 심벌
    
    Symbol()을 사용해 생성한다. 호출할 때마다 새로운 값을 만든다. Symbol()에 인수를 전달하면 생성된 심벌의 설명을 덧붙일 수 있다. 유일무이한 값으로 변수 값 확인에 제한을 두고 싶을 때 쓰면 된다.
    
    Symbol.for()로 문자열과 연결된 심벌을 생성할 수 있다. 전역 레지에서 위에 지정한 문자열로 심벌을 불러올 수 있다. 연결된 문자열은 Symbol.keyFor()로 구할 수 있다.
    
2. 템플릿 리터럴
    
    일부만 변경해서 반복하거나 재사용할 수 있는 틀을 말한다. 역따옴표로 묶는다.
    
    템플릿 리터럴을 사용하면 일반적인 줄 바꿈 문자를 사용할 수 있게 된다. 이스케이프 시퀀스 문자도 사용 가능한데 그대로 출력하고 싶으면 앞에 String.raw를 붙이면 된다.
    
3. 보간 표현식
    
    템플릿 리터럴 안에 플레이스 홀더를 넣을 수 있다. ${…}로 표기한다. 문자열 안에 변수나 표현식의 결괏값을 삽입할 수 있다. 기존에는 문자열에 변수 값을 삽입하고 싶다면 더하기 연산자를 사용했지만 이를 통해 더 알아보기 쉽게 작성할 수 있다.


# 4장 객체와 배열, 함수의 기초
[4장 객체와 배열, 함수의 기초](https://ys0626.notion.site/4-9728d7859c0c4eac99ea2c91d77f337d?pvs=4)


## 1. 객체의 기초

원시 타입 제외 모든 값이 객체이다. 객체는 **객체 리터럴**과 **생성자**로 생성할 수 있다.

객체는 이름과 값을 한 쌍으로 묶은 데이터를 여러 개 모은 것으로 연관 배열 또는 사전이라고 부른다. 객체에 포함된 데이터 하나를 객체의 프로퍼티라고 부른다. 프로퍼티의 이름 부분을 프로퍼티 이름 또는 **키**라고 부른다.

### 객체 리터럴

트럼프 카드의 정보를 객체 리터럴로 표현하면 아래와 같다.

```jsx
var card = {suit: "하트", rank: "A"};
var card = {"suit": "하트", "rank": "A"};
```

{…} 부분이 객체 리터럴이며 이를 변수 card에 대입한 것이다. 프로퍼티 값에는 모든 타입의 값과 표현식을 대입할 수 있다.

변수에 대입된 객체 안의 값을 읽거나 쓸 때는 마침표 또는 대괄호를 사용한다.

```jsx
card.suit // 하트
card["rank"] // A
```

객체에 없는 프로퍼티를 읽으려 하면 undefined가 반환된다. 객체 리터럴 안에 아무것도 작성하지 않으면 빈 객체가 생성된다.

없는 프로퍼티 이름에 값을 대입하면 새로운 프로퍼티가 추가된다.

```jsx
card.value = 14;
console.log(card); // Object {suit: "하트", rank: "A", value: 14}
```

delete 연산자를 사용하면 삭제를 할 수 있다.

```jsx
delete card.rank;
console. log(card); // Object {suit: "하트", value: 14}
```

실행 중에 자유롭게 추가하거나 삭제할 수 있다.

in 연산자를 사용해 특정 프로퍼티가 있는지 확인할 수 있다. 있으면 true, 없으면 false를 반환한다.

```jsx
var card = {suit: "하트", rank: "A"};
console.log("suit" in card); // true
console.log("color" in card); // false
console.log("toString" in card); // true
```

Object 객체를 상속받았기 때문에 toString 프로퍼티가 있다는 결과가 나오는데 9장에서 보자.

프로퍼티 안에 프로퍼티를 넣을 수도 있다. 마침표 연산자로 계속 이어서 표현할 수 있다.

객체는 참조 타입으로 메모리의 영역을 차지한다. 참조는 다른 변수에 저장할 수 있다.

다른 변수여도 참조하는 (가리키는) 값이 같게 되는 것이다.

```jsx
var a = card;

console.log(a.suit); // 하트
a.suit = "스페이드";
console.log(a.suit); // 스페이드
console.log(card.suit); // 스페이드
```

### 함수의 기초

입력 값을 받으면 출력 값으로 함수 값을 반환한다. 함수의 입력 값을 인수라고 부르고 **출력값**을 **반환값**이라고 부른다. 함수는 function 키워드를 사용해 정의한다.

```jsx
function square(x) {return x*x;}
return x*x;
```

함수가 처리하는 내용은 return문 뿐이다. return문 다음에는 줄 바꿈을 하지 않는다.

함수 이름과 마찬가지로 모든 식별자를 함수 이름으로 사용할 수 있으나 기능을 이해하기 쉽게 지어야 가독성과 유지 보수성이 높아진다. 함수를 호출하는 방법은 다음과 같다.

```jsx
square(3)
```

return문의 값인 9가 반환된다. 함수를 호출할 때 전달하는 값을 인수, 정의문의 인수를 인자라고 부른다. 함수는 인수를 여러 개 받을 수 있으며 쉼표로 구분한다. 또한 인수를 받지 않는 함수도 정의할 수 있다. 이때에는 return문이 없을 수 있으며 반환값이 undefined가 된다.

일반적으로 함수를 실행하게 되면 호출 코드의 인수가 함수 정의문의 인자에 대입되고 중괄호 안에 적힌 프로그램이 순차적으로 실행된 뒤 return문이 실행되면 호출한 코드로 돌아가 반환값이 반환된다. return문이 실행되지 않으면 호출한 코드로 돌아가 undefined가 반환된다.

함수 선언문은 변수 선언문과 마찬가지로 첫머리로 끌어올려진다. 따라서 어떤 위치에나 작성할 수 있다.

JS에서는 함수가 객체이다. 따라서 함수의 이름이 변수로 저장되고 참조도 저장된다. 이 변수 값을 다른 변수에 할당하면 그 변수 이름으로 함수를 실행하는 것이 가능하다.

### 참조에 의한 호출과 값에 의한 호출

인수가 원시 값일 때

```jsx
function add1(x) {return x = x + 1;}
var a = 3;

var b = add(a);
console.log("a = " + a + "b = " + b); // a = 3, b = 4
```


# 5장 표현식과 연산자
=======
[5장 표현식과 연산자](https://ys0626.notion.site/5-007c5178edf5433688983e4381bf1664?pvs=4)

## 1. 연산자

**표현식**이란 숫자, 문자열, 논리값 등의 원시 값을 포함해 변수, 프로퍼티, 배열 요소, 함수 호출, 매서드 호출과 같은 어떠한 값을 말한다. **연산자**는 이러한 표현식들을 조합해 더욱 복잡한 표현식을 만드는 역할을 한다. (ex. +, -,  *,  &&, ?: 등) 연산자로 연산 대상이 되는 표현식을 **피연산자**라고 한다.

연산자의 우선순위가 따로 있기는 하지만 그룹 연산자 ()를 사용해서 계산 순서를 명시적으로 지정할 수 있다. 따라서 +보다 *가 뒤에 될 수도 있다.  따라서 결합 법칙이 있다고 할 수 있다.

기본적인 우선순위는 이렇다.

1. ()

2. 단항 연산자 ( --, ++, ! )

3. 산술 연산자 ( *, /, %, +, - )

4. 비교 연산자 ( >, >=, <, <=, ==, ===, !==, != )

5. 논리 연산자 ( &&, || )

6. 대입(복합 대입) 연산자 ( =, +=, -=, *=, /=, %= )

## 2. 산술 연산

산술 연산자는 피연산자가 숫자인 연산자이다. 피연산자가 숫자가 아닐 때에는 숫자 타입으로 바꾸어 연산한다. 숫자로 바꿀 수 없는 값이거나 계산할 수 없으면 NaN이 나온다. 64비트 부동소수점 연산으로 이루어진다.

산술 이항 연산자에는 +, -, *,  /(나누기), %(나머지)가 있다.

주의사항

1. 정수끼리 나누어도 결과가 부동소수점이 된다.
2. 나머지 연산자 %의 피연산자는 부동소수점이다.
3. + 연산자는 피연산자 중 하나가 문자열이면 나머지 피연산자를 문자열로 만들어 연결한다.
4. undefined도 NaN으로 평가한다.
5. true = 1, false = 0 으로 평가한다.

산술 단항 연산자에는 ++, - -, + (처리 없음), - (부호 반전)이 있다. 좌변이 있어야만 한다. 증가, 감소 연산자는 전위와 후위 표기법에 따라 값 처리가 달라지는데 전위 표기법을 사용하면 피연산자 값을 바꾼 뒤 평가를 하고 후위 표기법을 사용하면 피연산자를 평가한 다음 값을 바꾼다. 또한 증가, 감소 연산자를 연속으로 사용하면 참조 오류가 발생한다.

산술 대입 연산자에는 +=, -=, *=, /=, %=가 있는데 sum += data;는 sum = sum + data와 같다.

Math 객체 프로퍼티는 책의 표를 참고하도록 하자.

### 부동소수점과 정확도 문제

유효한 자릿수가 있으므로 계산할 때 오차가 발생한다. JS의 경우 IEEE754로 규정된 64비트 부동소수점이며 2진수 부동소수점을 표현한다.

64비트는 부호(1비트), 가수부(11비트), 지수부(52비트)로 이루어져 있다. 가수 부분은 1.dddd…d로 표현하며 소수점 아래 부분이 52비트를 차지한다. 유효한 자릿수가 2진수 53자리이므로 10진수의 자릿수는 2^53 으로 약 16자리가 된다.

이러한 부동소수점으로 계산하면 오차가 발생하는데 이것을 정확도 문제라고 한다. JS로 계산한 값과 수학적으로 정확히 계산한 값에 차이가 생기는 것인데 10진수로 딱 떨어지는 값 또한 조금씩 어긋나게 된다. 예를 들어 0.16 / 0.8 = 0.8 이지만 JS로 계산하면 0.799999…. 로 나온다. 이처럼 숫자를 비교할 때는 오차가 있다는 것을 고려해야 한다.

## 3. 문자열 제어하기


# 6장 웹 브라우저에서의 입출력
[6장 웹 브라우저에서의 입출력](https://ys0626.notion.site/6-0daa957265184a59b1373dd1e3165042?pvs=4)

## 1. 대화상자 표시하기

Window 객체에는 대화상자를 표시하기 위한 메서드가 세 개 있다. (alert, prompt, confirm) 대화상자란 입력을 하거나 메세지를 확인하기 위해 별도로 여는 창을 말한다.

- window.alert: 경고 대화상자를 표시
- window.prompt: 사용자의 문자열 입력을 받는 대화상자를 표시
- window.confirm: 확인 버튼과 취소 버튼이 있는 대화상자를 표시

대화상자는 모달창이다. 대화상자가 떠 있을 때는 부모 창의 작업이 일시적으로 정지가 되어 조작할 수 없어진다. 대화상자에서는 일반 텍스트만 표시할 수 있고 줄 바꿈 문자는 이스케이프 시퀀스로 표현한다. window.은 생략하고 호출할 수 있다.

```jsx
alert("안녕하세요!");
var name = prompt("이름을 입력하십시오");
var age = parseInt(prompt("나이를 입력하십시오"));
var ret = confirm("링크를 표시하시겠습니까?");
```

위와 같이 코드를 작성한다. **alert**는 대화상자에 경고창처럼 표시되며 확인 버튼을 누르면 사라진다.

**prompt**는 입력 대화상자를 표시해 문자열을 받는다. 이는 prompt 메서드의 반환값이 되어 name에 저장된다. 숫자 값을 구하려면 parseInt나 parseFloat 메서드를 사용하여 바꿔주면 된다.

**confirm** 메서드는 확인과 취소 버튼이 있는 대화상자를 표시한다. 논리값을 반환하며 확인을 누르면 true가 반환되고 취소를 누르면 false가 반환된다.

## 2. console

지금까지 출력 때 사용한 console.log()도 Console 객체의 메서드 중 하나다. 부모창의 동작을 간섭하지 않기 때문에 동작을 확인하거나 디버깅하는 데에 자주 사용된다.

## 3. 이벤트 처리기 등록하기와 타이머 알아보기

## 4. HTML 요소를 동적으로 읽고 쓰기

## 5. Canvas를 활용한 컴퓨터 그래픽스


# 7장 제어 구문
[7장 제어 구문](https://ys0626.notion.site/7-fdecad4c34d243cab9799e8723f2b291?pvs=4)

## 1. 제어 구문

## 2. 조건문

## 3. 반복문

## 4. 점프문

## 5. 예제
