
# Скрипт для наповнення бази даних SOAP-вебсервісу тестовими записами

Для забезпечення зручності тестування розробленого вебсервісу потрібно наповнити його БД тестовими записами.

З цією метою було створено окремий скрипт на мові програмування Python, який використовує бібліотеку Faker для генерації тестових записів для бази даних (реєстру) користувачів.


Скрипт генерує тестові дані для записів про користувачів, такі як:
- ім'я, 
- прізвище, 
- по батькові, 
- дата народження, 
- РНОКПП, 
- УНЗР, 
- номер паспорта (формат для ID-карти, без серії), 
- стать.

І надсилає ці дані на локальний сервер за адресою http://localhost:8000/?wsdl.

Запит виконується з використанням бібліотеки zeep, успішні запити відображають відповідь сервера, а помилкові — статусний код і текст відповіді.

Для його запуску на віртуальній машині з розгорнутим та налаштованим вебсервісом необхідно виконати наступні дії:


1. Встановити необхідні бібліотеки:
```bash
sudo apt install python3-pip
pip install zeep requests Faker

```
2. Клонувати репозиторій:
```bash
git clone https://github.com/kshypachov/soap_web_service_sync.git
```

3. Клонувати репозиторій:

```bash
cd PutFakeDataSOAP
```

4. Запустити скрипт:

```bash
python3 client.py
```
## Опис змінних у файлі main.py

- `fake`: Об'єкт класу `Faker`, налаштований для використання української локалі.
- `wsdl`: URL-адреса, на яку будуть надсилатися дані.
- `count`: Кількість запитів, які будуть виконані.

