# Инструкция по развёртыванию проекта #

## Для запуска проекта необходимо: ##
- PhpStorm (версия PHP 8.1.9)
- OpenServer
- Composer

## OpenServer ## 
#### Настройки для OpenServer: ####
- HTTP: Apache_2.4-PHP_8.0-8.1
- PHP: PHP_8.1
- MySQL: MySQL-5.7-Win10

Необходимо создать базу данных с именем **eshop**. Затем создать пользователя (имя и пароль) и предоставить ему все привилегии для этой базы данных.

## PhpStorm ##
Необходимо установить версию языка PHP 8.1 в настройках и версию 8.1.9 у интерпретатора.
В случае проблем с версией PHP при запуске проекта, необходимо изменить **path** переменную, указав в ней путь до файла **php.exe** версии 8.1 в **OpenSever**.
В настройках, во вкладке **directories** выбрать директорию **public** и включить у неё свойство **Resource Root**
Затем нужно подключить базу данных **eshop** к проекту, указав пользователя, которому предоставили все привилегии при создании базы.

В папке **config** создать файл **config.local.php**, в котором будет код:
```
<?php

return [
	'DB_HOST' => '127.0.0.1',
	'DB_USER' => '', //Сюда вписать имя пользователя
	'DB_PASSWORD' => '', //Сюда вписать пароль пользователя
	'DB_NAME' => 'eshop',
];
```
Затем зайти в файл **composer.json** и нажать **install**. После этого произойдёт установка **composer** и появится необходимая папка **vendor**.
Или же произвести установку **composer** через терминал.

Для запуска проекта необходимо открыть терминал и написать следующую команду:
```
php -S localhost:8000 -t public
```
Перейти по появившейся ссылке.