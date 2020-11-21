---
title : "11.람다,pass,\_\_doc\_\_,help, 이터레이터 객체"
categories:
  - Python(문법)
# tags:
#  - Python
date : 2020-11-21
---

개발을 하면서 필요한 기본 함수들에 대해 알아보도록 하자.  
이번 포스팅에서는 람다,pass,\_\_doc\_\_,help, 이터레이터 객체에 대해서 알아보려고 한다.  

람다 (lambda) : 익명 함수를 만들 때 사용  
pass : 아무것도 하지 않고 그냥 넘어가도록 할 떄 사용  
\_\_doc\_\_, help : 생성한 함수의 설명을 추가하거나 확인하고 싶을 때 사용      
이터레이터 객체 : 순회가능한 형식에서 값을 안전하고 빠르게 나열하고 싶을 때 사용  

람다 함수   
---

- 파이썬에서는 함수의 이름이 없는 바디만 정의한 익명의 함수를 만들 수 있음  
- 일반함수와 마찬가지로 여러개의 인자를 전달 받을 수 있음  
- return 구문을 적지 않아도 반환값을 돌려줄 수 있음  

```python 
>>> g=lambda x,y : x*y    #g라는 변수에 저장해서 계속 호출할 수 있음
>>> g(2,3)
6
>>> (lambda x : x*x) (3)  #람다함수를 정의 후 호출하고 바로 사라지기 때문에 계속 호출할 수 없음 (1회성 함수)
9
>>> globals
<built-in function globals>
>>> globals()
{... 'g': <function <lambda> at 0x00000169EE0D1CA0> ...} #1회성 함수는 저장되지 않고 g만 저장된 것을 확인
```

Pass 함수  
- 아무것도 하지 않고 그냥 넘어가도록 할 경우 pass 키워드를 사용해서 함수, 모듈, 클래스의 내부를 채울 수 있다. 

```python 

>>> def extract_a(a):
	templist=[]
	for x in a:
		if x  == 'a' :
			templist.append(x)
		else :
			pass     #x='a'가 아닌 경우에는 아무것도 하지 않고 넘어감
	return templist

>>> extract_a("ham")
['a']
>>> extract_a("haaaam")
['a', 'a', 'a', 'a']

```

\_\_doc\_\_, help 함수 
- 생성한 함수에 대해 자세한 설명을 추가하고 싶을 때 사용, help의 경우 특정 함수의 자세한 설명을 확인 할 수 있다.   

```python 
>>> def add(a,b):
	return a+b

>>> help(add)           #add 함수의 설명을 추가하지 않았으므로 설명이 나오지 않음 
Help on function add in module __main__:

add(a, b)

#__doc__를 통해 함수의 설명을 추가
>>> add.__doc__="이 함수는 두개의 인자를 더하는 함수 입니다."  

>>> help(add)
Help on function add in module __main__:

add(a, b)
    이 함수는 두개의 인자를 더하는 함수 입니다.   #정의한 함수의 설명이 출력됨을 확인

>>> help(print)                                #내장된 함수의 설명을 출력
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.

```

이터레이터 객체  
- 순회가능한 객체의 요소를 순차적으로 열거하도록 하는 객체  
- 리스트, 튜플, 문자열처럼 순회 가능한 시퀀스 형식에는 구현되어 있음  

아래와 같이 반복구문인 for in 루프를 통해서 각각의 아이템을 순차적으로 접근해서 리턴할 수 있다


```python 
>>> for element in [1,2,3]:  #리스트의 이터레이션 처리 
	print (element)
	
1
2
3
>>> for element in (1,2,3):  #튜플의 이터레이션 처리 
	print (element)
	
1
2
3
>>> for key in {'one':1,'two':2}:  #딕셔너리의 이터레이션 처리 
	print(key)
	
one
two

>>> for char in "123":      #문자열의 이터레이션 처리 
	print(char)
	
1
2
3
```
또한 다음과 같이 내장함수인 iter()함수를 통해 이터레이션 객체를 만들어서 사용할 수 있다.

```python 
>>> s='abc'
>>> it=iter(s)           #이터레이터 객체 생성
>>> it
<str_iterator object at 0x000001C2DFF104C0>  #이터레이터 객체가 저장된 것을 확인 
>>> next(it)             #next() 함수를 통해 순차적으로 다음번 방에 있는 값을 리턴 
'a'
>>> next(it)
'b'
>>> next(it)
'c'
>>> next(it)            #다음번 방에 값이 없으면 순회작업 중단 
Traceback (most recent call last):
  File "<pyshell#23>", line 1, in <module>
    next(it)
StopIteration
```

