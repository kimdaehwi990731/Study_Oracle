## **📜 Join**

### 📜 Inner Join
`두 테이블의 공통된 데이터 조회`
<p align="center">
	<img src="https://github.com/kimdaehwi990731/Study_Oracle/assets/167949524/62be4eda-9d68-4bfd-89bd-5f9cb1db99a5" width="350" height="250"/>
</p>

#### 01. 생성
##### 001. 기본 방식
```
(INNER) JOIN {테이블B} ON {테이블A 공통칼럼} = {테이블B 공통칼럼};
```

##### 002. ORACLE에서만 사용하는 방식
```
FROM {테이블A}, {테이블B}
WHERE ON {JOIN 조건}
```
- ⚠️ 참고
  
  `01. 어떤 테이블의 어떤 칼럼을 사용할 것인지 명시해야 함`
  
  `02. 공통된 칼럼은 하나의 테이블에서만 조회할 수 있도록 해야 함`

#### 02. 등가 Join
`공통된 칼럼의 값이 같은(=) 조건에 해당`

```
SELECT {칼럼1}, {칼럼2}
FROM {테이블A}
JOIN {테이블B} ON {테이블A 공통칼럼} = {테이블B 공통칼럼};
```

#### 03. 비등가 Join
`Join 조건에서 값의 의미가 동일한 데이터들의 대/소비교를 해주는 형식의 Join(>, <, >=, <=, Between And)`

```
SELECT {칼럼1}, {칼럼2}
FROM {테이블A}
JOIN {테이블B} ON {테이블A 공통칼럼} BETWEEN {테이블B의 작은 값을 가진 칼럼} AND {테이블B의 큰 값을 가진 칼럼};
```
---
#### 04. Self Join
`두 테이블이 동일할 때 사용되는 Join`
<p align="center">
  <img src="https://github.com/kimdaehwi990731/Study_Oracle/assets/167949524/ce953e01-0135-4148-b587-0123fce3d88d" width="250" height="250"/>
</p>

```
SELECT {칼럼1}, {칼럼2}
FROM {테이블A1} {테이블A 별칭1}
JOIN {테이블A2} {테이블A 별칭2} ON {테이블A1 공통칼럼} = {테이블A2 공통칼럼};
```

---
#### 05. Cross Join(잘못된 Join)
`01. 여러가지 테이블을 Join 할 때, Join 조건을 지정하지 않으면 발생`

`02. Cross Join: Join 되는 모든 테이블의 데이터들이 1대1로 매핑되어 조화되는 현상`

--- 
### 📜 Outer Join
`01. Inner Join 결과에 추가로 기준이 되는 테이블에 남아있는 데이터 조회`

`02. OUTER는 생략 가능`
#### 01. 생성
```
SELECT {칼럼1}, {칼럼2}
FROM {테이블A1} {테이블A 별칭1}
(LEFT/RIGHT/FULL) {테이블A1} {테이블A 별칭2} ON {테이블A 공통칼럼} = {테이블B 공통칼럼};
```

##### 001. Left Outer Join
`From절에 사용한 테이블 기준`


##### 002. Right Outer Join
`Join 되는 절에 사용한 테이블 기준`

##### 003. Full Outer Join
`01. From절 테이블과 Join 되는 테이블 모두가 기준이 되어 From절 테이블에만 존재하는 데이터와 Join 되는 테이블에만 존재하는 데이터도 모두 추가로 조회`

`02. 합집합을 행하는 Join`

### 📜 다중 테이블 Join
`세개 이상의 테이블이 Join 될 때, 관계를 형성하여 데이터를 추출하는 방식`
```
FROM {테이블A}
JOIN {테이블B} ON {테이블A 공통칼럼} = {테이블B 공통칼럼1}
JOIN {테이블C} ON {테이블B 공통칼럼2} = {테이블C 공통칼럼};
```
