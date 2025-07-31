# О чём эта статья?

О том что делать если перестал работать прокси, как восстановить его работу.
Здесь будет публиковаться актуальная информация по настройке прокси.

# У меня перестал работать WireGuard, OpenVPN, Outline, ShadowSocks, Amnezia, socks5, PPTP и т. д.

В последнее время данные протоколы РКН блокируются, блокировки происходят постепенно, поэтому всё ещё эти протоколы могут где-то пока работать.
Рекомендую отказаться от использования данных протоколов перейти на Vless протокол следуя [этой инструкции](https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-3x-ui)

# У меня перестала работать 3x-ui панель

РКН начал блокировать нестандартные http/https порты, вы можете восстановить работу панели подключившись к серверу по [SSH](https://wiki.yukikras.net/ru/kak-podklyuchitsya-po-ssh-i-sftp) и введя следующую команду в консоли сервера:
``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/3xuiportfix.sh)
```

# У меня перестал работать Vless ключ в 3x-ui панели

После того как войдёте в панель убедитесь что у вас Vless настроен на 443 и 8443 портах:
<img width="2345" height="317" alt="waterfox_NeiCVMYYfB" src="https://github.com/user-attachments/assets/25c1f344-329e-4ce5-b653-4c140c960862" />

Если это не так то это нужно изменить, для этого нужно отредактировать Vless подключение:
<img width="555" height="578" alt="waterfox_IDtfPIglOw" src="https://github.com/user-attachments/assets/997478e2-36cb-498e-8a74-b5616029db19" />

Далее измените порт на 443 или 8443 где подчёркнуто и сохраните изменения:
<img width="543" height="1306" alt="eYiEyVTTNu" src="https://github.com/user-attachments/assets/fb077139-cb8c-4f9b-8498-acf150d0e26c" />

Если вы не настраивали подписки в 3x-ui то вам необходимо передобавить Vless ключи в ваши клиенты заново.

# У меня перестала работать Marzban панель.

Если у вас не получается зайти в Marzban панель вообще, то вам необходимо либо её [полностью переустановить](https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban), или подключиться к ней с помощью SSH туннеля или изменить её порт на `8080`

# Как сменить порт в Marzban панели?

Если вы ранее настраивали SSL для Marzban то зайдите на сервер по [SSH](https://wiki.yukikras.net/ru/kak-podklyuchitsya-po-ssh-i-sftp) и откройте файл настройки Marzban:

``` bash
nano /opt/marzban/.env
```

<img width="857" height="420" alt="изображение" src="https://github.com/user-attachments/assets/9aebd8f6-25da-4fb4-bc28-1fa94e675772" />

Нужно отредактировать вторую строку заменив `8000` порт например на порт `8080`, чтобы сохранить изменения в nano нажмите на сочетание клавиш **Ctlr + O** и **Enter**, чтобы выйти из nano нажмите на **Ctrl + X**
Далее чтобы применить изменения перезапустите Marzban с помощью следующей команды:

``` bash
marzban restart
```

Готово! Можете пробовать входить по новому порту.

# У меня перестал работать Vless в Marzban 

Если у вас получается зайти в Marzban панель, и при этом не работают Vless подключения то перейдите в настройки:

<img width="768" height="97" alt="image(2)" src="https://github.com/user-attachments/assets/c0216508-8b5e-4f6c-9365-ef4d9124e805" />


Убедитесь что тут стоит 443 или 8443 порт:

<img width="420" height="273" alt="изображение" src="https://github.com/user-attachments/assets/771957fc-7892-44a1-8189-22b814608b63" />


Если вы внесли изменения то нажмите на кнопку **Сохранить**, перезагрузить страницу с помощью клавиши **F5** и если вы не настраивали подписки в Marzban то вам необходимо передобавить Vless ключи в ваши клиенты заново.
