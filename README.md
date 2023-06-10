## 동치관계 확인 코드

동치관계 코드는 관계 R 이 set 으로 주어질 때, 이 관계 R 이 동치 관계인지를 판단하는 코드이다. 

동치 관계인지 판단하기 위해서는 1. 반사적 2. 대칭적 3.추이적이 모두성립 할 시 동치관계가 성립한다.

## 설치 , 실행 

이 코드의 정의된 관계는 다음과 같다.  R = {(1, 1), (1, 3), (2, 2), (3, 3),(3, 1), (3, 4), (4, 4), (4, 3)} # 정의된 관계 
동치 관계인경우 True 동치 관계가 아닌경우 False가 나온다.

py 파일을 다운받은 뒤  py 파일을 colab에 업로드후 다음 코드를 실행시킨다.
```python
! python3 202210688_안혁진_코드과제4_equiv_relation_check_student.py
```

## 코드설명 
```python
def check_transitive(R):
    for (a, b) in R:
        for (c, d) in R:
            if b == c and (a, d) not in R:
                return False
    return True
```

- 추이적 : "aRb이고 bRc이면 aRc가 성립한다. 성립하지 않을시 False"

```python
def check_symmetric(R):
    for (a, b) in R:
        if (b, a) not in R:
            return False
    return True
```
- 대칭적 : "aRb가 성립하면 bRa도 성립한다. 성립하지 않을시 False "
```python
def check_reflexive(R):
    for a in set(x[0] for x in R):
        if (a, a) not in R:
            return False
    return True
```
- 반사적 :  "All x ∈ X, if (x,x)∈ R 성립하지 않을시 False "  
## 팀원
안혁진,이은서
