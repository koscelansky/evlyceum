# Vnorené cykly

Cyklus je základný výstabný blok *imperatívnych* programovacích jazykov. Inak to nie je ani v Pythone. Cykly sa môžu do seba ľubovoľne vnárať, až do hĺbky cca 20. To je už ale priveľa cyklov a ak sa niekedy nájdeme v situácií, že budeme potrebovať toľko, tak niečo robíme zle. 

## Syntax

Štandardne sa do seba vnárajú hlavne `for` cykly, pri `while` cykloch sa už dosť tažko rozmýšla nad tým, čo vlastne program robí. 

```py
for i in range(10):
  for j in range(10):
    print(i, j)
```

Takýto program vypíše `100` riadkov. Začne pri `0 0`, potom ide aź k `0 9`, potom `1 0` až `1 9`, posledný vypísaný prvok bude `9 9`. Dôležite je aby sme premennú vo vnorenom cykle nazvali ina ako vo vonkajšom inak budeme mať problémy. Štandardne sa používajú názvy premenných `i`, `j`, `k`. Samozrejme nič nám nebráni použiť iné názvy.

## `print`

Funkcia `print` má dva parametre, pomocou ktorých vieme určovať ako sa budú prvky vypisovať. Jeden je `end` a druhý `sep`.

* `end` je string, ktorý sa vypíše po celom printe, štandardne nový riadok, teda `\n`. 
* `sep` je string, ktorý sa vypíše medzi jednotlivými prvkami, štandardne je to medzera. 

```py
print(1, 2, 3, sep='X', end='koniec')
print(4)
```

Vypíše `1X2X3koniec4`.

## Úlohy

1. Vypíšte dvojice čísel `1..9`, kde jedno delí druhé. Teda dvojica `4 2` bude na výstupe, ale `3 4` nie. 
2. Napíšte program, ktorý pre zadané `n` (zo vstupu) vykresli tabuľku. 
   ```
   1234..n
   1234..n
   .
   .
   1234..n
   ```
   Pričom riadkov bude `n`. Napríklad pre vstup `4`. Bude výsledok 
   ```
   1234
   1234
   1234
   1234
   ```
3. Upravte program z úlohy *(2)* tak aby vypisoval nie stvorce, ale trojuholníky, teda pre vstup `4`. 
   ```
   1
   12
   123
   1234
   ```
4. Upravte program z úlohy *(2)* tak aby boli riadky o jedno posunuté. Napríklad pre `4`.
   ```
   1234
   2341
   3412
   4123
   ```
5. Napíšte program, ktorý vypíše malú násobilku, teda tabuľku
   ```
      1  2  3  4  5  6  7  8  9 10
   1  1  2  3  4  5  6  7  8  9 10
   2  2  4  6  8 10 12 14 16 18 20
   3  3  6  9 12 15 18 21 24 27 30
   4  ...
   5
   6
   7
   8
   9
   10
   ```
6. Napište program, ktorý pre zadané `n` vypíše trojuholník. 
   ```
      1
     222
    33333
   4444444
   ...
   ```

## Domáca úloha (3 body)

Deadline utorková skupina 8. novembra (nedeľa) 2020 23:59.

Deadline stredajšia skupina 9. novembra (pondelok) 2020 23:59.

1. Urobte aplikáciu, ktorá pre zadané `n` vypíše trojuholník s počtom riadkov `n`, ale prvky nebudú čísla ale písmená. Teda pre `8` bude výstup
   ```
   A
   BC
   DEF
   GHIJ
   KLMNO
   PQRSTU
   VWXYZAB
   CDEFGHIJ
   ```
   Ako vidíte abeceda sa cyklí, teda ked sa dostanem na `Z`, tak pokra+cujem `A`. Tu vám pomôžu funkcie `chr` a `ord` čo sme mali minule. 