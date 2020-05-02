# Seeker-RUS-
Русификация для скрипта seeker


<p align="center"><img src="https://psv4.userapi.com/c856236/u370917353/docs/d2/d29704554ab9/Fioletovaya_i_Rozovaya_Sovremennaya_Rabota_iz_Doma_Prostaya_Prezentatsia.png?extra=Ip4gQ7AT03jHt4lrLPpF0YmLSnvUBF9ecB1LWMnmcg_vkFSPLeam3rcLB29yJCoyqo0DUpdBgn0q5nYfy7itKfQrtwsIJby6-iJFlLA6LPhj3Yj_tsOzIXhZA3af5Pl8I1wQr36EGAzM7xbrHQKZg-pY"></p>

<p align="center">
<img src="https://img.shields.io/badge/Python-3-brightgreen.svg?style=plastic">
<img src="https://img.shields.io/badge/Docker-✔-blue.svg?style=plastic">
</p>

<p align="center">
  <a href="https://twitter.com/thewhiteh4t"><b>Twitter</b></a>
  <span> - </span>
  <a href="https://t.me/thewhiteh4t"><b>Telegram</b></a>
  <span> - </span>
  <a href="https://thewhiteh4t.github.io"><b>thewhiteh4t's Blog</b></a>
</p>

<p align="center">
  <br>
  <b>Доступно в</b>
  <br>
  <img src="https://i.imgur.com/1wJVDV5.png">
</p>

Концепция Seeker проста, подобно тому, как мы размещаем фишинговые страницы для получения учетных данных, почему бы не разместить поддельную страницу, которая запрашивает ваше местоположение, как многие популярные веб-сайты, основанные на местоположении. Узнайте больше на <a href="https://thewhiteh4t.github.io"> блоге thewhiteh4t </a>. Seeker размещает поддельный веб-сайт на ** встроенном PHP-сервере ** и использует ** Serveo ** для создания ссылка, которую мы передадим на цель, веб-сайт запрашивает разрешение на местоположение и, если цель позволяет, мы можем получить:

* Долгота
* Широта
* Точность
* Высота - не всегда доступна
* Направление - доступно только если пользователь движется
* Скорость - Доступно только если пользователь движется

Наряду с информацией о местоположении мы также получаем ** информацию об устройстве ** без каких-либо разрешений:

* Операционная система
* Платформа
* Количество ядер процессора
* Объем оперативной памяти - приблизительные результаты
* Разрешение экрана
* Информация о GPU
* Имя и версия браузера
* Публичный IP-адрес
* Разведка IP-адреса

** Этот инструмент является проверкой концепции и предназначен только для образовательных целей. Seeker показывает, какие данные может собирать вредоносный веб-сайт о вас и ваших устройствах, и почему вы не должны нажимать на случайные ссылки и разрешать критические разрешения, такие как местоположение и т. Д. **

## Чем это отличается от IP-геолокации?

* Другие инструменты и сервисы предлагают IP-геолокацию, которая НЕ является точной и не дает определения местоположения цели, а является приблизительным местоположением провайдера.

* Seeker использует HTML API и получает разрешение на местоположение, а затем захватывает долготу и широту с помощью GPS-оборудования, которое присутствует в устройстве, поэтому Seeker лучше всего работает со смартфонами, если отсутствует GPS-оборудование, например, на ноутбуке, Seeker откатывается на IP Геолокация или он будет искать кэшированные координаты.

* Как правило, если пользователь принимает разрешение на определение местоположения, точность полученной информации составляет ** с точностью приблизительно до 30 метров **, точность зависит от устройства.

** Примечание **: На iPhone по какой-то причине точность определения местоположения составляет приблизительно 65 метров.

## Шаблоны

Вы можете выбрать шаблон, который будет использоваться на сайте:

* NearYou
* Google Drive (Suggested by @Akaal_no_one)
* WhatsApp (Suggested by @Dazmed707)

## Тестировалось на  :

* Kali Linux 2019.2
* Deepin Linux
* BlackArch Linux
* Ubuntu 19.04
* Kali Nethunter
* Termux
* Parrot OS

## Installation

### Kali Linux / Ubuntu / Parrot OS

```bash
Тут установка немного иная, скачайте архив из релиза ниже, а дальше по командам
https://github.com/WebFSBuilder/Seeker-RUS-/releases/download/1.2.5/seeker.RUS.zip
unzip seeker[RUS].zip
cd seeker/
chmod 777 install.sh
./install.sh
```

### BlackArch Linux

```bash
pacman -S seeker
```

### Docker

```bash
docker pull thewhiteh4t/seeker
```

### Termux

```bash
Тут установка немного иная, скачайте архив из релиза ниже, а дальше по командам
https://github.com/WebFSBuilder/Seeker-RUS-/releases/download/1.2.5/seeker.RUS.zip
unzip seeker[RUS].zip
cd seeker/
chmod 777 install.sh
./termux_install.sh
```

## Использование

```bash
python3 seeker.py -h

usage: seeker.py [-h] [-s SUBDOMAIN]

optional arguments:
   -h, --help             показать это справочное сообщение и выйти
   -s SUBDOMAIN,        --subdomain Поддомен Укажите поддомен для URL-адреса Serveo (необязательно)
   -k KML,              --kml KML Предоставить имя файла KML (необязательно)
   -t TUNNEL,           --tunnel TUNNEL Указать туннельный режим [руководство]

# Пример

# SERVEO
########
python3 seeker.py

# NGROK ETC.
############

# В First Terminal Start ищущий в ручном режиме, как это
python3 seeker.py -t руководство

# Во втором терминале запустите Ngrok или любой другой туннельный сервис на порту 8080
./ngrok http 8080

# ----------------------------------- #

# Субдомен
###########
python3 seeker.py --subdomain google
python3 seeker.py - руководство по туннелю - subdomain zomato

# ----------------------------------- #

# Subdomain
########### 
python3 seeker.py --subdomain google
python3 seeker.py --tunnel manual --subdomain zomato

#-----------------------------------#

# Docker Usage
##############

# SERVEO
########
docker run -t --rm thewhiteh4t/seeker

# NGROK
#######

# Step 1
docker network create ngroknet

# Step 2
docker run --rm -t --net ngroknet --name seeker thewhiteh4t/seeker python3 seeker.py -t manual

# Step 3
docker run --rm -t --net ngroknet --name ngrok wernight/ngrok ngrok http seeker:8080
```

## Известные проблемы

* Такие службы, как Serveo и Ngrok, запрещены в некоторых странах, таких как Россия и т. Д., Поэтому, если они запрещены в вашей стране, вы можете не получить URL-адрес, если нет, то сначала ПРОЧИТАЙТЕ ЗАКРЫТЫЕ ПРОБЛЕМЫ, если вашей проблемы нет в списке, создайте новую проблему ,

## Демо

<p align="center">
	<a href="https://www.youtube.com/watch?v=FEyAPjkJFrk"><img src="https://i.imgur.com/48yrleF.png"></a>
</p>
