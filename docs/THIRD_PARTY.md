# Использованные проекты и исходники

WxP — отдельный клиент, который интегрирует перечисленные ниже компоненты.
Это не официальный выпуск Xray, zapret, WinDivert или Telegram. Ссылки ведут
к исходным проектам; их авторство и лицензии сохраняются.

## Сетевые компоненты

| Проект | Что используется | Источник и лицензия |
|---|---|---|
| Xray-core | Ядро передачи выбранных соединений; основа 26.10.21, upstream commit `1b1647c`, с локальными изменениями WxP | [XTLS/Xray-core](https://github.com/XTLS/Xray-core), MPL-2.0; [исходный PR Windows UDP](https://github.com/XTLS/Xray-core/pull/7214) |
| zapret | Обработка соединений без удалённого узла | [bol-van/zapret](https://github.com/bol-van/zapret), MIT |
| zapret-discord-youtube | Набор Windows-компонентов и стратегий первой интеграции; версия локального снимка комплекта 1.10.2 | [Flowseal/zapret-discord-youtube](https://github.com/Flowseal/zapret-discord-youtube), MIT с уведомлениями о сторонних компонентах |
| zapret2 / Windows bundle | Компоненты второй интеграции; снимок комплекта `0e9e3fbfb04a1681f3f8b5eb644dee4ecedcccf0` | [bol-van/zapret2](https://github.com/bol-van/zapret2), [bol-van/zapret-win-bundle](https://github.com/bol-van/zapret-win-bundle); условия компонентов проверяются отдельно |
| TG WS Proxy | Основа встроенного MTProto/WebSocket-модуля для Telegram Desktop; с изменениями интеграции WxP | [Flowseal/tg-ws-proxy](https://github.com/Flowseal/tg-ws-proxy), MIT |
| WinDivert | Перехват выбранных Windows-пакетов; для компонента совместимости используется библиотека 2.2.2 | [basil00/WinDivert](https://github.com/basil00/WinDivert/tree/v2.2.2), LGPL-3.0; upstream также предлагает альтернативные условия |
| gVisor | TCP/IP-стек компонента совместимости; revision `89a5d21be8f0440c78fa6bbc01f98e23021e7132` | [google/gvisor](https://github.com/google/gvisor/tree/89a5d21be8f0440c78fa6bbc01f98e23021e7132), Apache-2.0 |
| Wintun | Виртуальный сетевой интерфейс Windows | [wintun.net](https://www.wintun.net/), [исходники](https://git.zx2c4.com/wintun/); исходный код GPL-2.0, официальные подписанные DLL имеют отдельные условия в архиве поставщика |
| Cygwin runtime | Среда выполнения в составе Windows-комплекта второго движка | [cygwin.com](https://cygwin.com/), [условия LGPL-3.0-or-later и linking exception](https://cygwin.com/licensing.html) |

Включённый Xray отличается от официального бинарного выпуска: применены
исправления Windows UDP, DNS/IPv6, выбора исходного интерфейса, внешнего
транспорта и поиска процесса. Изменённые MPL-файлы сохраняют MPL-2.0.
Эта таблица не заменяет выдачу соответствующего исходного кода таких изменений
при распространении изменённого бинарного компонента.

Точная исходная ревизия скопированного Telegram-модуля отдельно не зафиксирована.
Версия Windows-комплекта zapret не является версией каждого EXE/DLL внутри него.
Не следует подменять соответствующий исходник текущей веткой upstream без проверки.

## Правила доменов и адресов

| Источник | Назначение | Лицензия |
|---|---|---|
| [v2fly/domain-list-community](https://github.com/v2fly/domain-list-community) | Категории доменов сервисов | MIT |
| [runetfreedom/russia-blocked-geosite](https://github.com/runetfreedom/russia-blocked-geosite) | Дополнение правил доменов | GPL-3.0 |
| [runetfreedom/russia-blocked-geoip](https://github.com/runetfreedom/russia-blocked-geoip) | Источник ASN-данных | GPL-3.0 |

Объединённый набор правил сервисов содержит отфильтрованные и изменённые данные;
он сохраняет GPL-3.0 и MIT-атрибуцию. Для общих `geoip.dat` и `geosite.dat`
нужна отдельная фиксация происхождения именно распространяемого снимка.

## Интерфейс, Python и сборка

| Проект | Использование | Источник / лицензия |
|---|---|---|
| CPython | Среда Python | [python/cpython](https://github.com/python/cpython), PSF и сопутствующие лицензии |
| pywebview | Окно приложения и мост Python/JavaScript | [r0x0r/pywebview](https://github.com/r0x0r/pywebview), BSD-3-Clause |
| pystray | Системный трей | [moses-palmer/pystray](https://github.com/moses-palmer/pystray), LGPL-3.0 |
| Pillow | Изображения и иконки | [python-pillow/Pillow](https://github.com/python-pillow/Pillow), MIT-CMU и уведомления встроенных компонентов |
| cryptography | Криптографические примитивы | [pyca/cryptography](https://github.com/pyca/cryptography), Apache-2.0 OR BSD-3-Clause; OpenSSL и другие встроенные зависимости имеют свои лицензии |
| psutil | Сведения о собственных процессах | [giampaolo/psutil](https://github.com/giampaolo/psutil), BSD-3-Clause |
| pyperclip | Буфер обмена | [asweigart/pyperclip](https://github.com/asweigart/pyperclip), BSD-3-Clause |
| certifi | Корневые сертификаты TLS | [certifi/python-certifi](https://github.com/certifi/python-certifi), MPL-2.0 |
| pythonnet / clr-loader | Интеграция .NET | [pythonnet/pythonnet](https://github.com/pythonnet/pythonnet), [pythonnet/clr-loader](https://github.com/pythonnet/clr-loader), MIT |
| cffi / pycparser | Зависимости вызовов нативного кода | [python-cffi/cffi](https://github.com/python-cffi/cffi), MIT-0; [eliben/pycparser](https://github.com/eliben/pycparser), BSD-3-Clause |
| Bottle / proxy-tools | Зависимости pywebview | [bottlepy/bottle](https://github.com/bottlepy/bottle), [r0x0r/proxy-tools](https://github.com/r0x0r/proxy-tools), MIT |
| PyInstaller | Упаковка приложения | [pyinstaller/pyinstaller](https://github.com/pyinstaller/pyinstaller), GPL с исключением для сборки приложений |
| Go | Сборка нативного компонента | [golang/go](https://github.com/golang/go), BSD-3-Clause |
| golang.org/x/sys, x/exp, x/time | Нативные зависимости Go | [golang](https://github.com/golang), BSD-3-Clause |
| google/btree | Косвенная зависимость стека | [google/btree](https://github.com/google/btree), Apache-2.0 |
| Microsoft Edge WebView2 | Системная среда интерфейса | [Microsoft WebView2](https://learn.microsoft.com/en-us/microsoft-edge/webview2/), условия Microsoft |

Копии доступных текстов лицензий находятся в `../licenses/`. Файл
[LICENSE_INDEX.md](LICENSE_INDEX.md) указывает происхождение этих копий.
Набор является публичным уведомлением об использованных проектах, а не полным
SBOM всех транзитивных зависимостей опубликованного EXE. Готовый EXE и
[материалы сторонних компонентов 1.3.1](https://github.com/WxP-best/WxP/releases/download/v1.3.1/WxP-third-party-1.3.1.zip)
размещаются отдельно в Releases. В архиве сохранены исходники/изменения
MPL-компонентов, лицензии, редактируемые таблицы и инструкции замены библиотек.
Исторические ограничения происхождения снимков описаны в SOURCE_PROVENANCE.md
внутри архива. Исходники закрытого клиента и backend туда не включены.
