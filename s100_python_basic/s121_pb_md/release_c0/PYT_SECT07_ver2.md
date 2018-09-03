
# Industry 4.0 의 중심, BigData

<div align='right'><font size=2 color='gray'>Data Processing Based Python @ <font color='blue'><a href='https://www.facebook.com/jskim.kr'>FB / jskim.kr</a></font>, 김진수</font></div>
<hr>

## <font color='brown'>실습 프로젝트, Practice Project</font>
> 
- 구구단 출력하기
- 총합과 팩토리얼 테이블 출력하기
- 문자열 바꾸기 
- 대소문자 변경
-실습 프로젝트, 
- 도서 목록 입력 및 출력
- 그래픽(Turtle Graphics) 출력하기
- 모양 그리기, 다각형 그리기
- 패턴을 찾아 모양을 그리기


### 구구단 출력


```python
dan = input('출력할 단을 입력해주세요.[2~9] ')
# dan = 5
dan = int(dan)
gop = 0

print(dan, '단 출 력 \n' + '-'*20)
# print(dan, '단 출 력 - Case1\n' + '-'*20)
for i in range(9):
    num = i + 1
    gop = dan * num
    print(dan, '*', num, '=', gop)

```

### 팩토리얼 표: 0~100 까지의 Factorial Table


```python
# 팩토리얼 표: 0~100 까지의 Factorial Table
idx, gop, sum  = 0, 0, 0
factorial = [ ]
total_sum = [ ]

# 입력값 확인
# num_check = list(range(10))
num_chk_list = list('0123456789')
# print(num_chk_list)

while True:
    key_in = input('숫자를 입력해 주세요. (1~100)')
    chk_num = True
    for char in key_in:
        is_num = char in num_chk_list
        chk_num *= is_num
        if not is_num:
            break
        # print(char, is_num, chk_num)

    if chk_num:
        last_num = int(key_in)
        print('입력한 숫자 :', last_num)
        break
    else:
        print('입력한 값이 숫자가 아닙니다.')

# print('숫자확인 완료!')
# last_num = 10


# 입력값이 숫자인 경우, 미션 수행
title =  str(last_num) + '까지의 팩토리얼 테이블 구하기!!'
print('-'*100)
print(title)
print('-'*100)

numbers = list(range(last_num+1))
# print('numbers :', numbers)

while idx < len(numbers):
    num = numbers[idx]
    gop *= num
    # if gop < 1:
    #     gop = 1
    gop = 1 if gop<1 else gop

    factorial.append(gop)
    idx += 1

for fact_num in range(len(factorial)):
    print(str(fact_num)+'! = ', factorial[fact_num])

```

### 팩토리얼 표: 0~100 까지의 Factorial Table


```python
# 팩토리얼 표: 0~100 까지의 Factorial Table
idx, gop, sum  = 0, 0, 0
factorial = [ ]
total_sum = [ ]

# 입력값 확인
# num_check = list(range(10))
num_chk_list = list('0123456789')
# print(num_chk_list)

while True:
    key_in = input('숫자를 입력해 주세요.[1~100] => ')
    chk_num = True
    for char in key_in:
        is_num = char in num_chk_list
        chk_num *= is_num
        if not is_num:
            break
        # print(char, is_num, chk_num)

    if chk_num:
        last_num = int(key_in)
        print('입력한 숫자 :', last_num)
        break
    else:
        print('입력한 값이 숫자가 아닙니다.')

# print('숫자확인 완료!')
# last_num = 10

# 입력값이 숫자인 경우, 미션 수행
title =  str(last_num) + ' 까지의 합계 및 팩토리얼 테이블 구하기!!'
print('-'*50)
print(title)
print('-'*50)

numbers = list(range(last_num+1))
# print('numbers :', numbers)

while idx < len(numbers):
    num = numbers[idx]
    sum += num
    gop *= num

    gop = 1 if gop<1 else gop
    # if gop < 1:
    #     gop = 1

    total_sum.append(sum)
    factorial.append(gop)
    idx += 1

print(last_num, '까지의 합계는', total_sum[-1], '입니다.')
print('아래는 팩토리얼 테이블입니다.')
for fact_num in range(len(factorial)):
    print(str(fact_num)+'!\t= ', factorial[fact_num])

```

### 문자열 대소문자 바꾸기


```python
# swap case
# s = 'The BigpyCraft find the information to design valuable society with Technology & Craft.'
s = input('영어 대소문자로 이루어진 문장을 입력하세요.\n')  # 문자열 입력

print('모두 대문자로 출력\n' + s.upper())   # 대문자로 모두 변환

print('모두 소문자로 출력\n' + s.lower())   # 소문자로 모두 변환

new_s = str()   # 신규 문자열 형 변수 선언

for c in s:     # 입력 받은 문자를 하나씩 꺼내서 c에 대입

    if c.islower():         # 해당 문자가 소문자이면
        new_s += c.upper()  # 대문자로 변경하여 new_s에 붙이기
    else:                   # 해당 문자가 대문자이면
        new_s += c.lower()  # 소문자로 변경하여 new_s에 붙이

print('대소문자 바꿔서 출력\n' + new_s)             # 최종 변환 결과 출력

print('대소문자 바꿔서 출력\n' + s.swapcase())      # 대소문자 모두 변환


```

### 문자열 순서 바꾸기


