# Eratosthenovo sito

Najprv pár zaujímavstí o poliach, ktoré sa nám môžu dnes, alebo v budúcnosti hodiť. 

* Na poliach fungujú slice, teda `a[2:4]` vráti nové pole, ktoré obsahuje prvky od druhého (vrátane) po štvrtý (bez)
* Ak potrebujeme pole skopirovať, tak môžeme použiť `a[:]`, je to vlastne slice, ktorý zoberie celé pole a teda efektívne vráti kópiu
* V Pythone fungujú takzvané list comprehensions, syntax je približne takáto `[x*x for x in range(10)]`, tento zápis nám vlastne vygeneruje nové pole, v ktorom sú štvorce čísel od `0` po `9` (vrátane).

Hľadanie prvočísla sme už mali (na zopakovanie je táto funkcia aj ako prvá úloha :)). Štandardne sa vyuťíva prístup, ktorý sa volá aj *trial division*, teda skúšame deliť číslo až pokiaľ sa nám nepodarí nájsť číslo, ktoré nášho kandidáta prvočíslo delia, ak také nájdeme, tak už vieme, že to prvočíslo nie je. Ak takého deliteľa ale nenájdeme, tak vieme že ide o prvočíslo. Takýchto deľiteľov stačí hľadať po druhú odmocninu z čísla, ktoré testujeme. 

Táto vlastnosť je ľahko vidieť ak si uvedomíme, že ak testujeme číslo `p` a našli sme deliteľa `a`, tak potom `p = ab` pre nejaké `b`. Jedno z čísel `a`, `b` musi byť menšie rovné ako `sqrt(p)`. Ak by obe boli väčšie ako `sqrt(p)`, tak to znamená, že 

```plain
p = ab
a > sqrt(p)    b > sqrt(p)
p > sqrt(p)sqrt(p) = p
p > p
```

Dôjdeme do sporu, že `p > p`.

Na testovanie prvočiselnosti existujú aj rýchlejšie algoritmy (dajte do wiki Miller-Rabin, alebo Lucas-Lehmer). Tie sú už ale komplikovanejšie a nie je ľahko vidieť, že naozaj robia to čo majú. Využívajú totiž netriviálne poznatky z teórie čísel. 

Podobná úloha ako zistenie či je číslo prvočíslo je nájdeme všetkých prvočísel menších ako nejaké zadané číslo. Ak už máme funkciu `jeprvocislo`, tak je uloha veľmi jednoduchá. 

```py
n = int(input('n='))
for i in range(1, n):
    if jeprvocislo(i):
        print(i)
```

Keď sa nad tým zamyslíme, tak tento prístup nie je veľmi rýchly a pre väčšie čísla `n` pôjde veľmi pomaly. Alternatívny spôsob je využiť sito (Eratostenovo). Princíp je nasledovný, ak si zapíšeme všetky čísla menšie ako 20, tak dostaneme. 

1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19

Postupne budeme z tohoto zoznamu eliminovať čísla (budeme ich preosievať ✌). Eliminácia pôjde po násobkoch prvočísel. Najprv eliminujem `1`, to je špeciálny prípad. Potom začne od začiatku zoznamu a prvé číslo, ktoré nie je ani preškrtnuté ani eliminované prehlásim za prvočíslo. Potom eliminujem všetky násobky tohoto čísla. Teda

~~1~~, **2**, 3, ~~4~~, 5, ~~6~~, 7, ~~8~~, 9, ~~10~~, 11, ~~12~~, 13, ~~14~~, 15, ~~16~~, 17, ~~18~~, 19

Takže moje prvé prvočíslo je `2`, znovu opakujem nájdenie prvočísla, teda sa pozriem zľava na prvé neprečiarknuté a nie ešte prvočíslo

~~1~~, **2**, **3**, ~~4~~, 5, ~~6~~, 7, ~~8~~, ~~9~~, ~~10~~, 11, ~~12~~, 13, ~~14~~, ~~15~~, ~~16~~, 17, ~~18~~, 19

Pokračujem ďalej, až prídem na koniec zoznamu a ostanú mi len prvočísla 

~~1~~, **2**, **3**, ~~4~~, **5**, ~~6~~, **7**, ~~8~~, ~~9~~, ~~10~~, **11**, ~~12~~, **13**, ~~14~~, ~~15~~, ~~16~~, **17**, ~~18~~, **19**

Znovu si môžeme uvedomiť, že tento postup nám stačí iba po druhú odmocninu z hornej hranice. Z rovnakého dôvodu ako vyššie ak dôjdeme na toto číslo, tak už stačí len pozberať preosiate čísla. 

Implementácia sa väčšinou robí pomocou pola boolov. Tu uvádzame tri rôzne implementácie preosievanie čísel. 

```py
from time import perf_counter

x=int(input("Zadaj cislo"))

def jeprvocislo(x):
    if x > 1:
        if x == 2:
            return True
        for i in range(2, int(x ** 0.5) + 1):
            if (x % i) == 0:
                return False

        return True
start = perf_counter()

pole = []
for i in range(x):
    if jeprvocislo(i):
        pole.append(i)

print('Elapsed jeprvocislo ', perf_counter() - start)

def sito(n):
    # vypisat vsetky cisla mensie ako n, ktore su zaroven prvocisla
    a = [i for i in range(n)]
    a[0] = None # zahodime 0
    a[1] = None # zahodime 1

    for i in range(n):
        if a[i] != None:
            for j in range(a[i] * 2, len(a), a[i]):
                a[j] = None

    return [i for i in a if i != None]

def sito2(n):
    # vypisat vsetky cisla mensie ako n, ktore su zaroven prvocisla
    a = [True] * n
    a[0] = False # zahodime 0
    a[1] = False # zahodime 1

    for i in range(n):
        if a[i] == True:
            for j in range(i * 2, len(a), i):
                a[j] = False

    return [i[0] for i in enumerate(a) if i[1]]

start = perf_counter()
sito(x)
print('Elapsed sito ', perf_counter() - start)

start = perf_counter()
sito2(x)
print('Elapsed sito2 ', perf_counter() - start)

```

## Úlohy

1. Spomeňme si na prvočísla. Naprogramujme funkciu, ktorá vráti `True`/`False`, podľa toho, či je číslo na vstupe prvočíslo, alebo nie. 
2. Ako vieme úlohu *1* vylepšiť aby sa prvočísla hľadali rýchlejšie? (wiki?)
3. Naprogramujte eratosthenovo sito. 
4. Naprogramujte aplikáciu, ktorá simuluje hod dvoma kockami. Urobte 10000 takýchto hodov a do poľa uložte súčty čísel na oboch kockách, teda budú tam čísla od `2` do `12`. Potom urobte nové pole, kde na pozícií `i` bude počet hodov, ktoré vyšli v súčte `i`. Vypište ho. 
5. Vieme úlohu `4` urobiť aj krajšie? Napríklad nejak pekne vizualizovať naše výsledky?

## Domáca úloha (3 body)

Deadline utorková skupina 28. marec (nedeľa) 2021 23:59.

Deadline stredajšia skupina 29. marec (pondelok) 2021 23:59.

Naprogramujte aplikáciu, ktorá naprv vygenruje `1000` náhodných čísel v intervale [0, 1000). Aplikácia potom z tohoto pola odstráni všetky duplikáty. To znamená, že vo výslednom poli bude každé číslo práve raz. 

### Bonus (1bod)

Ak naprogramujete domácu úlohu, tak že tam nepoužijete žiadne pomocné pole, tak dostanete jeden bod. Znamená to, že všetky operácie sa musia diať nad zadaným polom. 