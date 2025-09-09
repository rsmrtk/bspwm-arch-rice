# BSPWM Arch Rice Configuration

*Switch to: [🇺🇦 Українська](#ukrainian-version) | [🇺🇸 English](#english-version)*

---

## English Version

### 🚀 Overview

This is a customized **BSPWM** (Binary Space Partitioning Window Manager) rice for Arch Linux featuring a modern, minimal dark theme with **Polybar** integration.

#### 🎨 **Features**
- **Window Manager**: BSPWM with custom configuration
- **Status Bar**: Polybar with custom modules
- **Terminal**: Kitty terminal emulator
- **Application Launcher**: Rofi
- **Compositor**: Picom for transparency and effects
- **Notifications**: Dunst notification daemon
- **Color Scheme**: Dark theme with purple accents

---

### ⚙️ **System Configuration**

#### 📺 **Display Setup**
- **External Monitor** (DP-0): Workspaces 1-7
- **Laptop Screen** (eDP-1-2): Workspaces 8-14
- **Window Gaps**: 17px
- **Border Width**: 2px
- **Focus Follows Pointer**: Enabled

#### 🎯 **Window Rules**
- **feh** (image viewer): Floating window
- **Border Colors**: 
  - Focused: `#7899FA` (Blue)
  - Normal: `#1f222b` (Dark)
  - Active: `#bd93f9` (Purple)

---

### 🔥 **Hotkeys & Controls**

#### 🖥️ **System Controls**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Super + Escape + R` | Reload sxhkd | Reload hotkey configuration |
| `Ctrl + Shift + Q` | Quit BSPWM | Exit window manager |
| `Ctrl + Shift + R` | Restart BSPWM | Restart window manager |
| `Super + P` | Toggle Polybar | Show/Hide status bar |

#### 🖱️ **Applications**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Super + Return` | Terminal | Launch Kitty terminal |
| `Super + D` | App Launcher | Open Rofi application menu |
| `Super + X` | Power Menu | System power options |
| `Super + W` | Random Wallpaper | Set random wallpaper |
| `Alt + Shift` | Language Toggle | Switch keyboard layout |
| `Print` | Screenshot | Take screenshot with Flameshot |

#### 🚀 **Quick Launch Apps**
| Hotkey | Application |
|--------|-------------|
| `Super + Shift + F` | Firefox |
| `Super + Shift + N` | Thunar (File Manager) |
| `Super + Shift + P` | Pavucontrol (Audio) |
| `Super + Shift + T` | Telegram |
| `Super + Shift + C` | VS Code |
| `Super + Shift + V` | VirtualBox |
| `Super + Shift + I` | Firefox Private |
| `Super + Shift + X` | Color Picker |
| `Super + Shift + Q` | Bible App |
| `Super + Shift + K` | Calendar |
| `Super + Shift + L` | Screen Lock |

#### 🪟 **Window Management**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Super + C` | Close Window | Close focused window |
| `Super + Space` | Toggle Floating | Float/tile window |
| `Super + T` | Tiled Mode | Set window to tiled |
| `Super + Ctrl + T` | Pseudo-tiled | Set pseudo-tiled mode |
| `Super + F` | Fullscreen | Toggle fullscreen |
| `Alt + Tab` | Next Window | Focus next window |
| `Alt + Shift + Tab` | Previous Window | Focus previous window |
| `Super + G` | Biggest Window | Swap with biggest window |

#### 🔄 **Window Movement**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Super + H/J/K/L` | Focus Direction | Move focus (left/down/up/right) |
| `Super + Shift + H/J/K/L` | Move Window | Move window in direction |
| `Super + Ctrl + H/J/K/L` | Resize Window | Resize window borders |

#### 🏢 **Workspaces**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Super + 1-9,0` | Switch Workspace | Go to workspace 1-10 |
| `Super + Shift + 1-9,0` | Move to Workspace | Send window to workspace |
| `Super + Grave` | Last Window | Focus last window |
| `Super + Tab` | Last Workspace | Switch to last workspace |

#### 🎚️ **Media Controls**
| Hotkey | Action | Description |
|--------|---------|-------------|
| `Volume Up Key` | Increase Volume | Raise system volume |
| `Volume Down Key` | Decrease Volume | Lower system volume |
| `Mute Key` | Toggle Mute | Mute/unmute audio |
| `Brightness Up Key` | Increase Brightness | Raise screen brightness |
| `Brightness Down Key` | Decrease Brightness | Lower screen brightness |

---

### 📊 **Polybar Modules**

#### 🖱️ **Clickable Modules**
- **📁 File Manager** (Left): Opens Rofi application launcher
- **🌐 WiFi Icon**: Opens WiFi connection menu
- **🔋 Power Icon** (Right): Opens power menu (Lock/Logout/Suspend/Reboot/Shutdown)

#### 📈 **Information Modules**
- **🖥️ Workspaces**: BSPWM workspace indicator with colors
- **🌡️ Temperature**: CPU temperature (real-time)
- **💾 Memory**: RAM usage in GB
- **⚡ CPU**: CPU usage percentage
- **🔋 Battery**: Battery level with charging status
- **🔆 Brightness**: Screen brightness level
- **🔊 Volume**: Audio volume with mute indicator
- **⌨️ Keyboard**: Current keyboard layout
- **🕐 Time**: Current time and date

---

### 🛠️ **File Structure**

```
~/.config/
├── bspwm/
│   ├── bspwmrc              # Main BSPWM configuration
│   ├── scripts/launch.sh    # Startup scripts
│   ├── dunstrc             # Notification settings
│   └── picom_configurations/1.conf  # Compositor settings
├── sxhkd/
│   └── sxhkdrc             # Hotkey definitions
└── polybar/
    ├── config.ini          # Polybar main config
    ├── modules.ini         # Module definitions
    ├── colors.ini          # Color scheme
    └── launch.sh           # Polybar startup script

~/bin/ (or ~/bspwm-dotfiles/bin/)
├── wifimenu                # WiFi connection manager
├── powermenu               # Power management menu
├── volume                  # Volume control script
├── brightness              # Brightness control
├── weather                 # Weather information
├── screen-lock             # Screen locker
└── random_wallpaper        # Wallpaper changer
```

---

### 🔧 **Dependencies**

#### Required Packages:
```bash
# Core WM
bspwm sxhkd polybar

# Applications
kitty rofi firefox thunar

# Media & Utils  
flameshot picom dunst redshift
pavucontrol telegram-desktop code

# Fonts
ttf-jetbrains-mono-nerd

# Network
networkmanager
```

---

### 🚨 **Troubleshooting**

#### Modules Not Clickable?
```bash
# Fix script permissions
chmod +x ~/bspwm-dotfiles/bin/{wifimenu,powermenu}
ln -sf ~/bspwm-dotfiles/bin/wifimenu ~/bin/
ln -sf ~/bspwm-dotfiles/bin/powermenu ~/bin/
```

#### Temperature Shows Wrong Value?
```bash
# Check thermal zones
ls /sys/class/thermal/
# Edit polybar modules.ini thermal-zone value
```

#### Polybar Not Showing?
```bash
# Restart polybar
killall polybar && ~/.config/polybar/launch.sh
```

---

## Ukrainian Version

### 🚀 Огляд

Це кастомізована **BSPWM** (Binary Space Partitioning Window Manager) конфігурація для Arch Linux з сучасною мінімальною темною темою та інтеграцією **Polybar**.

#### 🎨 **Особливості**
- **Віконний менеджер**: BSPWM з користувацькою конфігурацією
- **Статус бар**: Polybar з кастомними модулями
- **Термінал**: Емулятор терміналу Kitty
- **Лаунчер**: Rofi для запуску програм
- **Композітор**: Picom для прозорості та ефектів
- **Сповіщення**: Dunst daemon для нотифікацій
- **Колірна схема**: Темна тема з фіолетовими акцентами

---

### ⚙️ **Конфігурація системи**

#### 📺 **Налаштування дисплеїв**
- **Зовнішній монітор** (DP-0): Робочі столи 1-7
- **Екран ноутбука** (eDP-1-2): Робочі столи 8-14
- **Відступи між вікнами**: 17px
- **Ширина рамки**: 2px
- **Фокус слідує за мишкою**: Увімкнено

#### 🎯 **Правила для вікон**
- **feh** (переглядач зображень): Плаваюче вікно
- **Кольори рамок**: 
  - Активне: `#7899FA` (Синій)
  - Звичайне: `#1f222b` (Темний)
  - Вибране: `#bd93f9` (Фіолетовий)

---

### 🔥 **Гарячі клавіші та управління**

#### 🖥️ **Системні команди**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Super + Escape + R` | Перезавантаження sxhkd | Оновити конфігурацію клавіш |
| `Ctrl + Shift + Q` | Вихід з BSPWM | Закрити віконний менеджер |
| `Ctrl + Shift + R` | Перезапуск BSPWM | Перезавантажити віконний менеджер |
| `Super + P` | Перемикач Polybar | Показати/сховати статус бар |

#### 🖱️ **Програми**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Super + Return` | Термінал | Запустити Kitty термінал |
| `Super + D` | Лаунчер програм | Відкрити Rofi меню програм |
| `Super + X` | Меню живлення | Опції управління живленням |
| `Super + W` | Випадкові шпалери | Встановити випадкові шпалери |
| `Alt + Shift` | Переключення мови | Змінити розкладку клавіатури |
| `Print` | Скриншот | Зробити знімок екрану з Flameshot |

#### 🚀 **Швидкий запуск програм**
| Комбінація | Програма |
|------------|----------|
| `Super + Shift + F` | Firefox |
| `Super + Shift + N` | Thunar (файловий менеджер) |
| `Super + Shift + P` | Pavucontrol (звук) |
| `Super + Shift + T` | Telegram |
| `Super + Shift + C` | VS Code |
| `Super + Shift + V` | VirtualBox |
| `Super + Shift + I` | Firefox приватний |
| `Super + Shift + X` | Вибір кольору |
| `Super + Shift + Q` | Біблія |
| `Super + Shift + K` | Календар |
| `Super + Shift + L` | Блокування екрану |

#### 🪟 **Управління вікнами**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Super + C` | Закрити вікно | Закрити активне вікно |
| `Super + Space` | Переключити плавання | Плаваюче/плиткове вікно |
| `Super + T` | Плитковий режим | Встановити плиткове вікно |
| `Super + Ctrl + T` | Псевдо-плиткове | Встановити псевдо-плитковий режим |
| `Super + F` | Повний екран | Переключити повноекранний режим |
| `Alt + Tab` | Наступне вікно | Фокус на наступне вікно |
| `Alt + Shift + Tab` | Попереднє вікно | Фокус на попереднє вікно |
| `Super + G` | Найбільше вікно | Поміняти з найбільшим вікном |

#### 🔄 **Переміщення вікон**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Super + H/J/K/L` | Напрямок фокусу | Перемістити фокус (ліво/вниз/вгору/право) |
| `Super + Shift + H/J/K/L` | Перемістити вікно | Перемістити вікно в напрямку |
| `Super + Ctrl + H/J/K/L` | Змінити розмір | Змінити розмір вікна |

#### 🏢 **Робочі столи**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Super + 1-9,0` | Перейти до столу | Перейти до робочого столу 1-10 |
| `Super + Shift + 1-9,0` | Перемістити на стіл | Відправити вікно на робочий стіл |
| `Super + Grave` | Останнє вікно | Фокус на останнє вікно |
| `Super + Tab` | Останній стіл | Переключитися на останній стіл |

#### 🎚️ **Медіа управління**
| Комбінація | Дія | Опис |
|------------|-----|------|
| `Клавіша Гучності +` | Збільшити гучність | Підвищити системну гучність |
| `Клавіша Гучності -` | Зменшити гучність | Знизити системну гучність |
| `Клавіша Вимкнути` | Переключити звук | Вимкнути/увімкнути звук |
| `Клавіша Яскравості +` | Збільшити яскравість | Підвищити яскравість екрану |
| `Клавіша Яскравості -` | Зменшити яскравість | Знизити яскравість екрану |

---

### 📊 **Модулі Polybar**

#### 🖱️ **Інтерактивні модулі**
- **📁 Файловий менеджер** (Ліворуч): Відкриває Rofi лаунчер
- **🌐 Іконка WiFi**: Відкриває меню підключення до WiFi
- **🔋 Іконка живлення** (Праворуч): Відкриває меню живлення (Блокування/Вихід/Сон/Перезавантаження/Вимкнення)

#### 📈 **Інформаційні модулі**
- **🖥️ Робочі столи**: Індикатор робочих столів BSPWM з кольорами
- **🌡️ Температура**: Температура процесора (в реальному часі)
- **💾 Пам'ять**: Використання RAM в ГБ
- **⚡ CPU**: Відсоток використання процесора
- **🔋 Батарея**: Рівень заряду з індикатором зарядки
- **🔆 Яскравість**: Рівень яскравості екрану
- **🔊 Гучність**: Гучність звуку з індикатором вимкнення
- **⌨️ Клавіатура**: Поточна розкладка клавіатури
- **🕐 Час**: Поточний час та дата

---

### 🛠️ **Структура файлів**

```
~/.config/
├── bspwm/
│   ├── bspwmrc              # Основна конфігурація BSPWM
│   ├── scripts/launch.sh    # Скрипти запуску
│   ├── dunstrc             # Налаштування сповіщень
│   └── picom_configurations/1.conf  # Налаштування композітора
├── sxhkd/
│   └── sxhkdrc             # Визначення гарячих клавіш
└── polybar/
    ├── config.ini          # Основна конфігурація Polybar
    ├── modules.ini         # Визначення модулів
    ├── colors.ini          # Колірна схема
    └── launch.sh           # Скрипт запуску Polybar

~/bin/ (або ~/bspwm-dotfiles/bin/)
├── wifimenu                # Менеджер WiFi підключень
├── powermenu               # Меню управління живленням
├── volume                  # Скрипт управління гучністю
├── brightness              # Управління яскравістю
├── weather                 # Інформація про погоду
├── screen-lock             # Блокування екрану
└── random_wallpaper        # Зміна шпалер
```

---

### 🔧 **Залежності**

#### Необхідні пакети:
```bash
# Основний WM
bspwm sxhkd polybar

# Програми
kitty rofi firefox thunar

# Медіа та утиліти
flameshot picom dunst redshift
pavucontrol telegram-desktop code

# Шрифти
ttf-jetbrains-mono-nerd

# Мережа
networkmanager
```

---

### 🚨 **Усунення неполадок**

#### Модулі не реагують на кліки?
```bash
# Виправити права доступу до скриптів
chmod +x ~/bspwm-dotfiles/bin/{wifimenu,powermenu}
ln -sf ~/bspwm-dotfiles/bin/wifimenu ~/bin/
ln -sf ~/bspwm-dotfiles/bin/powermenu ~/bin/
```

#### Температура показує неправильне значення?
```bash
# Перевірити термальні зони
ls /sys/class/thermal/
# Відредагувати значення thermal-zone в polybar modules.ini
```

#### Polybar не відображається?
```bash
# Перезапустити polybar
killall polybar && ~/.config/polybar/launch.sh
```

---

### 📝 **Примітки**

- Конфігурація оптимізована для dual-monitor setup
- Використовуються Nerd Fonts для правильного відображення іконок
- Всі скрипти знаходяться в `~/bspwm-dotfiles/bin/`
- Для коректної роботи потрібні символічні посилання в `~/bin/`

---

**Створено для Arch Linux + BSPWM** 🐧