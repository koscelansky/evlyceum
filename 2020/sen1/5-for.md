# Jednoduchý cyklus

Všetky programy čo sme doposial stvorili boli v istom zmysle sekvenčné. Teda vykonali sa zhora dolu, vedeli sme ich vetviť pomocou príkazu `if`. Druhá základná konštrukcia v programoch je cyklus (teda opakovanie niektorých príkazov dopredu zadaný počet krát).

## Format `for` cyklu

V Python-e používame kľúčové slovo `for` a `in`. Najjednoduchší cyklus potom bude vyzerať takto. 

```py
for i in range(10):
  print(i)
```

Tento kúsok programu vypíše pod seba čísla `0` až `10`. Ak si tento cyklus rozoberieme na drobné. Tak začíname s kľúčovým slovom `for`, potom je názov premennej. *Historicky sa tieto premenné nazývajú písmenami `i`, `j`, `k` (`i` ako index). Ale môžete použiť ľubovoľný iný názov.* Potom je znovu kľúčové slovo `in` a za ním `range(X)`. *range je funkcia vracajúca iterable, to nás ale nemusí na teraz trápiť.* Potom musí nasledovať `:`, nasledujúce odsadené riadky sú telo cyklu. Telo cyklu sa vykoná potom opakovane a premenná `i` nadobúda hodnoty `0..X`.

Napríklad tento cyklus 

```py
for i in range(3):
  print("Telo cyklu")
  print(i*2)
```

je ekvivalentný tomuto programu

```py
i = 0
print("Telo cyklu")
print(i*2)
i = 1
print("Telo cyklu")
print(i*2)
i = 2
print("Telo cyklu")
print(i*2)
```

Tu je celkom vidieť prečo asi chceme používať cykly. Aby sme sa veľa nenapísali a aby sme mohli nejaký kus kódu opakovať počet krát, ktorý dopredu nevieme. 

```py
n = int(input('Enter a number: '))
for i in range(n):
  print(i*i)
```

Tento program vypíše všetky štvorce až po n. 

## Posunutý štart

Funkcia `range(n)` štandardne vracia čísla od `0` po `n`, pričom `n` tam už nepatrí. Ak napríklad `n == 5`, tak dostaneme čísla `0, 1, 2, 3, 4`. Ak dáme `n == 0`, tak `i` nenadobudne ani jednu hodnotu a teda telo cyklu sa nevykoná ani raz. 

Vieme ale použiť ešte jeden parameter

```py
for i in range(2, 4):
  print(i)
```

potom sa cyklus vykoná pre hodnty `2, 3`. Prvá hranica (v príklade `2`) sa použije a druhá nie (v príklade `4`).

## Úlohy

1. Vypíšte všetky prirodzené čísla menšie ako 100.

2. Vytvorte program, ktorému zadáme dve čísla (`a`, `b`) a vypíše všetky čísla od `a` po `b` vrátane. Teda pre `a = 2, b = 5` vypíše `2, 3, 4, 5`.

3. Upravte predchádzajúci program aby vypísal iba párne čísla. 

4. Vytvorte program, ktorý prečíta číslo zo vstupu `n` a vypíše súčet všetkých prirodzených čísel menších, rovných ako `n`. Teda pre `n == 5`, to bude súčet `1 + 2 + 3 + 4 + 5` a teda vypíšeme `15`.

5. Pre zadané číslo `n` vypíšte reťazec `n` hviezdičiek. Teda pre `n == 7` bude výsledok `*******`.

6. Upravte program v bode 4, aby vypísal dva výsledky, jeden súčet párnych čísel a jeden súčet nepárnych čísel. 

   Pre `n == 5` budú výsledky `1 + 3 + 5` a `2 + 4`, teda `9` a `6`.

## Domáca úloha (3 body + 1 bod)

Deadline utorková skupina 18. októbra (nedeľa) 2020 23:59.

Deadline stredajšia skupina 19. októbra (pondelok) 2020 23:59.

1. Naprogramujte program, ktorý prečíta zo vstupu dve čísla `a`, `b` a vypíše všetky prirodzené čísla menšie, alebo rovné ako `a`, ktoré nie sú deliteľné `b`. 

   Takže pre `a == 20`, `b == 3` vypíše čísla. `1, 2, 4, 5, 7, 8, 10, 11, 13, 14, 16, 17, 19, 20`.

2. *Bonus za jeden bod.* Naprogramujte program, ktorý dostane na vstupe číslo `n` a vypíše všetky štvorce menšie ako `n`, teda pre `n == 100` bude výstup čísla `0, 1, 4, 9, 16, 25, 36, 49, 64, 81`, číslo `100` už nevypíše, lebo nie je menšie ako `100`. 