# Súbory

Pred tým, než sa budeme venovať súborom a prácou s nimi, mali by sme si pripomenúť (alebo sa naučiť) formátovanie stringov. [Kapitola o tom je v sekcií pre SEN1](../sen1/16-string-format.md).

Zatiaľ sme vždy pracovali s dátami, ktoré boli uložené v pamäti, teda po ukončení násho programu po nich nezastali žiadne stopy. Súbory sú taký najjednoduhší príklad dát, ktoré prežijú reštart aplikácie a dokonca aj reštart počítača. Preto je ich použitie veľmi rozšírené (na nastavenia programu, na ukladanie spracovaných dát, ...)

## Otváranie súborov

Pre začatím práce so súbormi ich musíme otvoriť. Musíme vlastne povadať operačnému systému, že tento súbor chceme používať. Na identifikáciu súboru použijeme cestu (môžeme použit aj relatívne cesty používajúce `..` a `.`). 

```py
file = open('path/to/file.txt')
```

Toto spôsobí, že sa nám súbor otvorí na čítanie. Ak by daný súbor neexistoval, tak program skončí s chybou. 

Súbor musíme vždy po použití zavrieť zavolaním funkcie `close`, totiž chceme čo najrýchlejšie vrátiť všetky prostriedky, ktoré nám dal operačný systém. V týchto naších jednoduchých príkladoch to nie je až taký problém, ale je veľmi dôležité sa to naučiť dobre.

```py
file.close() # release all resources
```

Moderný spôsob práce v pythone je taký, že namiesto explicitného `close`, radšej použijeme konštrukciu `with`. Táto zabezpečí uzavretie súboru. 

```py
with open('./file.txt') as file:
  # do stuff with file
  pass
```

## Čítanie súborov

Na čítanie súborov máme tri hlavné funkcie

1. `.read(size=-1)`, ktorá prečíta prvých `size` znakov zo súboru, prípadne ak je `size` `-1`, tak prečíta celý súbor. 
2. `.readline()`, ktorá prečíta jeden riadok
3. `.readlines()`, ktorá prečíta všetky riadky a uloží ich do poľa 

Ak chceme čítať súbor po riadkoch, tak môžeme použiť nasledujúcu konštrukciu. 

```py
with open('./file.txt') as file:
  for line in file.readlines():
    print(line, end='')
```

Súčasťou riadkov sú aj ukončovacie nové riadky, takže preto sme vo výpise vynechali nové riadky. 

Prípadne sa to dá ešte skrátiť ako 

```py
with open('./file.txt') as file:
  for line in file:
    print(line, end='')
```

Python si interne udržuje *index*, kde sa nadházdame v súbore, preto ak chceme súbor prečítať po 10 znakoch, tak môžeme použiť nasledujúci kód. 

```py
with open('./file.txt') as file:
  s = file.read(10)
  while s != '':
    print(s)
    s = file.read(10)
```

## Úlohy

Pozrite sa aj na úlohy z [formátovania stringov](../sen1/16-string-format.md).

1. Prečítajte samého seba (teda python zdroják) a vypíšte ho bez všetkych whitespaceov (všetky znaky kde `isspace` vráti `True`).
2. V súbore `cisla.txt` budú celé čísla, každé na jednom riadku, vypíšte ich priemer.
3. V súbore `cisla.txt` budú celé čísla (od `0` do `99`), každé na jednom riadku, vypíšte ich modus, teda číslo, ktoré sa v súbore vyskytuje najviackrát.
4. V súbore `strings.txt` budú stringy, vypíšte tento súbor na konzolu obrátene. Napríklad 
   ```
   Ahoj evlyceum!
   Uz je druhy polrok.
   Koniec.
   ```
   ```
   .ceinoK
   .korlop yhurd ej zU
   !muecylve johA
   ```

## Domáca úloha

Deadline utorok 9. február 2021 (23:59).

Prvá časť (1,5boda)

K nasledujúcim trom príkladam napíšte formátovací reťazec, ktorý vytvorí daný výstup, teda napríklad výstup je `********2.28********` a vstup je `format(2.278)`, tak odpoveď je `'{:*^20.2f}'`. 

* `_****************2.286_` a vstup je `format(2.2859)`
* `0x123 100100011` a vstup je `format(291, 291)`
* `+1.23 -1.23 1.23` a vstup je `format(1.23, -1.23)` (tu si uvedomte, že parametre sa môžu aj opakovať vo formátovacom reťazci)

Druhá časť (1,5boda)

V súbore `uloha.txt` budú na začiatku dve čísla, prvé bude hovoriť po koľkých riadkov má byt medzera a druhé na kolko znakov majú byť riadku zarovnané v strede (ak bude niektorý riadok dlhší, tak tento riadko ostane tak, bez akéhokoľvek zarovnania). Teda napríklad pre vstup 

```
3
20
Lorem ipsum dolor sit amet, 
consectetur adipiscing 
elit, sed do eiusmod
        tempor 
incididunt ut labore 
et dolore magna aliqua. 
Rhoncus mattis 
rhoncus urna neque
  viverra justo nec.
```

Bude výstup 

```
TBA
```

### Bonus (1bod)

