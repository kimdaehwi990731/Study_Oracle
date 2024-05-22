## **JOIN**

### **INNER JOIN**
1. 두 TABLE_의 공통된 데이터 조회
<p align="center">
  <img src="https://github.com/kimdaehwi990731/Study_Oracle/assets/167949524/62be4eda-9d68-4bfd-89bd-5f9cb1db99a5" width="350" height="250"/>
</p>
        
  - FROM TABLE_A
     ```
     (INNER) JOIN TABLE_B ON TABLE_A 공통컬럼 = TABLE_B 공통컬럼
     ```
    ⚠️ ON: JOIN 조건으로 공통된 데이터(컬럼)을 지정
    - ORACLE에서만 사용하는 방식의 JOIN
      ```
      FROM TABLE_A, TABLE_B
        WHERE ON의 JOIN 조건
      ```
2. ⚠️ 주의사항
  - 어떤 TABLE의 어떤 컬럼을 사용할 것인지 명시해야 함
  - 공통된 컬럼은 하나의 TABLE에서만 조회할 수 있도록 해야 함

3. 등가JOIN & 비등가JOIN
  - 등가JOIN
      - 
  - 비등가JOIN
