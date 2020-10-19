# Reťazce

Stringy, teda reťazce znakov sú jeden zo základných typov v jazyku Python. Zadávajú sa buď s `'`, alebo `"`. 

```py
"Toto je retazec"
'Ak toto je reťazec'
"""Viacriadkový
reťazec"""
```

Reťazec nám vracajú funkcie ako `input()`.

## Jednotlivé znaky

Dĺžku reťazca získame volaním funkcie `len`, prístup k jednotlivým znakom je cez operátor `[]`, teda ak chceme pod seba vypísať všetky písmena v reťazci, môžeme zo urobiť takto. 

```py
s = input()
for i in range(len(s)):
  print(s[i])
```

Pripadne sa to dá skrátiť ako 

```py
for i in s:
  print(s)
```

tu `i` nadobúda postupne všetky znaky v reťazci, teda už nepoužívame `s[i]`, ale priamo `i`.

Stringy sa nedajú meniť, takže ak potrebuje string upraviť musíme vytvoriť nový. Teda napríklad nemáme radi všetky písmena `x` a `X`, tak to urobíme takto 

```py
s = 'strixnxg x s pxismenxami'
t = ''
for i in s:
  if i != 'x' and i != 'X':
    t += i
```

## Operácie s reťazcami

Reťazce vieme sčítavať pomocou volania `+`, teda 

```py
s = "Ahoj"
t = "svet!"
msg = s + ' ' + t
print(msg) # will print Ahoj svet!
```

Prípadne ak potrebujeme `s = s + 'P'`, tak sa to dá skrátiť ako `s += 'P'`.

Funguje aj operátor `*`, ktorý daný reťazec znásobí, takže `'ahoj' * 3` je `'ahojahojahoj`, to isté je aj `3 * 'ahoj'`.

Ďalej vieme reťazec konvertovať na číslo pomocou funkcie `int` a naopak pomocou funkcie `str`. 

```py
i = int(input())
s = "Zadal si cislo " + str(i)
print(s)
```

Toto sa môže zdať neužitočné, ale týmto spôsobom si overíme, že užívateľ naozaj zadal číslo.

## Uvodzovky a nové riadky

Ak potrebujeme do reťazca dať `'`, tak máme dve možnosti, buď reťazec uzatvoríme do `"` takto `"retazec s '"` (opačne pre druhú uvodzovku), alebo použijeme escape sekvenciu. Teda takto `'retazec s \''`, iné escape sekvecie sú `\"`, `\\`, alebo `\n` čo je nový riadok. 

## `while` cyklus

Mali sme už `for` cyklus, ktorý beží zadaný počat krát, ak ale chceme aby cyklus bežal pokiaľ nie je splnená nejaká podmienka, tak použije `while`. 

```py
x = input()
while x != 'bonifac':
  print('skus este raz')
  x = input()
```

Tento program bude bežať až pokiaľ nezadáte meno `bonifac`. Teda cyklus bude bežať dokiaľ je pomienka splnená. 

Napríklad nás program môže vygenerovať náhodné číslo, a my ho musíme potom uhádnuť. 

```py
import random

x = random.randint(0, 100) # nahodne cislo 0..100 vratane
p = int(input('hadaj cislo 0..100'))
while p != x:
  p = int(input('skus este raz'))
```

## Úlohy

1. Modifikujte hádací program v časti o `while`, tak aby na záver vypísal koľko pokusov na to potreboval.
2. Modifikujte program *(1)* tak aby po každom tipe vypísal, či je tip menši ako hádané číslo, alebo väčší. 
3. Naprogramujte program, ktorý zo zadaného reťazca vymaže všetky samohlásky.
4. Naprogramujte program, ktorý použije iba `while` cyklus a zistí prvý výskyt zadaného znaku v reťazci. Teda pre reťazec `ajfghif` a `f` vypíše `2` (čísluje sa od 0).
5. Naprogramujte program, ktorý dostane na vstup string `s` a vypíše, či je reťazec palindrom, teda či sa číta oboma smermi rovnako. 
   * aa, abba, aaafaaa sú palindromy
   * ab, abbac, caaa nie sú palindromy
6. Urobte program, ktorý pod seba vypíše jednotlivé cifry čísla (skúste to aj pomocou `while` cyklu) a potom súčet týchto cifier.
7. Naprogramujte program, ktorý vypíše nasledovný útvar pre zadané `n`. 

   ```
   *
   **
   ***
   ****
   ```

   Pričom najdlhší riadok má dĺžku `n`. Teda vyššie je uvedený výsledok pre `n == 4`. Pre `n == 1` bude výsledkom iba jedna `*`.

## Domáca úloha (3body)

Deadline utorková skupina 25. októbra (nedeľa) 2020 23:59.

Deadline stredajšia skupina 26. októbra (pondelok) 2020 23:59.

1. Naprogramujte program, ktorý načíta číslo a potom vypíše súčin jeho cifier + dĺžku čísla. Teda pre číslo `123` to bude `9` (`1*2*3 + 3`) a pre `5212` (`5*2*1*2 + 4`) to bude `24`. 

2. Naprogramujte program, ktorý vypíše nasledovný útvar pre zadané `n`. 

   ```
      *
     **
    ***
   ****
   ```

   Pričom najdlhší riadok má dĺžku `n`. Teda vyššie je uvedený výsledok pre `n == 4`. Pre `n == 1` bude výsledkom iba jedna `*`.