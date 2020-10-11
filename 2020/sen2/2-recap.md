# Opakovanie

* [Výpisy na konzolu a načítanie vstupu z konzoly](../sen1/2-recap.md).
* Základné typy v Pythone `int`, `float` a `str`.
* Podmienený príkaz `if`, jeho zložitú verziu `elif` a zložené podmienky `and` a `or`.
* Jednoduchý `for` cyklus a vnorené cykly.
* Prevody medzi číselnými sústavami.
* Funkcie.
* Lokálne a globálne premenné.
* Náhodné čísla.
* Práca s reťazcami.
* Práca s poliami (listami).

## Úlohy

1. Napíšte program, ktorý prečíta mesiac (číslom) a rok a vypíše počet dní v danom mesiaci. Zohľadnice priestupné roky, rok je priestupný ak je deliteľný 4, no ak je deliteľný 100, tak musí byť aj 400. Teda rok 2000 bol, ale 1900 nebol a ani 2100 nebude. 

   ```
   Zadaj mesiac 1
   Zadaj rok 2021
   Mesiac 1 v roku 2021 ma 31 dni

   Zadaj mesiac 2
   Zadaj rok 2020
   Mesiac 2 v roku 2020 ma 29 dni
   ```

2. Napíšte program, ktorý dostane na vstup číslo `n` a vypíše nasledovnú tabuľku. 

   ```
   1234...n
   234...n1
   34...n12
   .
   .
   .
   n1234...
   ```

   Pre `n == 4` bude výsledok

   ```
   1234
   2341
   3412
   4123
   ```

3. Napíšte program, ktorý dostane na vstup číslo `n` a vypíše nasledovnú tabuľku. 

   ```
   *
   **
   ***
   ****
   ***
   **
   *
   ```

   Pričom najdlhší riadok má dĺžku `n`. Teda vyššie je uvedený výsledok pre `n == 4`. Pre `n == 1` bude výsledkom iba jedna `*`.

4. Naprogramujte funkcie `def hex2bin(s):`, ktorá dostane na vstup string `s` číslom v šesťnáskovej sústave, toto číslo potom prevedie do binárnej a vypíše ho na konzolu.

   ```
   hex2bin('deadbeef')
   11011110101011011011111011101111
   ```

5. Naprogramujte funkcie `def removePrimes(s):`, ktorá dostane na vstup pole čísel a vymaže z neho všetky prvočísla.

6. Naprogramujte Eratostenovo sito.

## Domáca úloha (3 body)

Deadline 6. októbra 2020 23:59.

1. Napíšte program, ktorý dostane na vstup čísla `n`, `a`, `b` a vypíše na výstup všetky čísla **menšie** ako `n`, ktoré nie sú deliteľné ani číslom `a`, ani `b`.
   ```
   n=10
   a=3
   b=7
   1 2 4 5 8 
   ```
