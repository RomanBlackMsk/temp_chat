Простой клиент-сервер на Android (интернет-мессенджер).
Это не готовое приложение, просто мысли вслух.
Папка server содержит 3 файла:
- sql_table.txt (sql комманда для создания таблицы нужной структуры)
- showBD.php (выводит содержимое таблицы БД - не обязательно, но удобно для веб контроля)
- chat.php (api для взаимодейсвия мобильного клиента с БД на сервере)
ВАЖНО
код сырой, не все исключения обработаны, не все переменные и, скорее всего, методы грамотно разведены, возможно есть повторы кода
но, это просто скелет и скелет рабочий
работает через связку http запрос -> json ответ

p.s. как настроить "сервер"
Для реализации «сервера», нам нужно зарегистрироваться на любом хостинге, который дает возможность
работы с SQL и PHP. Я использовал несколько хостингов ... банят через какето время ((
на текущий момент 10/2015 использую бесплатный сервис интернет-провайдера beget.ru.
Возможно еще живой http://l29340eb.bget.ru/showBD.php и покажет структуру таблицы.
После регистрации нужно:
1. создать SQL БД, а в ней таблицу (sql_table.txt)
2. изменить в файлах showBD.php и chat.php на свои полученные значения
  $mysql_host = "localhost"; // sql сервер, может быть локальным или внешним. например mysql5.000webhost.com
  $mysql_user = "l29340eb_chat"; // пользователь
  $mysql_password = "123456789"; // пароль
  $mysql_database = "l29340eb_chat"; // имя базы данных на сервере SQL
3. залить эти 2 файла в корень, пройти по ссылке на showBD.php - если пишет что база доступна - все ок
4. изменить путь к своему "серверу" в файлах
  ChatActivity.java
  FoneService.java
  MainActivity.java
                      // ИМЯ СЕРВЕРА (url зарегистрированного нами сайта)
	                    // например http://l29340eb.bget.ru
	                    String server_name = "http://l29340eb.bget.ru";
5. все

Если мой http://l29340eb.bget.ru/showBD.php еще жив, можно использовать готовый bin/temp_chat.apk

andreidanilevich@gmail.com
