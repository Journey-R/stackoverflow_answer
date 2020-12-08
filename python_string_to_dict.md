# python_ string to dict

- link: https://stackoverflow.com/questions/65206601/formatting-string-to-dict/65207671#65207671

![image](https://user-images.githubusercontent.com/71396432/101548419-26737580-39ef-11eb-904d-e4dd258b7b66.png)



## My Answer

```python
splitStr = 'b:0.1 a:0.5 n:0.2 p:0.1 c:0.1 k:0.1'.split(' ')

strList = []

for s in splitStr :
    strList.append(s.split(':'))
    
dict(strList)
```



---



## Another Answer

```python
s = "b:0.1 a:0.5 n:0.2 p:0.1 c:0.1 k:0.1"
dict([i.split(':') for i in s.split()])
```

- 내가 짠 5줄짜리 코드가 이렇게 2줄과 같다.



---



## Another Answer 보고 정리

### for문 한 줄쓰기 :  [ do  for ___ in _____ ]

- 반환타입 : list

```python
[s.split(':') for s in splitStr]
```



---

## My first answer in stackoverflow



나의 첫번째 스택오버플로 답변

넘나 흥분된다. 나도 스택오버플로에서 누군가에게 답변을 달아주다니...><

기억하고 싶어서 답변 올리기 전 화면을 캡쳐해뒀다:)

![image](https://user-images.githubusercontent.com/71396432/101548795-d943d380-39ef-11eb-9a36-b5d3f5a81578.png)

