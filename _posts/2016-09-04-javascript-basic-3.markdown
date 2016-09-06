---
layout: post
title:  "JavaScript Basic 3"
date:   2016-09-04 02:00:00 +0900
categories: jekyll update
excerpt: "- 스코프와 클로저"
---
## 실행 컨텍스트
* 실행 가능한 자바스크립트 코드 블럭(함수)이 실행되는 환경
* 함수가 실행되면 하나의 새로운 실행컨텍스트가 생성되고 스택에 쌓임.
* 가장 최근에 만들어진 실행 컨텍스트부터 확인
* 실행컨텍스트 안에 필요한 정보들이 생성
  * 함수내의 변수
  * 변수들의 유효범위 정보를 담고있는 스코프
  * 현재 코드를 실행한 객체를 나타내는 this 바인딩

<br>

------------------------
<br>

## 스코프 정보
  * 실행 컨텍스트에서 접근 할 수 있는 변수들의 유효범위
  * 연결리스트 형식의 자료구조 (스코프 체인)
  * 현재 컨텍스트의 변수 뿐만 아니라, 상위 실행 컨텍스트의 변수에도 접근이 가능.
{% highlight javascript %}
var value = "value1";

function printFunc() {
  var value = "value2";

  function printValue() {
    return value;
  }
  console.log(printValue());
}
printFunc();
{% endhighlight %}
* 전역 실행 컨텍스트
  * 0 : 전역 객체
* printFunc 실행 컨텍스트
  * 1 : printFunc 변수 객체
  * 0 : 전역 객체
* printValue 실행 컨텍스트
  * 2 : printValue 변수 객체
  * 1 : printFunc 변수 객체
  * 0 : 전역 객체

<br>

------------------------
<br>

## 클로저
* 이미 생명 주기가 끝난 외부 함수의 변수를 참조하는 내부 함수자신의 스코프 밖에 있는 데이터에 접근할 수 있게 참조를 남겨둔 상태( by 스코프체인)
*  public, private 구현에 사용
{% highlight javascript %}
function outerFunc(){
    var x = 10;
    var innerFunc = function(){
        console.log(x + 10);
    };
    return innerFunc;
}
var inner = outerFunc();
// outerFunc()의 생명주기가 끝났지만 내부 함수
// 자신의 스코프 밖에 있는 데이터에 계속 접근 할 수
// 있는 상태
inner(); // 20
{% endhighlight %}
