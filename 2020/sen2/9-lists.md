# Polia

Pole je základná dátová štruktúra v každom programovacom jazyku. V Pythone sa označuje ako `list`. Polia sú vlastne kolekcie prvkov, ku ktorým vieme pristupovať. Polia na rozdieľ od reťazcov môžeme priamo modifikovať. 

## Definovanie poľa 

Najjednoduhšie pole je prázdne pole, ktoré sa v Pythone označuje ako `[]`. V poli nemusime byť vždy homogénne prvky, teda buď čísla, alebo booly, prípadne reťazce. V praxi sa ale väčšinou používajú hlavne polia s rovnakym typom prvkov. 

* `[1, 2, 4]` pole obsahujúce čísla `1`, `2` a `4`
* `['a', 'b', 'cd']` pole obsahujúce stringy
* `['a', 1]` neplatne pole

## Prístup k prvkom

Dĺžky pola `p` získame ako `len(p)`. Pristupovať k jednotlivým prvkom sa potom dá ako `p[0]`, čo bude prvý prvok (ako znaky v reťazci sa čísluje od `0`). Druhý prvok je `p[1]` a tak ďalej, až posledný je `p[len(p) - 1]`. Na pozícií `p[len(p)]` nie je žiaden prvok, to je už mimo hranice pola a ten to skončí výnimkou. 

Iterovať, teda prechádzať, cez všetky prvky pola sa dá urobiť ako 

```python
p = [1, 2, 3, 4]
for i in range(len(p)):
  print(p[i])
```

Prípadne ako 

```python
p = [1, 2, 3, 4]
for i in range(p):
  print(i)
```

Výpis celého listu sa dá urobiť priamo pomocou funkcie `print`. 

## Modifikácia pola

Polia sa dajú zreťazovať za seba (toto nie je priamo modifikácia 😜, ale tak čo). Teda napríklad 

```python
a = [1, 2]
b = [1, 2, 2]
c = a + b # 1, 2, 1, 2, 2
```

Pridavanie prvku na koniec poľa sa robí cez funkciu `append`. 

```python
a = [1, 2]
a.append(3) # 1, 2, 3
```

Pridávanie prvku do streduje pomocou funkcie `insert`, ktorej prvý parameter je kam sa má vložiť (ak na začiatok, tak je to `0`, ak za prvý prvok tak `1`, ...)

```python
a = [1, 2, 3]
a.insert(0, 10) # 10, 1, 2, 3
a.insert(1, 11) # 10, 11, 1, 2, 3
a.insert(len(a), 12) # 10, 11, 1, 2, 3, 12
```

Mazanie prvku sa robí buď pomocou funkcie `pop`, ktora ako parameter chce index odstraňovaného prvku, funkcie ako výstup vráti práve odstránený prvok. Prípadne operátor `del`, ktorý prvok iba odstráni a nevráti. 

```python
a = [1, 2, 3, 4]
print(a.pop(1)) # 2
print(a) # [1, 3, 4]
del a[2]
print(a) # [1, 3]
```

**Poznámka na záver, je veľmi zlý nápad iterovať cez pole a zároveň ho modifikovať.**

```py
a = [1, 2, 3, 4, 5]
for i in range(len(a)):
  a.pop(i) # nebude fungovat dobre
```

## Reťazce a polia

Ak máme pole reťazcov, tak môžeme ich zučiť do jedného stringu pomocou funkcie `join`.

```python
a = ['hello', 'world', '!']
print(''.join(a)) # helloworld!
print(' '.join(a)) # hello world !
print(' word '.join(a)) # hello word world word !
```

Opačná operácia sa robí pomocou funkcii `split`. Ako parameter je string, ktorý slúži na odseparovanie stringov do pola.

```python
s = "najlepsi string"
print(s.split(' ')) # ['najlepsi', 'string']
print(s.split('i')) # ['najleps', ' str', 'ng']
```

## Úlohy

1. Naprogramujte funkcia, ktorá dostana ako vstup pole a vymaže z neho všetky prvky na párnej pozícií (začíname od `0`).
2. Naprogramujte funkciu, ktorá pre zadané pole čísel a hodnotu vráti pozíciu hodnoty v poli, prípadne `-1`, ak sa tam nenachadza. 
3. Naprogramujte aplikáciu, ktorá načítava postupne čísla zo vstupu do poľa, skončí ak je zadaná `0` a potom vypíše druhú mocninu všetkých hodnôt v poli. 
4. Naprogramujte funkciu, ktorá pre zadané pole a hodnotu, vymaže z poľa všetky prvky danej hodnotý. Teda pre `[1, 2, 3, 1, 2]` a hodnote `2` ostane `[1, 3, 1]`.
5. Naprogramujte funkcie ako `join`, bez použitia `join`, teda funkcia bude mat dva prametre a to pole stringov a string oddelovať. Pre `['a', 'b', 'c']` a oddelovač `XXX` bdue výstup `aXXXbXXXc`. 

## Domáca úloha (3 body)

Deadline utorok 1. december 2020 (23:59)

1. Naprogramujte funkciu `pocet`, ktorá pre zadaná pole a hodnotu vráti koľkokrát sa daná hodnota v poli nachádza, takže pre `[1, 2, 1, 2, 3, 4, 3, 1, 2]` a hodnotu `2` bude výsledok `3`.

2. Naprogramujte funkciu `parne`, ktorá pre zadané pole, vráti nové pole, ktoré bude ako pôvodné, akurát, že každým párnym číslom bude vložené číslo 0. Teda pre pole `[0, 1, 2, 3, 2, 2, 5]` bude výsledom `[0, 0, 1, 2, 0, 3, 2, 0, 2, 0, 5]`. 
