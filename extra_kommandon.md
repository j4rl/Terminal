# Extra Linux-kommandon - coola och ovanliga

Det här är ett urval av mindre vanliga men väldigt användbara eller roliga kommandon som du kan testa i Linux. Många av dem kräver att programmet är installerat först.

---

## 1. btop
`btop` visar systeminformation i realtid: CPU, RAM, disk, processer och mer. Det är mycket snyggare och mer användbart än `top`.

Installera:
```bash
sudo apt install btop
```

Starta:
```bash
btop
```

Använd:
- piltangenter för att navigera
- q för att avsluta

---

## 2. hollywood
`hollywood` visar en terminal med ett "hackerman"-utseende och påminner om Hollywood-film. Det är mest en rolig effekt, men ibland används det för demonstration eller underhållning.

Installera:
```bash
sudo apt install hollywood
```

Starta:
```bash
hollywood
```

Avsluta med:
```bash
Ctrl + C
```

---

## 3. lynx
`lynx` är en textbaserad webbläsare. Du kan öppna webbsidor utan grafisk miljö.

Installera:
```bash
sudo apt install lynx
```

Starta:
```bash
lynx https://www.example.com
```

Navigera med:
- piltangenter
- q för att stänga

Det är väldigt användbart om du bara har terminalen tillgänglig.

---

## 4. cmatrix
`cmatrix` visar ett klassiskt "matrix"-liknande fallande koden i terminalen.

Installera:
```bash
sudo apt install cmatrix
```

Starta:
```bash
cmatrix
```

Avsluta med:
```bash
Ctrl + C
```

---

## 5. figlet
`figlet` gör stora ASCII-texter i terminalen.

Installera:
```bash
sudo apt install figlet
```

Exempel:
```bash
figlet Hej
```

Du kan även kombinera det med färger eller annan text:
```bash
figlet Linux | lolcat
```

---

## 6. toilet
`toilet` gör stora text-effekter i terminalen, liknande figlet men med fler stilar.

Installera:
```bash
sudo apt install toilet
```

Exempel:
```bash
toilet -f mono12 Linux
```

---

## 7. cowsay
`cowsay` visar en ko som pratar. Det är väldigt roligt och används ofta för demo eller skoj.

Installera:
```bash
sudo apt install cowsay
```

Exempel:
```bash
cowsay Hello Linux!
```

Du kan också kombinera med andra kommandon:
```bash
fortune | cowsay
```

---

## 8. fortune
`fortune` visar slumpmässiga citat eller skämt.

Installera:
```bash
sudo apt install fortune-mod
```

Exempel:
```bash
fortune
```

Kombinera med `cowsay`:
```bash
fortune | cowsay
```

---

## 9. neofetch
`neofetch` visar information om ditt system, såsom operativsystem, kernel, RAM, skärm och mer.

Installera:
```bash
sudo apt install neofetch
```

Starta:
```bash
neofetch
```

---

## 10. onefetch
`onefetch` visar information om ett Git-projekt, inklusive repo-namn, senaste commit, språk och mer.

Installera:
```bash
sudo apt install onefetch
```

Kör i ett Git-projekt:
```bash
cd /path/to/repo
onefetch
```

---

## 11. sl
`sl` står för "Steam Locomotive" och visar ett tåg som rör sig i terminalen.

Installera:
```bash
sudo apt install sl
```

Starta:
```bash
sl
```

Det är ett klassiskt skämtkommando i Linux.

---

## 12. rig
`rig` genererar slumpmässiga falska personuppgifter som namn, adress och telefonnummer.

Installera:
```bash
sudo apt install rig
```

Exempel:
```bash
rig
```

---

## 13. whatis
`whatis` visar en kort beskrivning av ett kommando.

Exempel:
```bash
whatis ls
whatis chmod
whatis grep
```

Det är ett snabbt sätt att förstå vad ett kommando gör.

---

## 14. cal
`cal` visar en kalender i terminalen.

Exempel:
```bash
cal
cal 2026
```

---

## 15. yes
`yes` skriver upprepade gånger ett visst ord eller meddelande.

Exempel:
```bash
yes hello
```

Avsluta med:
```bash
Ctrl + C
```

---

## 16. rev
`rev` vänder text på varje rad baklänges.

Exempel:
```bash
echo "Linux" | rev
```

Resultat:
```bash
xunil
```

---

## 17. shuf
`shuf` blandar rader slumpmässigt.

Exempel:
```bash
printf '%s\n' ett två tre fyra fem | shuf
```

---

## 18. lolcat
`lolcat` lägger till färger i text i terminalen.

Installera:
```bash
sudo apt install lolcat
```

Exempel:
```bash
echo "Hej Linux!" | lolcat
```

---

## 19. pv
`pv` visar framsteg när data flyttas mellan filer eller kommandon.

Installera:
```bash
sudo apt install pv
```

Exempel:
```bash
pv bigfile.txt > copy.txt
```

---

## 20. asciinema
`asciinema` spelar in terminal-sessioner som kan visas i webbläsaren.

Installera:
```bash
sudo apt install asciinema
```

Starta inspelning:
```bash
asciinema rec
```

---

## 21. ranger
`ranger` är en terminalbaserad filhanterare med bildvisning, flikar och snabb navigering.

Installera:
```bash
sudo apt install ranger
```

Starta:
```bash
ranger
```

---

## 22. tldr
`tldr` visar korta, praktiska exempel på hur ett kommando används.

Installera:
```bash
sudo apt install tldr
```

Exempel:
```bash
tldr ls
tldr grep
tldr chmod
```

Detta är ofta bättre än att läsa hela `man`-sidan.

---

## 23. jq
`jq` används för att läsa, filtrera och manipulera JSON-data i terminalen.

Installera:
```bash
sudo apt install jq
```

Exempel:
```bash
echo '{"namn":"Anna","age":25}' | jq
```

---

## 24. curl
`curl` används för att hämta data från webben via terminalen.

Exempel:
```bash
curl https://example.com
```

Du kan även hämta och spara innehåll:
```bash
curl -o sida.html https://example.com
```

---

## 25. tree
`tree` visar kataloger i ett träd-format.

Installera:
```bash
sudo apt install tree
```

Exempel:
```bash
tree
```

---

## Tips för att testa dem
Du kan prova ett i taget och se vad som passar dig bäst. Många av dessa kommandon är perfekta för att göra terminalen roligare eller mer kraftfull.

Exempel på blandning:
```bash
fortune | cowsay | lolcat
btop
cmatrix
```

---

## Sammanfattning
Dessa kommandon visar att Linux-terminalen inte bara är för arbete — den kan också vara rolig, kreativ och mycket kraftfull.

Om du vill kan du också skapa en egen lista med:
- mest användbara kommandon
- roliga kommandon
- kommandon för systemövervakning
- kommandon för nätverk och webb
