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
Danny is expanding his new Pizza Empire and at the same time, he wants to Uberize it, so Pizza Runner was launched!

Danny started by recruiting “runners” to deliver fresh pizza from Pizza Runner Headquarters (otherwise known as Danny’s house) and also maxed out his credit card to pay freelance developers to build a mobile app to accept orders from customers. 

## Entity Relationship Diagram

![HR Analytics](https://github.com/baynazoglu/Alistirmalarla-SQL-Ogreniyorum/blob/c4e5739eaa4b272762ab3fbca2f8d62c7e169750/Case%20Study%20%232%20-%20Pizza%20Runner/ENTITY%20DIAGRAM%3DCASE2.jpg)



## Questions and Solutions



### 1. Şirketimizde hala çalışmaya devam eden çalışanların listesini getiren sorgu nedir? Not:İşten çıkış tarihi boş olanlar çalışmaya devam ediyor demektir.

````sql
SELECT TOP 10 * FROM PERSON
WHERE OUTDATE IS NOT NULL
````

**Cevap**
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

### 2. Şirketteki departman bazlı halen çalışmaya devam eden KADIN ve ERKEK sayılarını getiren sorguyu yazınız.

Çözüm-

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

**Cevap**
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

### 3. Şirketteki departman bazlı halen çalışmaya devam eden KADIN ve ERKEK sayılarını "MALE_PERSONCOUNT" ve "FEMALE_PERSONCOUNT" şeklinde iki column oluşturarak getiren sorguyu yazınız.

Çözüm-

````sql
SELECT D.DEPARTMENT,
(SELECT COUNT(*) FROM PERSON P WHERE P.GENDER ='E' AND P.DEPARTMENTID=D.ID AND P.OUTDATE IS NOT NULL) AS 'MALE_PERSONCOUNT',
(SELECT COUNT(*) FROM PERSON P WHERE P.GENDER ='K' AND P.DEPARTMENTID=D.ID AND P.OUTDATE IS NOT NULL) AS 'FEMALE_PERSONCOUNT'
FROM DEPARTMENT D
ORDER BY 1
````

**Cevap**

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

### 4.Şirketimizin Planlama departmanına yeni bir şef ataması(--PLANLAMA ŞEFİ--) yapıldı ve maaşını belirlemek istiyoruz. Planlama departmanı için minimum,maximum ve ortalama şef maaşı getiren sorgu?
--NOT:İşten Çıkanlar da dahil.

--Çözüm 1 -
````sql
SELECT PT.POSITION,COUNT(P.SALARY) [HOW MANY PEOPLE],AVG(P.SALARY)AS AVG_SALARY,MAX(P.SALARY) AS MAX_SALARY,MIN(P.SALARY) AS MIN_SALARY
FROM PERSON P
INNER JOIN POSITION PT ON P.POSITIONID=PT.ID
WHERE PT.POSITION = 'PLANLAMA ŞEFİ'
GROUP BY PT.POSITION
````

--Çözüm 2 -
-Subquery ile
````sql
SELECT PT.POSITION,
(SELECT MIN(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID) AS MIN_SALARY,
(SELECT AVG(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID)AS AVG_SALARY,
(SELECT MAX(P.SALARY)FROM PERSON P WHERE POSITIONID=PT.ID) AS MAX_SALARY
FROM POSITION PT
WHERE POSITION ='PLANLAMA ŞEFİ'
````
**Basamaklar**
-AVG():Sorguda belirtilen bir alanda yer alan bir değer kümesi aritmetik ortalamayı hesaplar
-MIN () ve MAX () Fonksiyonu: MIN() işlevi, seçilen sütunun en küçük değeri çağırır. MAX() işlevi, seçilen sütunun en büyük değeri çağırır

**Çözüm**

| POSITION      | MIN_SALARY | AVG_SALARY | MAX_SALARY |
| ------------- | ---------- | ---------- | ---------- |
| PLANLAMA ŞEFİ | 7926       | 9239       | 10427      |
|               |



***


### 5. Her bir pozisyonda mevcut çalışanlar olarak kaç kişi ve ortalama maaşları ne kadardır?**
Çözüm 1- 

````sql
SELECT PT.POSITION,COUNT(P.SALARY) [HOW MANY PEOPLE],ROUND(AVG(P.SALARY),0)AS AVG_SALARY,ROUND(MAX(P.SALARY),0) AS MAX_SALARY,ROUND(MIN(P.SALARY),0) AS MIN_SALARY
FROM PERSON P
RIGHT JOIN POSITION PT ON P.POSITIONID=PT.ID
WHERE OUTDATE IS NOT NULL
GROUP BY PT.POSITION
ORDER BY PT.POSITION
````

Çözüm 2- 
--Subquery ile 

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

-İki farklı çözümde iki farklı sonuç aldık. Çünkü inner joinle group by yaparken position isimlerine göre işlem yaptık. Fakat Subquery'de bi nevi positionid ye göre group by yapmış olduk.Satın alma şefi iki farklı ID'ye sahip olduğu için subqueryli çözümde 2 farklı satırda yer aldı. 


**Cevap**

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


### 6.Yıllara göre işe alınan personel sayısını kadın ve erkek bazında listeleyen sorguyu yazınız

````sql
SELECT  DISTINCT YEAR(P.INDATE) AS YEAR_,
(SELECT COUNT(*) FROM PERSON WHERE GENDER='E' AND YEAR(INDATE)=YEAR(P.INDATE)) AS MALECOUNT_,
(SELECT COUNT(*) FROM PERSON WHERE GENDER='K' AND YEAR(INDATE)=YEAR(P.INDATE)) AS FEMALECOUNT_
FROM PERSON P
ORDER BY 1

````

**Basamak**

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

### 7. Her bir personelimizin ne kadar zamandır çalıştığı bilgisini şekildeki gibi ay olarak getiren sorguyu yazınız.

--Çözüm 1-

````sql
SELECT TOP 20 CONCAT(NAME_,' ',SURNAME) AS PERSON,INDATE,OUTDATE,
CASE
	WHEN OUTDATE IS NULL THEN ABS(DATEDIFF(MONTH,GETDATE(),INDATE))
	ELSE ABS(DATEDIFF(MONTH,OUTDATE,INDATE))
END AS WORKINGTIME FROM PERSON
````

--Çözüm 2- 
 --Union kullanarak
````sql
SELECT NAME_ +' ' +SURNAME AS PERSON,INDATE,OUTDATE,DATEDIFF(MONTH,INDATE,GETDATE()) AS WORKINGTIME
FROM PERSON WHERE OUTDATE IS  NULL

UNION ALL

SELECT NAME_ +' ' +SURNAME AS PERSON,INDATE,OUTDATE,DATEDIFF(MONTH,INDATE,OUTDATE) AS WORKINGTIME
FROM PERSON WHERE OUTDATE IS  NOT NULL

````
**Basamak**
-CONCAT() function adds two or more strings together.
UNION ALL command combines the result set of two or more SELECT statements (allows duplicate values).


 
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

### 8. 

--Çözüm-


````sql
SELECT  
  SUM(
    CASE WHEN exclusions IS NOT NULL AND extras IS NOT NULL THEN 1
    ELSE 0
    END) AS pizza_count_w_exclusions_extras
FROM #customer_orders AS c
JOIN #runner_orders AS r
  ON c.order_id = r.order_id
WHERE r.distance >= 1 
  AND exclusions <> ' ' 
  AND extras <> ' ';
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129738278-dd3e7056-309d-42fc-a5e3-00f7b5d4609e.png)

- Only 1 pizza delivered that had both extra and exclusion topping. That’s one fussy customer!

### 9. What was the total volume of pizzas ordered for each hour of the day?

````sql
SELECT 
  DATEPART(HOUR, [order_time]) AS hour_of_day, 
  COUNT(order_id) AS pizza_count
FROM #customer_orders
GROUP BY DATEPART(HOUR, [order_time]);
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129738302-573430e9-1785-4c71-adc1-464ffa94de8a.png)

- Highest volume of pizza ordered is at 13 (1:00 pm), 18 (6:00 pm) and 21 (9:00 pm).
- Lowest volume of pizza ordered is at 11 (11:00 am), 19 (7:00 pm) and 23 (11:00 pm).

### 10. What was the volume of orders for each day of the week?

````sql
SELECT 
  FORMAT(DATEADD(DAY, 2, order_time),'dddd') AS day_of_week, -- add 2 to adjust 1st day of the week as Monday
  COUNT(order_id) AS total_pizzas_ordered
FROM #customer_orders
GROUP BY FORMAT(DATEADD(DAY, 2, order_time),'dddd');
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129738331-233744f6-3b57-4f4f-9a51-f7a699a9eb2e.png)

