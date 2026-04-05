# zmk-sweep-ru — Ferris Sweep Config for Linux + Russian

Based on [duckyb/zmk-sweep](https://github.com/duckyb/zmk-sweep) structure.  
Adapted for: **Linux (Pop!_OS)** | **English + Russian** | **Mouse-free workflow**

Hardware: Ferris Sweep v2.2 · nice!nano v2 · ZMK · Kailh Choc v1

---

## Layer Map

```
KEY POSITIONS:
 0  1  2  3  4      5  6  7  8  9
10 11 12 13 14     15 16 17 18 19
20 21 22 23 24     25 26 27 28 29
            30 31  32 33
```

### 0 · BASE

```
Q  W  E  R  T      Y  U  I  O  P
A  S  D  F  G      H  J  K  L  '
Z  X  C  V  B      N  M  ,  .  /
      [NAV/SPC] [⇧]   [⇧] [SYM/SPC]
```

### 1 · NAV (hold left thumb)

```
Search  WS1  WS2  WS3  Term     PgUp  Home  ↑     End   Bspc
Lock    ←■   □▲   ■→   Close    PgDn  ←     ↓     →     Enter
Ctrl Alt Shft Gui Mv1   Mv2   Mv3   Tab   Esc   Del
             [held]  [ ]      [ ]  [FUN]
```

Left hand controls Linux desktop (Super+key shortcuts).  
Right hand is pure navigation — arrows, page, home/end.

### 2 · SYM (hold right thumb)

```
!  @  #  $  %      ^  &  *  (  )
-  =  [  ]  \      `  ;  :  ~  |
_  +  {  }  /      ?  <  >  "  &
      [NUM] [ ]     [ ] [held]
```

### 3 · NUM (NAV+SYM together → hold both thumbs)

```
F1  F2  F3  F4  F5     F6  F7  F8  F9  F10
1   2   3   4   5      6   7   8   9   0
F11 F12 -   =   .      ,   *   /   +   -
```

### 4 · FUN (NAV layer → right thumb)

```
BT0  BT1  BT2  BT3  BT_CLR    Mute  Vol-  Vol+  Play  Stop
OutTog  -    -    -   Reset     Prev  Next  PrtSc ScLk  Pause
Boot    -    -    -     -         -     -     -     -   Boot
```

### 5 · MOUSE (combo: V+B to toggle)

```
-  -  -  -  -      ScrollUp   MB4  MouseUp    MB5  ScrollUp
-  -  -  -  -      ScrollDn   ←    MouseDn    →    ScrollDn
-  -  -  -  -         -       LClick MClick RClick   -
      [toggle off] [ ]        [LClick] [RClick]
```

---

## Combos

| Combo | Keys | Output |
|-------|------|--------|
| ESC | Q+W | Escape |
| TAB | A+S | Tab |
| ENTER | J+K | Return |
| BSPC | U+I | Backspace |
| DEL | I+O | Delete |
| CAPS_WORD | F+J | Caps Word |
| MOUSE toggle | V+B | Toggle mouse layer |
| EN/RU switch | inner thumbs (31+32) | Shift+Alt (switches OS layout) |

---

## Russian Input

Russian layout is handled by the **OS** (Pop!_OS / IBus / fcitx).  
Switch with the combo on inner thumb keys → sends `Shift+Alt` to OS.

Set your OS input method shortcut to `Shift+Alt` for this to work.  
In GNOME: Settings → Keyboard → Input Sources → add Russian, set shortcut.

---

## Linux Shortcuts (NAV layer, left hand)

| Key | Action |
|-----|--------|
| Super+Space | App launcher |
| Super+L | Lock screen |
| Super+T | Terminal |
| Super+1/2/3 | Switch workspace |
| Super+Shift+1/2/3 | Move window to workspace |
| Super+←/→ | Snap window left/right |
| Super+↑ | Maximize window |
| Alt+F4 | Close window |

Adjust these in the keymap `#define` section to match your desktop shortcuts.

---

## Setup

1. Fork this repo on GitHub
2. GitHub Actions will build firmware automatically on every push to `config/`
3. Download artifacts: `cradio_left-nice_nano_v2.uf2` and `cradio_right-nice_nano_v2.uf2`
4. Flash: hold reset button → controller appears as USB drive → drag .uf2 file

Flash left half first, then right half.

---

## Tuning

- **Combo timing**: edit `COMBO_TERM` in keymap (default 40ms — fast typists can go lower)
- **Sticky key timeout**: `release-after-ms` in `skq` behavior (default 1000ms)
- **Linux shortcuts**: edit the `#define LX_*` lines at the top of `cradio.keymap`
- **RU switch shortcut**: change `LX_LANG` define to match your OS setting
