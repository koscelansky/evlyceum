# `if` pokračovanie

Základnú štruktúru príkazu `if` už [poznáme](./3-if.md). Slúži na vetvenie programu na základe podmienky. Dnes sa pozrieme na ďalšie možnosti, ktoré nám Python ponúka. 

## Neúplný príkaz

V príkaze `if` môžeme vynechať `else` vetvu. Je to ekvivalentné prázdnej else vetve. 

```python
x = int(input())
if x == 10:
  print('Je to desat')
```

```python
x = int(input())
if x == 10:
  print('Je to desat')
else:
  pass
```

*Ak chceme niečo v pythone nechať prázdne (napríklad `else` vetvu), tak tam musíme dať aspoň kľúčové slovo `pass`, inak sa bude Python sťažovať na neplatnú syntax.*

## Vnorený `if`

Všetky príkazy v jazyku Python sa dajú do seba vkladať. V jednom podmienenom príkaze môže byť ďalší. Ak chceme napríklad zistiť či je číslo deliteľné aj `5` aj `7`, môžeme to urobiť pomocou operátora `and`

```python
if x % 5 == 0 and x % 7 == 0:
  print('je delitelne aj 5 aj 7')
```

prípadne môžeme urobiť dve podmienky

```python
if x % 5 == 0:
  if x % 7 == 0:
    print('je delitelne aj 5 aj 7')
```

tieto dva programy su ekvivalentné. Oba `if`-y môžu mať aj svoj `else`, tuná pozor na odsadenie, `else` musí byť vždy zarovno `if`-u ku ktorému patrí. Prípadne môžeme iba niektorú vetvu vynechať. Program, ktorý "rozpozná" moje meno.

## Viacnásobný `if`

V niektorých programovacích jazykoch sa stretávame s konštrukciami ako `switch` a `case`, tieto v Pythone neexistujú. Existuje ale náhrada a to je `if ... elif ... else`. Napríklad

```python
x = int(input())
if x % 4 == 0:
  print('cislo je delitelne 4')
elif x % 4 == 1:
  print('cislo ma zvysok 1 po deleni 4')
elif x % 4 == 2:
  print('cislo ma zvysok 2 po deleni 4')
else:
  print('cislo ma zvysok 3 po deleni 4')
```

Toto je ekvivalentné programu

```python
x = int(input())
if x % 4 == 0:
  print('cislo je delitelne 4')
else:
  if x % 4 == 1:
    print('cislo ma zvysok 1 po deleni 4')
  else: 
    if x % 4 == 2:
      print('cislo ma zvysok 2 po deleni 4')
    else:
      print('cislo ma zvysok 3 po deleni 4')
```

`elif`-ov môžeme mať za sebou koľko chceme.

## Zložené porovnávacie operátory

Python má na rozdieľ od iných programovacích jazykov operátory, ktoré sa dajú reťaziť. Teda `a < b < c` je ekvivalentné `a < b and b < c`. Nemusíťe ani používať ten istý operátor, teda je legálne urobiť `a < b > c`, čo bude ekvivaletné `a < b and b > c`. Napríklad

```python
a, b, c, d = 1, 3, 3, 4
print(a < b == c < d) # prints true
print(a < b < c < d) # prints false
```

## Úlohy

1. Napíšte program, ktorému zadáte počet kusov a cenu za jeden kus, on vám potom vypíše celkovú cenu tovaru s tým, že nad 500 kusov je zľava 5% a nad 1000 je zľava 11%.

2. Naprogramujte program, ktorému zadáte počet bodov a on vám podľa [stupnice](./grading.md) vypíše známku. Pri riešení môžete použiť `elif`. 

3. Skúste program z úlohy 2 prepísať bez použitia konštrukcie `elif`, teda iba pomocou `if` a `else`.

4. Rozmyslite si aspoň 3 vstupy, pre ktoré by program nižšie vypísal OK. 

   ```python
   x = int(input())
   if x < 100 and x >= 37:
     if x % 5 > 3:
       if x % 3 == 0 and x % 2 == 0:
         print('OK')
     else:
       if x % 4 == 0 and x % 3 == 0:
         print('OK')
   ```

## Domáca úloha (3 body)

Deadline utorková skupina 11. októbra (nedeľa) 2020 23:59.

Deadline stredajšia skupina 12. októbra (pondelok) 2020 23:59.

Naprogramujte program, ktorý vám povie či je zadaný rok [priestupný](https://sk.wikipedia.org/wiki/Priestupn%C3%BD_rok). Tentokrát budeme používať úplný výpočet. Takže pristupný je ak je deliteľný 4. Ak je ale deliteľný aj 100, tak musí byť aj 400. Ciže napríklad

* 2020 je priestupný (je deliteľný 4 a nie je 100)
* 2000 je priestupný (je deliteľný 4 aj 100 aj 400)
* 1900 nie je priestupný (je deliteľný 4 aj 100, ale nie 400)
* 2021 nie je priestupný (nie je deliteľný 4)
* 1600 je priestuplný (je deliteľný 4 aj 100 aj 400)
* 2100 nie je priestupný (je deliteľný 4 aj 100, ale nie 400)