Инструкция по запуску Лабораторной работы №1 PDO
Чтобы всё работало корректно, выполни эти 4 простых шага.

Шаг 1. Размещение файлов
Распакуй папку с проектом в директорию твоего локального веб-сервера (OpenServer).

Если у тебя старая версия OpenServer (5.x), это папка OSPanel\domains.

Если новая (6.0), это папка OSPanel\home.

<img width="904" height="649" alt="image" src="https://github.com/user-attachments/assets/f14a8bf0-ca3f-46c5-8778-876361607b71" />

Здесь не забудь создать папку surgdb.local, это обязательно, и закинь туда все файлы:

<img width="644" height="45" alt="image" src="https://github.com/user-attachments/assets/b3e452c5-2882-453b-af87-11c86b236fc2" />

<img width="1102" height="443" alt="image" src="https://github.com/user-attachments/assets/7edc2704-6887-4d7f-a161-ca1b5ed0c1ed" />

Шаг 2. Загрузка базы данных (ОБЯЗАТЕЛЬНО)
Проект не будет работать без базы данных.

Запусти OpenServer и открой phpMyAdmin.

<img width="499" height="570" alt="image" src="https://github.com/user-attachments/assets/10d6dff1-4a22-4f74-9117-c037e33a23fd" />

<img width="1917" height="491" alt="image" src="https://github.com/user-attachments/assets/b523fff5-3e41-43f5-8e0e-9236b0783e49" />

Перейди во вкладку Импорт (Import) в верхнем меню.

<img width="1919" height="835" alt="image" src="https://github.com/user-attachments/assets/5a5a09e3-5ef7-437f-aad0-57282112d417" />

Выбери файл iteh2lb1var4.sql (он лежит в папке с проектом) и нажми Import.
База данных iteh2lb1var4 и все таблицы с данными создадутся автоматически.

<img width="1494" height="548" alt="image" src="https://github.com/user-attachments/assets/0d6fcfc1-aec2-48a1-a288-c5b08e6ec26b" />

Шаг 3. Настройка подключения (db.php)
Важный момент! Настройки базы зависят от твоей версии OpenServer.
Открой файл db.php в любом редакторе. Сейчас там стоят настройки для OpenServer 6.0:

$host = 'MySQL-8.4';

$db   = 'iteh2lb1var4';

$pass = '';

Если у тебя старая версия OpenServer (или XAMPP), измени эти строки на стандартные:

$host = 'localhost';

$pass = 'root'; (или оставь пустым '', если пароля нет).

Шаг 4. Запуск
Запусти проект (или перезапусти OpenServer, чтобы он увидел новую папку). Открой браузер и перейди по локальному адресу проекта http://surgdb.local.

Также просмотри, чтобы у тебя были эти версии PHP и MySQL:

<img width="459" height="331" alt="image" src="https://github.com/user-attachments/assets/3487b779-0d0b-4ca3-98af-64e5df07e249" />

Шаг 5. Проверка приложения
Пройдись по всем запросам, тебе должны показываться все списки данных из БД (Перелік палат медсестри, Медсестри відділення, Чергування у зміну).

<img width="745" height="223" alt="image" src="https://github.com/user-attachments/assets/c6d84afe-134d-4a66-a5c0-6d0f49cf8322" />

<img width="434" height="231" alt="image" src="https://github.com/user-attachments/assets/bce65d29-7a32-4626-9d34-2c6ddbae4b89" />

<img width="430" height="192" alt="image" src="https://github.com/user-attachments/assets/464f61ae-8f17-4db8-a27a-07be3b69c6c1" />

🛠 Частые ошибки:
Списки пустые: Ты забыла импортировать файл iteh2lb1var4.sql в phpMyAdmin.

Ошибка "target machine actively refused it" (SQLSTATE 2002): Сервер не может найти базу. Проверь, правильно ли указан $host в файле db.php для твоей версии OpenServer.
