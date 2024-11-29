# **Terminalkommandon i Linux**
# Vanliga Terminalkommandon
## Tangentbordsgenvägar och Navigering
Innan vi går igenom några vanliga kommandon, är här några tangentbordsgenvägar som är mycket användbara:

- Uppåtpil: Visar ditt senaste kommando
- Nedåtpil: Visar ditt nästa kommando
- Tab: Autofyller ditt kommando
- Ctrl + L: Rensar skärmen
- Ctrl + C: Avbryter ett kommando
- Ctrl + R: Söker efter ett kommando
- Ctrl + D: Stänger terminalen
- Man Command

På Linux och Mac används `man`-kommandot för att visa manualen för ett kommando som kan köras i terminalen. Om du exempelvis vill veta mer om ls-kommandot kan du skriva:

```bash
man ls
```
Tyvärr finns inte `man` inkluderat om du använder Git Bash på Windows. Istället kan du skriva kommandot du vill veta mer om följt av `--help` för liknande information:

```bash
ls --help
```

Du kan använda piltangenterna eller page up och page down för att navigera. När du är klar, tryck q för att avsluta.

## Kommandot whoami
whoami visar användaren du för närvarande är inloggad som:

```bash
whoami
```
## Kommandot date
Ett annat enkelt kommando är date, som visar det aktuella datumet och tiden:

```bash
date
```
## Navigering i Filsystemet
Att navigera i filsystemet är grundläggande. Här är några kommandon du bör känna till:

|Kommando	                             |Beskrivning                                             |
|--------------------------------------|--------------------------------------------------------|
|pwd	                                 |Visar sökvägen till arbetskatalogen                     |
|ls	                                   |Listar innehåll i en katalog                            |
|ls -a	                               |Listar även dolda filer (filer som börjar med en punkt) |
|ls -l	                               |Listar innehåll med mer information (lång lista)        |
|ls -r	                               |Listar innehåll i omvänd ordning                        |
|cd	                                   |Byter till hemkatalogen                                 |
|cd [katalognamn]	                     |Byter till specifik katalog                             |
|cd ~	                                 |Byter till hemkatalogen                                 |
|cd ..	                               |Byter till överordnad katalog                           |
|cd -	                                 |Byter till föregående katalog                           |
|find [sökväg] -name [filnamn]      	 |Hittar en fil eller katalog                             |

Du kan kombinera flaggor för att korta kommandon. Exempel: `ls -l -a` kan skrivas som `ls -la`.

## Öppna Mappar eller Filer
Kommandot för att öppna en fil eller mapp varierar beroende på OS:

Mac: `open [katalognamn]`
Windows: `start [katalognamn]`
Linux: `xdg-open [katalognamn]`

### Exempelvis:

```bash
open https://traversymedia.com
```
## Modifiera Filer och Kataloger
Här är några grundläggande kommandon för att skapa, kopiera, flytta och ta bort filer och kataloger:

