# DeployBotsWinSCP - ветка "easy-guide"

<img src="https://i.imgur.com/vRPZlfF.jpeg" width="70%" align="center"/>

## Описание

Данная ветка создана [для участия в конкурсе тут](https://t.me/+c8r_IMXAMjpkZTY6).

В ней вы найдёте, краткую информацию, как запустить (задеплоить) простейшего бота в ТГ, на удаленном хостинге VPS, через команду `nohup`.

Использование будет реализованочерез команду `nohup` - не идеальный user experience, но холивары на эту темы мы сейчас развивать не будем!

Всё произойдёт за **7**  шагов!!!

Поехали...

---

## Супер короткий гайд
- Подготовли простейшего бота
- Скачали [спец по](https://github.com/gitalexhubuser/DeployBotsWinSCP/tree/main#%D1%81%D0%BE%D1%84%D1%82)
- [Получили](https://t.me/Lvikme) лог \ пасс \ адрес \ порт от сервера
- Вошли через [WinSCP](https://github.com/gitalexhubuser/DeployBotsWinSCP/tree/main#winscp-61)
- Перенесли файлы бота
- Открыли [PyTTY](https://github.com/gitalexhubuser/DeployBotsWinSCP/tree/main#putty)
- Перемещаемся в папку с проектом
- Если вы используете виртуальное окружение
    - вводим макрос `cd /MYBOT; source venv/bin/activate; nohup python3 main.py &`
- Если вы не используете виртуальное окружение
    - вводим макрос `cd /MYBOT; nohup python3 main.py`
- Всё заработало!

---

## Короткий гайд
- Скачиваем и устанавливаем последние версии 2-х этих программ: [1](https://winscp.net/download/WinSCP-6.1-Setup.exe), [2](https://the.earth.li/~sgtatham/putty/latest/w64/putty-64bit-0.78-installer.msi)
- Получаем 1) логин, 2) пароль, 3) ip, и 4) порт у [Леонида](https://t.me/Lvikme)
```bash
# Пример
194.xxx.xxx.xxx     # Имя хоста
22101               # Порт
root                # Имя пользователя
password            # Пароль

```
- Авторизуемся в [WinSCP](https://github.com/gitalexhubuser/DeployBotsWinSCP/tree/main#winscp-61) используя полученные данные
- Далее переносим из винды на сервер папку с проектом бота (и визуально запоминаем путь) например `/MYBOT`

<details>
<summary>Подробней...</summary>

![](https://i.imgur.com/QSRAGSr.jpeg)
</details>

- Открываем [PyTTY](https://github.com/gitalexhubuser/DeployBotsWinSCP/tree/main#putty)
<details>
<summary>Подробней...</summary>

![](https://i.imgur.com/UmbCVJg.jpeg)
</details>

- В терминате PyTTY:
    - перемещаемся в папку с проектом командой `cd /MYBOT`
    - командой `cd /MYBOT; nohup python3 main.py &` запускаем вашего бога (если у вас **нету** виртуального окружения)
    - командой `cd /MYBOT; source venv/bin/activate; nohup python3 main.py &` запускаем вашего бога (если у вас уже **есть*** виртуальное окружение)
- Всё заработало!

> Подробней что такое venv, nohup, виртуальное окружение, requirements.txt - можно почитать в master ветке.

---

# Ссылки
| Описание | Ссылка |
| ------ | ------ |
Чат VPS хостинга: | https://t.me/+c8r_IMXAMjpkZTY6
Бесплатный хостинг (пишите в личку Леониду): | https://t.me/Lvikme
Репо: | https://github.com/gitalexhubuser/DeployBotsWinSCP
