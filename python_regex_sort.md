## 문자열 뒤의 숫자 기준으로 정렬(frame1.jpg, frame2.jpg, frame10.jpg)

- link : https://stackoverflow.com/questions/65238270/issue-in-reading-frames-sequence-wise-from-folder-in-python

![image](https://user-images.githubusercontent.com/71396432/101805682-62751a80-3b56-11eb-8a55-ca6e5c1ecf73.png)



---



## Search result

- 참고 url : https://www.tutorialspoint.com/How-to-correctly-sort-a-string-with-a-number-inside-in-Python
- 테스트를 위해 filenameList에 'a1.jpg', 'z12345.jpg'

```python
filenameList = ['frame0.jpg', 'frame1.jpg', 'frame10.jpg', 'frame100.jpg', 'frame2.jpg', 'frame11.jpg', 'frame12.jpg', 'a1', 'z12345', '12345.jpg']

import re

def atoi(text):
    return int(text) if text.isdigit() else text

def natural_keys(text):
    return [ atoi(c) for c in re.split('(\d+)',text) ]

filenameList.sort(key=natural_keys)
filenameList
```



- result

```python
['12345.jpg',
 'a1.jpg',
 'frame0.jpg',
 'frame1.jpg',
 'frame2.jpg',
 'frame10.jpg',
 'frame11.jpg',
 'frame12.jpg',
 'frame100.jpg',
 'z12345.jpg']
```



- 스스로 풀지 못해 검색한 결과로 얻은 코드에서 ```list.sort(key = )```와 ```re.split('(\d+)', text)``` 코드를 이해하지 못해서 답변을 달지 않았다.
  - 정규 표현식에 대해서 익히지 않은 상태
  - 코드 분석 후 git에 commit 하기! (2020.12.11)
- 소스 코드 파악 후 commit (commit 후 날짜 기재하기!) : 



---



## Another answer (△)

```python
files_list = ['frame0.jpg', 'frame1.jpg', 'frame10.jpg', 'frame100.jpg', 'frame2.jpg', 'frame11.jpg', 'frame12.jpg', 'a1,jpg', 'z12345.jpg', '12345.jpg']

files_list.sort(key=lambda f: int(re.sub('\D', '', f))) 
```

- 위의 코드로는 숫자에 대한 정렬만 이루어지고, 숫자 앞의 영문자에 대해서는 정렬되지 않는다.

  - 내가 테스트를 위해 추가한 'a1.jpg', 'z12345.jpg', '12345.jpg'가 포함됨으로써 원하는 방식으로 정렬되지 않는다.

     (문자열의 패턴이 달라지면 정렬이 원하는 방식으로 되지 않는다.)

  

- result

```python
['frame0.jpg',
 'frame1.jpg',
 'a1.jpg',
 'frame2.jpg',
 'frame10.jpg',
 'frame11.jpg',
 'frame12.jpg',
 'frame100.jpg',
 'z12345.jpg',
 '12345.jpg']
```



---



## 참고 코드와 Another answer을 보고 정리

- 문자열 데이터에 문자와 숫자가 있을 때 이에 대한 정렬에는 정규 표현식과 이를 지원하는 re 라이브러리의 함수들을 사용해야 한다.

- 정규 표현식 코드 및 실행 결과 테스트 가능한 웹 페이지 link : https://regex101.com/r/cO8lqs/11

