# Číselné konverzie

Poznáme mnohé číslené sústavy, štandardne používame desiatkovú (preto lebo máme 10 prstov). V IT svete sa často vykytujú binárne (základ 2), osmičkové (základ 8), šestnástkové (alebo aj hexadecimálne so základom 16) a 64kové (base64). Všetky tieto sústavy používajú znaky na kódovanie číslic

* desiatková `0-9`
* binárna `0-1`
* šestnásková `0-9` a `a-f`

Hodnota daného čísla je potom daná pozíciami čísel. Napríklad 

* `123` v desiatkovej sústave je vlastne `1*10^2 + 2*10^1 + 3*10^0`,
* `1001` v binárnej je potom `1*2^3 + 0*2^2 + 0*2^1 + 1*2^0`,
* `af` v šestnáskovej je `10*16^1 + 15*16^0`.

## Konverzie

Ak chcem jednu sústavu konvertovať na druhú, tak najprv si prvú prevediem na číslo a potom toto číslo zakódujem do výslednej sústavy. 

Príklad. Mám reťazec v osmičkovej sústave a chcem z neho šestnáskovú. 

Najprv načítame číslo ako reťazec a prevedieme ho na číslo. 

```py
o = input('zadaj oct cislo')
n = 0
mocnina = 0
for i in range(len(o) - 1, -1, -1):
  n = n + int(o[i]) * (8 ** mocnina)
  mocnina += 1
```

Išli sme odzadu po jednotlivých cifrách (posledný parameter v range hovorí aký je krok, teda kam sa posuniem v nasledujúcej iterácií). Potom sme skladali číslo po jednodlivých mocninách, zobrali sme cifru, skonverovali a vynásobili príslušnou mocninou osmičky.

Teraz musíme číslo previesť na šestnáskovú sústavu. To urobíme štandardným delením a prechádzaním po hex cifrách. 

```py
h = ''
while (n > 0):
  x = n % 16
  if x < 10:
    h = str(x) + h
  else:
    h = chr(ord('a') + (x - 10)) + h
  n //= 16

print(h)
```

V príklade vyššie chýba pravdepodobne ošetrenie vstupu `0` a spoliehame sa na to, že vstup má dobrý formát, bolo by to dobré skontrolovať a vypísať chybu, ak to tak nie je. 

## Funkcie `chr` a `ord`

1. Funkcia `ord` slúži na zistenie internej reprezentácie znaku. Python používa kódovanie utf-8, v ňom má znak `'a'` číslo `97` a znak velké `'A'` má číslo `65`, všetky kódy bežných znakov bez diakritiky sa dajú nájsť napríklad na stránke <https://www.asciitable.com/>.
2. Funkcia `chr` potom z čisla znaku vytvorí znak samotný, teda pre vstup `65` vráti veľké `'A'`. 

Použitie majú tieto funkcie hlavne v tamdeme, kde najprv znak skonvertuje na číslo (ak ste si všimli v tabuľke ASCII, tak písmená idú za sebou), potom ho nejak posunieme a konvertujeme späť na znak. Napríklad `chr(ord('A') + 2)` bude `C`. 

## Vstavané funkcie

Python samozrejme číselné konverzie rovno podporuje. Funkcia `int` má druhý parameter, ktorý hovorí o tom v akej sústave je vstupný string. Rovnako existujú funkcie `bin`, `oct` a `hex`, ktoré zase konvertujú číslo na string požadovanej reprezentácie. Tieto funkcie, ale štandardne pridávajú prefix, napríklad pre hex je to `0x`. Tieto funkcie na tejto hodine a ulohe používať nebudeme. 

## Úlohy

1. Dorobte do príkladu na konverziu vyššie spracovanie nuly a ošetrenie chybného vstupu.
2. Urobte program, ktorý skonvertuje šestnáskový reťazec do binárnej sústavy. 
3. Doprogramujte do úlohy *(2)* a aby mohol byť vstup aj veľké aj malé písmena. 

## Domáca úloha (3 body + 1 bod)

Deadline utorková skupina 6. novembra (piatok) 2020 23:59.

Deadline stredajšia skupina 7. novembra (sobota) 2020 23:59.

1. Urobte aplikáciu, ktorá na vstup dostane číslo `n` od `2` do `16`, toto číslo bude reprezentovať v akej sústave sa nachádzame, potom bude na vstupe string `s`, ktorý je v tejto sústave (povolené cifry sú `0-9` a `a-f`). Na výstup máte tento string potom vypísať v štandardnej desiatkovej sústave. Nezabudnite aby program fungoval aj pre nulu a ak je `s` mimo tejto sústavy, tak vypíše chybu. Napríklad

   * ```
     n=3
     s='102'
     Vysledok=11
     ```
     Je to preto, lebo v trojkovej sústave je to vlastne `1*3^2 + 0*3^1 + 2*3^0 = 9 + 0 + 2 = 11`
     
   * ```
     n=11
     s='10a'
     Vysledok=131
     ```
     Tu `'a'` považujeme za `10`, teda výsledok vznikol ako `1*11^2 + 0*11^1 + 10*11^0`. Ak by bol string `s` `10b`, tak to je neplatný string, lebo `b` je už `11` to to nepatri do našej jedenástkovej sústavy.

### Bonus

1. Youtube id používa ako identifikátor číslo zakódované do 64kovej sústavy. Napríklad <https://www.youtube.com/watch?v=INscMGmhmX4>, id je tá časť za `=`, teda v tomto prípade `INscMGmhmX4`. Toto je vlastne čislo (youtube to síce negarantuje, ale tak... :)) zakódované do sústavy 64. Jeho cifry sú 

   * `'A-Z'` -> `0-25`
   * `'a-z'` -> `26-51`
   * `'0-9'` -> `52-61`
   * `'-'` -> `62`
   * `'_'` -> `63`

   Urobte aplikáciu, ktorej keď na vstup dáme toto youtube id, tak vypíše jeho číselnú reprezentáciu. 