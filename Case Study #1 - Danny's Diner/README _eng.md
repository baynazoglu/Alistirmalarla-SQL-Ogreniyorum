# 💸 Case Study #1: Customer Database
<img src="https://www.xero.com/blog/wp-content/uploads/2020/07/164402-Xero-blog-header-01_800x480_acf_cropped.png" alt="Image" width="400" height="400">

## 📚 Table of Contents
- [Business Task](#business-task)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Question and Solution](#question-and-solution)

Please note that all the information regarding the case study has been sourced from the following link: [here](https://www.udemy.com/course/alistirmalarla-sql-ogreniyorum/). 

***

## Business Task

In this scenario, we will be answering questions according to our Customer dataset.
***

## Entity Relationship Diagram

<img src="https://github.com/baynazoglu/SQL-ALISTIRMALARI/blob/08ca455e314b92db37e4bddd19a3baff7422b8e8/Case%20Study%20%231%20-%20Danny's%20Diner/customer_1.png" alt="Image" width="500" height="400" >

## Question and Solution

 I have also published this case study on [Medium](https://medium.com/@fbaynazoglu).

If you have any questions, reach out to me on [LinkedIn](https://www.linkedin.com/in/baynazoglu/).

**1. Print the first 10 names starting with "A" from the Customer table.**

````sql
SELECT TOP 10 * FROM CUSTOMERS
WHERE CUSTOMERNAME LIKE 'A%'

````

#### Steps:
- Use **LIKE** to retrieve the data in a column of a table, based on a specified pattern.
- Use **%** to specify conditions in an SQL statement 

#### Answer:
| ID | CUSTOMERNAME         | TCNUMBER    | GENDER | EMAIL                 | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       |
| -- | -------------------- | ----------- | ------ | --------------------- | ---------- | ------ | ---------- | ------------ | ------------ |
| 6  | Ahmet İNCİKAPI       | 6722155596  | E      | a_incikapi@miuul.com  | 28.05.1991 | 53     | 225        | (532)2414618 | (538)8459085 |
| 7  | Arif TEMELOĞLU       | 43691911318 | E      | a_temeloglu@miuul.com | 11.12.1967 | 40     | 638        | (554)5504524 | (534)6379277 |
| 9  | Ali Eymen DEVE       | 80011834707 | E      | a_eymen@miuul.com     | 23.01.1985 | 39     | 463        | (533)8082176 | (538)4811026 |
| 35 | Ayhan ÖZÇİL          | 3328037338  | E      | a_ozcil@miuul.com     | 8.11.1963  | 10     | 114        | (543)2007274 | (534)1062665 |
| 36 | Azad ÖNÜR            | 65514513990 | E      | a_onvr@miuul.com      | 23.03.1989 | 55     | 722        | (532)7551426 | (542)2487070 |
| 45 | Azra TÜTNCÜ          | 26491895261 | K      | a_tvtncv@miuul.com    | 1.01.1977  | 73     | 815        | (534)6093597 | (537)4311757 |
| 49 | Ada VAPUR            | 11963169229 | K      | a_vapur@miuul.com     | 18.01.1949 | 37     | 569        | (532)6239599 | (532)9787325 |
| 54 | Aslıhan DOLAY        | 79576777794 | K      | a_dolay@miuul.com     | 8.01.1957  | 19     | 734        | (554)8938397 | (544)5597413 |
| 55 | Abdurrahman ALTINGÖZ | 55960130916 | E      | a_altingoz@miuul.com  | 7.08.1999  | 37     | 720        | (544)6667247 | (538)2796190 |


***

**2.List 10 people whose names end with the letter "N" and whose gender is male in the "Customers" table.**

````sql
SELECT TOP 10 * FROM CUSTOMERS
WHERE CUSTOMERNAME LIKE '%N' AND GENDER = 'E'
````

#### Steps:
- The AND operator is used to filter records based on more than one condition, like if you want to return all customers from Spain that starts with the letter 'G':

#### Answer:
| ID  | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                   | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP  |
| --- | --------------------- | ----------- | ------ | ----------------------- | ---------- | ------ | ---------- | ------------ | ------------ | --------- |
| 58  | Umut SAFALTIN         | 51937342075 | E      | u_safaltin@miuul.com    | 16.08.1952 | 37     | 720        | (542)2692488 | (533)6412455 | 65 Over   |
| 73  | Sebahattin SUKUSTURAN | 32933375870 | E      | s_sukusturan@miuul.com  | 9.01.1951  | 1      | 4          | (535)4032232 | (534)4738142 | 65 Over   |
| 75  | Suat GİRİGN           | 43573980158 | E      | s_girign@miuul.com      | 17.12.1976 | 67     | 173        | (555)3754614 | (543)2335559 | 46-55 Age |
| 78  | Efe BİRSAN            | 39503368325 | E      | e_birsan@miuul.com      | 4.05.1960  | 42     | 752        | (541)3999883 | (537)2063996 | 56-65 Age |
| 104 | Necati DOĞUKAN        | 28235335234 | E      | n_dogukan@miuul.com     | 10.01.1984 | 27     | 728        | (536)7777583 | (541)8505041 | 36-45 Age |
| 114 | Polat ŞENGEZKEN       | 48347440281 | E      | p_sengezken@miuul.com   | 27.12.1949 | 32     | 601        | (544)5388154 | (555)3781465 | 65 Over   |
| 117 | Metehan GÖÇEMEN       | 86191747794 | E      | m_gocemen@miuul.com     | 6.12.1990  | 18     | 129        | (505)6368191 | (532)4167785 | 20-35 Age |
| 136 | Oğuzhan KÖKAN         | 33377086930 | E      | o_kokan@miuul.com       | 9.07.1941  | 19     | 734        | (505)6358327 | (541)2616615 | 65 Over   |
| 152 | Fırat KILICARSLAN     | 41288781936 | E      | f_kilicarslan@miuul.com | 26.08.1989 | 73     | 815        | (537)5509258 | (533)6106975 | 20-35 Age |
| 185 | Ersin SEKMEN          | 44465589374 | E      | e_sekmen@miuul.com      | 19.10.1975 | 23     | 343        | (532)7922697 | (544)5402036 | 46-55 Age |
|     |

***
**3. Display customers born between 1990 and 1995 years including 1990 and 1995.**

Solution 1-
````sql
SELECT TOP 10 * FROM CUSTOMERS
WHERE BIRTHDATE BETWEEN '1990-01-01' AND '1995-12-31'
````
#### Steps:
The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.
The BETWEEN operator is inclusive: begin and end values are included. 

Solution 2-
````sql
SELECT TOP 10 * FROM CUSTOMERS
WHERE YEAR(BIRTHDATE) BETWEEN 1990 AND 1995
````
#### Steps:
The DATEPART() function returns a specified part of a date. This function returns the result as an integer value. SELECT DATEPART(month, '2017/08/25')

The YEAR() function returns the year part for a specified date.

  
#### Answer:
| ID | CUSTOMERNAME      | TCNUMBER    | GENDER | EMAIL                   | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP  |
| -- | ----------------- | ----------- | ------ | ----------------------- | ---------- | ------ | ---------- | ------------ | ------------ | --------- |
| 6  | Ahmet İNCİKAPI    | 6722155596  | E      | a_incikapi@miuul.com    | 28.05.1991 | 53     | 225        | (532)2414618 | (538)8459085 | 20-35 Age |
| 8  | Elif ÖZÇELİKBAŞ   | 84870496920 | K      | e_ozcelikbas@miuul.com  | 6.06.1993  | 73     | 815        | (536)9014627 | (544)3937372 | 20-35 Age |
| 13 | Dilan DOKUYUCU    | 74659763913 | K      | d_dokuyucu@miuul.com    | 21.01.1993 | 25     | 333        | (538)8929868 | (534)4275461 | 20-35 Age |
| 14 | Selim ÖZBAY       | 77720855989 | E      | s_ozbay@miuul.com       | 2.10.1992  | 73     | 815        | (535)5906635 | (533)4273519 | 20-35 Age |
| 30 | Bülent KAÇAROĞLU  | 21971116249 | E      | b_kacaroglu@miuul.com   | 9.01.1995  | 42     | 311        | (554)6844639 | (541)5324664 | 20-35 Age |
| 34 | Ela nur SEREK     | 53475314899 | K      | e_nur@miuul.com         | 11.01.1994 | 19     | 734        | (544)2251131 | (538)3066585 | 20-35 Age |
| 57 | Leyla AYLANC      | 73737020787 | K      | l_aylanc@miuul.com      | 12.04.1992 | 60     | 431        | (555)6741797 | (554)7082859 | 20-35 Age |
| 64 | Emrah KARAAT      | 43499469521 | E      | e_karaat@miuul.com      | 28.12.1990 | 20     | 724        | (544)6687598 | (505)8084086 | 20-35 Age |
| 82 | Gamze ADAL        | 22231514956 | K      | g_adal@miuul.com        | 17.01.1991 | 20     | 2          | (536)3915594 | (535)4321850 | 20-35 Age |
| 94 | Gönül ATILANEVLAT | 68119051500 | K      | g_atilanevlat@miuul.com | 20.01.1991 | 42     | 732        | (553)1707137 | (533)6289816 | 20-35 Age |
|    |

***

**4. Write a query that retrieves people living in Istanbul using Join.**


Solution:
````sql
SELECT TOP 10 C.*,CT.CITIES FROM CUSTOMERS C
INNER JOIN CITIES CT ON C.CITYID = CT.ID
WHERE CT.CITIES ='İSTANBUL'
````

#### Steps:
The INNER JOIN keyword selects records that have matching values in both tables.

  
#### Answer:
| ID  | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                  | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP  | CITIES   |
| --- | --------------------- | ----------- | ------ | ---------------------- | ---------- | ------ | ---------- | ------------ | ------------ | --------- | -------- |
| 15  | Yasin AĞAGÜL          | 32764684197 | E      | y_agagvl@miuul.com     | 19.10.1979 | 34     | 897        | (532)6102663 | (537)3381012 | 36-45 Age | İSTANBUL |
| 88  | Sebahat CİLALITAŞ     | 65960134490 | K      | s_cilalitas@miuul.com  | 30.09.1978 | 34     | 64         | (535)7019065 | (532)2408341 | 36-45 Age | İSTANBUL |
| 97  | Deniz BENDER          | 31619199155 | E      | d_bender@miuul.com     | 4.04.1986  | 34     | 134        | (542)4181722 | (536)4621320 | 36-45 Age | İSTANBUL |
| 101 | Çağla BEĞEN           | 85581395736 | K      | c_begen@miuul.com      | 22.12.1991 | 34     | 81         | (535)1338012 | (533)8331511 | 20-35 Age | İSTANBUL |
| 127 | Nurettin GAYRETLİ     | 2822523822  | E      | n_gayretli@miuul.com   | 27.04.1950 | 34     | 84         | (532)7969080 | (536)7322740 | 65 Over   | İSTANBUL |
| 139 | Yeliz KÜÇÜKALP        | 65432369284 | K      | y_kvcvkalp@miuul.com   | 26.02.1965 | 34     | 488        | (555)9613650 | (543)1071715 | 56-65 Age | İSTANBUL |
| 164 | Eylül GÜLÜ            | 56388773535 | K      | e_gvlv@miuul.com       | 24.08.1969 | 34     | 3          | (537)5953916 | (532)4647711 | 46-55 Age | İSTANBUL |
| 174 | Müzeyyen OCAKÇI       | 89589164667 | K      | m_ocakci@miuul.com     | 19.02.1972 | 34     | 707        | (543)1576124 | (505)9181537 | 46-55 Age | İSTANBUL |
| 199 | Muhammed Emin TEKKAYA | 87271968026 | E      | m_emin@miuul.com       | 19.04.1984 | 34     | 897        | (542)2911632 | (535)9881318 | 36-45 Age | İSTANBUL |
| 208 | Neslihan KILIÇÇEKER   | 53734331933 | K      | n_kilicceker@miuul.com | 4.10.1982  | 34     | 707        | (543)1432619 | (505)2287257 | 36-45 Age | İSTANBUL |
|     |
***
**5. Write a query that retrieves people living in Istanbul using subquery.**

Solution 1-
````sql
SELECT TOP 10 * FROM CUSTOMERS
WHERE CITYID = (SELECT ID FROM CITIES WHERE CITIES ='İSTANBUL')
````
#### Steps:
A subquery is a query that is nested inside a SELECT, INSERT, UPDATE, or DELETE statement, or inside another subquery.


  
#### Answer:
| ID  | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                  | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP  |
| --- | --------------------- | ----------- | ------ | ---------------------- | ---------- | ------ | ---------- | ------------ | ------------ | --------- |
| 15  | Yasin AĞAGÜL          | 32764684197 | E      | y_agagvl@miuul.com     | 19.10.1979 | 34     | 897        | (532)6102663 | (537)3381012 | 36-45 Age |
| 88  | Sebahat CİLALITAŞ     | 65960134490 | K      | s_cilalitas@miuul.com  | 30.09.1978 | 34     | 64         | (535)7019065 | (532)2408341 | 36-45 Age |
| 97  | Deniz BENDER          | 31619199155 | E      | d_bender@miuul.com     | 4.04.1986  | 34     | 134        | (542)4181722 | (536)4621320 | 36-45 Age |
| 101 | Çağla BEĞEN           | 85581395736 | K      | c_begen@miuul.com      | 22.12.1991 | 34     | 81         | (535)1338012 | (533)8331511 | 20-35 Age |
| 127 | Nurettin GAYRETLİ     | 2822523822  | E      | n_gayretli@miuul.com   | 27.04.1950 | 34     | 84         | (532)7969080 | (536)7322740 | 65 Over   |
| 139 | Yeliz KÜÇÜKALP        | 65432369284 | K      | y_kvcvkalp@miuul.com   | 26.02.1965 | 34     | 488        | (555)9613650 | (543)1071715 | 56-65 Age |
| 164 | Eylül GÜLÜ            | 56388773535 | K      | e_gvlv@miuul.com       | 24.08.1969 | 34     | 3          | (537)5953916 | (532)4647711 | 46-55 Age |
| 174 | Müzeyyen OCAKÇI       | 89589164667 | K      | m_ocakci@miuul.com     | 19.02.1972 | 34     | 707        | (543)1576124 | (505)9181537 | 46-55 Age |
| 199 | Muhammed Emin TEKKAYA | 87271968026 | E      | m_emin@miuul.com       | 19.04.1984 | 34     | 897        | (542)2911632 | (535)9881318 | 36-45 Age |
| 208 | Neslihan KILIÇÇEKER   | 53734331933 | K      | n_kilicceker@miuul.com | 4.10.1982  | 34     | 707        | (543)1432619 | (505)2287257 | 36-45 Age |
|     |
***

**6. Write the query that returns the information about how many customers we have in which city.**

Solution 1-
````sql
SELECT CT.CITIES,COUNT(C.ID) AS CUSTOMERCOUNT FROM CUSTOMERS C
INNER JOIN CITIES CT ON C.CITYID=CT.ID
GROUP BY CT.CITIES
````
Solution 2-
````sql
SELECT *,
(SELECT COUNT(*) FROM CUSTOMERS C WHERE CITYID=CITIES.ID) AS CUSTOMERCOUNTS 
FROM CITIES
````

#### Steps:
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

  
#### Answer:
| CITIES         | CUSTOMERCOUNT |
| -------------- | ------------- |
| ADANA          | 16            |
| ADIYAMAN       | 11            |
| AFYONKARAHİSAR | 19            |
| AĞRI           | 13            |
| AKSARAY        | 12            |
| AMASYA         | 5             |
| ANKARA         | 29            |
| ANTALYA        | 13            |
| ARDAHAN        | 8             |
| ARTVİN         | 12            |
| AYDIN          | 15            |
| BALIKESİR      | 20            |
| BARTIN         | 2             |
| BATMAN         | 6             |
| BAYBURT        | 1             |
| BİLECİK        | 7             |
| BİNGÖL         | 12            |
| BİTLİS         | 7             |
| BOLU           | 9             |
| BURDUR         | 11            |
| BURSA          | 22            |
| ÇANAKKALE      | 9             |
| ÇANKIRI        | 9             |
| ÇORUM          | 22            |
| DENİZLİ        | 14            |
| DİYARBAKIR     | 20            |
| DÜZCE          | 2             |
| EDİRNE         | 7             |
| ELAZIĞ         | 13            |
| ERZİNCAN       | 7             |
| ERZURUM        | 14            |
| ESKİŞEHİR      | 3             |
| GAZİANTEP      | 25            |
| GİRESUN        | 10            |
| HAKKARİ        | 3             |
| HATAY          | 7             |
| IĞDIR          | 1             |
| ISPARTA        | 19            |
| İSTANBUL       | 47            |
| İZMİR          | 24            |
| KAHRAMANMARAŞ  | 8             |
| KARABÜK        | 7             |
| KARAMAN        | 1             |
| KARS           | 2             |
| KASTAMONU      | 23            |
| KAYSERİ        | 17            |
| KIRIKKALE      | 1             |
| KIRKLARELİ     | 2             |
| KIRŞEHİR       | 6             |
| KİLİS          | 7             |
| KOCAELİ        | 6             |
| KONYA          | 19            |
| KÜTAHYA        | 3             |
| MALATYA        | 3             |
| MANİSA         | 14            |
| MARDİN         | 10            |
| MERSİN         | 17            |
| MUĞLA          | 12            |
| MUŞ            | 7             |
| NEVŞEHİR       | 5             |
| NİĞDE          | 5             |
| ORDU           | 9             |
| OSMANİYE       | 12            |
| RİZE           | 12            |
| SAKARYA        | 5             |
| SAMSUN         | 13            |
| SİİRT          | 4             |
| SİNOP          | 5             |
| SİVAS          | 17            |
| ŞANLIURFA      | 17            |
| ŞIRNAK         | 110           |
| TEKİRDAĞ       | 12            |
| TOKAT          | 8             |
| TRABZON        | 8             |
| TUNCELİ        | 4             |
| UŞAK           | 5             |
| VAN            | 2             |
| YALOVA         | 6             |
| YOZGAT         | 13            |
|                |

***

**7. Let's see the cities with more than 10 customers and the number of customers per cities in order from more to less according to the number of customers.**

Solution 1-
````sql
SELECT CT.CITIES, COUNT(C.ID) AS COUNTCUSTOMER FROM CUSTOMERS C
INNER JOIN CITIES CT ON C.CITYID=CT.ID
GROUP BY CT.CITIES
HAVING COUNT(C.ID)>10 
ORDER BY COUNTCUSTOMER DESC
````
Solution 2-
````sql
SELECT CITIES, 
(SELECT COUNT(CITYID)FROM CUSTOMERS C WHERE C.CITYID =CITIES.ID ) AS COUNTCUSTOMER
FROM CITIES
WHERE (SELECT COUNT(CITYID)FROM CUSTOMERS C WHERE C.CITYID =CITIES.ID )>10
ORDER BY CUSTOMERCOUNT DESC
````

#### Steps:
The ORDER BY keyword is used to sort the result-set in ascending or descending order.

The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions
 

  
#### Answer:
| CITIES         | COUNTCUSTOMER |
| -------------- | ------------- |
| ŞIRNAK         | 110           |
| İSTANBUL       | 47            |
| ANKARA         | 29            |
| GAZİANTEP      | 25            |
| İZMİR          | 24            |
| KASTAMONU      | 23            |
| BURSA          | 22            |
| ÇORUM          | 22            |
| DİYARBAKIR     | 20            |
| BALIKESİR      | 20            |
| AFYONKARAHİSAR | 19            |
| ISPARTA        | 19            |
| KONYA          | 19            |
| SİVAS          | 17            |
| ŞANLIURFA      | 17            |
| KAYSERİ        | 17            |
| MERSİN         | 17            |
| ADANA          | 16            |
| AYDIN          | 15            |
| ERZURUM        | 14            |
| DENİZLİ        | 14            |
| MANİSA         | 14            |
| SAMSUN         | 13            |
| YOZGAT         | 13            |
| ELAZIĞ         | 13            |
| AĞRI           | 13            |
| ANTALYA        | 13            |
| ARTVİN         | 12            |
| BİNGÖL         | 12            |
| AKSARAY        | 12            |
| TEKİRDAĞ       | 12            |
| MUĞLA          | 12            |
| OSMANİYE       | 12            |
| RİZE           | 12            |
| ADIYAMAN       | 11            |
| BURDUR         | 11            |
|                |

***

**8. Write the query that returns the information about how many male and how many female customers we have in which city.**


Solution 1-
````sql
SELECT CT.CITIES,C.GENDER,COUNT(C.ID) AS CUSTOMERCOUNT FROM CUSTOMERS C
INNER JOIN CITIES CT ON C.CITYID=CT.ID
GROUP BY CT.CITIES, C.GENDER
ORDER BY CITIES ASC
````

  
#### Answer:
| CITIES         | GENDER | CUSTOMERCOUNT |
| -------------- | ------ | ------------- |
| ADANA          | E      | 10            |
| ADANA          | K      | 6             |
| ADIYAMAN       | E      | 7             |
| ADIYAMAN       | K      | 4             |
| AFYONKARAHİSAR | E      | 6             |
| AFYONKARAHİSAR | K      | 13            |
| AĞRI           | E      | 7             |
| AĞRI           | K      | 6             |
| AKSARAY        | E      | 7             |
| AKSARAY        | K      | 5             |
| AMASYA         | E      | 3             |
| AMASYA         | K      | 2             |
| ANKARA         | E      | 13            |
| ANKARA         | K      | 16            |
| ANTALYA        | E      | 8             |
| ANTALYA        | K      | 5             |
| ARDAHAN        | E      | 3             |
| ARDAHAN        | K      | 5             |
| ARTVİN         | E      | 5             |
| ARTVİN         | K      | 7             |
| AYDIN          | E      | 7             |
| AYDIN          | K      | 8             |
| BALIKESİR      | E      | 11            |
| BALIKESİR      | K      | 9             |
| BARTIN         | E      | 1             |
| BARTIN         | K      | 1             |
| BATMAN         | E      | 3             |
| BATMAN         | K      | 3             |
| BAYBURT        | K      | 1             |
| BİLECİK        | E      | 2             |
| BİLECİK        | K      | 5             |
| BİNGÖL         | E      | 3             |
| BİNGÖL         | K      | 9             |
| BİTLİS         | E      | 2             |
| BİTLİS         | K      | 5             |
| BOLU           | E      | 4             |
| BOLU           | K      | 5             |
| BURDUR         | E      | 8             |
| BURDUR         | K      | 3             |
| BURSA          | E      | 6             |
| BURSA          | K      | 16            |
| ÇANAKKALE      | E      | 4             |
| ÇANAKKALE      | K      | 5             |
| ÇANKIRI        | E      | 5             |
| ÇANKIRI        | K      | 4             |
| ÇORUM          | E      | 11            |
| ÇORUM          | K      | 11            |
| DENİZLİ        | E      | 11            |
| DENİZLİ        | K      | 3             |
| DİYARBAKIR     | E      | 8             |
| DİYARBAKIR     | K      | 12            |
| DÜZCE          | E      | 1             |
| DÜZCE          | K      | 1             |
| EDİRNE         | E      | 1             |
| EDİRNE         | K      | 6             |
| ELAZIĞ         | E      | 3             |
| ELAZIĞ         | K      | 10            |
| ERZİNCAN       | E      | 2             |
| ERZİNCAN       | K      | 5             |
| ERZURUM        | E      | 5             |
| ERZURUM        | K      | 9             |
| ESKİŞEHİR      | E      | 3             |
| GAZİANTEP      | E      | 14            |
| GAZİANTEP      | K      | 11            |
| GİRESUN        | E      | 4             |
| GİRESUN        | K      | 6             |
| HAKKARİ        | E      | 2             |
| HAKKARİ        | K      | 1             |
| HATAY          | E      | 4             |
| HATAY          | K      | 3             |
| IĞDIR          | E      | 1             |
| ISPARTA        | E      | 8             |
| ISPARTA        | K      | 11            |
| İSTANBUL       | E      | 21            |
| İSTANBUL       | K      | 26            |
| İZMİR          | E      | 10            |
| İZMİR          | K      | 14            |
| KAHRAMANMARAŞ  | E      | 4             |
| KAHRAMANMARAŞ  | K      | 4             |
| KARABÜK        | K      | 7             |
| KARAMAN        | K      | 1             |
| KARS           | K      | 2             |
| KASTAMONU      | E      | 10            |
| KASTAMONU      | K      | 13            |
| KAYSERİ        | E      | 8             |
| KAYSERİ        | K      | 9             |
| KIRIKKALE      | K      | 1             |
| KIRKLARELİ     | E      | 2             |
| KIRŞEHİR       | E      | 2             |
| KIRŞEHİR       | K      | 4             |
| KİLİS          | E      | 7             |
| KOCAELİ        | E      | 2             |
| KOCAELİ        | K      | 4             |
| KONYA          | E      | 12            |
| KONYA          | K      | 7             |
| KÜTAHYA        | E      | 2             |
| KÜTAHYA        | K      | 1             |
| MALATYA        | E      | 1             |
| MALATYA        | K      | 2             |
| MANİSA         | E      | 11            |
| MANİSA         | K      | 3             |
| MARDİN         | E      | 3             |
| MARDİN         | K      | 7             |
| MERSİN         | E      | 5             |
| MERSİN         | K      | 12            |
| MUĞLA          | E      | 7             |
| MUĞLA          | K      | 5             |
| MUŞ            | E      | 5             |
| MUŞ            | K      | 2             |
| NEVŞEHİR       | E      | 3             |
| NEVŞEHİR       | K      | 2             |
| NİĞDE          | E      | 2             |
| NİĞDE          | K      | 3             |
| ORDU           | E      | 6             |
| ORDU           | K      | 3             |
| OSMANİYE       | E      | 5             |
| OSMANİYE       | K      | 7             |
| RİZE           | E      | 5             |
| RİZE           | K      | 7             |
| SAKARYA        | E      | 1             |
| SAKARYA        | K      | 4             |
| SAMSUN         | E      | 9             |
| SAMSUN         | K      | 4             |
| SİİRT          | E      | 3             |
| SİİRT          | K      | 1             |
| SİNOP          | E      | 3             |
| SİNOP          | K      | 2             |
| SİVAS          | E      | 10            |
| SİVAS          | K      | 7             |
| ŞANLIURFA      | E      | 12            |
| ŞANLIURFA      | K      | 5             |
| ŞIRNAK         | E      | 47            |
| ŞIRNAK         | K      | 63            |
| TEKİRDAĞ       | E      | 4             |
| TEKİRDAĞ       | K      | 8             |
| TOKAT          | E      | 4             |
| TOKAT          | K      | 4             |
| TRABZON        | E      | 4             |
| TRABZON        | K      | 4             |
| TUNCELİ        | E      | 1             |
| TUNCELİ        | K      | 3             |
| UŞAK           | E      | 2             |
| UŞAK           | K      | 3             |
| VAN            | K      | 2             |
| YALOVA         | E      | 5             |
| YALOVA         | K      | 1             |
| YOZGAT         | E      | 5             |
| YOZGAT         | K      | 8             |
| ZONGULDAK      | E      | 5             |
| ZONGULDAK      | K      | 3             |
|                |

E: Male in Turkish
K: Female in Turkish

***

** 9. Write the query that retrieves the information about how many male and how many female customers we have in which city by creating "number of men" and "number of women" columns. **


Solution 1-
````sql
SELECT CITIES, 
(SELECT COUNT(*)FROM CUSTOMERS  WHERE CITYID=CT.ID AND GENDER ='E') AS ERKEKSAYISI,
(SELECT COUNT(*)FROM CUSTOMERS  WHERE CITYID=CT.ID AND GENDER ='K') AS KADINSAYISI
FROM CITIES CT
````
  
#### Answer:
| CITIES         | ERKEKSAYISI | KADINSAYISI |
| -------------- | ----------- | ----------- |
| ADANA          | 10          | 6           |
| ADIYAMAN       | 7           | 4           |
| AFYONKARAHİSAR | 6           | 13          |
| AĞRI           | 7           | 6           |
| AMASYA         | 3           | 2           |
| ANKARA         | 13          | 16          |
| ANTALYA        | 8           | 5           |
| ARTVİN         | 5           | 7           |
| AYDIN          | 7           | 8           |
| BALIKESİR      | 11          | 9           |
| BİLECİK        | 2           | 5           |
| BİNGÖL         | 3           | 9           |
| BİTLİS         | 2           | 5           |
| BOLU           | 4           | 5           |
| BURDUR         | 8           | 3           |
| BURSA          | 6           | 16          |
| ÇANAKKALE      | 4           | 5           |
| ÇANKIRI        | 5           | 4           |
| ÇORUM          | 11          | 11          |
| DENİZLİ        | 11          | 3           |
| DİYARBAKIR     | 8           | 12          |
| EDİRNE         | 1           | 6           |
| ELAZIĞ         | 3           | 10          |
| ERZİNCAN       | 2           | 5           |
| ERZURUM        | 5           | 9           |
| ESKİŞEHİR      | 3           | 0           |
| GAZİANTEP      | 14          | 11          |
| GİRESUN        | 4           | 6           |
| GÜMÜŞHANE      | 0           | 0           |
| HAKKARİ        | 2           | 1           |
| HATAY          | 4           | 3           |
| ISPARTA        | 8           | 11          |
| MERSİN         | 5           | 12          |
| İSTANBUL       | 21          | 26          |
| İZMİR          | 10          | 14          |
| KARS           | 0           | 2           |
| KASTAMONU      | 10          | 13          |
| KAYSERİ        | 8           | 9           |
| KIRKLARELİ     | 2           | 0           |
| KIRŞEHİR       | 2           | 4           |
| KOCAELİ        | 2           | 4           |
| KONYA          | 12          | 7           |
| KÜTAHYA        | 2           | 1           |
| MALATYA        | 1           | 2           |
| MANİSA         | 11          | 3           |
| KAHRAMANMARAŞ  | 4           | 4           |
| MARDİN         | 3           | 7           |
| MUĞLA          | 7           | 5           |
| MUŞ            | 5           | 2           |
| NEVŞEHİR       | 3           | 2           |
| NİĞDE          | 2           | 3           |
| ORDU           | 6           | 3           |
| RİZE           | 5           | 7           |
| SAKARYA        | 1           | 4           |
| SAMSUN         | 9           | 4           |
| SİİRT          | 3           | 1           |
| SİNOP          | 3           | 2           |
| SİVAS          | 10          | 7           |
| TEKİRDAĞ       | 4           | 8           |
| TOKAT          | 4           | 4           |
| TRABZON        | 4           | 4           |
| TUNCELİ        | 1           | 3           |
| ŞANLIURFA      | 12          | 5           |
| UŞAK           | 2           | 3           |
| VAN            | 0           | 2           |
| YOZGAT         | 5           | 8           |
| ZONGULDAK      | 5           | 3           |
| AKSARAY        | 7           | 5           |
| BAYBURT        | 0           | 1           |
| KARAMAN        | 0           | 1           |
| KIRIKKALE      | 0           | 1           |
| BATMAN         | 3           | 3           |
| ŞIRNAK         | 47          | 63          |
| BARTIN         | 1           | 1           |
| ARDAHAN        | 3           | 5           |
| IĞDIR          | 1           | 0           |
| YALOVA         | 5           | 1           |
| KARABÜK        | 0           | 7           |
| KİLİS          | 7           | 0           |
| OSMANİYE       | 5           | 7           |
| DÜZCE          | 1           | 1           |
|                |

"ERKEKSAYISI" : Number of Men in Turkish
"KADINSAYISI" : Number of Women in Turkish

***


**10.Add a new column for age group to the Customers table (Name AGEGROUP data type VARCHAR(50)).**


Solution 1-
````sql
ALTER TABLE CUSTOMERS ADD AGEGROUP VARCHAR(50)

````

#### Steps:
The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

***


**11.Update the AGEGROUP column you added to the Customers table as:
20-35 years old, 36-45 years old, 46-55 years old, 55-65 years old and over 65 years old.**


Solution 1-
````sql
UPDATE CUSTOMERS 
SET AGEGROUP =
(CASE
WHEN (select YEAR(getdate()) - YEAR(CUSTOMERS.BIRTHDATE)) BETWEEN 20 AND 35 THEN '20-35 YAŞ'
WHEN (select YEAR(getdate()) - YEAR(CUSTOMERS.BIRTHDATE)) BETWEEN 36 AND 45 THEN '36-45 YAŞ'
WHEN (select YEAR(getdate()) - YEAR(CUSTOMERS.BIRTHDATE)) BETWEEN 46 AND 55 THEN '46-55 YAŞ'
WHEN (select YEAR(getdate()) - YEAR(CUSTOMERS.BIRTHDATE)) BETWEEN 55 AND 65 THEN '55-65 YAŞ'
WHEN (select YEAR(getdate()) - YEAR(CUSTOMERS.BIRTHDATE)) > 65 THEN '65 YAŞ ÜSTÜ'
END)	
````

Solution 2-
````sql
UPDATE CUSTOMERS 
SET AGEGROUP =
(CASE
WHEN (SELECT DATEDIFF(YEAR,BIRTHDATE,GETDATE())) BETWEEN 20 AND 35 THEN '20-35 YAŞ'
WHEN (SELECT DATEDIFF(YEAR,BIRTHDATE,GETDATE())) BETWEEN 36 AND 45 THEN '36-45 YAŞ'
WHEN (SELECT DATEDIFF(YEAR,BIRTHDATE,GETDATE())) BETWEEN 46 AND 55 THEN '46-55 YAŞ'
WHEN (SELECT DATEDIFF(YEAR,BIRTHDATE,GETDATE())) BETWEEN 55 AND 65 THEN '55-65 YAŞ'
WHEN (SELECT DATEDIFF(YEAR,BIRTHDATE,GETDATE())) > 65 THEN '65 YAŞ ÜSTÜ'
END)
````

  
#### Steps:
The UPDATE statement is used to modify the existing records in a table.

The CASE expression goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

The DATEDIFF() function returns the difference between two dates.




#### Answer:
| ID | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                  | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP    |
| -- | --------------------- | ----------- | ------ | ---------------------- | ---------- | ------ | ---------- | ------------ | ------------ | ----------- |
| 1  | Sevda AKÇAN           | 42074151323 | K      | s_akcan@miuul.com      | 12.05.1964 | 22     | 202        | (542)5255514 | (532)3438190 | 55-65 YAŞ   |
| 2  | Sebahat ŞERALI        | 74789296130 | K      | s_serali@miuul.com     | 11.06.1943 | 78     | 473        | (534)7157144 | (532)2212126 | 65 YAŞ ÜSTÜ |
| 3  | Irmak HAMİDİ          | 86856513494 | K      | i_hamidi@miuul.com     | 13.11.1973 | 21     | 675        | (533)2144819 | (555)1183975 | 46-55 YAŞ   |
| 4  | Tuğçe AKKOÇ           | 50190579600 | K      | t_akkoc@miuul.com      | 8.06.1958  | 30     | 158        | (543)4243115 | (533)6299636 | 55-65 YAŞ   |
| 5  | Necdet ERÇAM          | 26046030220 | E      | n_ercam@miuul.com      | 22.05.1986 | 60     | 718        | (532)6896237 | (534)2924742 | 36-45 YAŞ   |
| 6  | Ahmet İNCİKAPI        | 6722155596  | E      | a_incikapi@miuul.com   | 28.05.1991 | 53     | 225        | (532)2414618 | (538)8459085 | 20-35 YAŞ   |
| 7  | Arif TEMELOĞLU        | 43691911318 | E      | a_temeloglu@miuul.com  | 11.12.1967 | 40     | 638        | (554)5504524 | (534)6379277 | 55-65 YAŞ   |
| 8  | Elif ÖZÇELİKBAŞ       | 84870496920 | K      | e_ozcelikbas@miuul.com | 6.06.1993  | 73     | 815        | (536)9014627 | (544)3937372 | 20-35 YAŞ   |
| 9  | Ali Eymen DEVE        | 80011834707 | E      | a_eymen@miuul.com      | 23.01.1985 | 39     | 463        | (533)8082176 | (538)4811026 | 36-45 YAŞ   |
| 10 | Muhammed Ali ABDULLAH | 64660973116 | E      | m_ali@miuul.com        | 7.05.1987  | 25     | 851        | (536)4359524 | (532)3864478 | 36-45 YAŞ   |
|    |

YAŞ: Age in Turkish

**12.Write the query that is calculated according to the age of the customer in the Customers table and returns how many people are in which age range.**

****
NOTE: Write without using the 'agegroup' field we created in the previous question.

Solution 1-
````sql
SELECT COUNT(*) AS CUSTOMERCOUNT,
CASE
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 20 AND 35 THEN '20-35 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 36 AND 45 THEN '36-45 YAŞ'
    WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 46 AND 55 THEN '46-55 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 56 AND 65 THEN '56-65 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) >65 THEN  '65 YAŞ ÜSTÜ'
END AGEGROUP2
FROM CUSTOMERS
GROUP BY 
CASE
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 20 AND 35 THEN '20-35 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 36 AND 45 THEN '36-45 YAŞ'
    WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 46 AND 55 THEN '46-55 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 56 AND 65 THEN '56-65 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) >65 THEN  '65 YAŞ ÜSTÜ'
END

````

#### Answer:
| AGEGROUP  | CUSTOMERCOUNT |
| --------- | ------------- |
| 65 Over   | 266           |
| 20-35 Age | 207           |
| 46-55 Age | 163           |
| 56-65 Age | 161           |
| 36-45 Age | 154           |


Solution 2- 

````sql
SELECT AGEGROUP2,COUNT(TMT.ID) AS CUSTOMERCOUNT FROM 
(SELECT *,
CASE
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 20 AND 35 THEN '20-35 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 36 AND 45 THEN '36-45 YAŞ'
    WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 46 AND 55 THEN '46-55 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) BETWEEN 56 AND 65 THEN '56-65 YAŞ'
	WHEN DATEDIFF(YEAR,BIRTHDATE,GETDATE()) >65 THEN  '65 YAŞ ÜSTÜ'
END AGEGROUP2
FROM CUSTOMERS) TMT
GROUP BY AGEGROUP2
ORDER BY AGEGROUP2
````
#### Steps:
Using "case" again while doing "group by" can extend the code. For this reason, we can make dynamic view. Dynamic view is to go up to a sql query and write a query there as if you are pulling from the table. 

***
 
 **13.Let's see the people who live in Istanbul and whose district is not "Kadıköy".**
 
Solution 1-

````sql
 SELECT * FROM CUSTOMERS C
 INNER JOIN CITIES CT ON CT.ID =C.CITYID
 INNER JOIN DISTRICTS D ON D.ID=C.DISTRICTID
 WHERE CT.CITIES = 'İSTANBUL' AND D.DISTRICT != 'KADIKÖY'
````

Solution 2-
Let's use Inner Join.
````sql
SELECT TOP 10 C.*,CT.CITIES,D.DISTRICT FROM CUSTOMERS C
 INNER JOIN DISTRICTS D ON C.DISTRICTID=D.ID
 INNER JOIN CITIES CT ON C.CITYID=CT.ID
 WHERE CT.CITIES='İSTANBUL' AND D.DISTRICT != 'KADIKÖY'
````

#### Answer:
| ID  | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                  | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP    | CITIES   | DISTRICT     |
| --- | --------------------- | ----------- | ------ | ---------------------- | ---------- | ------ | ---------- | ------------ | ------------ | ----------- | -------- | ------------ |
| 15  | Yasin AĞAGÜL          | 32764684197 | E      | y_agagvl@miuul.com     | 19.10.1979 | 34     | 897        | (532)6102663 | (537)3381012 | 36-45 YAŞ   | İSTANBUL | SULTANBEYLİ  |
| 88  | Sebahat CİLALITAŞ     | 65960134490 | K      | s_cilalitas@miuul.com  | 30.09.1978 | 34     | 64         | (535)7019065 | (532)2408341 | 36-45 YAŞ   | İSTANBUL | BAKIRKÖY     |
| 97  | Deniz BENDER          | 31619199155 | E      | d_bender@miuul.com     | 4.04.1986  | 34     | 134        | (542)4181722 | (536)4621320 | 36-45 YAŞ   | İSTANBUL | ÇATALCA      |
| 101 | Çağla BEĞEN           | 85581395736 | K      | c_begen@miuul.com      | 22.12.1991 | 34     | 81         | (535)1338012 | (533)8331511 | 20-35 YAŞ   | İSTANBUL | BEŞİKTAŞ     |
| 127 | Nurettin GAYRETLİ     | 2822523822  | E      | n_gayretli@miuul.com   | 27.04.1950 | 34     | 84         | (532)7969080 | (536)7322740 | 65 YAŞ ÜSTÜ | İSTANBUL | BEYOĞLU      |
| 139 | Yeliz KÜÇÜKALP        | 65432369284 | K      | y_kvcvkalp@miuul.com   | 26.02.1965 | 34     | 488        | (555)9613650 | (543)1071715 | 55-65 YAŞ   | İSTANBUL | SARIYER      |
| 164 | Eylül GÜLÜ            | 56388773535 | K      | e_gvlv@miuul.com       | 24.08.1969 | 34     | 3          | (537)5953916 | (532)4647711 | 46-55 YAŞ   | İSTANBUL | ADALAR       |
| 174 | Müzeyyen OCAKÇI       | 89589164667 | K      | m_ocakci@miuul.com     | 19.02.1972 | 34     | 707        | (543)1576124 | (505)9181537 | 46-55 YAŞ   | İSTANBUL | KÜÇÜKÇEKMECE |
| 199 | Muhammed Emin TEKKAYA | 87271968026 | E      | m_emin@miuul.com       | 19.04.1984 | 34     | 897        | (542)2911632 | (535)9881318 | 36-45 YAŞ   | İSTANBUL | SULTANBEYLİ  |
| 208 | Neslihan KILIÇÇEKER   | 53734331933 | K      | n_kilicceker@miuul.com | 4.10.1982  | 34     | 707        | (543)1432619 | (505)2287257 | 36-45 YAŞ   | İSTANBUL | KÜÇÜKÇEKMECE |
|     |


***

**14.Suppose we delete the "Ankara" record from the Cities table. In this case, the "city" column of the customers whose city is "Ankara" will be empty. Write the query that lists the customers whose "city" column is empty.**


First, 'Let's delete "Ankara". If we know the ID of Ankara which is 6 we can easily delete it.

````sql
UPDATE CITIES SET CITIES = NULL WHERE ID= 6
````
Solution -
````sql
 SELECT TOP 10 * FROM CUSTOMERS C
 WHERE C.CITYID  = ( SELECT CT.ID FROM CITIES CT WHERE CT.CITIES IS NULL)
````
To add Ankara again:
````sql
SET IDENTITY_INSERT CITIES ON -- ID değerimixz identity_insert off modundaydı önce onu açmamız lazım.
INSERT INTO CITIES(ID,CITIES)
VALUES(6,'ANKARA')
SET IDENTITY_INSERT CITIES OFF -- ID için idendity_insert değerini kapattık.
````
#### Steps:
The INSERT INTO statement is used to insert new records in a table.

The only way to insert values into a field that is defined as an “IDENTITY” (or autonumber) field, is to set the IDENTITY_INSERT option to “ON” prior to inserting data into the table.


#### Answer:
| ID  | CUSTOMERNAME              | TCNUMBER    | GENDER | EMAIL                | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP    |
| --- | ------------------------- | ----------- | ------ | -------------------- | ---------- | ------ | ---------- | ------------ | ------------ | ----------- |
| 112 | Aslı GÜNE                 | 63618747382 | K      | a_gvne@miuul.com     | 6.05.1994  | 6      | 157        | (505)6442992 | (532)8235020 | 20-35 YAŞ   |
| 135 | Güllü SALUR               | 76464619181 | K      | g_salur@miuul.com    | 24.01.1998 | 6      | 128        | (533)7408614 | (535)5992618 | 20-35 YAŞ   |
| 160 | Rukiye ÜNGÖR              | 1490087423  | K      | r_vngor@miuul.com    | 7.07.1956  | 6      | 756        | (554)1519484 | (538)7692165 | 65 YAŞ ÜSTÜ |
| 180 | Güler BEŞKAYA             | 87951772201 | K      | g_beskaya@miuul.com  | 21.07.1998 | 6      | 756        | (553)8215027 | (555)8771930 | 20-35 YAŞ   |
| 188 | Sefa CANGAR               | 17673520419 | E      | s_cangar@miuul.com   | 31.07.1958 | 6      | 361        | (554)1434188 | (533)3133445 | 55-65 YAŞ   |
| 209 | İzzet CANKURU             | 76469454575 | E      | i_cankuru@miuul.com  | 11.12.1978 | 6      | 257        | (555)3724345 | (541)4935289 | 36-45 YAŞ   |
| 225 | Seval ÖZKANLI             | 52599001986 | K      | s_ozkanli@miuul.com  | 2.07.1995  | 6      | 425        | (534)7052964 | (538)6732660 | 20-35 YAŞ   |
| 227 | Halil İbrahim BİMBİRDİREK | 12831119936 | E      | h_ibrahim@miuul.com  | 19.07.1971 | 6      | 756        | (544)4642995 | (537)9514174 | 46-55 YAŞ   |
| 233 | Ecrin MÜRSEL              | 1693687461  | K      | e_mvrsel@miuul.com   | 17.01.1956 | 6      | 425        | (535)3784675 | (533)9489743 | 65 YAŞ ÜSTÜ |
| 358 | Cihan SAYGINER            | 14412309644 | E      | c_sayginer@miuul.com | 26.03.1943 | 6      | 30         | (533)8984184 | (537)3434486 | 65 YAŞ ÜSTÜ |
|     |

***

**15.We want to get the operator information of our customers' phone numbers. (We want to get the operator number (532)(505) next to TELN1 and TELNR2 columns). Write the SQL query required for this query.**

Solution -

````sql
 SELECT TOP 10 *,
 SUBSTRING(TELNR1,2,3) AS OPERATOR1,
 SUBSTRING(TELNR2,2,3) AS OPERATOR2
 FROM CUSTOMERS
````

#### Steps:
String verilerde istenilen karakter kadar verinin geri döndürülmesini sağlamak için SUBSTRING fonksiyonu kullanılır

The LEFT() function extracts a number of characters from a string (starting from left).


#### Answer:
| ID | CUSTOMERNAME          | TCNUMBER    | GENDER | EMAIL                  | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP    | OPERATOR1 | OPERATOR2 |
| -- | --------------------- | ----------- | ------ | ---------------------- | ---------- | ------ | ---------- | ------------ | ------------ | ----------- | --------- | --------- |
| 1  | Sevda AKÇAN           | 42074151323 | K      | s_akcan@miuul.com      | 12.05.1964 | 22     | 202        | (542)5255514 | (532)3438190 | 55-65 YAŞ   | 542       | 532       |
| 2  | Sebahat ŞERALI        | 74789296130 | K      | s_serali@miuul.com     | 11.06.1943 | 78     | 473        | (534)7157144 | (532)2212126 | 65 YAŞ ÜSTÜ | 534       | 532       |
| 3  | Irmak HAMİDİ          | 86856513494 | K      | i_hamidi@miuul.com     | 13.11.1973 | 21     | 675        | (533)2144819 | (555)1183975 | 46-55 YAŞ   | 533       | 555       |
| 4  | Tuğçe AKKOÇ           | 50190579600 | K      | t_akkoc@miuul.com      | 8.06.1958  | 30     | 158        | (543)4243115 | (533)6299636 | 55-65 YAŞ   | 543       | 533       |
| 5  | Necdet ERÇAM          | 26046030220 | E      | n_ercam@miuul.com      | 22.05.1986 | 60     | 718        | (532)6896237 | (534)2924742 | 36-45 YAŞ   | 532       | 534       |
| 6  | Ahmet İNCİKAPI        | 6722155596  | E      | a_incikapi@miuul.com   | 28.05.1991 | 53     | 225        | (532)2414618 | (538)8459085 | 20-35 YAŞ   | 532       | 538       |
| 7  | Arif TEMELOĞLU        | 43691911318 | E      | a_temeloglu@miuul.com  | 11.12.1967 | 40     | 638        | (554)5504524 | (534)6379277 | 55-65 YAŞ   | 554       | 534       |
| 8  | Elif ÖZÇELİKBAŞ       | 84870496920 | K      | e_ozcelikbas@miuul.com | 6.06.1993  | 73     | 815        | (536)9014627 | (544)3937372 | 20-35 YAŞ   | 536       | 544       |
| 9  | Ali Eymen DEVE        | 80011834707 | E      | a_eymen@miuul.com      | 23.01.1985 | 39     | 463        | (533)8082176 | (538)4811026 | 36-45 YAŞ   | 533       | 538       |
| 10 | Muhammed Ali ABDULLAH | 64660973116 | E      | m_ali@miuul.com        | 7.05.1987  | 25     | 851        | (536)4359524 | (532)3864478 | 36-45 YAŞ   | 536       | 532       |
|    |


***

**16.We want to return the operator information of our customers' phone numbers. For example, let the phone numbers be operator X starting with "50" or "55", operator Y starting with "54", operator Z starting with "53". Write the query that will return the information about how many customers we have from which operator.**

Solution -

```sql
SELECT SUM(TELNR1_X + TELNR2_X) AS OPERATOR_X,
SUM(TELNR1_Y + TELNR2_Y) AS OPERATOR_Y,
SUM(TELNR1_Z + TELNR2_Z) AS OPERATOR_Z FROM
(SELECT *,
 CASE
	WHEN TELNR1 LIKE '(50%' OR TELNR1 LIKE '(55%' THEN 1
	ELSE 0
END AS TELNR1_X,
 CASE
	WHEN TELNR1 LIKE '(54%' THEN 1
	ELSE 0
END AS TELNR1_Y,
 CASE
	WHEN TELNR1 LIKE '(53%' THEN 1
	ELSE 0
END AS TELNR1_Z,
 CASE
	WHEN TELNR2 LIKE '(50%' OR TELNR2 LIKE '(55%' THEN 1
	ELSE 0
END AS TELNR2_X,
 CASE
	WHEN TELNR2 LIKE '(54%' THEN 1
	ELSE 0
END AS TELNR2_Y,
CASE
	WHEN TELNR2 LIKE '(53%' THEN 1
	ELSE 0
END AS TELNR2_Z
FROM CUSTOMERS) TT
```

#### Answer:
| OPERATOR_X | OPERATOR_Y | OPERATOR_Z |
| ---------- | ---------- | ---------- |
| 461        | 478        | 963        |
|            |

***

**17.Write the query that brings the districts in each province where we have the most customers, ordered from most to least according to the number of customers.**

Solution -

````sql
SELECT TOP 20 CT.CITIES,D.DISTRICT, COUNT(C.ID) AS CUSTOMERCOUNT FROM CUSTOMERS C
INNER JOIN CITIES CT ON  CT.ID = C.CITYID 
INNER JOIN DISTRICTS D ON D.ID = C.DISTRICTID 
GROUP BY CT.CITIES,D.DISTRICT
ORDER BY 1,3 DESC
````
 

#### Answer:
| CITIES         | DISTRICT              | CUSTOMERCOUNT |
| -------------- | --------------------- | ------------- |
| ADANA          | SEYHAN                | 8             |
| ADANA          | ALADAĞ                | 6             |
| ADANA          | YÜREĞİR               | 2             |
| ADIYAMAN       | ADIYAMAN MERKEZ       | 5             |
| ADIYAMAN       | BESNİ                 | 2             |
| ADIYAMAN       | SAMSAT                | 2             |
| ADIYAMAN       | GÖLBAŞI/ADIYAMAN      | 1             |
| ADIYAMAN       | KAHTA                 | 1             |
| AFYONKARAHİSAR | AFYONKARAHİSAR MERKEZ | 5             |
| AFYONKARAHİSAR | BOLVADİN              | 4             |
| AFYONKARAHİSAR | DİNAR                 | 4             |
| AFYONKARAHİSAR | DAZKIRI               | 2             |
| AFYONKARAHİSAR | EMİRDAĞ               | 1             |
| AFYONKARAHİSAR | İHSANİYE              | 1             |
| AFYONKARAHİSAR | SİNANPAŞA             | 1             |
| AFYONKARAHİSAR | SULTANDAĞI            | 1             |
| AĞRI           | TUTAK                 | 4             |
| AĞRI           | ELEŞKİRT              | 3             |
| AĞRI           | AĞRI MERKEZ           | 2             |
| AĞRI           | DİYADİN               | 2             |
|                |


***

**18.Write the query that brings customers' birthdays as days of the week in Turkish.**

Solution -

```sql
SET LANGUAGE Turkish
SELECT TOP 10 CUSTOMERNAME,
DATENAME(DW,BIRTHDATE) AS BIRTHDAY
FROM CUSTOMERS
```

#### Steps:
The DATENAME() function returns a specified part of a date.

This function returns the result as a string value.



#### Answer:
| CUSTOMERNAME          | BIRTHDAY  |
| --------------------- | --------- |
| Sevda AKÇAN           | Salı      |
| Sebahat ŞERALI        | Cuma      |
| Irmak HAMİDİ          | Salı      |
| Tuğçe AKKOÇ           | Pazar     |
| Necdet ERÇAM          | Perşembe  |
| Ahmet İNCİKAPI        | Salı      |
| Arif TEMELOĞLU        | Pazartesi |
| Elif ÖZÇELİKBAŞ       | Pazar     |
| Ali Eymen DEVE        | Çarşamba  |
| Muhammed Ali ABDULLAH | Perşembe  |
|                       |


Monday   	pazartesi 
Tuesday 	salı 
Wednesday 	çarşamba 
Thursday 	perşembe 
Friday 	        cuma 
Saturday 	cumartesi 
Sunday 	        pazar 

***


**19.Write the query that prints the day of the customer's birthday in this year.**

Solution -

```sql

SELECT TOP 10 *,
	CASE
		WHEN KMKK.KACGUNGECTI%7 = 0 THEN DATENAME(weekday, GETDATE())
		WHEN KMKK.KACGUNGECTI%7 = 1 THEN DATENAME(weekday, DATEADD(day, -6, GETDATE()))
		WHEN KMKK.KACGUNGECTI%7 = 2 THEN DATENAME(weekday, DATEADD(day, -5, GETDATE()))
		WHEN KMKK.KACGUNGECTI%7 = 3 THEN DATENAME(weekday, DATEADD(day, -4, GETDATE()))
		WHEN KMKK.KACGUNGECTI%7 = 4 THEN DATENAME(weekday, DATEADD(day, -3, GETDATE()))
		WHEN KMKK.KACGUNGECTI%7 = 5 THEN DATENAME(weekday, DATEADD(day, -2, GETDATE()))
		WHEN KMKK.KACGUNGECTI%7 = 6 THEN DATENAME(weekday, DATEADD(day, -1, GETDATE()))
	END AS HANGIGUN
FROM
(SELECT KMK.CUSTOMERNAME, DATEDIFF(DAY,KMK.BIRTHDATE,KMK.TODAYSDATE) AS KACGUNGECTI
FROM 
(SELECT *, GETDATE() AS TODAYSDATE FROM CUSTOMERS) KMK)KMKK
```

#### Steps:
 The DATEADD() function adds a time/date interval to a date and then returns the date.



#### Answer:
| CUSTOMERNAME          | KACGUNGECTI | HANGIGUN  |
| --------------------- | ----------- | --------- |
| Sevda AKÇAN           | 21709       | Cumartesi |
| Sebahat ŞERALI        | 29350       | Çarşamba  |
| Irmak HAMİDİ          | 18237       | Cumartesi |
| Tuğçe AKKOÇ           | 23874       | Pazartesi |
| Necdet ERÇAM          | 13664       | Perşembe  |
| Ahmet İNCİKAPI        | 11832       | Cumartesi |
| Arif TEMELOĞLU        | 20401       | Pazar     |
| Elif ÖZÇELİKBAŞ       | 11092       | Pazartesi |
| Ali Eymen DEVE        | 14148       | Cuma      |
| Muhammed Ali ABDULLAH | 13314       | Perşembe  |
|                       |

KACGUNGECTI: How many days have passed since birth.

***

**20.List customers whose birthday is today.**

Solution-

```sql
SELECT * FROM CUSTOMERS
WHERE DATEPART(DAY,BIRTHDATE)=DATEPART(DAY,GETDATE()) AND DATEPART(MONTH,BIRTHDATE)=DATEPART(MONTH,GETDATE()) 
```


#### Steps:
The DATEPART() function returns a specified part of a date.

This function returns the result as an integer value.

#### Answer:
| ID  | CUSTOMERNAME      | TCNUMBER    | GENDER | EMAIL                | BIRTHDATE  | CITYID | DISTRICTID | TELNR1       | TELNR2       | AGEGROUP    |
| --- | ----------------- | ----------- | ------ | -------------------- | ---------- | ------ | ---------- | ------------ | ------------ | ----------- |
| 15  | Yasin AĞAGÜL      | 32764684197 | E      | y_agagvl@miuul.com   | 19.10.1979 | 34     | 897        | (532)6102663 | (537)3381012 | 36-45 YAŞ   |
| 84  | Muhammed Ali ORUC | 1192159330  | E      | m_ali@miuul.com      | 19.10.1996 | 1      | 641        | (536)9081564 | (555)6774295 | 20-35 YAŞ   |
| 185 | Ersin SEKMEN      | 44465589374 | E      | e_sekmen@miuul.com   | 19.10.1975 | 23     | 343        | (532)7922697 | (544)5402036 | 46-55 YAŞ   |
| 923 | İsmail GÜLKOKAN   | 10165087167 | E      | i_gvlkokan@miuul.com | 19.10.1948 | 68     | 20         | (541)3681294 | (555)6582823 | 65 YAŞ ÜSTÜ |
|     |




***
