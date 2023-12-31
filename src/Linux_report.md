## Part 1. Установка ОС
 - Для установки Ubuntu Server LTC 20.04 был скачан образ с официального сайта Убунту. 
 - Далее с помощью программы для виртуализации VirtualBox была создана виртуальная машина. 

## 1.1. Вывод команды - версия ubuntu.

![part1](/src/screen/1.png)


## Part 2. Создание пользователя
 ## 2.1. Создать пользователя, отличного от пользователя, который создавался при установке. Пользователь должен быть добавлен в группу adm.

![part2](/src/screen/2.1.png)

 ## 2.2. Новый пользователь должен быть в выводе команды в cat /etc/passwd 

![part2.1](/src/screen/2.2.png)

## Part 3. Настройка сети ОС

## 3.1. Задать название машины вида user-1

С помощью команды :
```
sudo vim /etc/hostname
```
 поменял имя машины на user-1. И чтобы изменения вступили в силу перезагрузил с помощью команды sudo reboot.

![part3](/src/screen/3.1.png)

## 3.2. Установить временную зону соответствующую текущему местоположению.

![part3](/src/screen/3.2.png)

## 3.3. Вывести названия сетевых интерфейсов с помощью консольной команды.

![part3](/src/screen/3.3.png)

## 3.4 В отчете дать объяснение наличию интерфейса lo:

lo (loopback device) – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него есть dns-имя – localhost.

## 3.5.  Используя консольную команду получить ip адрес устройства, на котором вы работаете, от DHCP сервера.

![part3](/src/screen/3.4.png)

Протокол DHCP — это протокол клиента или сервера, который автоматически предоставляет узел протокола IP с его IP-адресом и другие связанные сведения о конфигурации, такие как маска подсети и шлюз по умолчанию.

## 3.6. Определить и вывести на экран внешний ip-адрес шлюза (ip) и внутренний IP-адрес шлюза, он же ip-адрес по умолчанию (gw).

![part3](/src/screen/3.5.png)

## 3.7. Задать статичные (заданные вручную, а не полученные от DHCP сервера) настройки ip, gw, dns (использовать публичный DNS серверы, например 1.1.1.1 или 8.8.8.8).

![part3](/src/screen/3.6.png)

## 3.8. Перезагрузить виртуальную машину. Убедиться, что статичные сетевые настройки (ip, gw, dns) соответствуют заданным в предыдущем пункте.

Данные ip после перезагрузки.

![part3](/src/screen/3.7.png)

## 3.9. После перезапуска системы, успешно пропинговать удаленные хосты 1.1.1.1 и ya.ru и вставить в отчет скрин с выводом команды. В выводе команды должна быть фраза "0% packet loss". 

![part3](/src/screen/3.7.1.png)

## Part 4. Обновление ОС
Для обновления системы использовал команды:
```
sudo apt-get update && sudo apt-get upgrade
```

![part4](/src/screen/4.png)

## Part 5. Использование команды SUDO

## 5.1. Разрешить пользователю, созданному в Part 2, выполнять команду sudo 
 Чтобы выдать права суперпользователя нами созданному пользователю, необходимо ввести команду: 
 ```
 $ sudo usermod -a -G sudo newuser
 ```

 ## 5.2. В отчёте объяснить истинное назначение команды sudo (про то, что это слово - "волшебное", писать не стоит).

Команда sudo позволяет выполнять все команды, которые не доступны обычному пользователю. Эти команды выполняются от имени суперпользователя - root. Так же позволяет давать определенные права другим пользователям или наоборот ограничить их. В основном она нужна для системного администрирования unix систем.

 ## 5.3. Поменять hostname ОС от имени пользователя, созданного в пункте Part 2 (используя sudo).

![part5](/src/screen/5.png)

![part5](/src/screen/5.2.png)

## Part 6. Установка и настройка службы времени

## 6.1 Вывести время, часового пояса, в котором вы сейчас находитесь.
 
![part6](/src/screen/6.1.png)

 ## 6.2. Вывод следующей команды должен содержать NTPSynchronized=yes: timedatectl show
![part6](/src/screen/6.png)

