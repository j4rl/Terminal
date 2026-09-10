# Skapa en Enkel Mappstruktur i Hemkatalogen

En tydlig mappstruktur i hemkatalogen hjälper dig att hålla ordning på filer och projekt. Här är en guide för att skapa en enkel struktur med kommandon i terminalen.

---

## **Exempel på Struktur**
```plaintext
~/                  # Hemkatalog
├── Projects/       # För arbets- och hobbyprojekt
│   ├── Web/        # Webbutvecklingsprojekt
│   ├── Python/     # Pythonprojekt
│   └── Arduino/    # Arduino-relaterade projekt
├── Documents/      # Dokument som rapporter och anteckningar
│   ├── Work/       # Arbetsrelaterade dokument
│   └── Personal/   # Personliga dokument
├── Media/          # Bilder, musik och videor
│   ├── Photos/     # Bilder och foton
│   ├── Music/      # Musikfiler
│   └── Videos/     # Videofiler
└── Temp/           # Tillfälliga filer
```
## Kommandon för att Skapa Mappstrukturen
### 1. Gå till din hemkatalog
Använd kommandot:

```bash
cd ~
```
### 2. Skapa huvudmapparna
Skapa huvudmappar med mkdir:

```bash
mkdir Projects Documents Media Temp
```
### 3. Skapa undermappar i Projects
```bash
mkdir -p Projects/Web Projects/Python Projects/Arduino
```
### 4. Skapa undermappar i Documents
```bash
mkdir -p Documents/Work Documents/Personal
```
### 5. Skapa undermappar i Media
```bash
mkdir -p Media/Photos Media/Music Media/Videos
```
## Bekräfta att Strukturen är Skapad
Visa mappstrukturen med:

```bash
tree ~
```
Om kommandot tree inte är installerat, kan du använda:

```bash
ls -R ~
```
## Tips för Användning
- Lagra projekt och filer i rätt mappar: Spara filer där de logiskt hör hemma.
- Rensa Temp-mappen regelbundet: Ta bort gamla filer för att hålla det rent.
- Anpassa strukturen efter dina behov: Lägg till fler mappar om du behöver fler kategorier.

---

## Enkelt sätt att redovisa
Skriv ett kort dokument med dina egna ord. Det behöver inte vara lång eller formellt. Skriv bara det som passar dig.

### Gör så här:
1. Titel: "Uppgift 1 – Grundläggande Linux-kommandon"
2. Skriv vad du gjorde
3. Lista de kommandon du använde
4. Skriv kort vad resultatet blev
5. Skriv din egen insikt: vad lärde du dig och vad var svårt eller enkelt?

### Exempel
```text
Jag lärde mig att använda pwd, ls och cd för att navigera i Linux. Jag skapade mappar och tittade på filer i hemkatalogen. Det var lätt att se hur katalogerna hängde ihop. Min viktigaste insikt var att terminalen är ett snabbt sätt att arbeta med filer och att man måste vara noggrann med var man befinner sig i systemet.
```

## Inlämning
Lämna in:
- kort text om vad du gjorde
- kommandon du använde
- din personliga reflektion
- ett kort resultat från terminalen

