## ESP32-ESP8266-Script-to-build-PlatformIO

Скрипт для cоздания прошивки, заливки в микроконтроллер, создания и заливки SPIFFS, мониторинг работы через COM порт

### Краткое описание
Cкрипт для сборки прошивки для ESP8266 с помощью PlatformIO непосредственно из терминала. Скрипт позволяет очистить от предыдущей сборки, собрать новую прошивку, создать из каталога ```data``` файловую систему ```SPIFFS```, залить прошивку и созданную файловую систему ```SPIFFS```. Кроме этого с помощью этого же скрипта из каталога проекта можно запустить мониторинг COM порта к которому подключен микроконтроллер.

Скрипт размещает все собранные прошивки и ```SPIFFS``` в каталоге ```bin```. Если при запуске скрипта каталог не существовал, он будет создан, так же будут проверено наличие файла ```.gitignore```, если он так же не существует он будет создан и в него будет дописано исключение не индексировать кателог ```bin```.

### Зависимости
Для работы скрипта необходимы:
* [PlatformIO](https://platformio.org/) и настроеный проект
* [mkspiffs](https://github.com/igrr/mkspiffs/releases) [GitHub](https://github.com/igrr/mkspiffs)
* [esptool](https://github.com/espressif/esptool)
* [pyserial](https://pythonhosted.org/pyserial/tools.html#miniterm)

### Использование

```bash

./tools-board -h

############################ HELP #############################
./tools-board -mb  | Moнитор порта UART
./tools-board -c   | Очистака проекта
./tools-board -m   | Сборка прошивки
./tools-board -e   | Очистка ESP8266
./tools-board -mf  | Сборка образа SPIFFS
./tools-board -mw  | Cборка прошивки, запись прошивки
./tools-board -owf | Только запись образа SPIFFS, необходимо передать имя образа SPIFFS
./tools-board -ow  | Только запись прошивки, необходимо передать имя прошивки
./tools-board -mwf | Cборка образа SPIFFS и его запись
./tools-board -id  | Информация об ID ESP8266
./tools-board -mac | MAC адрес ESP8266
./tools-board -fl  | ID Flash ESP8266
./tools-board -h   | Справка по работе со скриптом
###############################################################

```
***



