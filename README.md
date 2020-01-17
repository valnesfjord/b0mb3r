<h1 align="center">Добро пожаловать в b0mb3r 👋</h1>
<p align="center">
    <sub>Открытый и бесплатный СМС бомбер</sub>
    <br /><br />
    <img alt="Made with Python" src="https://img.shields.io/badge/Made%20with-Python-%23FFD242?logo=python&logoColor=white"></img>
    <img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></img>
    <img alt="HitCount" src="http://hits.dwyl.io/crinny/b0mb3r.svg"></img>
</p>

## 🚀 Установка
1. Установите Python версии не ниже 3.7. Сделать это можно так:
    ### Для Windows
    Скачайте установщик с [официального сайта](https://www.python.org/downloads/) и запустите его. Убедитесь, что при установке отметили галочку ![Add Python to PATH](https://user-images.githubusercontent.com/42045258/69171091-557d2780-0b0c-11ea-8adf-7f819357f041.png)
    ### Для Android
    Установите приложение [Termux](https://play.google.com/store/apps/details?id=com.termux), запустите его и следуйте [инструкции](https://wiki.termux.com/wiki/Python).

2. Введите следующую команду:
Для Android (и некоторых Linux систем):
```sh
pip3 install https://github.com/crinny/b0mb3r/archive/master.zip --upgrade
```
Для Windows (могут подойти и другие системы):
```sh
pip install https://github.com/crinny/b0mb3r/archive/master.zip --upgrade
```
Всё зависит от вашего способа установки Python 3.7

## Запуск
Всё просто! Введите команду `b0mb3r` или `bomber` и интерфейс бомбера будет запущен. Команда доступна из любой директории.

## 💻 Расширенное использование
### API
b0mb3r имеет API, которое позволит вам выполнять некоторые действия, доступные через интерфейс, программно. Запросы необходимо отправлять на сервер `127.0.0.1:8080`, перед этим запустив бомбер.

Ответ на каждый запрос к API возвращается в формате JSON и имеет одно обязательное поле: `success`. Оно будет иметь значение _true_, если запрос был обработан или _false_, если возникла ошибка. В случае ошибки в ответ будут добавлены поля `error_code` ([Код ошибки](https://ru.wikipedia.org/wiki/%D0%A1%D0%BF%D0%B8%D1%81%D0%BE%D0%BA_%D0%BA%D0%BE%D0%B4%D0%BE%D0%B2_%D1%81%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F_HTTP)) и `error_description` (Описание ошибки). При ошибке 500 в ответе также будет представлено поле `traceback`
<h1></h1>

### POST `/attack/start`
Начинает атаку на телефон.

| Название параметра | Описание                                                |
|--------------------|---------------------------------------------------------|
| phone_code         | Код страны, например 7                                  |
| phone              | Номер телефона без + и кода страны, например 9123456789 |
| number_of_cycles   | Количество повторений                                   |

**Пример запроса**

```python
import requests

params = {
    "phone_code": "7",
    "phone": "9123456789",
    "number_of_cycles": "1"
}

request = requests.post("http://127.0.0.1:8080/attack/start", data=params)

print(request.json())
```

**Пример ответа**
<img alt="Пример ответа" src="https://user-images.githubusercontent.com/42045258/70137798-da854680-169f-11ea-8133-2f37631292af.png"></img>

## 📝 Лицензия
<!--- Не надо это удалять, пожалуйста 😐  -->
Проект распространяется под лицензией [Mozilla Public License 2.0](https://github.com/crinny/b0mb3r/blob/master/LICENSE). Скачивая программное обеспечение из [этого](https://github.com/crinny/b0mb3r) репозитория, вы соглашаетесь с ней. По условиям лицензии вы обязаны выкладывать исходный код ваших модификаций под той же лицензией.

**Остались вопросы?** Я в [Telegram](https://t.me/crinny) (предпочтительно) или [ВКонтакте](https://vk.me/crinnyx). [Прочтите](http://neprivet.ru/), прежде чем писать
