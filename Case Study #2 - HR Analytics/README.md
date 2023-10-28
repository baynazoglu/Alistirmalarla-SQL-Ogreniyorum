# 💼 Case Study #2 HR ANALYTICS

<img src="https://netchex.com/wp-content/uploads/2022/12/HR-Analytics-768x512.png" alt="Image" width="500" height="420">

## 📚 Table of Contents
- [Business Task](#business-task)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Questions and Solutions](#questions-and-solutions)
  
Please note that all the information regarding the case study has been sourced from the following link: [Here](https://www.udemy.com/course/alistirmalarla-sql-ogreniyorum/)


I also published this on [Medium](https://medium.com/@fbaynazoglu)

If you have any questions, reach out to me on [Linkedin](https://www.linkedin.com/in/baynazoglu/)
***

## Business Task
In this case we will be looking at human resources datas and we will be focusing on some queries that our manager wants from us.

## Entity Relationship Diagram

![HR Analytics](https://github.com/baynazoglu/Alistirmalarla-SQL-Ogreniyorum/blob/c4e5739eaa4b272762ab3fbca2f8d62c7e169750/Case%20Study%20%232%20-%20Pizza%20Runner/ENTITY%20DIAGRAM%3DCASE2.jpg)



## Questions and Solutions



### 1.What is the query that returns the list of employees who are still working in our company? 
Note: Employees that "OUTDATE" values are null means that they are still working.

````sql
SELECT TOP 10 * FROM PERSON
WHERE OUTDATE IS NOT NULL
````

**Answer**
| ID | CODE | TCNUMBER    | NAME_  | SURNAME         | GENDER | BIRTHDATE  | INDATE     | OUTDATE    | DEPARTMENTID | POSITIONID | PARENTPOSITIONID | MANAGERID | TELNR          | SALARY |
| -- | ---- | ----------- | ------ | --------------- | ------ | ---------- | ---------- | ---------- | ------------ | ---------- | ---------------- | --------- | -------------- | ------ |
| 2  | 2    | 74789296130 | Azat   | COŞKUNYÜREK     | E      | 7.05.1963  | 6.04.2019  | 14.03.2020 | 4            | 38         | 28               | NULL      | (0322) 2235724 | 5818   |
| 3  | 3    | 86856513494 | Kemal  | TEKYİĞİT        | E      | 10.06.1959 | 20.01.2017 | 5.08.2018  | 7            | 41         | 31               | NULL      | (0322) 2338441 | 5805   |
| 5  | 5    | 26046030220 | Ferhat | CINAR           | E      | 17.05.1953 | 19.10.2018 | 19.04.2020 | 8            | 42         | 32               | NULL      | (0322) 2339074 | 5550   |
| 6  | 6    | 67221555969 | Tayfun | ŞENDİL          | E      | 8.10.1956  | 6.02.2015  | 12.07.2017 | 8            | 42         | 32               | NULL      | (0322) 2235363 | 5270   |
| 7  | 7    | 43691911318 | Gülşen | ÇOLAK           | K      | 22.07.1956 | 26.07.2019 | 18.05.2020 | 5            | 39         | 29               | NULL      | (0322) 2339785 | 4930   |
| 8  | 8    | 84870496920 | Deniz  | ERAVCI          | K      | 4.07.1977  | 25.07.2018 | 16.09.2019 | 8            | 42         | 32               | NULL      | (0322) 2231829 | 4915   |
| 10 | 10   | 64660973116 | Burhan | TOROSLUOĞLU     | E      | 13.12.1957 | 21.10.2015 | 3.04.2019  | 2            | 36         | 26               | NULL      | (0322) 2232544 | 4975   |
| 11 | 11   | 60820106615 | Meliha | ŞİRVANLI        | K      | 9.04.1976  | 1.07.2017  | 30.11.2018 | 2            | 36         | 26               | NULL      | (0322) 2232020 | 5393   |
| 12 | 12   | 79689059342 | Engin  | HACIİBRAHİMOGLU | E      | 28.06.1965 | 14.03.2018 | 2.01.2019  | 3            | 37         | 27               | NULL      | (0322) 2232587 | 5149   |
| 16 | 16   | 43712644333 | Zahide | CAYMAZ          | K      | 28.12.1995 | 22.03.2015 | 6.09.2019  | 7            | 41         | 31               | NULL      | (0322) 2234715 | 5863   |
|    |

***

 ### 2. Write the query that retrieves the number of WOMEN and MEN who are still working in the company based on departments.

Solution-

````sql
SELECT D.DEPARTMENT,
CASE
	WHEN P.GENDER='E'THEN 'ERKEK'
	ELSE 'KADIN'
END AS GENDER,
COUNT(P.ID) AS CUSTOMERCOUNT FROM PERSON P
INNER JOIN DEPARTMENT D ON P.DEPARTMENTID = D.ID
WHERE P.OUTDATE IS NOT NULL
GROUP BY D.DEPARTMENT,P.GENDER
ORDER BY DEPARTMENT,GENDER
````

**Answer**

| DEPARTMENT          | GENDER | CUSTOMERCOUNT |
| ------------------- | ------ | ------------- |
| BİLGİ TEKNOLOJİLERİ | ERKEK  | 41            |
| BİLGİ TEKNOLOJİLERİ | KADIN  | 36            |
| FİNANS              | ERKEK  | 39            |
| FİNANS              | KADIN  | 42            |
| İLETİŞİM            | ERKEK  | 3             |
| İLETİŞİM            | KADIN  | 7             |
| İNSAN KAYNAKLARI    | ERKEK  | 35            |
| İNSAN KAYNAKLARI    | KADIN  | 40            |
| MUHASEBE            | ERKEK  | 39            |
| MUHASEBE            | KADIN  | 38            |
| PAZARLAMA           | ERKEK  | 32            |
| PAZARLAMA           | KADIN  | 45            |
| PLANLAMA            | ERKEK  | 37            |
| PLANLAMA            | KADIN  | 31            |
| SATINALMA           | ERKEK  | 38            |
| SATINALMA           | KADIN  | 38            |
| SATIŞ               | ERKEK  | 1             |
| SATIŞ               | KADIN  | 3             |
| YÖNETİM             | ERKEK  | 7             |
| YÖNETİM             | KADIN  | 9             |
|                     |

***

### 3. Write the query that retrieves the number of WOMEN and MEN who are still working in the company based on departments by creating two columns as "MALE_PERSONCOUNT" and "FEMALE_PERSONCOUNT".

Solution-

````sql
SELECT D.DEPARTMENT,
(SELECT COUNT(*) FROM PERSON P WHERE P.GENDER ='E' AND P.DEPARTMENTID=D.ID AND P.OUTDATE IS NOT NULL) AS 'MALE_PERSONCOUNT',
(SELECT COUNT(*) FROM PERSON P WHERE P.GENDER ='K' AND P.DEPARTMENTID=D.ID AND P.OUTDATE IS NOT NULL) AS 'FEMALE_PERSONCOUNT'
FROM DEPARTMENT D
ORDER BY 1
````

**Answer**

| BİLGİ TEKNOLOJİLERİ | 41 | 36 |
| ------------------- | -- | -- |
| FİNANS              | 39 | 42 |
| İLETİŞİM            | 3  | 7  |
| İNSAN KAYNAKLARI    | 35 | 40 |
| MUHASEBE            | 39 | 38 |
| PAZARLAMA           | 32 | 45 |
| PLANLAMA            | 37 | 31 |
| SATINALMA           | 38 | 38 |
| SATIŞ               | 1  | 3  |
| YÖNETİM             | 7  | 9  |
|                     |

***

### A new chief (--PLANNING CHIEF--) has been hired in the Planning department of our company and we want to determine his salary. Write a query that brings minimum, maximum and average chief salary for the planning department.
--NOTE: Including those who quit their job.

--Solution 1 -
````sql
SELECT PT.POSITION,COUNT(P.SALARY) [HOW MANY PEOPLE],AVG(P.SALARY)AS AVG_SALARY,MAX(P.SALARY) AS MAX_SALARY,MIN(P.SALARY) AS MIN_SALARY
FROM PERSON P
INNER JOIN POSITION PT ON P.POSITIONID=PT.ID
WHERE PT.POSITION = 'PLANLAMA ŞEFİ'
GROUP BY PT.POSITION
````

--Solution 2 -
-Using Subquery 

````sql
SELECT PT.POSITION,
(SELECT MIN(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID) AS MIN_SALARY,
(SELECT AVG(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID)AS AVG_SALARY,
(SELECT MAX(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID) AS MAX_SALARY
FROM POSITION PT
WHERE POSITION ='PLANLAMA ŞEFİ'
````

**Steps**
-AVG () computes the average of a set of values by dividing the sum of those values by the count of nonnull values
-The MIN() function returns the smallest value of the selected column. The MAX() function returns the largest value of the selected column.

**Answer**

| POSITION      | MIN_SALARY | AVG_SALARY | MAX_SALARY |
| ------------- | ---------- | ---------- | ---------- |
| PLANLAMA ŞEFİ | 7926       | 9239       | 10427      |
|               |



***


### 5. How many current employees are there in each position and what is their average salary?

--Solution 1- 

````sql
SELECT PT.POSITION,COUNT(P.SALARY) [HOW MANY PEOPLE],ROUND(AVG(P.SALARY),0)AS AVG_SALARY,ROUND(MAX(P.SALARY),0) AS MAX_SALARY,ROUND(MIN(P.SALARY),0) AS MIN_SALARY
FROM PERSON P
RIGHT JOIN POSITION PT ON P.POSITIONID=PT.ID
WHERE OUTDATE IS NOT NULL
GROUP BY PT.POSITION
ORDER BY PT.POSITION
````

--Solution 2- 
--With Subquery  

````sql
SELECT PT.POSITION,
(SELECT COUNT(P.SALARY) FROM PERSON P WHERE P.POSITIONID= PT.ID AND OUTDATE IS NOT NULL) AS [HOW MANY PEOPLE],
(SELECT AVG(P.SALARY) FROM PERSON P WHERE P.POSITIONID= PT.ID AND OUTDATE IS NOT NULL)AS AVG_SALARY,
(SELECT MAX(P.SALARY) FROM PERSON P WHERE P.POSITIONID= PT.ID AND OUTDATE IS NOT NULL) AS MAX_SALARY,
(SELECT MIN(P.SALARY) FROM PERSON P WHERE P.POSITIONID= PT.ID AND OUTDATE IS NOT NULL) AS MIN_SALARY
FROM POSITION PT
ORDER BY POSITION
````

**Basamak**

--We got 2 different results in two different solutions. Because when we made group by with inner join, we did the process according to the "position" column. But in Subquery method, we did group by according to "positionid". Since the purchasing chief had two different IDs, he was in 2 different rows in the solution with subquery.


**Answer**

| POSITION                        | HOW MANY PEOPLE | AVG_SALARY | MAX_SALARY | MIN_SALARY |
| ------------------------------- | --------------- | ---------- | ---------- | ---------- |
| BİLGİ TEKNOLOJİLERİ MEMURU      | 66              | 5108       | 5962       | 4005       |
| BİLGİ TEKNOLOJİLERİ MÜDÜR YRD.  | 3               | 10769      | 11795      | 9941       |
| BİLGİ TEKNOLOJİLERİ MÜDÜRÜ      | 3               | 16959      | 17634      | 15850      |
| BİLGİ TEKNOLOJİLERİ ŞEFİ        | 3               | 10063      | 10635      | 9539       |
| FİNANS MEMURU                   | 68              | 5039       | 5988       | 4001       |
| FİNANS MÜDÜR YRD.               | 2               | 11439      | 11445      | 11432      |
| FİNANS MÜDÜRÜ                   | 3               | 14751      | 17358      | 12013      |
| FİNANS ŞEFİ                     | 4               | 9523       | 10151      | 8792       |
| GENEL MÜDÜR                     | 2               | 20023      | 21645      | 18400      |
| İDARİ MALİ İŞLERDEN SORUMLU GMY | 2               | 16652      | 18352      | 14951      |
| İK'DAN SORUMLU GMY              | 3               | 18322      | 19568      | 17513      |
| İLETİŞİM MEMURU                 | 70              | 5026       | 5958       | 4061       |
| İLETİŞİM MÜDÜRÜ                 | 4               | 15381      | 17010      | 13385      |
| İLETİŞİM ŞEFİ                   | 2               | 9522       | 9890       | 9154       |
| İNSAN KAYNAKLARI MEMURU         | 72              | 5044       | 5994       | 4062       |
| İNSAN KAYNAKLARI MÜDÜR YRD.     | 2               | 13861      | 14037      | 13685      |
| İNSAN KAYNAKLARI MÜDÜRÜ         | 2               | 14305      | 14831      | 13779      |
| İNSAN KAYNAKLARI ŞEFİ           | 1               | 8111       | 8111       | 8111       |
| MUHASEBE MEMURU                 | 73              | 4928       | 5992       | 4024       |
| MUHASEBE MÜDÜR YRD.             | 3               | 11614      | 13163      | 9601       |
| MUHASEBE MÜDÜRÜ                 | 2               | 16649      | 16799      | 16498      |
| MUHASEBE ŞEFİ                   | 3               | 8898       | 10153      | 7567       |
| PAZARLAMA MEMURU                | 61              | 5027       | 5994       | 4092       |
| PAZARLAMA MÜDÜR YRD.            | 3               | 11119      | 12571      | 9766       |
| PAZARLAMA MÜDÜRÜ                | 1               | 12329      | 12329      | 12329      |
| PAZARLAMA ŞEFİ                  | 3               | 9240       | 10529      | 8050       |
| PLANLAMA MÜDÜR YRD.             | 2               | 12744      | 13661      | 11827      |
| PLANLAMA MÜDÜRÜ                 | 3               | 15102      | 17794      | 12189      |
| PLANLAMA ŞEFİ                   | 1               | 9030       | 9030       | 9030       |
| SATINALMA MEMURU                | 68              | 5025       | 5985       | 4021       |
| SATINALMA MÜDÜR YRD.            | 3               | 11716      | 12340      | 11197      |
| SATINALMA MÜDÜRÜ                | 4               | 16410      | 17493      | 14222      |
| SATINALMA ŞEFİ                  | 6               | 9701       | 10318      | 8862       |
| SATIŞ MEMURU                    | 3               | 4471       | 4664       | 4310       |
| SATIŞ MÜDÜR YRD.                | 3               | 12089      | 14001      | 10336      |
| SATIŞ MÜDÜRÜ                    | 1               | 15646      | 15646      | 15646      |
| SATIŞ ŞEFİ                      | 3               | 9234       | 10764      | 7600       |
| TEKNİK GMY                      | 3               | 16929      | 18538      | 14115      |
|                                 |

***


### 6.Write the query that lists the number of personnel hired by years based on men and women.

--Solution-

````sql
SELECT  DISTINCT YEAR(P.INDATE) AS YEAR_,
(SELECT COUNT(*) FROM PERSON WHERE GENDER='E' AND YEAR(INDATE)=YEAR(P.INDATE)) AS MALECOUNT_,
(SELECT COUNT(*) FROM PERSON WHERE GENDER='K' AND YEAR(INDATE)=YEAR(P.INDATE)) AS FEMALECOUNT_
FROM PERSON P
ORDER BY 1

````

**Steps**

- The SELECT DISTINCT statement is used to return only distinct (different) values.


**Answer:**

| YEAR_ | MALECOUNT_ | FEMALECOUNT_ |
| ----- | ---------- | ------------ |
| 2015  | 151        | 178          |
| 2016  | 175        | 180          |
| 2017  | 161        | 205          |
| 2018  | 188        | 178          |
| 2019  | 170        | 194          |
|       |

***

### 7. Write the query that returns the information about how long each employee has been working in months.

--Solution 1-

````sql
SELECT TOP 20 CONCAT(NAME_,' ',SURNAME) AS PERSON,INDATE,OUTDATE,
CASE
	WHEN OUTDATE IS NULL THEN ABS(DATEDIFF(MONTH,GETDATE(),INDATE))
	ELSE ABS(DATEDIFF(MONTH,OUTDATE,INDATE))
END AS WORKINGTIME FROM PERSON
````

--Solution 2- 
 --Using Union 
 
````sql
SELECT NAME_ +' ' +SURNAME AS PERSON,INDATE,OUTDATE,DATEDIFF(MONTH,INDATE,GETDATE()) AS WORKINGTIME
FROM PERSON WHERE OUTDATE IS  NULL

UNION ALL

SELECT NAME_ +' ' +SURNAME AS PERSON,INDATE,OUTDATE,DATEDIFF(MONTH,INDATE,OUTDATE) AS WORKINGTIME
FROM PERSON WHERE OUTDATE IS  NOT NULL

````
**Steps**
-CONCAT() function adds two or more strings together.
-UNION ALL command combines the result set of two or more SELECT statements (allows duplicate values).


 
**Answer:**

| PERSON                | INDATE     | OUTDATE    | WORKINGTIME |
| --------------------- | ---------- | ---------- | ----------- |
| Erdem İSTİK           | 28.07.2018 | NULL       | 63          |
| Azat COŞKUNYÜREK      | 6.04.2019  | 14.03.2020 | 11          |
| Kemal TEKYİĞİT        | 20.01.2017 | 5.08.2018  | 19          |
| Bünyamin OKTAYOĞLU    | 29.03.2015 | NULL       | 103         |
| Ferhat CINAR          | 19.10.2018 | 19.04.2020 | 18          |
| Tayfun ŞENDİL         | 6.02.2015  | 12.07.2017 | 29          |
| Gülşen ÇOLAK          | 26.07.2019 | 18.05.2020 | 10          |
| Deniz ERAVCI          | 25.07.2018 | 16.09.2019 | 14          |
| Anıl HİÇDURMAZ        | 13.06.2018 | NULL       | 64          |
| Burhan TOROSLUOĞLU    | 21.10.2015 | 3.04.2019  | 42          |
| Meliha ŞİRVANLI       | 1.07.2017  | 30.11.2018 | 16          |
| Engin HACIİBRAHİMOGLU | 14.03.2018 | 2.01.2019  | 10          |
| Çiğdem GÜLSU          | 13.07.2016 | NULL       | 87          |
| Zerda KÜTÜKOĞLU       | 28.04.2019 | NULL       | 54          |
| Münevver MUTAF        | 26.08.2016 | NULL       | 86          |
| Zahide CAYMAZ         | 22.03.2015 | 6.09.2019  | 54          |
| Nazar KAYNAKÇI        | 21.04.2016 | NULL       | 90          |
| Naime SULTANOĞLU      | 13.04.2017 | NULL       | 78          |
| Fırat BOZDAĞ          | 13.08.2019 | 31.01.2020 | 5           |
| Fevzi DURAKLI         | 3.03.2016  | NULL       | 91          |
|                       |

***

### 8.In its 5th year, our company will give an agenda with the initials of everyone's name and surname as a gift to its employees. For this, write the query that brings at least how many agendas will be printed from which letter combination.
--Note: For those with two names, the initials of the first name will be used.


--Solution-


````sql
SELECT SUBSTRING(NAME_,1,1)+'.'+SUBSTRING(SURNAME,1,1) AS SHORTNAME, COUNT(*) AS PERSONCOUNT FROM PERSON
GROUP BY SUBSTRING(NAME_,1,1)+'.'+SUBSTRING(SURNAME,1,1)
ORDER BY 2 DESC
````

**Answer:**
	
| SHORTNAME | PERSONCOUNT |
| --------- | ----------- |
| S.K       | 31          |
| E.K       | 29          |
| S.A       | 29          |
| M.K       | 28          |
| A.K       | 21          |
| H.K       | 21          |
| N.K       | 19          |
| A.A       | 17          |
| M.B       | 17          |
| B.T       | 16          |
| E.G       | 15          |
| E.T       | 15          |
| M.A       | 15          |
| S.S       | 15          |
| E.S       | 14          |
| M.G       | 14          |
| B.K       | 13          |
| K.K       | 13          |
| E.B       | 12          |
| M.Ö       | 12          |
|           |

***

### 9. Write the query that lists the departments with average salary more than 5500TL.

--Solution -

````sql
SELECT DEPARTMENT,AVG(SALARY) AS AVGSALARY FROM PERSON P
INNER JOIN DEPARTMENT D ON P.DEPARTMENTID=D.ID
GROUP BY DEPARTMENT
HAVING AVG(SALARY)> 5500  
ORDER BY 2 DESC
````

**Answer:**

| DEPARTMENT          | AVGSALARY   |
| ------------------- | ----------- |
| YÖNETİM             | 14641.03125 |
| SATIŞ               | 5970.568966 |
| İLETİŞİM            | 5877.075    |
| FİNANS              | 5557.24537  |
| MUHASEBE            | 5546.486111 |
| PLANLAMA            | 5516.773148 |
| BİLGİ TEKNOLOJİLERİ | 5510.925926 |
| PAZARLAMA           | 5508.37037  |
|                     |

***

### 10.Write the query to calculate the average experience of the departments in months.

--Solution -

````sql
SELECT DEPARTMENT,AVG(AVG_WORKINGTIME) AS AVG_WORKINGTIME 
FROM 
(SELECT DEPARTMENT,
CASE
	WHEN  OUTDATE IS NULL THEN  (DATEDIFF(MONTH,INDATE,GETDATE()))
	ELSE (DATEDIFF(MONTH,INDATE,OUTDATE))
END AS AVG_WORKINGTIME FROM PERSON P 
INNER JOIN DEPARTMENT D ON P.DEPARTMENTID=D.ID ) KMK
GROUP BY DEPARTMENT
````

**Answer:**

| DEPARTMENT          | AVG_WORKINGTIME |
| ------------------- | --------------- |
| BİLGİ TEKNOLOJİLERİ | 55              |
| MUHASEBE            | 53              |
| SATIŞ               | 72              |
| İNSAN KAYNAKLARI    | 54              |
| PLANLAMA            | 56              |
| PAZARLAMA           | 55              |
| YÖNETİM             | 45              |
| İLETİŞİM            | 70              |
| FİNANS              | 51              |
| SATINALMA           | 54              |
|                     |

***

### 11. Write a query that retrieves the name, position of the each member and their manager names and the positions of the managers.

--Solution 1 -

````sql
SELECT TOP 10
P.NAME_+' '+P.SURNAME AS PERSON, 
POS.POSITION,
P2.NAME_+' '+P2.SURNAME  AS MANAGERNAME,
POS2.POSITION AS MANAGERPOSITION
FROM PERSON P
INNER JOIN POSITION POS ON POS.ID=P.POSITIONID
INNER JOIN PERSON P2 ON P.MANAGERID=P2.ID
INNER JOIN POSITION POS2 ON POS2.ID=P2.POSITIONID
````
--Solution 2.

````sql
SELECT P.NAME_+' '+P.SURNAME AS PERSON, 
POS.POSITION,
(SELECT NAME_+' '+SURNAME FROM PERSON WHERE ID=P.MANAGERID) MANAGER,
(SELECT POSITION FROM POSITION WHERE ID=P.PARENTPOSITIONID) MANAGERPOSITION
FROM PERSON P
INNER JOIN POSITION POS ON POS.ID=P.POSITIONID
WHERE P.MANAGERID IS NOT NULL
````

**Steps**

-Multiple Inner Join from the same table:
Wherever you have "INNER JOIN Metals AS m", m needs to be something unique (not m every time).

**Answer:**

| PERSON            | POSITION                   | MANAGERNAME      | MANAGERPOSITION          |
| ----------------- | -------------------------- | ---------------- | ------------------------ |
| Nazar KAYNAKLI    | SATINALMA MEMURU           | Emre UNNU        | SATINALMA ŞEFI           |
| Naime SULTANOGLU  | BÜLGÜ TEKNOLOJÜLERÜ MEMURU | Derya HIZLIATEŞ  | BILGI TEKNOLOJILERI ŞEFI |
| Fevzi DURAKLI     | SATIŞ MEMURU               | Şule OZVEZ       | SATIŞ ŞEFI               |
| Canan ÜZYURDU     | ILETIŞIM MEMURU            | Kerem SOYLU      | ILETIŞIM ŞEFI           |
| Sultan GATIKKAŞ   | MUHASEBE MEMURU            | Yuksel KIMIZOGLU | MUHASEBE ŞEFI            |
| Mevlut BAŞDAN     | SATINALMA MEMURU           | Neslihan VARHOL  | SATINALMA ŞEFI          |
| Selcuk ALÜKO‚     | FINANS ŞEFI                | Sare ARAZLI      | FINANS MUDUR YRD.        |
| Egemen DULGEROÚLU | MUHASEBE MEMURU            | YŸksel KIMIZOGLU | MUHASEBE ŞEFI            |
| Baran ŞAKU        | ILETIŞIM MEMURU            | Kerem SOYLU      | ILETIŞIM ŞEFI           |
| Türkan ILKAN      | ILETIŞIM MEMURU            | Kerem SOYLU      | ILETIŞIM ŞEFI            |
|                   |

***


