# Arch_Sem9

# Получение списка всех клиентов
GET http://localhost:8080/api/v1/clients

Ожидаемый ответ:
HTTP 200 
[
  {
    "idClient": 1,
    "name": "Иван"
  },
  {
   "idClient": 2,
   "name": "Петр" 
  }
]

# Добавление нового клиента
POST http://localhost:8080/api/v1/clients
Content-Type: application/json

{
  "name": "Сидоров"
}

Ожидаемый ответ: 
HTTP 200
{
  "idClient": 3,
  "name": "Сидоров"  
}


# Получение клиента по id
GET http://localhost:8080/api/v1/clients/3

Ожидаемый ответ:
HTTP 200
{
  "idClient": 3,
  "name": "Сидоров"
}


# Обновление клиента
PATCH http://localhost:8080/api/v1/clients/3
Content-Type: application/json

{
  "name": "Петров"
}

Ожидаемый ответ:
HTTP 200  
{
  "idClient": 3,
  "name": "Петров"
}


# Удаление клиента по id
DELETE http://localhost:8080/api/v1/clients/3

Ожидаемый ответ: 
HTTP 200
{}


# Получение клиентов с фильтрацией по имени
GET http://localhost:8080/api/v1/clients?name=Иван

Ожидаемый ответ:
HTTP 200
[
  {
    "idClient": 1, 
    "name": "Иван"
  }
]


# Получение информации о облачных ресурсах клиента
GET http://localhost:8080/api/v1/clients/1/cloud

Ожидаемый ответ:  
HTTP 200
{
  "OS": "Linux",
  "RAM": 512,
  "CPU": 4,
  "SSD": 2048, 
  "idClient": 1
}
