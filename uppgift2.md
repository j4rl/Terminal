# Uppgift 2 - Ägarskap och rättigheter på filer

## Mål
Du ska efter den här uppgiften kunna:
- skapa filer och kataloger i Linux
- ändra ägare och grupp för filer och kataloger
- sätta behörigheter med `chmod`
- förstå skillnaden mellan ägare, grupp och övriga
- kontrollera rättigheter med `ls -l`

---

## Teori
I Linux finns tre sorters behörigheter för varje fil eller katalog:
- ägare (user, u)
- grupp (group, g)
- övriga (others, o)

Varje kategori kan ha:
- r = läsa
- w = skriva
- x = exekvera / gå in i katalog

Exempel:
- `rw-r--r--` betyder: ägaren kan läsa och skriva, gruppen kan bara läsa, övriga kan bara läsa.
- `rwxr-x---` betyder: ägaren kan läsa, skriva och exekvera; gruppen kan läsa och exekvera; övriga har inga rättigheter.

Kommandon du kommer att använda:
```bash
ls -l
chown
chgrp
chmod
```

---

## Uppgift
Skapa en katalog och ett antal filer. Sätt därefter ägarskap och rättigheter så att bara vissa användare kan läsa och skriva i filerna.

### Steg 1: Kontrollera användare
Se om användaren `student` finns:
```bash
id student
```
Om den inte finns, skapa den:
```bash
sudo adduser student
```

### Steg 2: Skapa katalog och filer
```bash
sudo mkdir -p /srv/labb_uppgift2
cd /srv/labb_uppgift2
sudo touch hemligt.txt
sudo touch public.txt
sudo touch logg.txt
ls -l
```

### Steg 3: Titta på nuvarande rättigheter
```bash
ls -l /srv/labb_uppgift2
```
Notera vem som äger filerna och vilka rättigheter de har.

### Steg 4: Ändra ägare
Ge filerna ägare `student` och grupp `student`:
```bash
sudo chown student:student /srv/labb_uppgift2
sudo chown student:student /srv/labb_uppgift2/hemligt.txt
sudo chown student:student /srv/labb_uppgift2/public.txt
sudo chown student:student /srv/labb_uppgift2/logg.txt
```

### Steg 5: Sätt behörigheter
Sätt rättigheter enligt följande:
- `hemligt.txt`: ägaren ska kunna läsa och skriva, gruppen bara läsa, övriga inga rättigheter
- `public.txt`: alla ska kunna läsa
- `logg.txt`: ägaren ska kunna läsa och skriva, gruppen läsa, övriga inga rättigheter
- katalogen `/srv/labb_uppgift2`: ägaren ska kunna läsa, skriva och gå in, gruppen ska kunna gå in, övriga inga rättigheter

```bash
chmod 640 /srv/labb_uppgift2/hemligt.txt
chmod 644 /srv/labb_uppgift2/public.txt
chmod 640 /srv/labb_uppgift2/logg.txt
chmod 750 /srv/labb_uppgift2
```

### Steg 6: Kontrollera
```bash
ls -ld /srv/labb_uppgift2
ls -l /srv/labb_uppgift2
```

Skriv ner resultatet och förklara vad varje siffra betyder.

---

## Frågor att besvara
1. Vad betyder `chmod 640`?
2. Vad betyder `chmod 750`?
3. Vad är skillnaden mellan `chown` och `chmod`?
4. Vad betyder bokstäverna `r`, `w`, `x`?
5. Varför är det viktigt att begränsa rättigheter på känsliga filer?
6. Hur ser en fil ut i `ls -l` om den har rättigheterna `-rw-r-----`?
7. Vilken användare äger filerna efter du har ändrat ägarna?

---

## Extra övning
Försök att byta till användaren `student` och testa om hen kan:
```bash
su - student
ls -l /srv/labb_uppgift2
cat /srv/labb_uppgift2/public.txt
cat /srv/labb_uppgift2/hemligt.txt
```
Om rättigheterna är korrekta ska `student` kunna läsa `public.txt`, men inte `hemligt.txt` om det inte är tillåtet i gruppen.

---

## Enkelt sätt att redovisa
Skriv ett kort dokument med dina egna tankar och observationer. Det bör handla om vad du gjorde och vad du lärde dig.

### Gör så här:
1. Titel: "Uppgift 2 – Ägarskap och rättigheter på filer"
2. Beskriv kort vad du gjorde
3. Lista de kommandon du använde
4. Skriv vad du såg i `ls -l`
5. Skriv din personliga insikt: varför är rättigheter viktiga?

### Exempel
```text
Jag skapade en katalog och filer och ändrade därefter ägare och rättigheter med chown och chmod. Det var tydligt att olika filer kunde ha olika behörigheter. Min insikt var att rättigheter är viktiga för säkerhet, eftersom man inte vill att alla ska kunna läsa eller ändra känsliga filer. Jag förstod också att ägare och grupp spelar stor roll för vem som får göra vad.
```

## Inlämning
Lämna in:
- kort text om uppgiften
- kommandon du använde
- ett kort resultat från `ls -l`
- din egen reflektion om varför rättigheter behövs