- There are 5 pizzas ordered on Friday and Monday.
- There are 3 pizzas ordered on Saturday.
- There is 1 pizza ordered on Sunday.

***

## B. Runner and Customer Experience

### 1. How many runners signed up for each 1 week period? (i.e. week starts 2021-01-01)

````sql
SELECT 
  DATEPART(WEEK, registration_date) AS registration_week,
  COUNT(runner_id) AS runner_signup
FROM runners
GROUP BY DATEPART(WEEK, registration_date);
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129739658-a233932a-9f79-4280-a618-8bab6d3bd1f2.png)

- On Week 1 of Jan 2021, 2 new runners signed up.
- On Week 2 and 3 of Jan 2021, 1 new runner signed up.

### 2. What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pickup the order?

````sql
WITH time_taken_cte AS
(
  SELECT 
    c.order_id, 
    c.order_time, 
    r.pickup_time, 
    DATEDIFF(MINUTE, c.order_time, r.pickup_time) AS pickup_minutes
  FROM #customer_orders AS c
  JOIN #runner_orders AS r
    ON c.order_id = r.order_id
  WHERE r.distance != 0
  GROUP BY c.order_id, c.order_time, r.pickup_time
)

SELECT 
  AVG(pickup_minutes) AS avg_pickup_minutes
