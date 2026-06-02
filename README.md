# О чём эта статья?

О том что делать если перестал работать прокси, как восстановить его работу.
Здесь будет публиковаться актуальная информация по настройке прокси и некоторых панелей.

# Что произошло?

В некоторых регионах РКН начал блокировку Vless протокола, также нестандартных http портов, стандартные http порты которые не блокируются: `80`, `81`, `8080`, `443`, `8443`
Также РКН начал активнее блокировать легкозасекаемые VPN протоколы и некоторые SNI/Dest

# Оглавление

[АКТУАЛЬНО: У меня не работает Vless протокол не смотря на настройки SNI](https://github.com/YukiKras/russia-vpn/blob/main/README.md#%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-vless-%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB-%D0%BD%D0%B5-%D1%81%D0%BC%D0%BE%D1%82%D1%80%D1%8F-%D0%BD%D0%B0-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-sni)

[Инструкция по смене SNI в 3x-ui панели](https://github.com/YukiKras/russia-vpn#%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D1%81%D0%BC%D0%B5%D0%BD%D0%B5-snidest-%D0%B2-3x-ui-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8)

[Инструкция по смене SNI в Marzban панели](https://github.com/YukiKras/russia-vpn#%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D1%81%D0%BC%D0%B5%D0%BD%D0%B5-snidest-%D0%B2-marzban-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8)

[У меня перестал работать WireGuard](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-wireguard)

[У меня перестал работать WireGuard, WG Easy, OpenVPN, Outline, ShadowSocks, Amnezia, socks5, PPTP и т. д.](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-wireguard-wg-easy-openvpn-outline-shadowsocks-amnezia-socks5-pptp-%D0%B8-%D1%82-%D0%B4)

[Настройка Vless клиентов](https://github.com/YukiKras/russia-vpn#%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-vless-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%BE%D0%B2)

[У меня перестала работать 3x-ui панель](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB%D0%B0-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-3x-ui-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D1%8C)

[У меня перестал работать Vless ключ в 3x-ui панели](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-vless-%D0%BA%D0%BB%D1%8E%D1%87-%D0%B2-3x-ui-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8)

[У меня перестала работать Marzban панель.](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB%D0%B0-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-marzban-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D1%8C)

[У меня перестал работать Vless в Marzban ](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-vless-%D0%B2-marzban)

[Как сменить порт в Marzban панели?](https://github.com/YukiKras/russia-vpn#%D0%BA%D0%B0%D0%BA-%D1%81%D0%BC%D0%B5%D0%BD%D0%B8%D1%82%D1%8C-%D0%BF%D0%BE%D1%80%D1%82-%D0%B2-marzban-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8)

[У меня перестал работать TorrServer](https://github.com/YukiKras/russia-vpn#%D1%83-%D0%BC%D0%B5%D0%BD%D1%8F-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D1%82%D0%B0%D0%BB-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C-torrserver)

# Инструкция по смене SNI/Dest в 3x-ui панели

Для этого войдите в 3x-ui панель, далее перейдите во вкладку "Инбаунды" или если у вас старая панель 3x-ui во вкладку "Подключения"

<img width="1920" height="397" alt="waterfox_Nb8VT3xTfv" src="https://github.com/user-attachments/assets/720b8281-9158-4b26-ae5f-af2b6e9a9e06" />

Далее нажмите на троеточее и кнопку изменения

<img width="1920" height="676" alt="waterfox_7RkwyxAApN" src="https://github.com/user-attachments/assets/6498a722-dfdd-4508-bde7-9e975d9b354c" />

<img width="348" height="465" alt="waterfox_wm48c0K53W" src="https://github.com/user-attachments/assets/e4b2904a-5737-482b-b332-d9877237863c" />

Далее вам нужно тут заменить SNI и Target (Dest) из этого списка: [Список SNI/Dest](https://github.com/hxehex/russia-mobile-internet-whitelist/blob/main/whitelist.txt)

<img width="396" height="913" alt="waterfox_cM4oEt0zXZ" src="https://github.com/user-attachments/assets/55e4cd01-9cef-4e4f-9554-d10a31ad526f" />

# Не работает Vless протокол не смотря на настройки SNI

Для этого войдите в 3x-ui панель, далее перейдите во вкладку "Инбаунды" или если у вас старая панель 3x-ui во вкладку "Подключения"

<img width="1920" height="397" alt="waterfox_Nb8VT3xTfv" src="https://github.com/user-attachments/assets/720b8281-9158-4b26-ae5f-af2b6e9a9e06" />

Далее нажмите на троеточее и кнопку изменения

<img width="1920" height="676" alt="waterfox_7RkwyxAApN" src="https://github.com/user-attachments/assets/6498a722-dfdd-4508-bde7-9e975d9b354c" />

<img width="348" height="465" alt="waterfox_wm48c0K53W" src="https://github.com/user-attachments/assets/e4b2904a-5737-482b-b332-d9877237863c" />

Далее вам нужно выбрать любой utls кроме Chrome, например firefox:

<img width="400" height="915" alt="waterfox_WWZ1Mv3FWM" src="https://github.com/user-attachments/assets/2f61dc4e-d5a5-4b4a-97e3-388f7fa13904" />

<img width="408" height="914" alt="waterfox_12EtOTx4JK" src="https://github.com/user-attachments/assets/0b95f09c-77dc-4726-b47b-979d45216e73" />

После этого сохраните изменения:

<img width="383" height="681" alt="waterfox_gCPaVrJ1Ws" src="https://github.com/user-attachments/assets/cea53e5c-1c95-47d0-9831-25b81a8e2316" />

Если вы не настраивали подписку то вам необходимо будет скопировать Vless ключ и обновить его в вашем прокси клиенте, ниже показаны скриншоты как скопировать Vless ключ, с инструкциями по настройки прокси клиентов вы можете ознакомиться тут: https://wiki.yukikras.net/ru/nastroikavpn

<img width="645" height="474" alt="waterfox_I5x66l6KZJ" src="https://github.com/user-attachments/assets/26307247-8e1c-418b-a249-b1c5328c3918" />

<img width="614" height="926" alt="waterfox_lYUS1xxLJY" src="https://github.com/user-attachments/assets/8fbd4389-e942-4e00-a72f-83c9a7e57482" />

# Инструкция по смене SNI/Dest в Marzban панели

Для этого войдите в Marzban панель по инструкциям из [wiki.aeza.net](https://wiki.aeza.net/aezawiki/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban#id-2.1-vkhod-v-panel-cherez-ssh-tunnel), далее перейдите в настройки

<img width="1920" height="532" alt="waterfox_tBRXjqHzSB" src="https://github.com/user-attachments/assets/d49e03fb-c34b-4ff4-8b76-65236841b206" />

Далее вам нужно тут заменить SNI и Dest из этого списка: [Список SNI/Dest](https://github.com/hxehex/russia-mobile-internet-whitelist/blob/main/whitelist.txt) и **сохранить изменения**

> [!WARNING]  
> В Target (или в Dest) всегда прописывайте :443 на конце, без пробелов

<img width="961" height="927" alt="waterfox_CE2fjpOcxe" src="https://github.com/user-attachments/assets/2428c84b-033b-4abe-8a06-5d792a394359" />

Если вы не настраивали подписку то вам необходимо будет скопировать Vless ключ и обновить его в вашем прокси клиенте, ниже показан скриншот как скопировать Vless ключ, с инструкциями по настройки прокси клиентов вы можете ознакомиться тут: https://wiki.yukikras.net/ru/nastroikavpn

<img width="1920" height="534" alt="waterfox_3EGujOwrBP" src="https://github.com/user-attachments/assets/651da8bf-3b7a-40df-995d-8d41d390ecbc" />

> [!IMPORTANT]  
> Если не заработало то попробуйте вписать другой SNI/Dest из [этого списка](https://github.com/hxehex/russia-mobile-internet-whitelist/blob/main/whitelist.txt)

# У меня перестал работать WireGuard

В настоящее время протокол WireGuard подвергается блокировкам со стороны РКН, что приводит к его неработоспособности в большинстве случаев.

**[Что делать?](WIREGUARD.md) - [Подробная инструкция](WIREGUARD.md)**

# У меня перестал работать WireGuard, WG Easy, OpenVPN, Outline, ShadowSocks, Amnezia, socks5, PPTP и т. д.

В последнее время данные протоколы РКН блокируются, блокировки происходят постепенно, поэтому всё ещё эти протоколы могут где-то пока работать.
Рекомендую отказаться от использования данных протоколов перейти на Vless протокол следуя этой инструкции: https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-3x-ui

# Настройка Vless клиентов

Vless клиенты имеются для всех платформ, с их настройкой вы можете ознакомиться тут: https://wiki.yukikras.net/ru/nastroikavpn

# У меня перестала работать 3x-ui панель

В связи с последними ограничениями, доступ к панелям теперь осуществляется другим способом, с ним вы можете ознакомиться в следующей статье: https://github.com/YukiKras/wiki/blob/main/ssh-tunnels.md

# У меня перестал работать Vless ключ в 3x-ui панели

После того как войдёте в панель убедитесь что у вас Vless настроен на 443 и 8443 портах:
<img width="2345" height="317" alt="waterfox_NeiCVMYYfB" src="https://github.com/user-attachments/assets/25c1f344-329e-4ce5-b653-4c140c960862" />

Если это не так то это нужно изменить, для этого нужно отредактировать Vless подключение:
<img width="555" height="578" alt="waterfox_IDtfPIglOw" src="https://github.com/user-attachments/assets/997478e2-36cb-498e-8a74-b5616029db19" />

Далее измените порт на 443 или 8443 где подчёркнуто и сохраните изменения:
<img width="507" height="1284" alt="waterfox_BDD6Ypehlg" src="https://github.com/user-attachments/assets/9138fb16-2fcb-4d49-b082-73be456efe7e" />


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

# У меня перестал работать TorrServer

Вы можете восстановить работу панели подключившись к серверу по [SSH](https://wiki.yukikras.net/ru/kak-podklyuchitsya-po-ssh-i-sftp) и введя следующую команду в консоли сервера:
``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/torrserver-port-change-to-8080.sh)
```
