# Базовый MVC-компонент Битрикс

Базовый компонент, предназначенный для простой реализации MVC. Основные функции:
* Обработка ЧПУ "из коробки" 
(при условии, что параметры компонента правильно настроены при подключении)
* Обработка входящих запросов в MVC-стиле с применением кеширования по-умолчанию
* Обработка и кеширование AJAX в коде компонента
* Обработка ошибок, перехват исключений
* Возможность наследования
* Легковесность, для начала работы достаточно знать API битрикс.
* Мастер создания компонента позволяет быстро и просто создать рабочий прототип 
компонента для последующей доработки. 

Компонент в первую очередь ориентирован на работу с ЧПУ, хотя его можно использовать 
и не для ЧПУ-функционала.

Компонент напрямую не используется. 
От него необходимо наследоваться, [создавая свой класс компонента](https://dev.1c-bitrix.ru/learning/course/?COURSE_ID=43&LESSON_ID=2028).

## Установка

``composer require digitalwand/mvc.base``, или просто скопируйте модуль вручную. Учтановите как обычный модуль Битрикс из маркетплейса. 

## Использование

После установки модуля в разделе "Настройки"->"Настройки продукта"->"Список мастеров" появится новый мастер
"digitalwand:mvc - Мастер создания MVC-компонента". Запустите мастер и пройдите все шаги до конца: 
* На персом шаге будет предложено ввести основные данные о компоненте, которые повлияют на название власса 
и название компонента в пользовательском интерфейса
* На втором шаге предлагается заполнить данные ЧПУ компонента. По этой информации будут автоматически сгенерирован 
файл .parameters.php, а так же функции и переменные класса-компонента. Поле "Переменные стрницы (VARIABLES)" 
заполнять не обязательно, список переменных автоматически определится по данным поля "Шаблон ЧПУ страницы".  
* После завершения мастера ищем в /local/components/ новый компонент. Модифицируем код класса под свои нужды, или оставляем как есть. 
* Создаём новую страницу в публичной части сайта. Добавляем на страницу компонент. В настройках компонента включаем речим ЧПУ, сохраняем
* Пробуем перейти по урлам, указанным в настройках компонента. видим, что всё работает :-)


## Основные понятия

Небольшая "таблица соответствий" между сущностями битрикса, элементами данного класса, и терминами MVC.
* Контроллер - класс компонента. Компонент в целом стоит считать контроллером. 
* Action (действие) - функция, которую выполняет контроллер, при переходе пользователя по определенному уру.
* Роутинг - определение какое действие какого контроллера должно быть запущено при переходе по урлу. 

## Документация и примеры

* [Простой пример использования](doc/ru/basic-usage.md)
* ["Продвинутое" использование](doc/ru/advanced-usage.md)
* [Создание REST-сервера](doc/ru/rest-mode.md)
