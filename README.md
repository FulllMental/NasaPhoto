# Космический Телеграм

Проект представляет собой телеграм бота, скачивающего определенные фотографии из подборок сайтов SpaceX и NASA, к примеру
фото определенного запуска у SpaceX, фото дня или фото планеты земля от NASA, 
после чего публикует их в группу телеграма с необходимой периодичностью.

Почти каждый скрипт является самостоятельным:

#### fetch_nasa_apod_images.py

При запуске отдельно от основного скрипта, будет выводиться запрос на количество закачиваемых фото дня от NASA
```commandline
Сколько фото необходимо скачать: 3
```
При необходимости будет создана директория для скачивания файлов

#### fetch_nasa_epic_images.py

При запуске отдельно от основного скрипта, будут скачаны фото из категории EPIC 
Так же, если необходимо, будет создана директория для скачивания файлов

#### fetch_spacex_images.py

При запуске отдельно от основного скрипта, будет выводиться запрос на номер конкретного запуска SpaceX
```commandline
Введите номер запуска SpaceX: 67
```
При необходимости будет создана директория для скачивания файлов

#### publish_image_to_telegram.py

При запуске основного скрипта, будут скачаны фотографии всех типов, после чего с перерывом, по умолчанию в 4 часа, 
будут публиковаться ботом в телеграм, до тех пор, пока не будут опубликованы все фото из указанной директории.
После чего список фото в директории будет переставлен в случайном порядке и опубликован снова.

### Как установить

[TODO: объясните пользователю, откуда брать ключи, куда их класть и как они выглядят]
Для корректной работы вам понадобится указать в файле ```.env```:

- API-токен сайта NASA, его можно получить после регистрации на их официальном сайте [NASA](https://api.nasa.gov) . После получения
- API-токен телеграм бота. Как создать своего бота можно узнать тут: [Настройка телеграм бота](https://way23.ru/регистрация-бота-в-telegram.html) .
после чего вам в сообщении пришлют необходимые данные. Если же этого не произошло, отправьте запрос контакту @BotFather /token и выберете из списка нужного бота
- Необходимо указать количество времени (в секундах), по истечению которого будет опубликовано новое фото

В итоге эти данные должны быть внесены в ```.env``` файл в таком виде:
```
NASA_TOKEN=API-токен сайта NASA
API_BOT_TOKEN=API-токен телеграм бота
TIME_LIMIT=14400 - длительность перерыва между постами (в секундах)
CHAT_ID=@your_chat_name - имя вашего телеграм канала
```

Python3 должен быть уже установлен. 
Затем используйте `pip` (или `pip3`, есть конфликт с Python2) для установки зависимостей:
```
pip install -r requirements.txt
```

### Цель проекта

Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).