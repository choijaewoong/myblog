---
layout: post
title:  "JavaScript Basic 2"
date:   2016-09-04 01:00:00 +0900
categories: jekyll update
excerpt: "- 사용자 정의 객체<br>
     - 객체의 프로퍼티 읽기/갱신/생성<br>
     - 객체의 프로퍼티 삭제<br>
     - for in을 통한 객체의 프로퍼티 접근<br>
     - 객체비교<br>
     - 객체와 배열의 차이<br>"
---
## 사용자 정의 객체
{% highlight javascript %}
// 생성자 함수
var Person = function(){
    this.name = "choijaewoong";
    this.age = 27;
};
var jaewoong = new Person();
console.log(typeof jaewoong); // object
console.log(jaewoong); // Person {name: "choi~", age: 27}

// 객체 리터럴 생성
var person = {
    name : "choijaewoong",
    age : 27
};
console.log(typeof person); // object
console.log(person); // Object {name: "choi~", age: 27}

// Object() 생성자
var person = new Object();
person.name = "choijaewoong";
person.age = 27;
console.log(typeof person); // object
console.log(person); // Object {name: "choi~", age: 27}
{% endhighlight %}

<br>

----------------------------
<br>

## 객체의 프로퍼티 읽기/갱신/생성
{% highlight javascript %}
var person = {
    name: 'choijaewoong',
    age: 27,
};
// 객체 프로퍼티 읽기
console.log(person.name);
console.log(person['name']);  // 동일한 결과

// 객체 프로퍼티 갱신
person.age = 26;

// 객체 프로퍼티 생성
person.bloodType = 'B';
{% endhighlight %}

<br>

----------------------------
<br>

## 객체의 프로퍼티 삭제하기
{% highlight javascript %}
var Person = {
    name: 'jaewoong',
    age: 20,
    bloodType : 'A'
};

console.log(Person.bloodType); // A
delete Person.bloodType;  // 객체의 프로퍼티 삭제
console.log(Person.bloodType); // undefined

delete Person; // 객체의 삭제는 불가능
console.log(Person); // 그대로 객체 출력
{% endhighlight %}

<br>

---------------------------
<br>

## for in 을 통한 객체의 프로퍼티 접근
{% highlight javascript %}
var person = {
    name: 'choijaewoong',
    age: 27,
    bloodType: 'B'
};
var property;
for(property in person){
    console.log(property, person[property]);
}
// name choijaewoong
// age 27
// bloodType B  
{% endhighlight %}

<br>

---------------------------
<br>

## 객체 비교
* 객체 비교는 값이 아닌 참조를 비교
{% highlight javascript %}
var obj1 = { val: 10 };
var obj2 = { val: 10 };
console.log( obj1 == obj2 ); // false
console.log( obj1.val == obj2.val ); // true
{% endhighlight %}

<br>

---------------------------
<br>

## 객체와 배열의 차이
* type은 object로 동일
* 객체는 배열의 속성을 사용할 수 없음.
{% highlight javascript %}
var array = ['red', 'green', 'blue']
console.log(array[0]);
console.log(array[1]);
console.log(array[2]);
console.log(array.length); // 3

var obj = {
    '0' : 'red',
    '1' : 'green',
    '2' : 'blue'
};
console.log(obj[0]); //배열과 같은 값을 가짐.
console.log(obj[1]);
console.log(obj[2]);
console.log(obj.length); // undefined
{% endhighlight %}

<br>

---------------------------
<br>

## “==” 연산자와 “ ===” 연산자
* == 연산자
  * 압묵적으로 타입 캐스팅(형변환) 후에 비교 연산
* === 연산자
  * 각 변수의 타입까지 체크하여 더 명확한 비교 연산이 가능
{% highlight javascript %}
var nAge = 20;
var sAge = "20";
console.log(nAge == sAge); // true
console.log(nAge === sAge); // false
{% endhighlight %}

<br>

---------------------------
<br>

## Call By Value / Call By Reference
* 기본 타입과 참조 타입에 대한 차이
{% highlight javascript %}
var nNum = 100;
var sStr = "abc";
var aArr = ['1', 123, true];
var objA = {value: 100};

function changeValue(num, str, arr, obj){
    num = 200;
    str = "def";
    arr.push(35);
    obj.value = 200;
    console.log(num); // 200
    console.log(obj); // {value: 200}
}
changeValue(nNum, sStr, aArr, objA);
console.log(nNum); // 100
console.log(sStr); // "abc"
console.log(aArr); // ['1', 123, true, 35]
console.log(objA); // {value: 200}
{% endhighlight %}
