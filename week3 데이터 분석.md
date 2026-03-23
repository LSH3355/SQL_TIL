# 데이터분석 3주차 정규과제

📌데이터분석 정규과제는 매주 정해진 분량의 『*혼자 공부하는 데이터 분석 with 파이썬*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **DataAnalysis_3rd_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=CE3_InvbmLY&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=6
https://www.youtube.com/watch?v=hhbzUEQWdTg&list=PLVsNizTWUw7FGzSRCkQrPEEe-ljVXgS7k&index=7
-->


## DataAnalysis_3rd_TIL

### 3장 데이터 정제하기
#### 01. 불필요한 데이터 삭제하기
#### 02. 잘못된 데이터 수정하기


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~81    | ✅         |
| 2주차 | p.84~151   | ✅         |
| 3주차 | p.154~219  | ✅         |
| 4주차 | p.222~279 | 🍽️         |
| 5주차 | p.282~325 | 🍽️         |
| 6주차 | p.328~379 | 🍽️         |
| 7주차 | p.382~430 | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->


# 1️⃣ 개념 정리 

## 01. 불필요한 데이터 삭제하기

<데이터 정제 : 수집된 데이터에서 오류가 있는 값이나 불필요한 데이터를 수정하거나 제거항ㅕ 분석에 사용할 수 있는 형태로 만드는 과정이다.
데이터 정제가 제대로 이루어지지 않으면 분석 결과의 정확도가 떨어지고 잘못된 판단으로 이어질 수 있다.

데이터 랭글링 : 데이터를 정리하는 과정뿐만 아니라 분석이나 머신러닝에 활용하기 적절한 형태로 데이터를 가공하고 변환하는 전체 과정을 의미

원소별 비교 : 판다스에서 데이터프레임이나 인덱스를 하나의 값과 비교하면, 해당 값이 모든 요소와 각각 비교되어 결과가 계산된다.

불리언 배열 : 원소별 비교의 결과는 True와 False 값으로 이루어진 배열 형태로 반환되며, 이를 통해 조건에 맞는 데이터를 쉽게 찾을 수 있다.>

## 02. 잘못된 데이터 수정하기

<NaN : 판다스에서 결측값을 나타낼 때 사용하는 표시 isna메서드를 이용하면 값이 NaN인지 확인할 수 있다.
정규 표현식 : 문자열에서 특정한 규칙이나 패턴을 찾아내기 위해 사용하는 표현 방식이다.>


# 2️⃣ 수행 인증

<<img width="512" height="593" alt="image" src="https://github.com/user-attachments/assets/3ea91087-7982-4756-bdb9-10b62657efe1" />
>
<<img width="482" height="596" alt="image" src="https://github.com/user-attachments/assets/3dbc3fb7-ecd0-4c06-b96d-ac466b28fe05" />
>
<<img width="476" height="208" alt="image" src="https://github.com/user-attachments/assets/51a84469-5c9f-41fd-8998-e2cd730424a7" />
>

# 3️⃣ 확인 문제

## 문제 1.

> **🧚Q. 다음 두 데이터프레임 df1, df2를 합쳐서 데이터프레임 df3를 만들려고 합니다.**  
> 적절한 판다스 명령을 선택해주세요.

<table>
<tr>

<td>

### df1

| index | col1 | col2 |
|-------|------|------|
| 0     | x    | 5    |
| 1     | y    | 6    |
| 2     | z    | 7    |

</td>

<td>

### df2

| index | col3 | col4 |
|-------|------|------|
| 0     | x    | 50   |
| 1     | y    | 60   |
| 2     | w    | 70   |

</td>

<td align="center" valign="middle">

<h2> ➜ </h2>

</td>

<td>

### df3 (결과)

| index | col1 | col2 | col3 | col4 |
|-------|------|------|------|------|
| 0     | x    | 5.0  | x    | 50.0 |
| 1     | y    | 6.0  | y    | 60.0 |
| 2     | z    | 7.0  | NaN  | NaN  |
| 3     | NaN  | NaN  | w    | 70.0 |

</td>

</tr>
</table>

```
1️⃣ pd.merge(df1, df2)
2️⃣ pd.merge(df1, df2, how='left')
3️⃣ pd.merge(df1, df2, left_on='col1', right_on='col3', how='outer')
4️⃣ pd.merge(df1, df2, left_on='col1', right_on='col3', how='inner')
```

```
3번
df1의 기준 컬럼 -> col1
df2의 기준 컬럼 -> col3
결과를 보면 x,y는 공통이고 z는 df1에만, w는 df2에만 있다.  모두 결과에 포함되므로 outer join을 사용해야 한다.
```



### 🎉 수고하셨습니다.
