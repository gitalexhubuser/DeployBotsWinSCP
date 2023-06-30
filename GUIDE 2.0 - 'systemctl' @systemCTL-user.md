# Гайд по деплою, тг бота - при помощи либы "systemd"

Бота лучше положить в `/usr/local/bin`

Переносим ручками, при помощи WinSCP

Чтоб не мучаться с:
```bash
# CMD Terminal

# Туда
pscp.exe "C:\Users\PC2\PythonProjects\Bot\bot.py" root@123.123.123.123:/usr/local/bin/bot

# Назад
pscp.exe root@123.123.123.123:/usr/local/bin/bot/database "C:\Users\PythonProjects\Desktop
```

Переходим в папку с проектом
`cd /usr/local/bin/BOT229`

Переносим файл с библитеками requirements.txt

Устанавливаем виртуальное окружение
`python3 -m venv you-tube`
> Важно!!! В Win и Ubuntu - разные пути активации venv

Активируем виртуальное окружение
`source you-tube/bin/activate`

Устанавливаем либки строго в виртуальное окружение
`pip install -r requirements.txt`

Есть **systemd** ?
`systemctl --version`

Нету **systemd** ?
`apt-get install systemd`

Создаём файл `bot229.service`
```bash
# Ложим в /etc/systemd/system

[Unit]
Description=BOT229 через systemd
After=syslog.target
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=/usr/local/bin/BOT229
Environment=/usr/local/bin/BOT229/you-tube/bin
ExecStart=/usr/local/bin/BOT229/you-tube/bin/python3 /usr/local/bin/BOT229/main.py
RestartSec=10
Restart=always
# Restart=on-failure
 
[Install]
WantedBy=multi-user.target

```

Ложим `bot229.service` в `/etc/systemd/system`

Для применения изменений в PyTTY пишем:
```bash
systemctl daemon-reload
systemctl enable bot229.service
systemctl start bot229 # systemctl start bot229.service - так не работает!
systemctl status bot229.service
```
> PS: Очевидно, чтоб приостановить - нужно написать `systemctl stop bot229`

Бот запустился и работает!

# Ссылки
| Описание | Ссылка |
| ------ | ------ |
Оригинал: | https://habr.com/ru/articles/347106/
Репо: | https://gitlab.com/systemCTL-user/systemd-little-guide
