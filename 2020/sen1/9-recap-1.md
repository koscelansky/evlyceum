# Opakovanie

1. Naprogramujte aplikáciu, ktorá vypíše na konzolu všetky malé písmená anglickej abecedy, ktorých poradové číslo je delitelné `3` alebo `5`. `a` má poradové číslo `1`.
2. Naprogramujte aplikácie, ktorá zistí, či zadaný string je platná hex adresa na 32-bit architektúre. Tie sa zapisujú ako `0xDDDDDDDD`, kde `D` je hexa číslica, teda `0-9`, alebo `a-f`, prípadne `A-F`.
3. Pre zadané číslo `n`, vypíšte takýto útvar
   ```plain
   XO-XO-X
   O-XO-X
   -XO-X
   XO-X
   O-X
   -X
   X
   ```
   kde počet riadkov bude práve `n`.
4. Naprogramujte konverziu z binárnej sústavy do štvorkovej.
5. Naprogramujte aplikáciu, ktorá v reťazci znakov nájde znak, ktorý sa vyskytuje najčastejšie a potom ho zmení na veľké písmeno. 

## Domáca úloha

Deadline utorková skupina 22. novembra (nedeľa) 2020 23:59.

Deadline stredajšia skupina 23. novembra (pondelok) 2020 23:59.

Z troch úloh nižšie si vyberte **dve** ktoré urobíte (3 body), prípadne urobte *všetky tri za (4body, teda aj s bonusom)*.

1. Naprogramujte aplikáciu, ktorá vypíše pre zadané `n` takýto tvar
   ```
   XXXXXXX
   XXX XXX
   XX   XX
   X     X
   ```
   Toto je pre `n=4`, teda `n` je počet riadkov. Postupné výpisy pre `n=1` az `n=3`
   ```
   X
   ```
   ```
   XXX
   X X
   ```
   ```
   XXXXX
   XX XX
   X   X
   ```
2. Naprogramujte aplikáciu, ktorá si zo vstupu načíta string a vypíše rovnaký string s tým, že všetky písená ktorých ASCII hodnota (výsledok funkcie `ord`) je delitelná `3` sa objavia ako veľké písmena. Teda `abcd ef` sa zmení na `abCd eF`.
3. Naprogramujte konverziu z čísla do sústavy 26árnej. Kde jednotlivé cifry budú `a..z`, kde `a` je `0`, `b` je `1`, ..., `z` je `25`. Teda napríklad 
   * 0 bude `a`
   * 1 bude `b`
   * 28 bude `bc`
   * 1234 bude `bvm`

