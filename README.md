# text
text-test
```
[main]
font=JetBrains Mono:size=11
icons-enabled=yes

# Указываем нашу новую тему Gruvbox!
icon-theme=Gruvbox-Plus-Dark

prompt="❯  "
terminal=foot -e

width=35
lines=10
horizontal-pad=20
vertical-pad=15
inner-pad=10
image-size-ratio=0.5
layer=overlay

[colors]
# Оригинальная палитра Gruvbox Dark (с лёгкой полупрозрачностью)
# 282828dd — фирменный тёмно-серый фон Gruvbox (dd = ~85% opacity)
background=282828dd

# Текст (ebdbb2 — светлый бежевый)
text=ebdbb2ff
input=ebdbb2ff

# Промпт ❯ и совпадения (fe8019 — сочный оранжевый)
prompt=fe8019ff
match=fe8019ff

# Подсказки (928374 — серый)
placeholder=928374ff

# Выделенный элемент (3c3836 — подложка, fabd2f — жёлтый акцент совпадений)
selection=3c3836ff
selection-text=ebdbb2ff
selection-match=fabd2fff

# Рамка окна (fe8019 — оранжевый акцент)
border=fe8019ff

[border]
width=2
radius=10

```

```
[key-bindings]
# Перемещение вниз по списку (Down или Ctrl+j или Ctrl+n)
next=Down Control+n Control+j

# Перемещение вверх по списку (Up или Ctrl+k или Ctrl+p)
prev=Up Control+p Control+k

# Очистить всю строку ввода
delete-line=Control+u

# Удалить одно слово назад
delete-prev-word=Control+BackSpace Control+w

# Закрыть Fuzzel
cancel=Escape Control+g

```

```
curl -fLo /tmp/JetBrainsMono.zip https://github.com/ryanoasis/nerd-fonts/releases/latest/download/JetBrainsMono.zip
unzip /tmp/JetBrainsMono.zip -d ~/.local/share/fonts/JetBrainsMono/
rm /tmp/JetBrainsMono.zip
```
```
"layer": "top",
    "position": "top",
    "height": 32,
    "margin-top": 6,
    "margin-left": 10,
    "margin-right": 10,
    "spacing": 8,

    // Модули слева, по центру и справа
    "modules-left": ["sway/workspaces", "sway/mode", "sway/window"],
    "modules-center": ["clock"],
    "modules-right": ["pulseaudio", "sway/language", "battery", "tray"],

    // --- НАСТРОЙКА МОДУЛЕЙ ---

    "sway/workspaces": {
        "disable-scroll": true,
        "all-outputs": true,
        "format": "{icon}",
        "format-icons": {
            "1": "1",
            "2": "2",
            "3": "3",
            "4": "4",
            "5": "5",
            "urgent": " ",
            "focused": " ",
            "default": " "
        }
    },

    "sway/mode": {
        "format": "<span style=\"italic\">{}</span>"
    },

    "sway/window": {
        "format": "{title}",
        "max-length": 40,
        "separate-outputs": true
    },

    "clock": {
        "interval": 1,
        "format": " {:%H:%M}",
        "format-alt": " {:%A, %d %B %Y г. (%H:%M:%S)}",
        "tooltip-format": "<tt><small>{calendar}</small></tt>",
        "calendar": {
            "mode"          : "year",
            "mode-mon-col"  : 3,
            "weeks-pos"     : "right",
            "on-scroll"     : 1,
            "format": {
                "months":     "<span color='#ffead3'><b>{}</b></span>",
                "days":       "<span color='#ecc6d9'><b>{}</b></span>",
                "weeks":      "<span color='#99ffdd'><b>W{}</b></span>",
                "weekdays":   "<span color='#ffcc66'><b>{}</b></span>",
                "today":      "<span color='#ff6666'><b><u>{}</u></b></span>"
            }
        }
    },

    "pulseaudio": {
        "format": "{icon} {volume}%",
        "format-bluetooth": " {volume}%",
        "format-muted": " Muted",
        "format-icons": {
            "headphone": "",
            "hands-free": "",
            "headset": "",
            "phone": "",
            "portable": "",
            "car": "",
            "default": ["", "", ""]
        },
        "on-click": "pavucontrol" // запуск микшера по клику (если установлен)
    },

    "sway/language": {
        "format": " {}",
        "min-length": 5,
        "tooltip": false
    },

    "battery": {
        "states": {
            "warning": 30,
            "critical": 15
        },
        "format": "{icon} {capacity}%",
        "format-charging": " {capacity}%",
        "format-plugged": " {capacity}%",
        "format-icons": ["", "", "", "", ""]
    },

    "tray": {
        "icon-size": 16,
        "spacing": 10
    }
}
```

