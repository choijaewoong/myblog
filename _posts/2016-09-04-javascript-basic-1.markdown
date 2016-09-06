---
layout: post
title:  "JavaScript Basic 1"
date:   2016-09-04 00:00:00 +0900
categories: jekyll update
excerpt: "- 자바스크립트 데이터 타입<br>
     - null과 undefined<br>
     - 자바스크립트의 객체 속성<br>
     - 자바스크립트의 내장 객체<br>"
---
## JavaScript 타입

### 기본타입
* 숫자(2, 1.5, -100) - number
* 문자열(“abc”, “123”) - string
* 불리언 값(true, false) - boolean
* null - object
* undefined - undefined

### 참조타입
* 배열([2, “a”, 4, true,]) - object
* 객체({name: choijaewoong, age: 27}) - object
* 함수(function(){}) - fuction
* Regexp

<br>

-----------------------------------------
<br>

## null 과 undefined
* null : object 타입,  명시적으로 빈 값임을 나타낼 때 사용
* undefined : 존재하지 않거나, 빈 값을 나타내는 타입이자 값.

{% highlight javascript %}
var nVal = null;
var val;

console.log(typeof nVal); // object
console.log(typeof nVal === null); // false
console.log(typeof nVal === "object"); // true
console.log(nVal === null); // true

console.log(val); // undefined
console.log(typeof val === 'undefined'); // true
console.log(val === undefined); // true
{% endhighlight %}

<br>

-----------------------------------------
<br>

## 자바스크립트의 객체 속성

* 변수나 데이터 구조 안에 객체를 담을 수 있음.
* 인자로 전달 가능
* 반환값으로 사용 가능

<br>

-----------------------------------------
<br>

## 자바스크립트의 내장 객체

* Number()
* String()
* Boolean()
* Object()
* Array()
* Function()
* Data()
* RegExp()
* Error()
