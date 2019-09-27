# JAVA-Crud-operation-using-Servlet

Hi in this example I have use oracle database with table Name => emp 

Steps to create id with AUTO_INCREMENT on Oracle 11G.

=================================================================

Auto_increment  ORACLE-SQL  id.
You can refer this link => https://stackoverflow.com/questions/11296361/how-to-create-id-with-auto-increment-on-oracle

==================================================================

Step 1:-
CREATE TABLE dept (
  ID  NUMBER(10) NOT NULL,
  name VARCHAR2(50) NOT NULL,
  password VARCHAR2(50) NOT NULL,
  email VARCHAR2(50) NOT NULL,
  country VARCHAR2(50) NOT NULL);
  
------------------------------------------------------------------  

Step 2:-

ALTER TABLE dept ADD (
  CONSTRAINT deptt_pk PRIMARY KEY (ID));

-------------------------------------------------------------------
Step 3:-

CREATE SEQUENCE deptt_seq START WITH 1

OR

CREATE SEQUENCE dept_seq START WITH 1

------------------------------------------------------------------

Step 4:-

CREATE OR REPLACE TRIGGER deptt_bir 
BEFORE INSERT ON dept
FOR EACH ROW

BEGIN
  SELECT dept_seq.NEXTVAL
  INTO   :new.id
  FROM   dual;
END;
/
--------------------------------------------------------------------
