# arduino-control

Moderní webové ovládací centrum pro Arduino a kompatibilní mikrokontroléry.

arduino-control nabízí přehledný dashboard, správu hardwaru, sériovou komunikaci, automatizace, profily a speciální heslem chráněné BOSS MENU.

---

## ✨ Funkce

### 📊 Dashboard
- Přehled připojeného zařízení
- Stav digitálních výstupů
- Informace o sériovém připojení
- Doba běhu aplikace
- Rychlé ovládání LED, relé, RGB a PWM

### 🔌 Hardware Control
- LED ON / OFF
- Relay control
- RGB LED controller
- Nastavení jasu
- Servo motor (0–180°)
- PWM výstup (0–255)
- Režimy osvětlení

### 🎛️ Pin Manager
- Přehled digitálních pinů
- Ruční nastavení HIGH / LOW
- Omezení na povolené piny
- Ovládání přes sériový protokol

### ⚙️ Automation
- Startup sequence
- Shutdown sequence
- Status check
- RGB test
- Vlastní příkazové sekvence
- Nastavitelná prodleva mezi příkazy

### 💾 Profiles
- Ukládání konfigurací
- Načítání profilů
- Mazání profilů
- Lokální ukládání v prohlížeči

### 📈 Sensors
- Analog input A0
- Analog input A1
- Analog input A2
- Zobrazení hodnot ADC (0–1023)
- Historie naměřených hodnot

### 🖥️ Serial Terminal
- Odesílání vlastních příkazů
- Zobrazení odpovědí Arduina
- Časové značky
- Mazání terminálu
- Automatické posouvání na nové zprávy

### ♛ BOSS MENU
- Heslem chráněné administrátorské menu
- Device Ping
- LED Override
- RGB efekty
- Command Center
- Pin Override
- System Diagnostics
- Emergency Stop

**Doporučení:** Změň si ho přímo v souboru `index.html`.

Pozor: BOSS MENU je pouze klientská ochrana rozhraní. Heslo je součástí veřejného JavaScriptu, takže nejde o skutečné zabezpečení zařízení.

---

## 🎨 Design

- Forest Green
- Graphite Grey
- Sage Grey
- Warm Sand
- Font Inter
- JetBrains Mono pro terminál
- Responzivní rozložení
- Desktop i mobilní zařízení

---

## 🚀 Instalace a spuštění

### 1. GitHub repository

Vytvoř nový GitHub repository nebo otevři existující.

### 2. Nahraj soubory

V repozitáři by měla být tato struktura:

```text
NEBULA-CONTROL/
│
├── index.html
├── README.md
└── LICENSE
```

`LICENSE` je volitelný soubor.

### 3. Zapni GitHub Pages

1. Otevři repository.
2. Přejdi do Settings.
3. Otevři Pages.
4. V části Build and deployment vyber Deploy from a branch.
5. Vyber branch `main`.
6. Vyber složku `/ (root)`.
7. Klikni na Save.

Po dokončení bude aplikace dostupná na adrese:

`https://TVUJ-USERNAME.github.io/NAZEV-REPOSITORY/`

---

## 🔗 Připojení Arduina

Aplikace využívá Web Serial API.

Podporované prostředí:
- Google Chrome
- Microsoft Edge
- Další kompatibilní Chromium prohlížeče

Je potřeba:
- HTTPS nebo localhost
- USB kabel s datovým přenosem
- Arduino nebo kompatibilní zařízení
- Nahraný kompatibilní firmware

### Postup

1. Připoj Arduino přes USB.
2. Otevři arduino-control.
3. Klikni na Connect.
4. Vyber správný sériový port.
5. Nastav baud rate.
6. Potvrď připojení.

Výchozí baud rate je `9600`.

---

## 📡 Sériový protokol

Aplikace používá jednoduché textové příkazy zakončené novým řádkem.

| Příkaz | Funkce |
|---|---|
| `PING` | Test komunikace |
| `LED:1` | Zapnutí LED |
| `LED:0` | Vypnutí LED |
| `RELAY1:1` | Zapnutí relé |
| `RELAY1:0` | Vypnutí relé |
| `RGB:255,0,0` | Nastavení RGB |
| `SERVO:90` | Nastavení serva |
| `PWM:128` | Nastavení PWM |
| `MODE:BREATHING` | Efekt dýchání |
| `MODE:PARTY` | Party efekt |
| `MODE:OFF` | Vypnutí efektů |
| `PIN:5:1` | Nastavení pinu HIGH |
| `PIN:5:0` | Nastavení pinu LOW |

Arduino může posílat analogové hodnoty například:

```text
A0:428
A1:612
A2:205
```

Odpověď na `PING`:

```text
PONG
```

---

## 🧪 Demo Mode

Pokud nemáš Arduino připojené, můžeš používat Demo Mode.

Demo Mode umožňuje:
- Prohlížet dashboard
- Vyzkoušet ovládací prvky
- Testovat automatizace
- Ukládat profily
- Používat terminálovou simulaci
- Zobrazovat simulované analogové hodnoty

**Důležité:** Simulovaná data nejsou skutečné hodnoty ze senzorů.

---

## ⚠️ Bezpečnost

- Před připojením relé zkontroluj jeho napájení a zapojení.
- Nepřipojuj zařízení s vyšším napětím přímo na Arduino piny.
- Servo může potřebovat samostatné napájení.
- Před použitím Pin Manageru zkontroluj konflikty pinů.
- Emergency Stop je softwarová sekvence příkazů, nikoliv hardwarové nouzové odpojení.
- BOSS MENU není bezpečnostní autentizace.
- Nikdy nevystavuj citlivá zařízení veřejnému přístupu bez dalšího zabezpečení.

---

## 🛠️ Technologie

- HTML5
- CSS3
- Vanilla JavaScript
- Web Serial API
- Arduino C++
- Local Storage
- GitHub Pages

Žádný framework ani instalace balíčků nejsou potřeba.

---

## 📌 Verze

**arduino-control**

Version: `1.0.0`

Status: Development

---

## 💚 Autor

Created for Arduino hardware control and experimentation.

**arduino-control**

*Simple interface. Full control.*
