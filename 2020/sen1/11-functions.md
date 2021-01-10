# Funkcie

Funkcie sú základom každého imperatívneho programovacieho jazyka akým je aj Python. Slúžia na rozdelenie programu do logických celkov, ktoré potom lepšie dokážeme chápať a na znovu používanie kódu. 

## Definovanie funkcií 

V pythone máme kľúčové slovo `def`, za ním následuje meno funkcie, potom parametre a na záver dvojbodka. Potom telo funkcie, to môže byť akoby ďalší python program, môžeme robiť všetko to čo mimo funkcie. 

```py
def toto_je_Funkcia123():
  print('Ahoj od Funkcie123')
```

Ak potom chceme funkciu zavolať, tak použijeme jej meno a zátvorky. Funkciu môžeme volať aj viackrát za sebou.

```py
toto_je_Funkcia123()
toto_je_Funkcia123()
```

## Parametere

Funkcie môžu mať parametre, uvádzame ich ako mená v zátvorkách, potom vo funkcii sa na ne môžeme odvolávať danými menami. 

```py
def ahoj(meno, priezvisko):
  print('Ahoj' + meno + ' ' + priezvisko)
  print('Ako sa mas?')

priezv = input()
ahoj('First Name', priezv)
```

## Návratové hodnoty

Funkcie môžu aj vracať hodnoty, robí sa to pomocou kľúčového slova `return`.

```py
def parne(n):
  return n % 2 == 0

x = int(input())
if parne(x):
  print('ano je parne!')
```

## Úlohy

1. Naprogramujte funkciu, ktorá vypočíta faktoriál daného čísla. 
2. Naprogramujte funkciu, ktorá spočíta všetky čísla medzi zadanými hranicami ako parametre, teda napriklad `funkcia(4, 7)` vráti výsledok `4 + 5 + 6 + 7`, teda `22`.
3. Naprogramujte funkciu, ktorá z troch čísel na vstupe vráti maximum.
4. Naprogramujte funkciu, ktorá vráti či je číslo prvočíslo.
5. V úlohe *2* vypíšte celý výraz aj s výsledkom. 
6. Naprogramujte funkciu powmod, ktorá dostane tri (`a`, `b`, `n`) čísla a vypočíta `(a ** b) % n`. Viete to urobiť rýchlejšie?

## Domáca úloha

Deadline utorková skupina 6. december 🎅 (nedeľa) 2020 23:59.

Deadline stredajšia skupina 7. december (pondelok) 2020 23:59.

Vyberte si dve úlohy za 3 body, resp. urobte všetky tri a dostanete 4, teda aj s bonusom.

1. Naprogramujte funkciu `cislo`, ktorá dostane ako vstup string a zistí (teda vráti `True`, alebo `False`) podľa toho, či zadaný string je číslo, teda či obsahuje iba číslice `0..9`. 
2. Naprogramujte funkciu `velke`, ktorá pre zadaný string vypíše koľko velkých písmen sa v ňom vyskytuje. Teda pre string `Quick Brown Fox` vypíše `3`. 
3. Naprogramujte funkciu `binary`, ktorá ako vstup dostane číslo `n` a dva znaky `x, y`, teda napríklad `binary(11, 'A', 'X')`, funkcia vráti číslo `n` zakódované do binárnej sústavy, kde sa namiesto `0` použije `x` a namiesto `1` `y`. Teda pre príklad `binary(11, 'A', 'X')` bude výsledok (návratová hodnota) `XAXX`, lebo číslo `11` je binárne `1011`, čo mi zakódujeme ako `XAXX`.