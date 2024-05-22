# **JOIN**

## **01. INNER JOIN**
> 두 TABLE_의 공통된 데이터 조회
<p align="center">
	<img src="https://github.com/kimdaehwi990731/Study_Oracle/assets/167949524/62be4eda-9d68-4bfd-89bd-5f9cb1db99a5" width="350" height="250"/>
</p>

### 00. JOIN 형식
#### 0-1. JOIN형식 1) FROM TABLE_A
  ```
  (INNER) JOIN TABLE_B ON TABLE_A 공통컬럼 = TABLE_B 공통컬럼
  ```
  - ⚠️ ON: JOIN 조건으로 공통된 데이터(컬럼)을 지정
  
#### 0-2.  JOIN형식 2) ORACLE에서만 사용하는 방식
  ```
    FROM TABLE_A, TABLE_B
    	WHERE ON의 JOIN 조건
  ```
---
### 1. ⚠️ 주의사항
  - 어떤 TABLE의 어떤 컬럼을 사용할 것인지 명시해야 함
  - 공통된 컬럼은 하나의 TABLE에서만 조회할 수 있도록 해야 함
---
### 2. 등가 JOIN & 비등가 JOIN
#### 2-1. 등가 JOIN
  - 공통된 컬럼의 값이 같은(=) 조건에 해당
  ```
  SELECT A.C1, A.C2, B.COMC1
    FROM TABLE_A A
    JOIN TABLE_B B
      ON A.COMC1 = B.COMC1;
  ```

#### 2-2. 비등가 JOIN
  - JOIN조건에서 값의 의미가 동일한 데이터들의 대/소비교를 해주는 형식의 JOIN(>, <, >=, <=, BETWEEN AND)
  ```
  SELECT A.C1, A.C2, B.GRADE
    FROM TABLE_A A
    JOIN TABLE_B B
      ON A.C3 BETWEEN LOWC3 AND HIC3;
  ```
---
### 3. SELF JOIN
#### 3-1. 두 TABLE이 동일할 때 사용되는 JOIN
<p align="center">
  <img src="https://github.com/kimdaehwi990731/Study_Oracle/assets/167949524/ce953e01-0135-4148-b587-0123fce3d88d" width="250" height="250"/>
</p>

  ```
  SELECT A1.C1, A1.C2, A2.C3, A2.C4
		FROM TABLE_A A1
		JOIN TABLE_A A2
			ON A1.C3 = A2.C3;
  ```
---
### 4. CROSS JOIN(잘못된 JOIN)
#### 4-1. 특징
  - 여러가지 TABLE을 JOIN할 때, JOIN 조건을 지정하지 않으면 CROSS JOIN이 발생
  - CROSS JOIN: JOIN되는 모든 TABLE의 데이터들이 1대1로 매핑되어 조화되는 현상
--- 
## **02. OUTER JOIN**
> INNER JOIN 결과에 추가로 기준이 되는 TABLE에 남아있는 데이터 조회

> ⚠️ OUTER는 생략 가능
### 00. OUTER JOIN 형식
#### 0-1. LEFT/RIGHT/FULL OUTER JOIN
```
SELECT A.A1, A.A2, AA.A1 , AA.A3
	FROM TABLE_A A
	(LEFT/RIGHT/FULL) TABLE_A AA
		ON A.A2 = AA.A2
```
---
### 1. LEFT OUTER JOIN
> FROM절에 사용한 TABLE 기준
---
### 2. RIGHT OUTER JOIN
> JOIN되는 절에 사용한 TABLE 기준
---
### 3. FULL OUTER JOIN
> FROM절 TABLE과 JOIN되는 TABLE 모두가 기준이 되어 FROM절 TABLE에만 존재하는 데이터와 JOIN되는 TABLE에만 존재하는 데이터도 모두 추가로 조회
 - 합집합을 행하는 JOIN
---
### **03. 다중 TABLE JOIN**

