# Triedenie

Veľmi častá operácia nad poliami je ich triedenie. Teda usporiadanie oprvkov od najmenšieho po najväčší. Python nám na to poskytuje dve dva hlavné spôsoby. Jeden vytvorí nové pole a druhý utriedi pole in-situ teda pomení pôvodné pole. 

## sorted

Funkcia `sorted` vráti utriedenú kópiu pola. 

```py
a = [3, 6, 4, 7, 1, 0, 3]
b = sorted(a)

print(a) # 3 6 4 7 1 0 3
print(b) # 0 1 3 3 4 6 7
```

## a.sort()

Metóda (funkcia volaná nad polom) `sort` utriedi pole, nad ktorým je volaná. Je to trošku rýchlejsie ako volanie `sorted`, ale teda neostane nám pôvodné pole. 

```py
a = [3, 6, 4, 7, 1, 0, 3]
b = a.sort()

print(a) # 0 1 3 3 4 6 7
print(b) # None
```

## Triedenie v opačno poradí

Obe spomíné funkcie majú paramter `reverse`, ktorý keď nastavíme na `True`, tak sa zmení poradie na opačné (teda od najväčšieho po najmenšie).

```py
a = [3, 6, 4, 7, 1, 0, 3]
b = sorted(a, reverse=True)

print(b) # 7 6 4 3 3 1 0
```

## Modifikácia porovnania

Štandardne sa triedi podľa operátora `<` (resp. `>` ak je nastavene `reverse`). Toto nie je vždy žiadúce. Napríklad ak chceme porovnáva stringy, ale netrápi nás či je písmeno veľké, alebo malé. Prípadne chceme utriediť reťazce podľa dĺžky a nie podľa obsahu.

Nato sa používa parameter `key`, kde uvedieme funkciu, ktorá sa najprv nad prvkom zavolá a jej výsledok sa porovnáva. Napríklad ak chceme reťazce utriediť podľa ich obsahu a nezaujímajú nás veľkosti písmen (case insensitive compare) môžeme to urobiť takto. 

```py
def transform(s):
  return s.lower()

a = ['', 'Ahoj', 'ahoj', 'parameter', 'cHceme', 'PODLA']
b = sorted(a, key=transform)
```

Alternativne môžeme použiť skrátený zápis funkcie, Python nato požíva kľúčové slobo `lambda`, zápis je potom `lambda <parameter>: <telo funkcie>`. Telo funkciu môže byť iba jeden príkaz, ktorého výstup sa použije aj ako výstup celej lambdy. Teda napríklad

```py
a = ['', 'Ahoj', 'ahoj', 'parameter', 'cHceme', 'PODLA']
b = sorted(a, key=lambda x: x.lower())
```

Prípadne v tomto konkrétnom prípade môžeme použiť priamo aj funkciu `lower`. 

```py
a = ['', 'Ahoj', 'ahoj', 'parameter', 'cHceme', 'PODLA']
b = sorted(a, key=str.lower)
```

## Úlohy

1. Načítajte zo súboru čísla a utrieďte ich a zapíšte do toho istého súboru. 
2. Utriedte stringy zo súboru 
   * podľa dĺžky,
   * podľa počtu samohlások,
   * najprv podľa dĺžky a potom rovnaké podľa počtu samohlások.
3. Naprogramujte triedenie čísel bez použitia funkcie `sort`, alebo `sorted`. 
4. Naprogramujte funkciu, ktorá zo zadaného poľa nájde medián (prvok, ktorý sa nachádza v usporiadanej postupnosti v strede). 

## Domáca úloha 

Deadline streda 9. marec 2021 (23:59).

Vytvorte funkcie

1. `print_list`, ktorej vstupnym parametrom bude pole čísel a názov súboru. Táto funkcia vypíše prvky daného pola do súboru s tým, že každý prvok bude na novom riadku.
2. `read_list`, ktorej vstupným parametrom bude názov súboru, funkcie súbor otvorí, prečíta z neho čísla, ktoré su na riadkoch a vráti pole s týmito číslami. Efektívne keď zavolám `print_list` a potom `read_list`, mal by som dostať to isté pole.
 
Pomocou vašej vytvorenej funkcie prečítajte vstup zo súboru `cisla.txt`. Ďalej zotrieďte toto pole od najväčšie po najmenšieho číslo a uložte ho do nového pola. Následne toto zotriedené pole uložte pomocou funkcie `print_list` do súboru `sorted.txt`. 

### Bonus (1 bod)

Urobte funkciu `pridaj_nahodne`, ktorá do utriedeného poľa pridá `10` náhodných čísel od 1 po `1000` (vrátane) s tým, že pole ostane utriedené a vaša funkcia nikdy nezavolá `sort`, ani `sorted`, ani im podobné. 