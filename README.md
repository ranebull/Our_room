# Основы работы с Kali Linux
### План занятия
[Основная терминология](#Основная-терминология)   
[Основы работы в среде Kali Linux](#Основы-работы-с-kali-linux-1)  
[Методология pentest](#Методология-pentest)  
[Инструменты для сбора информации](#Конфиденциальность)  
[Идентификация целевых машин](#Идентификация-целевых-машин)  
[Open system interconnection basic reference model (OSI)](#open-system-interconnection-basic-reference-model-osi)  
[Transmission Control Protocol/Internet Protocol (TCP/IP)](#transmission-control-protocolinternet-protocol-tcpip)  
[Составление списка целей](#Составление-списка-целей)
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
* определить роль каждого устройства в сети.

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

### Transmission Control Protocol/Internet Protocol (TCP/IP)
![TCP/IP model](https://ehhe2q.dm2304.livefilestore.com/y3pUmYXsWBZRL2QVEWXRtGJ09fAskAF-XvDC3F5NrZcskho6W8HVYQBXuDb7dRiZ-AH1hA8dgyx4n20kFIvKypdRkcrCRhP1sJhOw_Obd3McXFeORtMxjLId9E5CTBOFWKQxLRYkw3P9OWKqrEUTTS3yAcNvmvRmCpj3-WCG3QVSE0/TCPIP.jpg?psid=1)

### Путь кадра
> Состояние покоя сети - утопия.  
![Network Status](https://habrastorage.org/getpro/habr/post_images/17e/31e/70f/17e31e70f22d7d5b725dea62008da6b9.jpg)

> Вы пытаетесь пропинговать, например, адрес соседнего компьютера командой ping 192.168.1.118. Данные этого приложения показаны фиолетовым параллелепипедом.
![Ping1](https://habrastorage.org/getpro/habr/post_images/4a3/dca/b98/4a3dcab98d4c67322ef5b631b5a87533.jpg)

> За это отвечает протокол ICMP. В него инкапсулируется информация от приложения — это означает, что к данным 5-го уровня добавляется заголовок со служебной информацией 4-го уровня
![ICMP](https://habrastorage.org/getpro/habr/post_images/f7b/dff/454/f7bdff454e14f2a19e2af08974f33bbf.jpg)

> Его данные упаковываются (инкапсулируются) в IP-пакеты, где в заголовке указан IP-адрес получателя (192.168.1.118) и IP-адрес отправителя — логические адреса.
![IP-packet](https://habrastorage.org/getpro/habr/post_images/28e/b99/244/28eb99244ffcb32f091eec8cca6b0933.jpg)

> А затем всё это инкапсулируется в Ethernet-кадры с MAC-адресами отправителя и получателя — физическими адресами.
![Ethernet frame](https://habrastorage.org/getpro/habr/post_images/a01/6cc/afd/a016ccafd998fe772fa06d324783047b.jpg)

> В последнюю очередь сетевая карта вашего компьютера дробит фрейм на биты и отправляет их в кабель.
![Bits](https://habrastorage.org/getpro/habr/post_images/83d/c2f/514/83dc2f51419b5eeb7ee589290912b9ba.jpg)
![Bits transfer](https://habrastorage.org/getpro/habr/post_images/5d9/30d/02d/5d930d02d3f066c4ee6426b17ff0cc51.jpg)

> Коммутатор из поступивших битов собирает первоначальный кадр
![Build Frame](https://habrastorage.org/getpro/habr/post_images/8c5/984/c6e/8c5984c6ecf47caa9d18c30ef7eb6c4a.jpg)

> Естественно, кадр опять передаётся в виде битов — это закон электроники, и вы должны просто всегда иметь это в виду.
![Bits2](https://habrastorage.org/getpro/habr/post_images/5d9/30d/02d/5d930d02d3f066c4ee6426b17ff0cc51.jpg)
![Bits3](https://habrastorage.org/getpro/habr/post_images/9fd/e22/ea7/9fde22ea7b8b225d4bf4ca580f1e1f01.jpg)

> Конечный хост, получив поток битов, собирает из них кадр, ещё только предполагая, что он предназначается ему. 
![Destination](https://habrastorage.org/getpro/habr/post_images/f20/da7/f25/f20da7f25024998e075cddec43e2ed18.jpg)

> Далее он сравнивает MAC-адрес получателя со своим и, если они совпадают, то заголовок второго уровня отбрасывается. IP-данные передаются на обработку вышестоящему протоколу. Если адреса не совпадают, то кадр отбрасывается вместе со всем содержимым.
![MAC compare](https://habrastorage.org/getpro/habr/post_images/fcf/ef6/7d3/fcfef67d3d72a93558d4e716492f2dec.jpg)

> Далее сравниваются IP-адрес получателя и этого устройства. Если совпадают, то заголовок сетевого уровня отбрасывается, и данные передаются транспортному уровню (ICMP)
![IP-address compare](https://habrastorage.org/getpro/habr/post_images/fe0/b26/f75/fe0b26f757776925aad6ef5cd6bfac28.jpg)
![IP2](https://habrastorage.org/getpro/habr/post_images/f1c/a8b/6fc/f1ca8b6fc3171f3562faf394f42c504e.jpg)
![IP3](https://habrastorage.org/getpro/habr/post_images/6cb/579/e19/6cb579e190b46eff609f4983f07e843d.jpg)
> Конечный хост обработал ICMP-запрос (echo-request) и готов послать ICMP-ответ (echo-reply) вашему компьютеру с адресом 192.168.1.131 и далее пункты 1-3 повторяются уже для нового кадра

### Составление списка целей
* Этот этап объединяет всё, что было получено на предыдущих
* Сканируются порты на целевых машинах
* Определяются запущенные службы
* Определяются системы обнаружения вторжений
* В Kali Linux для этого можно использовать автоматизированные инструменты

# Поиск и эксплуатация уязвимостей
