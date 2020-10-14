# Opakovanie (2/3)

## Úlohy

1. Napíšte program, ktorý dostane na vstup číslo `n` a vypíše nasledovný trojuhoľník. 

   ```
   1
   12
   123
   .
   .
   .
   123...n
   ```

   Pre `n == 4` bude výsledok

   ```
   1
   12
   123
   1234
   ```

2. Naprogramujte funkciu `def trojuholnik(n)`, ktorá vypíše nasledovný útvar. 

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

3. Naprogramujte funkcie `def jeprvocislo(n):`, ktorá dostane na vstup číslo `n` a vypíše či je toto číslo prvočíslo alebo nie.

4. Naprogramujte funkcie `def palindrom(s):`, ktorá dostane na vstup string `s` a vypíše, či je reťazec palindrom, teda či sa číta oboma smermy rovnako. 
   * aa, abba, aaafaaa sú palindromy
   * ab, abbac, caaa nie sú palindomy

## Domáca úloha (3 body + 1 bod)

Deadline 13. októbra 2020 23:59.

Naprogramujte dve funkcie.

1. Prvá sa bude volať `def stvorec(n):`, ktorá dostane na vstupe číslo `n` a vykresli nasledujúci tvar. (2body)
   
   * Pre `n <= 0` nevypíše nič.
   * Pre `n == 1` vypíše
     ```plain
     #
     ```
   * Pre `n == 2` vypíše
     ```plain
     ##
     ##
     ```
   * Pre `n == 3` vypíše
     ```plain
     ###
     # #
     ###
     ```
   * Pre `n == 4` vypíše
     ```plain
     ####
     #  #
     #  #
     ####
     ```
   A tak ďalej, vždy bude plná iba časť okolo a v strede budú medzery. 

2. Druhá sa bude volať `def ibaABC(s)`, dostane na vstupe string a vypíše `áno`, alebo `nie` podľa toho, či sú všetky znaky v `s` iba `A`, `B`, alebo `C`. Teda pre `ABBBAC` vypíše `áno` a pre `ABBBDC` vypiše `nie`. (1bod)

Bonus za jeden bod. Naprogramujte funkciu `def sachovnica(n):`, ktorá vykreslí nasledovný útvar
   ```
   n == 1

   *
   ```

   ```
   n == 2

   *-
   -*
   ```

   ```
   n == 3

   *-*
   -*-
   *-*
   ```

   ```
   n == 4

   *-*-
   -*-*
   *-*-
   -*-*
   ```

   ```
   n == 5
   *-*-*
   -*-*-
   *-*-*
   -*-*-
   *-*-*
   ```