```
/* Палитра Catppuccin Mocha */
@define-color base      #1e1e2e;
@define-color mantle    #181825;
@define-color crust     #11111b;
@define-color text      #cdd6f4;
@define-color subtext0  #a6adc8;
@define-color surface0  #313244;
@define-color surface1  #45475a;

@define-color lavender #b4befe;
@define-color blue     #89b4fa;
@define-color sapphire #74c7ec;
@define-color sky      #89dceb;
@define-color red      #f38ba8;
@define-color green    #a6e3a1;
@define-color yellow   #f9e2af;

* {
    border: none;
    border-radius: 0;
    font-family: "JetBrainsMono Nerd Font", "Font Awesome 6 Free", Roboto, Helvetica, Arial, sans-serif;
    font-size: 13px;
    font-weight: bold;
    min-height: 0;
}

/* Сам бар делается прозрачным, плавают только капсулы */
window#waybar {
    background-color: transparent;
    color: @text;
}

/* Общий стиль для всех блоков-капсул */
#workspaces,
#mode,
#window,
#clock,
#pulseaudio,
#language,
#battery,
#tray {
    background-color: @base;
    padding: 2px 12px;
    border-radius: 12px;
    border: 1px solid @surface0;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

/* --- ВОРКСПЕЙСЫ --- */
#workspaces button {
    padding: 0 5px;
    color: @subtext0;
    background-color: transparent;
    border-radius: 8px;
    transition: all 0.2s ease-in-out;
}

#workspaces button:hover {
    background-color: @surface0;
    color: @text;
}

#workspaces button.focused {
    color: @lavender;
    background-color: @surface1;
}

#workspaces button.urgent {
    color: @red;
}

/* --- МОДУЛИ ПО ОТДЕЛЬНОСТИ --- */

#window {
    color: @subtext0;
    font-weight: normal;
}

#clock {
    color: @sapphire;
    font-size: 14px;
}

#pulseaudio {
    color: @green;
}

#pulseaudio.muted {
    color: @red;
}

#language {
    color: @yellow;
}

#battery {
    color: @sky;
}

#battery.warning {
    color: @yellow;
}

#battery.critical:not(.charging) {
    color: @red;
    animation-name: blink;
    animation-duration: 0.5s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    animation-direction: alternate;
}

#tray {
    padding-right: 12px;
    padding-left: 12px;
}

#tray > .passive {
    -gtk-icon-effect: dim;
}

#tray > .needs-attention {
    -gtk-icon-effect: highlight;
}

/* Анимация мигания разряженной батареи */
@keyframes blink {
    to {
        background-color: @red;
        color: @base;
    }
}
```

```
{
    "layer": "top",
    "position": "top",
    "height": 32,
    "margin-top": 6,
    "margin-left": 10,
    "margin-right": 10,
    "spacing": 8,

    "modules-left": ["sway/workspaces", "sway/mode"],
    "modules-center": ["clock"],
    "modules-right": ["pulseaudio", "sway/language", "battery", "tray"],

    "sway/workspaces": {
        "disable-scroll": true,
        "all-outputs": true,
        "format": "{name}"
    },

    "clock": {
        "interval": 1,
        "format": " {:%H:%M}",
        "format-alt": " {:%A, %d %B %Y г.}"
    },

    "pulseaudio": {
        "format": "🔊 {volume}%",
        "format-bluetooth": "󰂯 {volume}%",
        "format-muted": "🔇 Muted"
    },

    "sway/language": {
        "format": "🌐 {}",
        "min-length": 5
    },

    "battery": {
        "states": {
            "warning": 30,
            "critical": 15
        },
        "format": "🔋 {capacity}%",
        "format-charging": "⚡ {capacity}%"
    },

    "tray": {
        "icon-size": 16,
        "spacing": 10
    }
}
```
```
* {
    /* Порядок важен: сначала ваш основной шрифт, затем шрифты с иконками */
    font-family: "JetBrainsMono Nerd Font", "Font Awesome 6 Free", "Font Awesome 6 Brands", Roboto, sans-serif;
    font-size: 13px;
    font-weight: bold;
}
```

```
/* Moon Forest */

* {
    border: none;
    border-radius: 0;
    min-height: 0;

    font-family: JetBrainsMono Nerd Font;
    font-size: 13px;
}

window#waybar {
    background: #0b0f0d;
    color: #d8ddd8;
}

/* Рабочие столы */

#workspaces {
    margin-left: 8px;
}

#workspaces button {
    color: #6d766f;
    padding: 0 10px;
    transition: none;
}

#workspaces button.active {
    color: #a4c8a8;
    background: #111715;
}

#workspaces button:hover {
    background: #161d1a;
    color: #a4c8a8;
}

/* Часы */

#clock {
    color: #d8ddd8;
    font-weight: bold;
    padding: 0 16px;
}

/* Язык */

#language {
    color: #7ea68a;
    padding: 0 10px;
}

/* Caps Lock */

#custom-capslock {
    color: #a4c8a8;
    font-weight: bold;
    padding-right: 10px;
}

/* Батарея */

#battery {
    color: #d8ddd8;
    padding: 0 10px;
}

#battery.warning {
    color: #c6b07f;
}

#battery.critical {
    color: #b06a6a;
}

/* Кнопка питания */

#custom-power {
    color: #7ea68a;
    font-size: 16px;
    padding-left: 12px;
    padding-right: 12px;
}

#custom-power:hover {
    color: #a4c8a8;
}
```
