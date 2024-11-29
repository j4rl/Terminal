# Hur man Använder `screen` i Terminalen

`screen` är ett terminalverktyg som låter dig hantera flera sessioner samtidigt. Det är särskilt användbart för att köra processer i bakgrunden eller behålla terminalsessioner öppna även om du stänger din terminal.

---

## **Installation**
Om `screen` inte redan är installerat kan du installera det:

- **Debian/Ubuntu:**
```bash
  sudo apt install screen
```

- CentOS/RHEL:
```bash
sudo yum install screen
```
- macOS (via Homebrew):
```bash
brew install screen
```
## Grundläggande Användning
### 1. Starta en ny screen-session
Kör kommandot:

```bash
screen
```
Detta öppnar en ny screen-session, där du kan köra dina kommandon.

### 2. Namnge en session
Du kan namnge sessionen för enkel identifiering:

```bash
screen -S session_namn
```
### 3. Koppla loss en session
För att koppla loss sessionen (låta den fortsätta i bakgrunden), tryck:

```plaintext
Ctrl + A, följt av D
```
### 4. Lista aktiva sessioner
Visa alla aktiva screen-sessioner:

```bash
screen -ls
```
### 5. Återanslut till en session
Återanslut till en specifik session:

```bash
screen -r session_namn
```
Om det bara finns en aktiv session kan du köra:

```bash
screen -r
```
## Exempel på Användning
Köra ett långvarigt skript
Starta en ny screen-session:
```bash
screen -S lång_skript
```
Kör ditt skript:
```bash
./min_skript.sh
```
Koppla loss sessionen:
```plaintext
Ctrl + A, följt av D
```
Återanslut senare:
```bash
screen -r lång_skript
```
## Vanliga Tangentkombinationer

|Tangentkombination	|Funktion                               |
|-------------------|---------------------------------------|
|Ctrl + A, D      	|Koppla loss sessionen                  |
|Ctrl + A, C	      |Skapa ett nytt fönster i samma session |
|Ctrl + A, N      	|Byt till nästa fönster                 |
|Ctrl + A, P        |Byt till föregående fönster            |
|Ctrl + A, K	      |Döda (stänga) det aktuella fönstret    |
|Ctrl + A, ?	      |Visa hjälp för tangentkombinationer    |

## Avsluta en screen-session
För att avsluta en session, stäng alla processer i sessionen eller skriv:

```bash
exit
```
## Tips
screen är perfekt för att köra långvariga processer som servrar eller skript som måste fortsätta även om du stänger terminalen.
Använd namngivna sessioner (-S) för att lättare hålla ordning på flera screen-sessioner.
