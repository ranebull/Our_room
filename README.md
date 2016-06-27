# Основы работы с Kali Linux
### План занятия
[Основная терминология](#Основная-терминология)   
[Основы работы в среде Kali Linux](#Основы-работы-с-kali-linux-1)  
[Методология pentest](#Методология-pentest)  
[Инструменты для сбора информации](#Конфиденциальность)  
[Идентификация целевых машин](#Идентификация-целевых-машин)  
### Основная терминология
**Penetration testing = pentest** = тестирование на проникновение  
Целевая система =жертва = цель = **Metasploitable2**  
**Attack system** = атакующая система = **Kali Linux**  
**vs = versus** = против/в сравнении  
### Коротко о Kali Linux
* Основана на Debian
* В её составе более 300 инструментов для проведения тестирования на проникновение
* Поддерживает множество Wi-Fi адаптеров
* Ядро имеет патчи для packet injection
* Есть поддержка ARM

### Основы работы с Kali Linux
Работа с файлами и директориями  
`ls, pwd, cd, mkdir, cp, rm`  
Работа с пользователями
```
adduser alex
adduser alex sudo 
su alex
```
### Metasploitable 2
* Специально собранный дистрибутив-жертва
* Включает в себя множество уязвимостей, бэкдоров, слабых паролей, etc.
* При использовании должен быть недоступен извне 

### Задание на дом
* Скачать и установить Metasploitable 2
* Ознакомиться с имеющейся обстановкой
* Попробовать использовать nmap для поиска открытых портов
* Более подробный разбор на следующем занятии

### Методология pentest
* Черный ящик **vs** белый ящик
* Поиск уязвимостей **vs** pentest
* [Open Source Security Testing Methodology](http://www.isecom.org/mirror/OSSTMM.3.pdf)
* [Information Systems Security Assessment Framework](http://cuchillac.net/archivos/pre_seguridad_pymes/2_hakeo_etico/lects/metodologia_oissg.pdf)
* [Open Web Application Security Consortium Threat Classification](http://projects.webappsec.org/f/WASC-TC-v2_0.pdf)
* [Penetration Testing Execution Standard](http://www.pentest-standard.org/index.php/Main_Page)

### Этапы тестирования на проникновение
* Обзор целей
* Сбор информации
* Определение целей
* Составление списка целей
* Поиск уязвимостей
* Социальная инженерия
* Эксплуатация целей
* Повышение привилегий
* Удержание доступа
* Составление отчета

### Обзор целей
* Что нужно тестировать?
* Как нужно тестировать?
* Какие условия нужно соблюдать во время тестирования?
* Какие ограничения по времени тестирования?
* Сколько времени понадобиться для завершения тестирования?
* Какие цели будут достигнуты?

### Сбор информации
Включает инструменты для сбора информации о DNS, Intrusion Detection System/Intrusion Prevention System (IDS/IPS),  
сетях, операционных системах, маршрутизации, Secure Sockets Layer (SSL), Server Message Block (SMB), Virtual Private Network (VPN), Voice over IP (VoIP), Simple Network Management Protocol и e-mail адресах.

### Где собирать информацию?
* Форумы
* Доски объявлений
* Новостные группы
* Статьи
* Блоги
* Социальные сети
* Веб-сайты

### Данные о регистрации
* Whois - протокол поиска данных о регистрации доменных имен, IP-адресов, автономных систем
* Работает согласно RFC 3912
* По умолчанию в Kali Linux уже установлен, вызывается командой whois
 
### IP-адрес 
* После получения информации о регистрации домена, следующий этап-получения IP-адреса.
* Для этого в **Kali Linux** есть команда `host` или `dig`
* По результатам будет видно по каким IPv4 и IPv6 доступен сервер
* `dig ssga.ru any`
* `dig @ns.ssga.ru ssga.ru axfr`
* `Dnsenum`

### Задание на дом
* Установить виртуальную машину (VmWare Player/VirtualBox)
* Скачать и установить **Kali Linux**
* С помощью Maltego найти информацию о каком-нибудь сайте или человеке

### Конфиденциальность
* **Theharvester** - зачем искать самому, если есть поисковые системы Google, Linkedin, etc
* **Metagoofil** - получение файлов, доступных на сайте

### Определение целей
Определить:
* живые компьютеры в сети;
* операционные системы этих компьютеров;
* определить роль каждого устройства в сети;  

Эти данные можно получить с помощью активных или пассивных технологий поиска

### Идентификация целевых машин
* `ping`, `ping6` (использует ICMP)
*  `arping` (использует ARP)
*  `nping` (способен работать по TCP, UDP, ICMP и ARP)
*  `p0f` (определяет операционную систему)
*  `nmap` (сканер сетей)

### Задание на дом
* Настроить сетевое подключение виртуальных машин Kali Linux и Metasploitable 2, так чтобы они находились в одной локальной сети
* С помощью сканера (например, nmap) из Kali Linux получить IP-адрес жертвы и список открытых портов

### Open system interconnection basic reference model (OSI)
![OSI model](https://ehhe2q.dm2304.livefilestore.com/y3pxKlUKsRhUALwxZPVh6DIB3UIZrxbVdS1zQfyvq8hGfQUvEhrM-PsvBLfKF2JRxBQgkkXkP7juYlKCwA2LDnxg8p5x1vGYxgndHdBl-gQdq1dAOC36lAQJ8N4hajAXRQPrbzSXXHpEmcAyU2Ghqt6zavjk1rA-CC6GfFBUY0RdHc/OSI%20model.jpg?psid=1)


