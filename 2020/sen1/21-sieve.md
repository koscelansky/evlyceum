# Eratosthenovo sito

Naprv pár zaujímavstí o poliach, ktoré sa nám môžu dnes, alebo v budúcnosti hodiť. 

* Na poliach fungujú slice, teda `a[2:4]` vráti nové pole, ktoré obsahuje prvky od druhého (vrátane) po štvrtý (bez)
* Ak potrebujeme pole skopirovať, tak môžeme použiť `a[:]`, je to vlastne slice, ktorý zoberie celé pole a teda efektívne vráti kópiu
* V Pythone fungujú takzvané list comprehensions, syntax je približne takáto `[x*x for x in range(10)]`, tento zápis nám vlastne vygeneruje nové pole, v ktorom sú štvorce čísel od `0` po `9` (vrátane).

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