|Kommando	                           |Beskrivning                                                           |
|------------------------------------|----------------------------------------------------------------------|
|mkdir [katalognamn]	               |Skapa en ny katalog                                                   |
|touch [filnamn]	                   |Skapa en ny fil                                                       |
|rm [filnamn]	                       |Ta bort en fil                                                        |
|rm -i [filnamn]	                   |Ta bort en fil, men bekräfta först                                    |
|rm -r [katalognamn]	               |Ta bort en katalog och dess innehåll                                  |
|rm -rf [katalognamn]	               |Tvinga borttagning av katalog och innehåll (använd med försiktighet!) |
|rm ./*	                             |Ta bort allt i den aktuella mappen                                    |
|cp [filnamn] [katalognamn]	         |Kopiera en fil till en katalog                                        |
|mv [filnamn] [katalognamn]	         |Flytta en fil till en katalog                                         |
|mv [filnamn] [nyttfilnamn]	         |Byt namn på en fil                                                    |
|mv [katalognamn] [nyttkatalognamn]	 |Byt namn på en katalog                                                |

Du kan kombinera kommandon med &&. Exempelvis:

```bash
cd test2 && mkdir test3
```
## Redirecting Output med >
Symbolen > används för att styra utdata till en fil. Exempel:

```bash
echo "Hej världen" > nyfil.txt
```
Detta skapar en fil `nyfil.txt` och skriver texten `"Hej världen"` i den.

## Använd >> för att lägga till innehåll i en befintlig fil:

```bash
echo "Mer text" >> nyfil.txt
```
## Kommandot cat (concatenate)
cat används för att visa innehållet i filer, skapa filer, och mer. Här är några exempel:

|Användning	          |Beskrivning                             |
|---------------------|----------------------------------------|
|cat [filnamn]	      |Visa innehållet i en fil                |
|cat [fil1] [fil2]	  |Visa innehållet i flera filer samtidigt |
|cat > [filnamn]	    |Skapa en ny fil och börja skriva i den  |
|cat >> [filnamn]	    |Lägg till innehåll i en befintlig fil   |
|cat -n [filnamn]	    |Visa innehåll med radnummer             |

Avsluta och spara med Ctrl + D när du skriver i en fil.

## Kommandot less
less används för att visa innehåll i en fil, likt cat, men låter dig bläddra upp och ner:

```bash
less [filnamn]
```
Avsluta genom att trycka på q.

## Kommandot echo
echo används för att visa meddelanden eller skriva till filer:

```bash
echo "Hej världen"
```
## Skapa eller lägga till innehåll i en fil:

```bash
echo "Nytt innehåll" > nyfil.txt
echo "Mer innehåll" >> nyfil.txt
```

## Kommandot nano
nano är en enkel textredigerare som finns på de flesta Linux- och Mac-system samt i Git Bash på Windows:

```bash
nano [filnamn]
```
Avsluta genom att trycka Ctrl + X, följt av Y för att spara eller N för att inte spara.

## Kommandona head och tail

|Kommando	             |Beskrivning                        |
|----------------------|-----------------------------------|
|head [filnamn]	       |Visa de första 10 raderna i en fil |
|head -n 5 [filnamn]	 |Visa de första 5 raderna           |
|tail [filnamn]	       |Visa de sista 10 raderna i en fil  |
|tail -n 5 [filnamn]	 |Visa de sista 5 raderna            |

## Kommandot grep
grep används för att söka efter textmönster i filer:

```bash
grep [sökterm] [filnamn]
```
Sök i flera filer:

```bash
grep [sökterm] [fil1] [fil2]
```
## Kommandot find
find används för att hitta filer och kataloger:

|Exempel	                       |Beskrivning                           |
|--------------------------------|--------------------------------------|
|find [sökväg] -name [filnamn]	 |Hitta en specifik fil                 |
|find . -name "file-*"	         |Hitta filer som matchar ett mönster   |
|find . -empty	                 |Hitta tomma filer                     |
|find . -name "file-*" -delete	 |Ta bort filer som matchar ett mönster |

## Piping
Piping är ett sätt att omdirigera utdata från ett kommando till ett annat. Här är några exempel:

Skapa 10 filer:

```bash
touch file-{001..010}.txt
```
Hitta dessa filer och skriv resultatet till en ny fil:

```bash
find . -name "file-0*" > output.txt
```
Visa innehållet i den nya filen:

```bash
cat output.txt
```
## Skapa en Symbolisk Länk (Symlink)
En symbolisk länk (symlink) är en genväg till en fil eller katalog.
Skapa en symlink:

```bash
ln -s [filnamn] [symlinknamn]
```
Ta bort en symlink:

```bash
rm [symlinknamn]
```
På Windows, om du inte använder Git Bash, kan du skapa en symlink med:

```bash
mklink [symlinknamn] [filnamn]
```
## Filkomprimering med tar
Kommandot tar används för att skapa eller extrahera tarbollar (arkivfiler).

|Kommando	                                     |Beskrivning                            |
|----------------------------------------------|---------------------------------------|
|tar czvf [katalognamn].tar.gz [katalognamn]	 |Skapa en tarball med gzip-komprimering |
|tar tzvf [tarboll]	                           |Visa innehållet i en tarball           |
|tar xzvf [tarboll]	                           |Extrahera en tarball                   |

Vanliga flaggor:

- -c: Skapa ett arkiv
- -x: Extrahera ett arkiv
- -f: Använd ett filnamn för arkivet
- -z: Komprimera eller dekomprimera med gzip
- -v: Visa information under processen

## Kommandot history
history visar en lista över tidigare körda kommandon.

```bash
history
```
Du kan köra ett tidigare kommando direkt med !:

```bash
!100
```
Detta kör kommandot som ligger på position 100 i historiken.

### Kommandot chmod
chmod används för att ändra fil- och katalogbehörigheter.

|Exempel	         |Beskrivning                                                                            |
|------------------|---------------------------------------------------------------------------------------|
|chmod 755 [fil]	 |Ger läs-, skriv- och körbehörighet till ägaren, och läs- och körbehörighet till andra. |
|chmod 644 [fil]	 |Ger läs- och skrivbehörighet till ägaren, och endast läsbehörighet till andra.         |

## Kommandot chown
chown ändrar ägaren av en fil eller katalog.

Ändra ägare:

```bash
chown [ny_ägare] [filnamn]
```
Ändra ägare och grupp:

```bash
chown [ny_ägare]:[ny_grupp] [filnamn]
```

## Fler Användbara Kommandon

|Kommando	           |Beskrivning                       |
|--------------------|----------------------------------|
|df -h	             |Visa diskutrymme i läsbart format |
|du -sh [katalog]	   |Visa storlek av en katalog        |
|ps aux	             |Lista alla körande processer      |
|kill [process-ID]	 |Avsluta en process                |
|wget [URL]	         |Ladda ner en fil från en URL      |
|curl [URL]	         |Hämta data från en URL            |

## Kommandon för Nätverk

|Kommando	                  |Beskrivning                     |
|---------------------------|--------------------------------|
|ping [adress]	            |Testa anslutning till en adress |
|ifconfig	                  |Visa nätverkskonfiguration      |
|netstat -tuln	            |Visa öppna portar               |
|ssh [användare]@[server]	  |Anslut till en server via SSH   |

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

