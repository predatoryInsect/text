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
