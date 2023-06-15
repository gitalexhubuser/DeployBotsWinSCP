# DeployBotsWinSCP
![](https://i.imgur.com/6TIoe54.jpeg)

## Описание

Инфа про то, как задеплоить бота на питоне на сервер LXD SSH VPS Server

---

## Использование
`cd /BOT228; source tik-tok/bin/activate; nohup python3 main.py &`
> Chat gpt помогла!

---

## Todo
- [ ] как читать логи
- [ ] deamon ubuntu
- [ ] screen https://youtu.be/x-VB3b4pKcU
- [ ] docker
- [ ] как переключиться после закрытия консоли на логи бота
- [ ] крутые ссылки на разные VPS в PuTTY

---

## Python

### Узнать версию питона
`python3 --version`
> Python 3.10.6

### Версия установщика пакетов
`pip3 -v`
> pip 23.0 from /usr/local/lib/python3.10/dist-packages/pip (python 3.10)

### Создать виртуальное окружение
`python3 -m venv tik-tok`

---

## Pytty

`.\tik-tok\Scripts\activate`
> С Пк

`source tik-tok/bin/activate` <!-- Урок https://youtu.be/x-VB3b4pKcU?t=638 -->
> На хостинге по другому

`pip install -r requirements.txt`
> Устанавливаем зависимости (желательно в venv)

`python3 main.py`
> Запуск скрипта из терминала
> С Пк `python main.py`
> На хостинге `python3 main.py`

---

## nohup
`nohup` -- утилита ставить процесс питона на фон

`&` -- команду на фон кинуть, чтоб терминалом дальше пользоваться

`nohup python3 main.py`

<details>
<summary>Подробней...</summary>
Команда nohup python3 main.py запускает процесс python3 main.py в фоновом режиме и перенаправляет вывод в файл nohup.out. В этом случае, процесс python3 main.py будет выполняться в том же терминале, в котором была запущена команда nohup, и вы НЕ сможете использовать этот терминал для других задач, пока процесс не завершится.
</details>

`nohup python3 main.py &`  -- спс https://youtu.be/ibwjI6mKwLM
<details>
<summary>Подробней...</summary>
Ключевое слово nohup означает "no hangup" (нет отключения) и позволяет запустить команду в фоновом режиме, не прерывая ее выполнение при закрытии терминала или отключении от удаленного сервера.
</br>
</br>
Символ амперсанда & используется для запуска команды в фоновом режиме, что означает, что команда будет выполняться в фоновом режиме и не будет блокировать терминал.
</br>
</br>
Таким образом, команда nohup python3 main.py & запускает Python-скрипт main.py в фоновом режиме на Unix-подобной операционной системе, не прерывая его выполнение при закрытии терминала или отключении от удаленного сервера.
</details>

> Таким образом, разница между этими двумя командами заключается в том, что первая команда запускает процесс в терминале, а вторая команда запускает процесс в фоновом режиме и освобождает терминал для других задач.


### Найти ID процесса 

`ps aux | grep main.py` 
> root 361  0.0 11.0 327896 55196 pts/1    Sl   08:31   0:00 python3 main.py

`ps aux | grep python3`
> root 458  0.0 13.7 407916 68860 pts/1    Sl   08:43   0:04 python3 main.py

### Как остановить процесс nohup

<!-- Убить процесс -->
`kill <ID процесса>` 
> [1]+  Terminated nohup python3 main.py

<!-- Насильно убить процесс -->
`pkill -f "python3"`

<!-- Убить процесс python -->
`killall python3`  -- у меня нету killall

---

# Ubuntu & Linux

## Команды

### Очистить консоль
`clear`

### Закрыть & остановить
`ctrl+z` -- закрыть при открытом терминале

`ctrl+c` -- остановить бота ?

### Получить список файлов

`ls`

`ls -a`
> Даже скрытые покажет

### Перемещение по директориям

`cd /BOT228`
> c - change
> d - directory 

### Скрытые файлы

.env

> Стандарт мира Unix: файлы, начинающиеся с точки считаются "скрытыми"

### Вывод списка всех установленных пакетов

`apt list --installed`
<details>
<summary></summary>

![](https://i.imgur.com/kKBf3m1.jpeg)

</details>

### Узнать версию системы

`uname -a`
> Linux bot-101 5.4.0-146-generic #163-Ubuntu SMP Fri Mar 17 18:26:02 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux

`lsb_release -a`
> No LSB modules are available.
> Distributor ID: Ubuntu
> Description:    Ubuntu 22.04.1 LTS
> Release:        22.04
> Codename:       jammy

---

# Софт

## WinSCP 6.1
<details>
<summary>WinSCP 6.1</summary>

![](https://i.imgur.com/WEMt4IQ.jpeg)

</details>

### Сайт
https://winscp.net/eng/download.php

### Последняя версия
https://winscp.net/download/WinSCP-6.1-Setup.exe

> При подключении мы в /root/

<details>
<summary>Фото чистой системы</summary>

<!-- <img src="https://i.imgur.com/L2HMdOP.jpeg" width="100%" align="center/> -->
![](https://i.imgur.com/L2HMdOP.jpeg)

</details>

---

## PuTTY

<details>
<summary>PuTTY</summary>

![](https://i.imgur.com/UmbCVJg.jpeg)
![](https://i.imgur.com/81bqR4k.jpeg)

</details>

### Сайт

https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

### Последняя версия
https://the.earth.li/~sgtatham/putty/latest/w64/putty-64bit-0.78-installer.msi

> C:\Program Files\PuTTY\

---

# Ссылки
| Описание | Ссылка |
| ------ | ------ |
Чатик: | https://t.me/+c8r_IMXAMjpkZTY6
Бесплатный хостинг (Леонид): | https://t.me/Lvikme
Репо: | 
