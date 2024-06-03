### Stored Procedure
`01. 특정 기능 및 작업 처리를 위한 서브 프로그램`

`02. 단독 실행만 가능 (쿼리문 호출 불가)`

### Stored Function
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

