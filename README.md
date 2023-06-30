# DeployBotsWinSCP

<img src="https://i.imgur.com/6TIoe54.jpeg" width="70%" align="center"/>

<img src="https://i.imgur.com/RosHgNx.jpeg" width="50%" align="center"/>

## Описание1

Инфа про то, как задеплоить бота на питоне на сервер LXD, SSH, VPS Server

На примере моего [бота для тик тока](https://t.me/pythonTikTok_chat)

Папка проекта называется - `BOT228`

---

## Использование

```bash
cd /BOT228; source tik-tok/bin/activate; nohup python3 main.py &
# Команда-макрос в 1-н клик - на запуск бота в телеграм на VPS
```

---

## Todo
- [ ] как читать логи (nohup.out)
- [ ] deamon ubuntu
- [ ] supervisor
- [ ] screen https://youtu.be/x-VB3b4pKcU
- [ ] docker
- [ ] как переключиться после закрытия консоли на логи бота
- [ ] крутые ссылки на разные VPS в PuTTY
- [ ] видел фикс проблемы с кодировкой на ют в бота добавлять РІРёРґРµРѕ - РќРµ РїРѕР»СѓС‡РёР»РѕСЃСЊ СѓР·РЅР°С‚СЊ РёР»Рё РІС‹СЃР»Р°С‚СЊ!
- [ ] для killall какая либа нужна?

---

## Python

### Узнать версию питона

```bash
python3 --version
# Python 3.10.6
```

### Версия установщика пакетов

```bash
pip3 -v
# pip 23.0 from /usr/local/lib/python3.10/dist-packages/pip (python 3.10)
```

### Создать виртуальное окружение

`python3 -m venv tik-tok`

---

## Pytty

```bash
# Активация venv с Пк
.\tik-tok\Scripts\activate

# Активация venv с Пк (2)
source tik-tok/Scripts/activate

# Активация venv на хостинге (путь отличается)
source tik-tok/bin/activate  -- Урок https://youtu.be/x-VB3b4pKcU?t=638

# Устанавливаем зависимости (желательно в venv)
pip install -r requirements.txt

# Запуск скрипта с Пк
python main.py

#  Запуск скрипта из терминала на хостинге 
python3 main.py
```

---

## nohup

```bash
# Утилита ставит процесс питона на фон
nohup

# Спец символ дающий команду на фон кинуть процесс питона, чтоб продолжать дальше пользоваться терминалом
& 
```

`nohup python3 main.py`

<details>
<summary>Подробней...</summary>
Команда nohup python3 main.py запускает процесс python3 main.py в фоновом режиме и перенаправляет вывод в файл nohup.out. В этом случае, процесс python3 main.py будет выполняться в том же терминале, в котором была запущена команда nohup, и вы НЕ сможете использовать этот терминал для других задач, пока процесс не завершится.
</details>

`nohup python3 main.py &`  -- Спс https://youtu.be/ibwjI6mKwLM
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

```bash
ps aux | grep main.py 
# root 361 0.0 11.0 327896 55196 pts/1 Sl 08:31 0:00 python3 main.py
# 361 ID

ps aux | grep python3
# root 458 0.0 13.7 407916 68860 pts/1 Sl 08:43 0:04 python3 main.py
# 458 ID
```

### Как остановить процесс nohup

```bash
# Убить процесс
kill <ID процесса>
# [1]+  Terminated nohup python3 main.py

# Насильно убить процесс
pkill -f "python3"

# Убить все процессы python3
killall python3
```
> У меня нету `killall`! Нужно ставить ...

---

# Ubuntu & Linux

## Команды

### Очистить консоль
`clear`

### Закрыть & остановить

```bash
# Закрыть при открытом терминале
ctrl + z

# Остановить бота
ctrl + c
```

### Получить список файлов

```bash
ls
ls -a
# Даже скрытые покажет
```

### Перемещение по директориям

```bash
cd /BOT228

# c - change
# d - directory
```

### Скрытые файлы

```bash
.env

# Стандарт мира Unix: файлы, начинающиеся с точки считаются "скрытыми"
```

### Вывод списка всех установленных пакетов

`apt list --installed`
<details>
<summary></summary>

![](https://i.imgur.com/kKBf3m1.jpeg)

</details>

### Узнать версию системы

```bash
uname -a

# Linux bot-101 5.4.0-146-generic #163-Ubuntu SMP Fri Mar 17 18:26:02 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

```bash
lsb_release -a

# No LSB modules are available.
# Distributor ID: Ubuntu
# Description:    Ubuntu 22.04.1 LTS
# Release:        22.04
# Codename:       jammy
```

```bash
cat /etc/*-release

# DISTRIB_ID=Ubuntu
# DISTRIB_RELEASE=22.04
# DISTRIB_CODENAME=jammy
# DISTRIB_DESCRIPTION="Ubuntu 22.04.1 LTS"
# PRETTY_NAME="Ubuntu 22.04.1 LTS"
# NAME="Ubuntu"
# VERSION_ID="22.04"
# VERSION="22.04.1 LTS (Jammy Jellyfish)"
# VERSION_CODENAME=jammy
# ID=ubuntu
# ID_LIKE=debian
# HOME_URL="https://www.ubuntu.com/"
# SUPPORT_URL="https://help.ubuntu.com/"
# BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
# PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
# UBUNTU_CODENAME=jammy
```

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
Чат VPS хостинга: | https://t.me/+c8r_IMXAMjpkZTY6
Бесплатный хостинг (пишите в личку Леониду): | https://t.me/Lvikme
Репо: | https://github.com/gitalexhubuser/DeployBotsWinSCP
