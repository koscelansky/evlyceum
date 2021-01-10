# Časovač timer

V konzolovom svete nemá veľmi časovač čo robiť, to skôr v grafických aplikáciach (vytvorených pomocou `tkinter`). Python, ale poskytuje funkcie, ktoré nám v tom môžu pomôcť. 

## Module `time`

Všetky funkcie v tejto sekcií sú v module `time`, teda na začiatok programu si musíte dať. Niečo z tohoto. 

```py
import time # potom volate funkcie pomocou time.monotonic()
from time import * # potom staci volat funkcie iba ako monotonic()
```

## `monotonic`

Funkcia `monotonic` vráti hodnotu `float`, ktorá sama o seba skoro nič neznamená, ale vieme ju porovnať s druhým volaním `monotonic` a ich rozdiel je počet sekúnd, ktoré uplynuli medzi nimi. Monotonic znamená, že aj keď niekto zmení čas na počítači, tak táto zmena sa neprejaví na výsledku funkcie `monotonic`. 

## `time`

Funkcia `time` vráti `float`, ktorý reprezentuje počet sekúnd uplynutých od Unix epochy (January 1, 1970, 00:00:00). Toto číslo môžete použiť, mení sa aj s tým ako sa mení čas na zariadení. Toto číslo sa dá reprezentovať pomocou funkcie `gmtime`. To vám vráti túto hodnotu konvertovanú na niečo viacej čitateľné. 

```py
import time

print(time.gmtime(time.time()))
'''
time.struct_time(tm_year=2020, tm_mon=12, tm_mday=14, tm_hour=22, tm_min=38, tm_sec=9, tm_wday=0, tm_yday=349, tm_isdst=0)
'''
```

## `sleep`

Funkcia `sleep` pozastaví vykonávanie na zadaný počet sekúnd, po tomto čase sa pokračuje vo funkcii ďalej.

```py
import time

start = time.monotonic()
time.sleep(1)
print(time.monotonic() - start) # 1.001228777345
```

## Úlohy

1. Vytvorte aplikáciu, ktorá vypísuje čísla od `1` do `100` s tým, že každé ďalšie číslo sa vypíše s jednosekundovým intervalom. 
2. Naprogramujte aplikáciu, ktorá nám povie aký bude dátum o zadaný počet sekúnd od dnes. 
3. Urobte aplikáciu, ktorá vypíše štvorec `8x8` z hviezdičiek, s tým, že sa začne od ľavej hornej hviezdičky a každá ďalšia hviezdička sa zobrazí s oneskorením `300ms`. 
4. Urobte aplikáciu, ktorá nakreslí štvorec ako úloha 3 s tým, že vykreslovanie zrýchluje z jednej sekundy pri druhej hviezdičke až po 0 sekúnd pri poslednej hviezdičke. 
5. Naprogramujte funkciu, ktorá zistí pre zadané čísla `a`, `b`, `n` vypočíta `(a ^ b) mod n`, spolu s týmto **vypíše** aj ako dlho táto funkcia bežala. 

## Domáce úlohy 

Najbližšie tri týždne sa nevidíme, tak dávam pre istotu 2 úlohy (každá za 3 body) a jeden bonus (za dva body). Aby sme stihli aspoň tých 12 úloh. 

Deadline utorková skupina 10. január (nedeľa) 2021 23:59.

Deadline stredajšia skupina 11. január (pondelok) 2021 23:59.

1. Naprogramujte aplikáciu, ktorá dostane ako vstup číslo `n`. A vypíše `n` riadkový trojuholník, s tým, že každý riadok sa vypisuje presne jednu sekundu. Takže prvý riadok vypíše jednu hviezdičku potom po sekunde sa vypíše ďalšia hviezdička na nový riadok, tu sa počká iba 500ms a vypíše sa druhá, potom po ďalších 500m sa pokračuje ďalším riadkom. Samotný trojuholník by mal vyzerať takto (príklad `n == 4`)

   ```plain
   *
   **
   ***
   ****
   ```

2. Vyrobte funkciu, ktorá dostane ako vstup číslo `n` a string `s`. Potom tento string **vypíše** počas `n` sekúnd. S tým, ale že samohlásky `aeiouAEIOU` sa vypisujú dvakrát rýchlejšie ako spoluhlásky. 

**BONUS** Naprogramujte aplikáciu, ktorá dostane ako vstup jedno číslo `n` a vypíše všetky dvojice prvočísel, ktoré sú ostro menšie ako `n`. Dvojice prvočísel sú prvočísla, ktoré sú od seba vzdialené `2`, teda ich rozdiel je `2`. Teda pre číslo 20 bude výpis. 

```
3 5
5 7
11 13
17 19
```