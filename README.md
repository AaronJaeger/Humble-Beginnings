# Humble-Beginnings
First Database
CREATE TABLE Title
(
titleCode VARCHAR(255),
titleDescription VARCHAR(255),
salary NUMBER(7,0),
CONSTRAINT Title_pk PRIMARY KEY (titleCode)
);

CREATE TABLE Department
(
deptCode INTEGER,
deptName VARCHAR(255),
location VARCHAR(255),
deptType VARCHAR(255),
CONSTRAINT Department_pk PRIMARY KEY (deptCode)
);

CREATE TABLE Employee
(
ID INTEGER,
emplName VARCHAR(255),
emplType VARCHAR(255),
deptCode INTEGER,
titleCode VARCHAR(255),
CONSTRAINT Employee_pk PRIMARY KEY (ID),
CONSTRAINT Employee_deptcode_fk FOREIGN KEY (deptCode) REFERENCES Department(deptCode),
CONSTRAINT Employee_title_fk FOREIGN KEY (titleCode) REFERENCES Title(titleCode)
);

INSERT INTO Title
VALUES ('T1','Accountant','10000');
INSERT INTO Title
VALUES ('T2','Analyst','20000');
INSERT INTO Title
VALUES ('T3','Programmer','30000');
INSERT INTO Title
VALUES ('T4','DBA','40000');
INSERT INTO Title
VALUES ('T5','Manager','50000');

INSERT INTO Department
VALUES (001,'Computer Center','Boston','IT');
INSERT INTO Department
VALUES (002,'Budget','New York','Business');
INSERT INTO Department
VALUES (003,'Marketing','Boston','Marketing');
INSERT INTO Department
VALUES (004,'Database Support','Cleveland','IT');
INSERT INTO Department
VALUES (005,'Purchasing','New York','Business');

INSERT INTO Employee
VALUES (1,'John','Full-time',002,'T1');
INSERT INTO Employee
VALUES (2,'Adam','Consultant',001,'T3');
INSERT INTO Employee
VALUES (3,'Mary','Part-time',004,'T4');
INSERT INTO Employee
VALUES (4,'Peter','Full-time',003,'T2');
INSERT INTO Employee
VALUES (5,'Scott','Consultant',002,'T1');
INSERT INTO Employee
VALUES (6,'Susan','Full-time',005,'T5');
INSERT INTO Employee
VALUES (7,'Alex','Part-time',004,'T2');
