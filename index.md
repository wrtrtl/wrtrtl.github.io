# OpenWRT Repo for rtl8196e
Привет, чтобы использовать этот репозиторий с пакетами от [Alter0ne](https://github.com/Alter0ne/rtl8196e/) вам следует ознакомиться с этой инструкцией.

Этот репозиторий собран благодаря Alter0ne и его сборке OpenWRT для нашего процессора.

## Внимание ! 
>Этот репозиторий предназначается для роутеров с процессорами от 
> Realtek  rtl8196e с прошивкой OpenWRT 14.07
> За приченный вред вашему роутеру мы не нисём ответсвенности. 
> Вы знали, что ставили мы вас уведомили.

### Инструкция
1. Войдите в WEB-интерфейс вашего роутера
2. Перейдите "Система"-"Програмное обеспечение"-"Конфигурация"
3. Замените это
```
dest root /
dest ram /tmp
lists_dir ext /var/opkg-lists
option overlay_root /overlay
src/gz barrier_breaker_base http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/base
src/gz barrier_breaker_telephony http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/telephony
src/gz barrier_breaker_packages http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/packages
src/gz barrier_breaker_routing http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/routing
src/gz barrier_breaker_luci http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/luci
src/gz barrier_breaker_management http://downloads.openwrt.org/barrier_breaker/14.07/realtek/rtl8196e/packages/management
```
# Этим
```
dest root /
dest ram /tmp
lists_dir ext /var/opkg-lists
option overlay_root /overlay
src/gz barrier_breaker_base https://wrtrtl.github.io/packages/base
src/gz barrier_breaker_telephony https://wrtrtl.github.io/packages/telephony
src/gz barrier_breaker_packages https://wrtrtl.github.io/packages/packages
src/gz barrier_breaker_routing https://wrtrtl.github.io/packages/routing
src/gz barrier_breaker_luci https://wrtrtl.github.io/packages/luci
src/gz barrier_breaker_management https://wrtrtl.github.io/packages/management
```
4. Жмем Применить
5. Зайдите в SSH консоль
6. Набирите команду *opkg update*
### Почему мы используем какие_то левые сервера
Это потому, что некоторые сервера стоят в режиме ожидания, если что-нибудь случится, то вы увидите на сайте, причину и на что было изменино

### Если вам нужны пакеты из oldpackages
Добавте к этому списку этот репозиторий
> src/gz barrier_breaker_oldpackages https://wrtrtl.github.io/packages/oldpackages

### Проблемы, остались вопросы

Если у вас остались вопросы, то пишите на почту pnsrc@yandex.ru
