<p align="center">
  <img src="assets/logo.png" width="400">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-blue?style=for-the-badge&logo=statuspage">
  <img src="https://img.shields.io/github/last-commit/wlunlocker/vpn-configs?style=for-the-badge&logo=git">
  <img src="https://img.shields.io/badge/Available_on-GitHub-orange?style=for-the-badge&logo=github">
  <img src="https://img.shields.io/badge/Keys_Count-1500+-purple?style=for-the-badge&logo=keybase">
  <img src="https://img.shields.io/badge/Update-Every_hour-red?style=for-the-badge&logo=clockify">
</p>

## 📌 О проекте

Автоматизированный генератор чистых, проверенных и стабильных подписок для обхода сетевых ограничений. Скрипты собирают более 1500 ключей, сортируют их по категориям и модерирует.

> 🛡️ **Главная фишка:** Все конфигурации проходят через **Тест пинга Proxy GET-тест**. Никакого рандома и минимальное количество серверов с **«Н.Д.» (Нет Данных)**. В списки попадают только те узлы, которые успешно ответили на HTTP GET-запрос через TLS-соединение со скоростью ответа до 1000 мс. Имеется интуитивно понятный сайт сайт - wlunlocker.github.io

---

## 🗂️ Доступные подписки

| Тип подписки | Описание | Ссылка на RAW (Копировать) |
| --- | --- | --- |
| 🌐🏳️ **WHITELIST ALL**/АНТИГЛУШИЛКИ - ВСЕ СЕРВЕРА | Полный набор белых списков (CIDR + SNI) для точечного обхода блокировок внутри РФ | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_all.txt` |
| 🌐🏴 **BLACKLIST ALL**/VPN - ВСЕ СЕРВЕРА | Полный набор черных списков для пуска всего трафика через зарубежные серверы | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_all.txt` |
| 🏳️ **WHITELIST CIDR 1 RU**/АНТИГЛУШИЛКИ #1 (CIDR) | Первая часть конфигураций, отфильтрованных по диапазонам IP адресов для России | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr1_ru.txt` |
| 🏳️ **WHITELIST CIDR 2 RU**/АНТИГЛУШИЛКИ #2 (CIDR) | Вторая часть конфигураций по диапазонам IP адресов для России | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr2_ru.txt` |
| 🏳️ **WHITELIST CIDR 3 EU**/АНТИГЛУШИЛКИ 3 EU (CIDR) | Европейские IP диапазоны для стабильного доступа к зарубежным сервисам | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/whitelist_cidr3_eu.txt` |
|
| 🏴 **BLACKLIST VPN 1**/VPN #1 | Черные списки для мобильных сетей, устойчивые к блокировкам ТСПУ | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn1.txt` |
| 🏴 **BLACKLIST VPN 2**/VPN #2 | Стандартные черные списки для использования на ПК и домашних роутерах | `https://raw.githubusercontent.com/wlunlocker/vpn-configs/main/blacklist_vpn2.txt` |

---

## 🚀 Поддерживаемые протоколы

Скрипты автоматизации обрабатывают, удаляют дубликаты и тестируют следующие типы прокси конфигураций:

* **VLESS** (включая XTLS, Reality, gRPC) для маскировки под стандартный HTTPS трафик
* **VMess** для классического зашифрованного соединения
* **Trojan** для маскировки под стандартный веб сервер
* **Shadowsocks** для быстрой обработки базового трафика

---

## 📖 Инструкция по установке (Пример: HAPP)

1. Скопируйте необходимую ссылку из таблицы выше.
2. Откройте приложение HAPP (или др.) на устройстве.
3. Нажмите справа сверху на **Три точки**.
4. Выберите пункт **Вставить из буфера обмена**.
5. Готово. Для стабильной работы регулярно обновляйте подписку используя кнопку **Обновить**

---

## ⚙️ Схема работы автоматизации

Источники данных обновляются по следующему алгоритму:

1. **GitHub Actions** запускаются по расписанию, опрашивают сырые источники, распределяют ключи по отдельным файлам, фильтруют дубликаты и невалидные строки.
2. **Локальный чекер** на выделенном хосте каждые 15 минут выполняет команду `git pull`, забирает обновленные файлы и тестирует каждый узел через защищенное TLS соединение. Серверы, не приславшие ответ на GET запрос или превысившие таймаут, удаляются из файлов. Измененные конфигурации автоматически отправляются обратно в репозиторий через `git push`.

---

## 📋 Источники конфигураций

VPN #1 (VLESS):
BLACK_VLESS_RUS_mobile.txt - https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_VLESS_RUS_mobile.txt
BLACK_VLESS_RUS.txt - https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_VLESS_RUS.txt
WangCai - https://shz.al/~WangCai

VPN #2 (SS + Hysteria2):
BLACK_SS+All_RUS.txt - https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/BLACK_SS%2BAll_RUS.txt
FreeProxyList (mirror) - https://raw.githubusercontent.com/nikita29a/FreeProxyList/refs/heads/main/mirror/1.txt

Whitelist (CIDR & SNI):
WHITE-SNI-RU-all.txt - https://raw.githubusercontent.com/igareck/vpn-configs-for-russia/refs/heads/main/WHITE-SNI-RU-all.txt
ByeWhiteLists2 - https://raw.githubusercontent.com/ByeWhiteLists/ByeWhiteLists2/refs/heads/main/ByeWhiteLists2.txt

---

## ❗ Дисклеймер:

Автор данного репозитория является исключительно агрегатором публично доступных конфигураций и не несет ответственности за сохранность, конфиденциальность и безопасность ваших персональных данных. Все представленные сервера принадлежат третьим лицам; использование данных ресурсов осуществляется вами на свой страх и риск. Проявляйте осмотрительность при передаче чувствительной информации через сторонние VPN-узлы.
