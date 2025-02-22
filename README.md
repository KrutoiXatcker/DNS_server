# DNS Server Project

Этот проект представляет собой простой DNS-сервер, который обрабатывает DNS-запросы и возвращает соответствующие IP-адреса. Сервер также поддерживает функциональность для передачи файлов через DNS-запросы.

## Содержание

- [Требования](#требования)
- [Сборка проекта](#сборка-проекта)
- [Использование](#использование)
- [Структура проекта](#структура-проекта)
- [Классы](#классы)
  - [DNS_Server](#dns_server)
- [Пример работы](#пример-работы)

## Требования

Для сборки и запуска проекта необходимы следующие компоненты:

- Компилятор C++ (например, `g++`)
- Утилита `make`
- Операционная система, поддерживающая сокеты (например, Linux)

## Сборка проекта

1. Клонируйте репозиторий:

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   
2. Соберите проект с помощью make:
	bash
		make

Это создаст исполняемый файл dns_server.

##Использование
После сборки проекта вы можете запустить DNS-сервер:

	bash
		./dns_server
		
##Структура проекта
 - DNS_Server.h / DNS_Server.cpp: Класс для работы с DNS-запросами и ответами.

 - main.cpp: Основной файл программы, который запускает DNS-сервер.

 - hostname.txt: Файл с доменными именами и их IP-адресами.

 - db: Файл с зашифрованными данными для передачи файлов через DNS-запросы.

 - Makefile: Файл для сборки проекта.

##Классы
DNS_Server
 - Класс DNS_Server предоставляет функциональность для обработки DNS-запросов и передачи файлов через DNS. Основные методы:

 - start(): Запускает сервер и начинает обработку запросов.

 - handle_dns_request(): Обрабатывает входящий DNS-запрос и формирует ответ.

 - extract_domain_name(): Извлекает доменное имя из DNS-запроса.

 - build_dns_response(): Формирует DNS-ответ на основе запроса и IP-адреса.

 - bayt_cripted(): Загружает зашифрованные данные для передачи файлов.
 
 
 ##Пример работы
 
Отправьте DNS-запрос на сервер, например, с помощью утилиты dig:
bash:
	dig @127.0.0.1 example.com

Сервер обработает запрос и вернет соответствующий IP-адрес, если домен найден в базе данных.