FROM time_taken_cte
WHERE pickup_minutes > 1;
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129739701-e94b75e9-7193-4cf3-8e77-3c76be8b638d.png)

- The average time taken in minutes by runners to arrive at Pizza Runner HQ to pick up the order is 15 minutes.

### 3. Is there any relationship between the number of pizzas and how long the order takes to prepare?

````sql
WITH prep_time_cte AS
(
  SELECT 
    c.order_id, 
    COUNT(c.order_id) AS pizza_order, 
    c.order_time, 
    r.pickup_time, 
    DATEDIFF(MINUTE, c.order_time, r.pickup_time) AS prep_time_minutes
  FROM #customer_orders AS c
  JOIN #runner_orders AS r
    ON c.order_id = r.order_id
  WHERE r.distance != 0
  GROUP BY c.order_id, c.order_time, r.pickup_time
)

SELECT 
  pizza_order, 
  AVG(prep_time_minutes) AS avg_prep_time_minutes
FROM prep_time_cte
WHERE prep_time_minutes > 1
GROUP BY pizza_order;
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129739816-05e3ba03-d3fe-4206-8557-869930a897d1.png)

- On average, a single pizza order takes 12 minutes to prepare.
- An order with 3 pizzas takes 30 minutes at an average of 10 minutes per pizza.
- It takes 16 minutes to prepare an order with 2 pizzas which is 8 minutes per pizza — making 2 pizzas in a single order the ultimate efficiency rate.

### 4. Is there any relationship between the number of pizzas and how long the order takes to prepare?

````sql
SELECT 
  c.customer_id, 
  AVG(r.distance) AS avg_distance
FROM #customer_orders AS c
JOIN #runner_orders AS r
  ON c.order_id = r.order_id
WHERE r.duration != 0
GROUP BY c.customer_id;
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129739847-5e338f4f-b42c-4531-9685-e2e822063183.png)

_(Assuming that distance is calculated from Pizza Runner HQ to customer’s place)_

- Customer 104 stays the nearest to Pizza Runner HQ at average distance of 10km, whereas Customer 105 stays the furthest at 25km.

### 5. What was the difference between the longest and shortest delivery times for all orders?

_Edit 08/10/21: Thanks to my reader, Ankush Taneja on Medium who caught my mistake. I've amended to the correct solution. Also, I was doing this case study using SQL Server few months ago, but I'm using PostgreSQL on SQLpad now so there could be a slight difference to the syntax._

Firstly, I'm going to filter results with non-null duration first just to have a feel. You can skip this step and go straight to the answer.

````sql
SELECT 
  order_id, duration
FROM #runner_orders
WHERE duration not like ' ';
````

<img width="269" alt="image" src="https://user-images.githubusercontent.com/81607668/136523519-98efb655-d144-496b-a946-42c1c5415403.png">

```sql
SELECT MAX(duration::NUMERIC) - MIN(duration::NUMERIC) AS delivery_time_difference
FROM runner_orders2
where duration not like ' ';
```

**Answer:**

<img width="196" alt="image" src="https://user-images.githubusercontent.com/81607668/136523820-c4504a25-83f8-4236-b08e-37bf542caad0.png">