## Part 7. Установка и использование текстовых редакторов

 ## 7.1. Установить текстовые редакторы VIM (+ любые 2 по желанию NANO, MCEDIT, JOE и т.д.)
 Чтобы установить данные программы, мы воспользуемся пакетным менеджером apt, с использованием прав суперпользователя, далее будут скрины с подтверждением того, что программа установлена. 
 Синтаксис команды:
 ```
 $ sudo apt install название_программы 
 ```

 ## 7.2. Используя каждый из трех выбранных редакторов, создайте файл test_X.txt, где X -- название редактора, в котором создан файл. Напишите в нём свой никнейм, закройте файл с сохранением изменений. В отчёт вставьте скриншоты. В отчёте укажите, что сделали для выхода с сохранением изменений: 

## VIM - esc -> : -> wq
![part7](/src/screen/7vim.png)

## NANO - ctrl+o -> ctrl+x
![part7](/src/screen/7nano.png)

## JOE - ctrl+k -> x
![part7](/src/screen/7joe.png)


 ## 7.3. Используя каждый из трех выбранных редакторов, откройте файл на редактирование, отредактируйте файл, заменив никнейм на строку "21 School 21", закройте файл без сохранения изменений. В отчёт вставьте скриншоты из каждого редактора с содержимым файла после редактирования. В отчёте укажите, что сделали для выхода без сохранения изменений. 

## VIM - esc -> : -> !q
![part7](/src/screen/7.2vim.png)


## NANO - ctrl+x -> N
![part7](/src/screen/7.2nano.png)


## JOE - ctrl+c -> y
![part7](/src/screen/7.2joe.png)



 ## 7.4. Используя каждый из трех выбранных редакторов, отредактируйте файл ещё раз (по аналогии с предыдущим пунктом), а затем освойте функции поиска по содержимому файла (слово) и замены слова на любое другое. В отчёт вставьте скриншоты: 

## 1.1 VIM

Поиск слова:
![part7](/src/screen/7.3vim.png)

Замена слова:
![part7](/src/screen/7.4vim.png)

## 1.2. NANO

Поиск слова:
![part7](/src/screen/7.3nano.png)

Замена слова:
![part7](/src/screen/7.4nano.png)

## 1.3. JOE

Поиск слова:
![part7](/src/screen/7.3joe.png)

Замена слова:
![part7](/src/screen/7.4joe.png)

## Part 8.  Установка и базовая настройка сервиса SSHD

 ## Установить службу SSHd 
Для начала Я обновил репозиторий sudo apt update. После установил ssh sudo apt-get install ssh и OpenSSH sudo apt install openssh-server. 

 ## Добавить автостарт службы при загрузке системы.
Добавил пакет ssh- сервера в автозагрузку sudo systemctl enable sshd. 

 ## Перенастроить службу SSHd на порт 2022.
Далее заменил порт на 2022 vim /etc/ssh/sshd_config.

 ## Используя команду ps, показать наличие процесса sshd. Для этого к команде нужно подобрать ключи.

С помощью команды: ps -A | grep 'sshd' вывел процесс sshd. Команда ps выводит процессы на сервере в виде таблице, в моем случае Я применил флаг -A для поиска вхождения слова и grep для поиска слова 'sshd'.

## В отчёте объяснить значение команды и каждого ключа в ней.

Команда ps выводит список текущих процессов на вашем сервере в виде таблицы, с которой можно удобно работать: сортировать, изменять количество колонок и прочие. У утилиты ps множество настроек, с помощью которых можно тонко настраивать вывод команды
 - `ps` (показывает запущенные процессы, выполняемые пользователем в окне терминала);
 - `ps -e` или `ps -A` (Для просмотра всех запущенных процессов);
 - `ps -d` (Чтобы показать все процессы, кроме лидеров сессий);
 - `ps -d -N` (Вы можете инвертировать вывод с помощью переключателя `-N`. Например, если я хочу отобразить только лидеров сессий)
 - `ps T` (показывает только процессы, связанные с этим терминалом);
 - `ps r` (посмотреть все запущенные (`running`) процессы);
 - `ps -p 'pid'` (если вы знаете PID процесса, вы можете просто использовать следующую команду, чтобы вывести процесс с этим `'pid'`);
 - `ps -p 'pid1' 'pid2'`
 - `ps U 'userlist'` (найти все процессы, выполняемые определенным пользователем);
 - `ps -ef` (получить полный список).


 ## Перезапустить систему: 

