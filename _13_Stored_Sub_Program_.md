## **📜 Stored Sub Program**
#### 01. 특징
`DB에 PL/SQL구문을 저장 ➡️ 필요할 때마다 PL/SQL구문 호출`

#### 02. 장점
`Oracle 저장/공유 가능 ➡️ 메모리 사용 효율, 성능, 재사용성 향상`

#### 03. 종류
`SP(Stored Procedure)`

`SF(Stored Function)`

`Trigger`

---
### **📜 Stored Procedure**
`01. 특정 기능 및 작업 처리를 위한 서브 프로그램`

`02. 단독 실행만 가능 (쿼리문 호출 불가)`

#### 01. 생성 ~ 삭제
`01. 생성`
```
CREATE OR REPLACE PROCEDURE {프로시저명}
IS/AS {선언부}
BEGIN {실행부}
EXCEPT {예외처리부}
END {프로시저명};
/
```
---
### **📜 Stored Function**
`프로시저(procedure)와 동일한 역할을 하는 프로그램`
#### 01. 차이점
|   | Procedure | Stored Function |
|:-----------:|:--------------|:--------------|
|호출| 1. EXEC 단독 호출<br> 2. PL/SQL구문 호출 | 1. EXEC 단독 호출<br> 2. PL/SQL구문 호출<br> 3. 쿼리문 호출|
|매개변수| IN, OUT, IN/OUT모드|IN모드|
|반환|OUT, IN/OUT으로 지정된 여러가지의 값 반환|RETURN문을 통해 하나의 값만 반환|

#### 02. 생성 ~ 삭제
`01. 생성`
```
CREATE OR REPLACE FUNCTION {함수명}(
  매개변수1 [IN] 자료형1
  매개변수2 [IN] 자료형2
  ...
)
RETURN 자료형 IS {선언부};
BEGIN
  {실행부}
  RETURN 자료형;
END;
/
```
`02. 삭제`
```
DROP FUNCTION {함수명}
```
---
### **📜 Trigger**
`DB 안의 특정 상황/동작/이벤트 발생 시, 자동으로 실행되는 기능을 정의하는 서브 프로그램`

#### 01.특징
##### 001. 장점
`01. 제약조건만으로는 어려운 복잡한 데이터 규칙 정의 가능`

`02. 데이터 변경과 관련된 일련의 정보 기록 가능 ➡️ 공유 데이터의 보안성/안전성과 오류 발생시, 대처 가능성 향상`

##### 002. 단점
`무분별한 사용시, DB 성능 하락`

##### 003. 기타
`DML, DDL 등을 지정할 수 있음`

#### 02. 선언
```
CREATE
```