- The difference between longest (40 minutes) and shortest (10 minutes) delivery time for all orders is 30 minutes.

### 6. What was the average speed for each runner for each delivery and do you notice any trend for these values?

````sql
SELECT 
  r.runner_id, 
  c.customer_id, 
  c.order_id, 
  COUNT(c.order_id) AS pizza_count, 
  r.distance, (r.duration / 60) AS duration_hr , 
  ROUND((r.distance/r.duration * 60), 2) AS avg_speed
FROM #runner_orders AS r
JOIN #customer_orders AS c
  ON r.order_id = c.order_id
WHERE distance != 0
GROUP BY r.runner_id, c.customer_id, c.order_id, r.distance, r.duration
ORDER BY c.order_id;
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129739931-54127037-0879-43bf-b53f-e4a1a6ebffeb.png)

_(Average speed = Distance in km / Duration in hour)_
- Runner 1’s average speed runs from 37.5km/h to 60km/h.
- Runner 2’s average speed runs from 35.1km/h to 93.6km/h. Danny should investigate Runner 2 as the average speed has a 300% fluctuation rate!
- Runner 3’s average speed is 40km/h

### 7. What is the successful delivery percentage for each runner?

````sql
SELECT 
  runner_id, 
  ROUND(100 * SUM(
    CASE WHEN distance = 0 THEN 0
    ELSE 1 END) / COUNT(*), 0) AS success_perc
FROM #runner_orders
GROUP BY runner_id;
````

**Answer:**

![image](https://user-images.githubusercontent.com/81607668/129740007-021d78fb-ec32-46c0-98f2-9e8f1891baed.png)

- Runner 1 has 100% successful delivery.
- Runner 2 has 75% successful delivery.
- Runner 3 has 50% successful delivery

_(It’s not right to attribute successful delivery to runners as order cancellations are out of the runner’s control.)_

***

## C. Ingredient Optimisation

### 1. What are the standard ingredients for each pizza?

### 2. What was the most commonly added extra?

```sql
WITH toppings_cte AS (
SELECT
  pizza_id,
  REGEXP_SPLIT_TO_TABLE(toppings, '[,\s]+')::INTEGER AS topping_id
FROM pizza_runner.pizza_recipes)

SELECT 
  t.topping_id, pt.topping_name, 
  COUNT(t.topping_id) AS topping_count
FROM toppings_cte t
INNER JOIN pizza_runner.pizza_toppings pt
  ON t.topping_id = pt.topping_id
GROUP BY t.topping_id, pt.topping_name
ORDER BY topping_count DESC;
```

**Solution**

<img width="582" alt="image" src="https://user-images.githubusercontent.com/81607668/138807557-08909e2e-8201-4e53-87b8-f927928292fb.png">

### 3. What was the most common exclusion?

### 4. Generate an order item for each record in the customers_orders table in the format of one of the following:
- Meat Lovers
- Meat Lovers - Exclude Beef
- Meat Lovers - Extra Bacon
- Meat Lovers - Exclude Cheese, Bacon - Extra Mushroom, Peppers

### 5. Generate an alphabetically ordered comma separated ingredient list for each pizza order from the customer_orders table and add a 2x in front of any relevant ingredients

### 6. For example: "Meat Lovers: 2xBacon, Beef, ... , Salami"

### 7. What is the total quantity of each ingredient used in all delivered pizzas sorted by most frequent first?

***

## D. Pricing and Ratings

1. If a Meat Lovers pizza costs $12 and Vegetarian costs $10 and there were no charges for changes - how much money has Pizza Runner made so far if there are no delivery fees?
2. What if there was an additional $1 charge for any pizza extras?
- Add cheese is $1 extra
3. The Pizza Runner team now wants to add an additional ratings system that allows customers to rate their runner, how would you design an additional table for this new dataset generate a schema for this new table and insert your own data for ratings for each successful customer order between 1 to 5.
4. Using your newly generated table - can you join all of the information together to form a table which has the following information for successful deliveries?
- customer_id
- order_id
- runner_id
- rating
- order_time
- pickup_time
- Time between order and pickup
- Delivery duration
- Average speed
- Total number of pizzas
5. If a Meat Lovers pizza was $12 and Vegetarian $10 fixed prices with no cost for extras and each runner is paid $0.30 per kilometre traveled - how much money does Pizza Runner have left over after these deliveries?

***
