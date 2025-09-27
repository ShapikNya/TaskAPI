# Tasks Web API

Проект на **ASP.NET Core Web API** с **Clean Architecture**.  
Реализованы **JWT-аутентификация**, авторизация по ролям и работа с задачами (Tasks). 
                     
## 🚀 Технологии

- **ASP.NET Core Web API**
- **Entity Framework Core**
- **MediatR + CQRS**
- **Dependency Injection**
- **FluentValidation**
- **AutoMapper**
- **Swagger**
- **Serilog**
- **JWT Authentication & Role-based Authorization**
- **xUnit, FluentAssertions, Moq** — модульные и интеграционные тесты

## 📸 Скриншоты    
  <img width="1857" height="737" alt="image" src="https://github.com/user-attachments/assets/891b0923-0d2a-44e3-b542-ed74b7e1aa80" />

  <img width="1383" height="727" alt="image" src="https://github.com/user-attachments/assets/41a35cc6-fb88-459d-90a1-421a429cf840" />


## 📂 Архитектура
Tasks.sln   
ㅤ -Tasks.Application --- Бизнес-логика, CQRS-команды/запросы, валидаторы   
ㅤ -Tasks.Domain --- Сущности и интерфейсы   
ㅤ -Tasks.Infrastructure --- JWT, безопасность, инфраструктурные сервисы   
ㅤ -Tasks.Persistence ---ㅤДоступ к данным, EF Core, миграции   
ㅤ -Tasks.WebApi --- Контроллеры, Swagger, запуск API  
    
    
## 🔑 Аутентификация и авторизация

- Используется **JWT**.
- Реализована авторизация по ролям: `User`, `Admin`.
- Пример:  
  - Удалять пользователей может только **Admin**.  
  - Обычные пользователи могут только работать с задачами.
  - Неавторизованные пользователи могут только создать учётную запись.
    
    
## 🧪 Тестирование

В проекте реализованы модульные тесты
Примеры тестов:  
- Проверка создания и удаления пользователей  
- Проверка валидации команд/запросов  
    
    
## 📜 Запуск проекта

1. Клонировать репозиторий:   
ㅤㅤ   bash
       git clone https://github.com/ShapikNya/TaskAPI
   
3. Применить миграции:   
ㅤㅤ  bash    
ㅤㅤ  dotnet ef database update --project Tasks.Persistence

4. Запустить проект:    
 ㅤㅤ bash    
ㅤㅤ  dotnet run --project Tasks.WebApi

5. Открыть Swagger UI:    
 ㅤㅤ bash    
 ㅤㅤ https://localhost:{port}/swagger
