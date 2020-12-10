## python_dict 자동 생성(숫자와 알파벳 순서대로)

- link : https://stackoverflow.com/questions/65231103/how-to-automate-the-creation-of-a-dictionnary-in-python

![image](https://user-images.githubusercontent.com/71396432/101757023-01c7ec80-3b1a-11eb-85a7-337d8b429bff.png)



---



## My Answer

```python
import string

alphabet = list(string.ascii_lowercase)

alphabet_dict = {alphabet[idx] : idx + 1 for idx in range(len(alphabet))}
alphabet_dict2 = {alphabet[idx] : idx + 1 for idx in range(len(alphabet)-1, -1, -1)}
```

- 아래의 Another Answer을 참고해서 작성한 답변이다.

  

---



## Another Answer

```python
import string

alphabet = string.ascii_lowercase
alpha_dict = {letter:index+1 for index,letter in enumerate(alphabet)}
```



---



## Another Answer 보고 정리

### enumerate()

- for문에서 순서가 자료형의 데이터를 index를 통하여 접근할 경우
  - ```for idx, value in enumerate(list)```
  - ```for idx in range(len(list)) ```보다 적절하다.



참고 link : https://docs.python.org/ko/3/tutorial/datastructures.html#tut-loopidioms

