# Uppgift 4 - Installera Apache, PHP och MySQL samt sätta rättigheter

## Mål

Du ska efter den här uppgiften kunna:

- installera ett webbserverprogram på Linux
- installera PHP och databassystemet MySQL
- kontrollera att Apache och MySQL körs
- skapa en enkel PHP-sida
- sätta ägarskap och rättigheter så att webservern kan läsa filerna

---

## Teori

En vanlig webbserver i Linux används ofta av Apache. För dynamiska webbplatser behövs PHP och en databas, till exempel MySQL. För att webbservern ska kunna läsa webbplatsfiler måste rätt användare och rättigheter vara satta.

Vanliga kommandon:

```bash
apt update
apt install
systemctl start
systemctl enable
chown
chmod
```

---

## Uppgift

Installera ett LAMP-miljö (Linux, Apache, MySQL, PHP) och kontrollera att allt fungerar.

### Steg 1: Uppdatera systemet

```bash
sudo apt update
sudo apt upgrade -y
```

### Steg 2: Installera programvaran

```bash
sudo apt install -y apache2 php php-mysql mysql-server
```

### Steg 3: Starta tjänsterna

```bash
sudo systemctl start apache2
sudo systemctl start mysql
sudo systemctl enable apache2
sudo systemctl enable mysql
```

### Steg 4: Kontrollera status

```bash
sudo systemctl status apache2
sudo systemctl status mysql
```

### Steg 5: Testa Apache i webbläsaren

Öppna webbläsaren och gå till:

```bash
http://localhost
```

Om Apache fungerar visas standardwebbsidan.

### Steg 6: Skapa en PHP-sida

```bash
sudo nano /var/www/html/info.php
```

Skriv in:

```php
<?php
phpinfo();
?>
```

Spara och öppna sedan:

```bash
http://localhost/info.php
```

### Steg 7: Kontrollera att PHP fungerar

Om phpinfo-sidan visas så fungerar PHP och Apache tillsammans.

### Steg 8: Sätt rättigheter för webbservern

Apache körs vanligtvis som användaren `www-data`. Eftersom webbplatsfiler i `/var/www/html` ska kunna läsas av Apache måste rätt ägare och rättigheter sättas.

```bash
sudo chown -R www-data:www-data /var/www/html
sudo find /var/www/html -type d -exec chmod 755 {} \;
sudo find /var/www/html -type f -exec chmod 644 {} \;
```

Kontrollera:

```bash
ls -ld /var/www/html
ls -l /var/www/html
```

### Steg 9: Skapa en enkel databasanslutningstest

```bash
sudo nano /var/www/html/dbtest.php
```

Skriv in:

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";

$conn = new mysqli($servername, $username, $password);

if ($conn->connect_error) {
    die("Anslutning misslyckades: " . $conn->connect_error);
}

echo "Anslutning till MySQL lyckades!";
?>
```

Gå till:

```bash
http://localhost/dbtest.php
```

Om anslutningen fungerar visas meddelandet.

---

## Viktigt att tänka på

- `www-data` är användaren Apache körs som
- kataloger behöver oftast `755`
- filer behöver oftast `644`
- `root` har full kontroll, men webbfilers rättigheter bör begränsas
- MySQL ska skyddas med ett starkt lösenord i verkliga system
- Om filerna ägs av `root` kan webservern ibland inte läsa dem

---

## Frågor att besvara

1. Varför används användaren `www-data`?
2. Vad gör kommandot `chown -R www-data:www-data /var/www/html`?
3. Varför används `chmod 755` på kataloger och `chmod 644` på filer?
4. Vad visar `phpinfo();`?
5. Hur kan du kontrollera om Apache körs?
6. Vad är syftet med MySQL i en webbapplikation?
7. Varför är rättigheter så viktiga i ett webbservermiljö?

---

## Enkelt sätt att redovisa

Skriv en kort text där du berättar vad du gjorde och vad du tänkte under arbetet. Det behöver inte vara en lång rapport.

### Gör så här:

1. Titel: "Uppgift 4 – Apache, PHP och MySQL"
2. Berätta kort vad du installerade
3. Lista kommandona du använde
4. Skriv om resultatet: startade Apache och fungerade PHP?
5. Skriv din personliga insikt: varför behövs rättigheter och varför är det viktigt att servern och databasen fungerar tillsammans?

### Exempel

```text
Jag installerade Apache, PHP och MySQL och testade sedan att öppna en server-sida via localhost. Det fungerade när PHP-sidan visade information och jag förstod att servern behöver rätt behörigheter för att läsa filer i webbrooten. Min viktigaste insikt var att alla delar måste fungera tillsammans: webbservern, PHP och databasen. Om en av dem inte fungerar kan hela lösningen bli oanvändbar.
```

## Inlämning

Lämna in:

- kort text om installationen
- kommandon du använde
- kort resultat från testet
- din egen reflektion om vad du lärde dig