Перезагрузил систему для изменения порта sshd. Далее ввел команду: netstat -tan. 
- Netstat - это инструмент для анализа данных о сети в unix подобных системах. Флаг -t — указывает, что нужно показать все TCP-соединения сетевой подсистемы; -a — показывает только активные соединения; -n — вместо названий служб показывает номера портов. 0.0.0.0 это означает - "любой адрес", т.е в соединении могут использоваться все IP-адреса существующие на данном компьютере. 

![part8](/src/screen/8.png)

## Значение каждого столбца вывода, значение 0.0.0.0.

![part8](/src/screen/8.png)

Первый столбец вывода - Имя - название протокола.

Второй - получено пакетов.

Третий - отправлено пакетов.

Четвертый - локальный IP-адрес участвующий в соединении или 
связанный со службой, ожидающей входящие соединения (слушающей порт).

Пятый - нешний IP-адрес, участвующий в создании соединения.

Шестой - состояние соединения.

## Part 9. Установка и использование утилит top, htop

## 9.1. По выводу команды top определить и написать в отчёте:

uptime - 1 hour 13 minutes

количество авторизованных пользователей - home

общую загрузку системы - 0.00 0.00 0.00

общее количество процессов - 26, 29 thr; 1 running

загрузку cpu - 1.0 %

загрузку памяти - 131m/1.93gb

pid процесса занимающего больше всего памяти - 761

pid процесса,
занимающего больше всего процессорного времени -  1621

## 9.2. Отсортированный вывод команды htop:

- Сортировка по PID:

![part9](/src/screen/9.1.png)

- Сортировка по PERCENT_MEM:

![part9](/src/screen/9.2.png)

- Сортировать по PERCENT_CPU:

![part9](/src/screen/9.3.png)

- Сортировать по TIME:

![part9](/src/screen/9.4.png)

- Фильтр 'sshd':

![part9](/src/screen/9.5.png)

- Поиск 'syslog':

![part9](/src/screen/9.6.png)

- Расширенный дисплей:

hostname, clock и uptime

![part9](/src/screen/9.png)



## Part 10. Использование утилиты fdisk

## 10.1. В отчёте написать название жесткого диска, его размер и количество секторов, а также размер swap.

 -Disk ubuntu--vg--ubuntu--lv: 14.102 GiB, 16101933056 bytes, 31449088 sectors/
- swap size - 2097148

![part10](/src/screen/10.png)

## Part 11. Использование утилиты df

![part11](/src/screen/11.png)

## 11.1. Запустить команду df. 

- В отчёте написать для корневого раздела (/):
размер раздела - 15371208
размер занятого пространства - 4813724
размер свободного пространства - 9754876
процент использования - 34%



- Определить и написать в отчёт единицу измерения в выводе.

 Вывод - единица измерения определяется в байтах.

## 11.2. Запустить команду df -Th.

- В отчёте написать для корневого раздела (/):

размер раздела - 15 gb
размер занятого пространства - 4.6 gb
размер свободного пространства - 9.4 gb
процент использования - 34%

- Определить и написать в отчёт тип файловой системы для раздела.

Тип файловой системы - ext4.

## Part 12. Использование утилиты du

- Запустить команду du.

![part12](/src/screen/12.png)

- Вывести размер папок /home, /var, /var/log (в байтах, в человекочитаемом виде)

![part12](/src/screen/12.1.png)

- Вывести размер всего содержимого в /var/log (не общее, а каждого вложенного элемента, используя *)

![part12](/src/screen/12.2.png)


## Part 13. Установка и использование утилиты ncdu

- Вывести размер папок /home, /var, /var/log.

![part13](/src/screen/13.png)

![part13](/src/screen/13.1.png)

![part13](/src/screen/13.2.png)

## Part 14. Работа с системными журналами

- Открыть для просмотра :

1. /var/log/dmesg

![part14](/src/screen/14.1.png)

2. /var/log/syslog

![part14](/src/screen/14.2.png)

3. /var/log/auth.log

![part14](/src/screen/14.3.png)

- Время последней успешной авторизации, имя и метод входа в систему:

wtmp begins Wed Jul 19 20:09:37 2023

- Рестарт sshd

![part14](/src/screen/14.png)

## Part 15. Использование планировщика заданий CRON

- Строчки с выполнением задания в планировщике cron

![part15](/src/screen/15.1.png)

- Список текущих задач

![part15](/src/screen/15.2.png)

- Планировщик после удаления всех задач

![part15](/src/screen/15.3.png)
