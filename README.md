# GB Link Firmware (Reconfigurable)

Прошивка для Raspberry Pi Pico, позволяющая подключить Game Boy к компьютеру через USB для игры в онлайн-тетрис.

**Firmware for Raspberry Pi Pico that allows connecting a Game Boy to a computer via USB to play online Tetris.**

---

## 🇷🇺 Русский

### Описание

Это форк прошивки [GB Link](https://github.com/stacksmashing/gb-link-firmware) от [stacksmashing](https://github.com/stacksmashing), модифицированный специально для [Музея Вычислительной Техники Дмитрия Бачило](https://t.me/retro_museum) в Новосибирске.

Прошивка превращает Raspberry Pi Pico в USB-адаптер для Game Boy Link Cable, позволяя играть в тетрис онлайн на сайте [tetris.gblink.io](https://tetris.gblink.io/).

### Подключение

![Схема подключения](docs/wiring-diagram.png)


#### Распиновка GPIO Raspberry Pi Pico:

| Пин Pico | Назначение | Описание |
|----------|------------|----------|
| GPIO 9   | SCK (PSC)   | Serial Clock |
| GPIO 10  | SIN (PSI)   | Serial In |
| GPIO 13  | SOUT (PSO)  | Serial Out |
| GPIO 14  | SI (PSD)    | Serial Data |
| GPIO 16  | LED         | Встроенный светодиод |
| GPIO 6   | TEST_PIN    | Тестовый пин (опционально) |

### Сборка

#### Требования

- Raspberry Pi Pico SDK
- CMake (версия 3.13 или выше)
- Компилятор GCC для ARM

#### Инструкции по сборке

1. Клонируйте репозиторий:
```bash
git clone <repository-url>
cd gb-link-firmware-reconfigurable
```

2. Установите Raspberry Pi Pico SDK:
```bash
# Установите переменную окружения PICO_SDK_PATH
export PICO_SDK_PATH=/path/to/pico-sdk
```

3. Создайте директорию для сборки:
```bash
mkdir build
cd build
```

4. Запустите CMake:
```bash
cmake ..
```

5. Соберите проект:
```bash
make
```

6. Прошивка будет находиться в файле `gbusb.uf2` в директории `build/`

### Установка прошивки

1. Удерживайте кнопку BOOTSEL на Raspberry Pi Pico
2. Подключите Pico к компьютеру через USB
3. Откройте появившийся диск RPI-RP2
4. Скопируйте файл `gbusb.uf2` на этот диск
5. Pico автоматически перезагрузится с новой прошивкой

### Изготовление разъема

Если у вас нет под рукой кабеля GB Link, вы можете распечатать 3D-модели из папки `models/` и использовать Dupont провода для создания собственного разъема GB Link или GBA Link.

### Использование

1. Подключите Game Boy к Raspberry Pi Pico согласно схеме подключения
2. Подключите Pico к компьютеру через USB
3. Откройте браузер и перейдите на [tetris.gblink.io](https://tetris.gblink.io/)
4. Начните игру!

### Оригинальный проект

- **Автор оригинальной идеи:** [stacksmashing](https://github.com/stacksmashing)
- **Оригинальный репозиторий:** [gb-link-firmware](https://github.com/stacksmashing/gb-link-firmware)
- **Оригинальное видео:** [YouTube](https://youtu.be/KtHu693wE9o?si=Lg1wDW6jH2z7b86g)

### Лицензия

Этот проект использует GNU General Public License v3.0. См. файл [LICENSE](LICENSE) для подробностей.

---

## 🇬🇧 English

### Description

This is a fork of the [GB Link](https://github.com/stacksmashing/gb-link-firmware) firmware by [stacksmashing](https://github.com/stacksmashing), modified specifically for the [Dmitry Bachilo Computer Museum](https://t.me/retro_museum) in Novosibirsk.

The firmware turns a Raspberry Pi Pico into a USB adapter for the Game Boy Link Cable, allowing you to play online Tetris at [tetris.gblink.io](https://tetris.gblink.io/).

### Wiring

![Wiring Diagram](docs/wiring-diagram.png)

#### GPIO Pinout for Raspberry Pi Pico:

| Pico Pin | Function | Description |
|----------|----------|-------------|
| GPIO 9   | SCK (PSC) | Serial Clock |
| GPIO 10  | SIN (PSI) | Serial In |
| GPIO 13  | SOUT (PSO)| Serial Out |
| GPIO 14  | SI (PSD)  | Serial Data |
| GPIO 16  | LED       | Built-in LED |
| GPIO 6   | TEST_PIN  | Test pin (optional) |

### Building

#### Requirements

- Raspberry Pi Pico SDK
- CMake (version 3.13 or higher)
- GCC compiler for ARM

#### Build Instructions

1. Clone the repository:
```bash
git clone <repository-url>
cd gb-link-firmware-reconfigurable
```

2. Install Raspberry Pi Pico SDK:
```bash
# Set the PICO_SDK_PATH environment variable
export PICO_SDK_PATH=/path/to/pico-sdk
```

3. Create build directory:
```bash
mkdir build
cd build
```

4. Run CMake:
```bash
cmake ..
```

5. Build the project:
```bash
make
```

6. The firmware will be in `gbusb.uf2` in the `build/` directory

### Flashing the Firmware

1. Hold the BOOTSEL button on the Raspberry Pi Pico
2. Connect the Pico to your computer via USB
3. Open the RPI-RP2 drive that appears
4. Copy the `gbusb.uf2` file to this drive
5. The Pico will automatically reboot with the new firmware

### Making Your Own Connector

If you don't have a GB Link cable, you can print the 3D models from the `models/` folder and use Dupont wires to create your own GB Link or GBA Link connector.


### Usage

1. Connect your Game Boy to the Raspberry Pi Pico according to the wiring diagram
2. Connect the Pico to your computer via USB
3. Open a browser and navigate to [tetris.gblink.io](https://tetris.gblink.io/)
4. Start playing!

### Original Project

- **Original Author:** [stacksmashing](https://github.com/stacksmashing)
- **Original Repository:** [gb-link-firmware](https://github.com/stacksmashing/gb-link-firmware)
- **Original Video:** [YouTube](https://youtu.be/KtHu693wE9o?si=Lg1wDW6jH2z7b86g)

### License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

---

**Создано для / Created for:** [Музей Вычислительной Техники Дмитрия Бачило](https://t.me/retro_museum) | [Dmitry Bachilo Computer Museum](https://t.me/retro_museum)
