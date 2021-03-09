# Polia cvičenia

Väčšina úloh sa dá vyriešiť pomocou použitia funkcií z Pythonu, my to ale skúsime bez nich iba s tým čo sme mali na minulej hodine. 

1. Naprogramujte funkciu, ktorá spočíta priemer z pola čísel. 
2. Naprogramujte funkciu, ktorá vráti pole otočené. `[1, 2, 3, 5]` bude na výstupe `[5, 3, 2, 1]`.
3. Naprogramujte funkciu, ktorá pre zadané pole a hodnotu vrátí index v tomto poli. Akú hodnotu môžeme vrátiť, ak sa tam prvok nenachádza?
4. Naprogramujte funkciu, ktorá ako vstup dostane dve polia a na výstupe vráti pole, ktoré obsahuje iba prvky, ktoré sa vyskytujú v oboch vstupných poliach (môžeme predpokladať, že prvky sa v poliach neopakujú). 
5. Vieme úlohu *4* vyriešiť lepšie ak by sme vedeli, že prvky v vstupných poliach sú zotriedené podľa veľkosti od najmenšieho po najväčšie. 
6. Naprogramujte funkciu, ktorá pre zdané pole vráti pole, ktoré neobsahuje duplikáty. Takže pre vstup `[1, 2, 1, 4, 2, 5, 4]` bude výsledok `[1, 2, 4, 5]`. 

## Domáca úloha (4body)

Deadline utorková skupina 18. marec (štvrtok) 2021 23:59.

Deadline stredajšia skupina 19. marec (piatok) 2021 23:59.

Rovnako ako v úlohách nepoužívajte žiadne knižničné funkcie na prácu s polom, okrem tých ktoré sme mali na minulej hodine. 

1. Naprogramujte funkciu, ktorá dostane dva polia `a` a `b` a vráti `True` ak sa všetky prvky z pola `b` na chádzajú aj v `a`, inak `False`.
   * `a = [1, 2, 4, 5]` `b = [1, 2, 3]` je `False`, lebo v `b` je aj `3` a tá nie je v `a`.
   * `a = [1, 2, 4, 5]` `b = [1, 2, 1, 2, 1]` je `True`, lebo v `b` sú iba prvky, ktoré sú aj v `a`. Nevadí, že pole `b` je dlhšie ako `a`.
2. Naprogramujete funkciu, ktorá pre zadané pole vráti druhú najmenšiu hodnotu. Napríklad pre `[1, 5, 0, 4, 8, 9, -1]` bude výsledok `0`, lebo majmenší je `-1` a `0` je druhý najmenší prvok. Pozor ak sa v poli nachádza dva krát najmenší prvok, tak vrátime ten, napríklad `[1, 5, 0, 4, -1, 8, 9, -1]` bude výsledok `-1`. *V podstate ak pole zoradíme od najmenšieho po najväčšie číslo, tak chceme vlastne druhý prvok v takomto poli.*

### Bonus (1bod)

Urobte funkciu, ktorá má dva parametre. Prvý je pole a druhý je hodnota. Funkcia presunie všetky prvky so zadanou hodnotou na koniec pola, realtívne poradie ostatných prvkou nechá zachované. Napríklad pre vstup `[1, 2, 0, 4, 1, 2, 0, 5, 4, 3, 2, 0]` a hodnotu `2` bude výstupom `[1, 0, 4, 1, 0, 5, 4, 3, 0, 2, 2, 2]`.