```python
# reverse case
# s = 'Lief is too short, You nee Python.'
s = input('영어 문장을 입력하세요.\n')  # 문자열 입력

new_s = str()                       # 신규 문자열형 변수 선언

for x in range(len(s)-1, -1, -1):   # range()를 활용한 역순 인덱스 추출
    new_s += s[x]                   # 문자열을 끝에서부터 앞으로 신규 변수에 붙이기

print(new_s)                        # 위 결과 출력

print(s[::-1])                      # 인덱스 사용법으로 역순 출력

```

### 도서 목록 입력 및 출력


```python
books = list()      # 책 목록 선언

# 책 목록 만들기
books.append({'제목':'파이썬 프로그램', '출판연도':'2016', '출판사':'A', '쪽수':200, '추천유무':False})
books.append({'제목':'플랫폼 비즈니스', '출판연도':'2013', '출판사':'B', '쪽수':584, '추천유무':True})
books.append({'제목':'빅데이터 마케팅', '출판연도':'2014', '출판사':'A', '쪽수':296, '추천유무':True})
books.append({'제목':'외식경영 전문가', '출판연도':'2010', '출판사':'B', '쪽수':526, '추천유무':False})
books.append({'제목':'십억만 벌어보자', '출판연도':'2013', '출판사':'A', '쪽수':248, '추천유무':True})

for book in books:  # 책 한 권씩 꺼내기 위한 루프 선언
    print(book)     # 책 한 권 데이터 출력

```


```python
# case 1
many_page = list()                              # 책 리스트 선언
recommends = list()                             # 책 리스트 선언
all_pages = int()                               # 전체 쪽수 변수 선언
pub_companies = set()                           # 출판사 집합 선

for book in books:                              # 책 한 권씩 꺼내기 위한 루프 선언
    if book['쪽수'] > 250:                       # 250쪽 넘는 책 목록 만들기
        many_page.append(book['제목'])
    if book['추천유무']:                          # 책 추천 목록 만들기
        recommends.append(book['제목'])
    all_pages = all_pages + book['쪽수']         # 책 쪽수 더하기
    pub_companies.add(book['출판사'])

print('쪽수가 250 쪽 넘는 책 리스트:', many_page)
print('내가 추천하는 책 리스트:', recommends)
print('내가 읽은 책 전체 쪽수:', all_pages)
print('내가 읽은 책의 출판사 목록:', pub_companies)

```


```python
# case 2
many_page     = [ book['제목']  for book in books  if book['쪽수'] > 250 ]
recommends    = [ book['제목']  for book in books  if book['추천유무']  ]
pub_companies = { book['출판사'] for book in books }
all_pages = 0
for book in books: all_pages += book['쪽수']

print('쪽수가 250 쪽 넘는 책 리스트:', many_page)
print('내가 추천하는 책 리스트:', recommends)
print('내가 읽은 책 전체 쪽수:', all_pages)
print('내가 읽은 책의 출판사 목록:', pub_companies)
```

### 모양 그리기
> Hint : 대각선 길이를 구하는 제곱근 (Root Square)
- import math
- math.sqrt(width**2 + height**2)


```python
import turtle
import math

width = 200
diagonal = math.sqrt(width**2 + width**2)

turtle.shape('turtle')
turtle.color('blue')
turtle.pensize(5)

for i in range(4):
    turtle.left(90)
    turtle.forward(width)

turtle.left(90+45)
turtle.forward(diagonal)
turtle.right(90)
turtle.forward(diagonal/2)
turtle.right(90)
turtle.forward(diagonal/2)
turtle.right(90)
turtle.forward(diagonal)

turtle.done()
```

### 다각형 그리기


```python
import turtle as t

print('다각형을 그리는 예제입니다.')
var1 = input('변의 수를 입력해주세요? [3-8] ')
var2 = input('한변의 길이를 입력해주세요? [100-200] ')
# var2 = str(150)

num_of_side = int(var1)
len_of_side = int(var2)

angle = 360.0 / num_of_side
c_mod = num_of_side % 3
color = 'red' if c_mod==0 else 'green' if c_mod==1 else 'blue'

t.begin_fill()
t.color(color)
t.pensize(5)

for i in range(num_of_side):
    t.forward(len_of_side)
    t.left(angle)

t.end_fill()

t.done()

```

### 패턴을 찾아 모양 그리기
> 반복문(for 혹은 while)을 사용하여 그려보기
- 1단계 : 먼저 정육각형을 그려보기
- 2단계 : 정육각형을 회전 이동하면서 반복하여 그려보기


```python
import turtle

turtle.color('red')
turtle.pensize(10)

for i in range (6):
    # 육각형 그리기
    for j in range(6):
        turtle.forward(100)
        turtle.left(360/6)

    # 패턴찾기
    turtle.forward(100)
    turtle.right(60)

turtle.done()
```

### 복합 패턴을 찾아 모양 그리기
> 복합적인 패턴을 찾아서, 반복문을 적용하기
- 패턴 : 각도, 길이, 굵기, 색상
- Hint : 적용된 색상 값은 아래와 같다.
- colors = ['red', 'green', 'blue', 'yellow', 'purple', 'cyan', 'magenta', 'violet']


```python
import turtle as t

colors = ['red', 'green', 'blue', 'yellow', 'purple', 'cyan', 'magenta', 'violet']

for i in range(45):
    t.color(colors[i%len(colors)])
    t.forward(2 + i*5)
    t.left(45)
    t.width(i)

t.done()
```

<hr>
<marquee><font size=3 color='brown'>The BigpyCraft find the information to design valuable society with Technology & Craft.</font></marquee>
<div align='right'><font size=2 color='gray'> &lt; The End &gt; </font></div>