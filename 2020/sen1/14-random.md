# Náhodné čísla

V module `random` sú funkcie, ktoré slúžia na získavanie náhodných čísel. Základné použitie je asi takéto 

```py
import random

print(random.randint(0, 10))
```

Program vyššie vypíše náhodné číslo od `0` do `10` vrátane oboch hraníc (to je trochu rozdiel oproti funkciú `range`, ktorá má hornú hranicu mimo intervalu). Náhodné číslo je v tom, že pri každom spustení programu uvidíme iné číslo. 

Niekedy nám nemusí vyhovovať, že máme pri každom spustení iné čislo. Napríklad ked debuggujeme a chceli by sme aby sme vedeli zreplikovať nejaký problém. Nato slúži funkcia `seed`, ktorej dáme číslo (alebo aj niečo iné) a od tohoto čísla sa budú generovať ďalšie. 

```py
import random

random.seed(1984)

print(random.randint(0, 1000))
```

Tento program síce používa náhodné čísla ale budú to stále tie isté aj po viacnásobnom spustení. 

## Ďalšie zaujímavé funkcie z modulu `random`

* `randrange`, správa sa rovnako ako funkcia `range`, ale vyberie iba jednu hodnotu z platného intervalu a tú vráti. Napríklad `randrange(0, 10, 2)` vráti jedno z čísel `0`, `2`, `4`, `5`, `6`, `8`.
* `random`, vráti desatiné číslo z intervalu `[0.0, 1.0)`.

## Úlohy

1. Naprogramujte funkciu `cislo(a, b)`, ktorá vráti náhodné číslo `x`, pre ktoré platí `a <= x < b`, kde všetky čísla sú desatinné. Teda volanie `cislo(5, 7.5)` môže vrátiť napríklad `6.5422144557`. 
2. Ako by sme vedeli upraviť funkciu z *úlohy 1*, aby platila nerovnosť `a <= x <= b`.
3. Naprogramujte aplikáciu, ktorá si vyberie náhodné čislo, ktoré potom máme za úlohu uhádnuť. Ak ho uhádneme povie nám koľko pokusov sme na to potrebovali.  
4. Naprogramujte aplikáciu, ktorá spočíta veľkosť plochy pod krivkou `x^2 + x + 0.5` na intervale `[0-1)`. Použite na to metódu monte carlo (zoberieme náhodne bud v obdĺžniku okolo krivky a zistíme, či je pod alebo nad, potom zistíme koľko percent je pod a taká plocha z obdĺžnika bude plocha pod krivkou). 

## Domáca úloha

Deadline utorková skupina 17. január (nedeľa) 2021 23:59.

Deadline stredajšia skupina 18. január (pondelok) 2021 23:59.

Opravovať budem priebežne, takže ak chcete vedieť aká známka vám vychádza na polrok, pošlite mi túto úlohu čím skôr. 

1. Naprogramujte aplikáciu ako je v *úlohe 3* s tým, že aplikácia bude mať na vstupe (pomocou funkcii input) číslo `n`. Počitač si vyberie čislo z intervali `0 <= x < n`. My ho potom hádame a vždy keď neuhádneme, tak nám povie či je číslo `x` väčšie, alebo menšie. Príklad vstupu môže byť napríklad takýto. 
   * Zadaj cislo *10*
   * *4*
   * hadane cislo je mensie
   * *1*
   * hadane cislo je vacsie
   * *2*
   * hadane cislo je vacsie
   * *3*
   * uhadil si, pocet pokusov 4
   Kurzivom je to čo zadáva užívateľ. 