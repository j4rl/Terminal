# Uppgift 3 - Skapa användare, ändra lösenord och lägga till sudo

## Mål
Du ska efter denna uppgift kunna:
- skapa en ny användare i Linux
- sätta ett lösenord för en användare
- lägga till en användare i sudo-gruppen
- kontrollera att användaren kan köra kommandon med `sudo`
- skapa en egen sudoers-regel

---

## Teori
Linux har användare och grupper som styr vilka rättigheter en användare har. För administrativa uppgifter används ofta `sudo`, vilket innebär att en vanlig användare kan köra kommandon som root temporärt.

Vanliga kommandon:
```bash
adduser
passwd
usermod
sudo
sudo -l
visudo
```

---

## Uppgift
Du ska skapa en ny användare, ge den ett lösenord och kontrollera att den får köra administratörskommandon via `sudo`.

### Steg 1: Skapa en användare
```bash
sudo adduser labbstudent
```
Följ instruktionerna och ange ett lösenord.

### Steg 2: Kontrollera användaren
```bash
id labbstudent
cat /etc/passwd | grep labbstudent
```

### Steg 3: Ändra lösenordet för användaren
```bash
sudo passwd labbstudent
```
Skriv ett nytt lösenord och bekräfta det.

### Steg 4: Lägg till användaren i sudo-gruppen
```bash
sudo usermod -aG sudo labbstudent
```

### Steg 5: Testa sudo
Logga in som användaren `labbstudent`:
```bash
su - labbstudent
```
Testa sedan:
```bash
sudo whoami
```
Om allt är korrekt blir resultatet:
```bash
root
```

### Steg 6: Kontrollera kommandon som användaren får köra
```bash
sudo -l -U labbstudent
```
Detta visar vilka kommandon användaren har rätt att köra med sudo.

---

## Extra uppgift: skapa en egen sudoers-regel
Istället för att lägga användaren i sudo-gruppen kan du skapa en egen regel i `/etc/sudoers.d/`.

```bash
sudo nano /etc/sudoers.d/labbstudent
```
Skriv:
```bash
labbstudent ALL=(ALL) ALL
```

Kontrollera syntaxen:
```bash
sudo visudo -cf /etc/sudoers.d/labbstudent
```

Om filen är korrekt kommer `visudo` att säga att den är giltig.

---

## Frågor att besvara
1. Vad gör kommandot `adduser`?
2. Varför använder vi `passwd`?
3. Vad är syftet med `sudo`?
4. Vad gör `usermod -aG sudo användarnamn`?
5. Hur visar `sudo -l -U användarnamn` vilka rättigheter användaren har?
6. Vad är skillnaden mellan att vara medlem i `sudo`-gruppen och att ha en regel i `/etc/sudoers.d/`?
7. Varför är det viktigt att skydda administratörsrättigheter?

---

## Enkelt sätt att redovisa
Skriv ett kort dokument med dina egna ord. Det ska visa vad du gjorde och vad du lärde dig.

### Gör så här:
1. Titel: "Uppgift 3 – Användare, lösenord och sudo"
2. Berätta vad du gjorde
3. Skriv kommandona du använde
4. Skriv kort vad resultatet blev
5. Skriv din personliga insikt: varför behövs sudo och hur skyddar man ett system?

### Exempel
```text
Jag skapade en ny användare och ändrade lösenordet. Sedan lade jag till användaren i sudo-gruppen och testade att den kunde köra sudo whoami. Min insikt var att sudo ger användare tillfällig administrativ behörighet utan att ge full kontroll till alla. Det känns viktigt att skydda systemet och endast låta rätt användare göra administrativa ändringar.
```

## Inlämning
Lämna in:
- kort text om vad du gjorde
- kommandon du använde
- resultatet av testet med sudo
- din egen reflektion om användare, lösenord och säkerhet
