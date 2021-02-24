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

