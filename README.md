# Scoring_api
Декларативный язык описания и система валидации запросов к HTTP API сервиса скоринга

# Структура запроса:
```
curl -X POST -H "Content-Type: application/json" -d '{"account": "horns&hoofs", "login": "h&f", "method":
"online_score", "token":
"55cc9ce545bcd144300fe9efc28e65d415b923ebb6be1e19d2750a2c03e80dd209a27954dca045e5bb12418e7d89b6d718a9e35af34e14e1d5bcd
"arguments": {"phone": "79175002040", 
              "email": "stupnikov@otus.ru", 
               "first_name": "Стансилав", 
               "last_name":"Ступников", 
               "birthday": "01.01.1990", 
               "gender": 1}}' 
http://127.0.0.1:8080/method/
```

- запрос валиден, если валидны все поля по отдельности
- аргументы валидны, если валидны все поля по отдельности и если присутсвует хоть одна пара 
phone-email, first name-last name, gender-birthday с непустыми значениями

# Методы:
  - online_score (в ответ выдается число, полученное вызовом функции get_score)
  - clients_interests (в ответ выдается словарь <id клиента>:<список интересов>)
