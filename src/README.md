## Part 1. Установка OC

- cat /etc/issue

![Task1](./screens/task1.png)
    

## Part 2. Создание пользователя

- sudo useradd -g adm JessieSHA

![Task2](./screens/task2.png)

## Part 3. Настройка сети ОС

- Задаем имя машины, командой sudo hostnamectl set-hostname user-1

![Task3](./screens/task3.png)

- Выводим название машины

![Task3.4](./screens/task3.4.png)

- Задаем временную зону 

![Task3.5](./screens/task3.5.png)

- timedatectl - для проверки устанавился ли нужный временной пояс 

![Task3.6](./screens/task3.6.png)

- Выводим названия сетевых интерфейсов

![Task3.7](./screens/task3.7.png)

- lo - виртуальный сетевой интерфейс позволяющий взаимедствовать компьюеру с самим собой, имеющий ip 127.0.0.1 именно к нему обращается компьютер для работы с сетевыми хостами

- sudo dhclient -v enp0s3 - получаем ip-адрес dhcp-сервера. dhcp - протокол который автоматически выдаёт устройствами  ip адреса и тд. 

![Task3.8](./screens/task3.8.png)

- ip route  внутренний  ip

![Task3.83](./screens/task3.83.png)

- wget -qO- eth0.me - внешний ip 

![Task3.9](./screens/task3.9.png)

- sudo nano /etc/netplan/00-installer-config.yaml редактируем настройки ip, gw, dns

![Task3.9](./screens/task3.96.png)

- Пингуем хосты 1.1.1.1 и ya.ru

![Task3.98](./screens/task3.98.png)

## Part 4. Обновление ОС

![Task4](./screens/task4.png)

- Проверяем что всё установлено 

![Task4.2](./screens/task4.2.png)


##  Part 5. Использование команды sudo

- usermod -aG sudo JessieSHA

![Task5](./screens/task5.png)

- sudo - команда позволяющая выполнять другие команды с правами суперпользователя. Полезна для работы с системными файлами и службами.

##  Part 6. Установка и настройка службы времени

установка автоматической синх. времени

![Task6](./screens/task6.png)

##  Part 7. Установка и использование текстовых редакторов

- nano(ctrl + O -> Enter -> Ctrl + X)

![Task7](./screens/task7.png)

- vim (Esc или i -> :wq)

![Task7](./screens/task7.2.png)

- mcedit (F2 -> F10)

![Task7](./screens/task7.3.png)


- Без сохранения изменений и замена на «21 School 21»

- nano (Ctrl + X -> No)

![Task7](./screens/task7.4.png)

- vim (Esc -> :q!)

![Task7](./screens/task7.5.png)

- mcedit (Esc -> No)

![Task7](./screens/task7.6.png)

- Поиск по слову и замена 

- nano (Ctrl + W -> Ctrl + \ )

![Task7](./screens/task7.8.png)

- vim (:%s/school/jacquela/g)

![Task7](./screens/task7.7.png)

- mcedit (F7 для поиска, F4 поиск и замена)

![Task7](./screens/task7.9.png)


##  Part 8. Установка и базовая настройка сервиса SSHD

- sudo apt install openssh-server - SSHd установка

- sudo upate-rc.d ssh defaults - автостарт при запуске системы 

- sudo systemctl enable ssh - включение  sshd

- sudo systemctl start ssh - старт sshd

- sudo vim /etc/ssh/sshd_config - смена порта ( поиск строки "port 2")

- ps -FC sshd - ps: Утилита для отображения информации о запущенных процессах.

-F: Выводит расширенную информацию о процессах (полный формат).

-C sshd: Фильтрует процессы по имени команды

![Task8](./screens/task8.png)

##  Part 9. Установка и использование утилит top, htop

![Task9](./screens/task9.png)

# top

- Uptime - 8 минут,

- авторизипованных пользователей - 1

- средняя загрузка - 0.05, 0.03, 0.00

- общее кол-во процессов - 113

- загрузка cpu - 0.0

- загрузка пямяти - 157.8 used 

- pid процесса занимающего больше всего памяти - 1  

- pid процесса, занимающего больше всего процессорного времени - 1.

# htop 

- отсортированному по PID;

![Task9.1](./screens/task9.1.png)

- отсортированному по PERCENT_CPU;

![Task9.2](./screens/task9.2.png)

- отсортированному по PERCENT_MEM;

![Task9.3](./screens/task9.3.png)

- отсортированному по TIME;

![Task9.4](./screens/task9.4.png)

- отфильтрованному для процесса sshd;

![Task9.5](./screens/task9.5.png)

- процесс syslog

![Task9.6](./screens/task9.6.png)

- с добавленным выводом hostname, clock и uptime.

![Task9.7](./screens/task9.7.png)

##  Part 10. Использование утилиты fdisk

![Task10](./screens/task10.png)

- название жеского диска VBOX HARDDISK
- размер 12.51gb 
- сектора 26214400
- swap 1.8gb

##  Part 11. Использование утилиты df

 # df

![Task11](./screens/task11.png)

 - размер корневого раздела 10218772
 - размер занятого пространства 2650356 
 - размер свободного пространства 7027744
 - процент исп. 28%
 - byte 

# df -Th

![Task11.5](./screens/task11.5.png)

 - размер корневого раздела 9.8gb
 - размер занятого пространства 2.6gb
 - размер свободного пространства 6.8gb
 - процент исп. 28%
 - ext4

##  Part 12. Использование утилиты du

- du /home -sh
- sudo du /var -sh
- sudo du /var/log -sh

![Task12](./screens/task12.png)


![Task12.5](./screens/task12.5.png)

- sudo du /var/log/* -sh

## Part 13. Установка и использование утилиты ncdu

![Task13](./screens/task13.png)

![Task13.5](./screens/task13.5.png)

![Task13.6](./screens/task13.6.png)

## Part 14. Работа с системными журналами

- vim /var/log/auth.log

![Task14](./screens/task14.png)

- sudo systemctl restart sshd

- tail /var/log/syslog

![Task14](./screens/task14.5.png)

## Part 15. Использование планировщика заданий CRON

- sudo crontab -e
- */2 * * * * uptime

![Task15](./screens/task15.png)

- sudo tail /var/log/syslog

![Task15.5](./screens/task15.5.png)

-

![Task15.6](./screens/task15.6.png)