# wireguard-install
это скрипт, устанавливающий серверную часть wireguard , а так же позволяющий создавать пользователей.
Подсказка по командам:
Опустить интерфейс после изменений
sudo wg-quick down wg0

Включить интерфейс
sudo wg-quick up wg0

Просмотр конфига
wg

Конфиг клиента:
/root/wg0-client-lobov.conf

Конфиг общий:
/etc/wireguard/wg0.conf

# ikev2-deploy-certs.sh
# ikev2-deploy-certs.sh
Скрипты настройки ipsec туннеля с использованием сертификата и по PSK ключу
Рабочий вариант конфига  для соединения с фортигейтом:
/etc/ipsec.conf
  GNU nano 4.8                                                                                                                                     
config setup
    charondebug="ike 1, knl 1, cfg 0, ike 2"
    uniqueids=no

conn ikev2-vpn
    auto=add
    compress=no
    type=tunnel
    keyexchange=ikev2
    fragmentation=yes
    forceencaps=yes
    ike=aes256-sha256-modp2048!
    esp=aes256-sha256-modp2048!
    dpdaction=clear
    dpddelay=300s
    rekey=no
    left=public ip of swan server
    leftid=%any
    leftsubnet=0.0.0.0/0
    right=public ip of fortigate
    rightid=%any
    authby=secret









