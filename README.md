
# arduino-control V2.0

České webové ovládací centrum pro Arduino.

arduino-control kombinuje čistý technický vzhled, útulnou barevnou paletu a přehledné ovládání hardwaru.

## Obsah projektu

- `index.html` – webové rozhraní
- `nebula_control.ino` – firmware pro Arduino
- `README.md` – dokumentace

## Funkce

- Přehledový dashboard
- Ovládání digitálních pinů
- LED a relé
- RGB světlo
- Servo motor
- PWM výstup
- Analogové vstupy A0, A1 a A2
- Historie měření
- Export dat do CSV
- Automatizace IF / THEN
- Modelovaný PWM osciloskop
- Ukládání profilů
- Import a export konfigurace
- Sériový terminál
- Protokol událostí
- Světlý a tmavý režim
- Servisní BOSS režim

## Spuštění

1. Ulož `index.html` do složky projektu.
2. Otevři Arduino IDE.
3. Otevři soubor `nebula_control.ino`.
4. Vyber správnou desku a port.
5. Nahraj firmware do Arduina.
6. Otevři `index.html` v Chrome nebo Edge.
7. Klikni na Připojit Arduino.
8. Vyber sériový port desky.

Web Serial vyžaduje podporovaný prohlížeč a bezpečný kontext HTTPS nebo localhost.

## Výchozí zapojení

| Funkce | Pin |
|---|---|
| LED | D13 |
| Reléový modul | D7 |
| PWM výstup | D5 |
| Servo | D9 |
| RGB červená | D3 |
| RGB zelená | D6 |
| RGB modrá | D10 |
| Analogový senzor 1 | A0 |
| Analogový senzor 2 | A1 |
| Analogový senzor 3 | A2 |

## Sériová komunikace

Rychlost komunikace je 115200 baud.

| Příkaz | Funkce |
|---|---|
| `PING` | Test spojení |
| `STATUS` | Stav Arduina |
| `LED:1` | Zapnutí LED |
| `LED:0` | Vypnutí LED |
| `RELAY1:1` | Zapnutí relé |
| `RELAY1:0` | Vypnutí relé |
| `PWM:120` | Nastavení PWM |
| `SERVO:90` | Nastavení serva |
| `RGB:30,120,60` | Nastavení RGB |
| `STOP` | Vypnutí výstupů |

Arduino odesílá analogové hodnoty ve formátu:

- `A0:512`
- `A1:438`
- `A2:225`

## BOSS režim

Výchozí lokální heslo:

`nebula-root`

Po prvním spuštění ho změň.

**Upozornění:** Heslo je uloženo v prohlížeči a chrání pouze uživatelské rozhraní. Není to skutečná bezpečnostní autentizace. Pro reálné zabezpečení použij serverovou autentizaci nebo ověřování přímo ve firmwaru.

## Bezpečnost

- Nepřipojuj výkonné motory přímo k pinům Arduina.
- Pro relé, motory a další zátěže používej vhodné budiče.
- Dodržuj napěťové a proudové limity desky.
- Před zapojením zkontroluj společnou zem a polaritu.
- Nouzové vypnutí ve webu je pouze příkaz do zařízení; nezaručuje bezpečné odpojení napájení.

## Omezení

- Demo režim používá simulovaná data.
- PWM osciloskop je vizualizace, nikoliv fyzické měření.
- Automatizace v prohlížeči běží jen při otevřené stránce.
- Pro dlouhodobé automatizace je vhodné přesunout pravidla do Arduina.
- Firmware je výchozí příklad pro Arduino Uno/Nano. Pro jiné desky je nutné upravit piny a případně knihovny.

## Verze

arduino-control V2.0 – česká edice
