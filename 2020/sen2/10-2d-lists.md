# Dvojrozmerné polia

Prvkom pola v Pythone môže byť aj ďalšie pole, potom hovoríme o dvojrozmerných poliach. 

```py
a = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

Alebo môžeme to naformátovať aj krajšie, na formátovaní nezáleží ako

```py
a = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]
```

Prístup je potom rovnaký ako k jednorozmernému polu, teda `a[0]` je prvé pole a teda `a[0][0]` je potom prvý prvok v prvom poli, teda vlastne `1`. `insert`, `append` a `pop` fungujú rovnako ako v prípade jednorozmerného pola. 

## Pozor na referencie

Ak vytvárame pole do ktorého ukládame ďalšie polia (to je v podstate dvojrozmerné pole - pole polí (: ) lahko sa môže stať, že vyrobíme pole referencíí na jedno pole. Napríklad máme pole ktoré chceme zreplikovať tri krát do ďalšieho pola:
```py
a = ['a', 'b', 'c']
b = []
for i in range(3):
  b.append(a)

print(b)
```
Toto bude na oko fungovať dobre:
```
[['a', 'b', 'c'], ['a', 'b', 'c'], ['a', 'b', 'c']]
```
Problém nastane až keď niektoré vnorené pole zmodifikujeme:
```
b[0][0] = 'c'
print(b)
```
```
[['c', 'b', 'c'], ['c', 'b', 'c'], ['c', 'b', 'c']]
```
Dôvodom je, že naše pole `b` obsahuje len tri krát referenciu na pole `a`. Nikde nebolo vytvorené nové pole ako by sme očakávali.
Spôsob ako to fixnúť je povedať Pythonu aby vytvoril nové pole pomocou `list(a)`
```py
a = ['a', 'b', 'c']
b = []
for i in range(3):
  b.append(list(a))
```

Rovnako si treba dať pozor na skrátený zápis inicializácie pola. Napríklad takto si inicializujeme pole s tromi nulami:
```py
c = 3 * [0]
```
Ak by sme ale použili tento zápis na výrobu matice 5x3:
```py
c = 5 * [3 * [0]]
```
tak pole `c` bude obsahovať päť krát referenciu na jedno trojprvkové pole.
```py
c[0][0] = 1
print(c)
```
```
[[1, 0, 0], [1, 0, 0], [1, 0, 0], [1, 0, 0], [1, 0, 0]]
```

Viac o dvojrozmerných poliach sa môžete dočítať napríklad na <https://www.tutorialspoint.com/python_data_structure/python_2darray.htm>.

## Úlohy

1. Vyrobte aplikáciu, ktorá načíta dvojrozmerné pole, najprv musíme zadať `n` a `m` a potom `n*m` čísel. Potom dané pole vypíšte. 
2. Naprogramujte funkciu, ktorá pre zadané `n` a `m` vyrobí 2d pole s tým, že obsahuje čísla `0` až `n*m-1`. 
3. Napíšte funkciu, ktorá pekne naformátuje 2d pole do tabuľky.
4. Napíšte aplikáciu, ktorá pre zadané `n` vyrobí tabuľku `n x n`, ktorá obsahuje násobilku od `1` po `n`.
5. Napíšte funkciu, ktorá dostane na vstupe dve matice (teda vlastne 2d polia) a vráti ich súčet, ako súčet matíc.

## Domáca úloha

Deadline utorok 8. december 2020 (23:59)

Naprogramujte funkciu, ktorá má na vstupe 2d pole plné čísel. Na výstupe vráti jednorozmerné pole, kde budú priemery (tie by mali byť ako `float`) jednotlivých riadkov, teda napríklad pre vstup

```py
a = [
  [1, 2, 3],
  [3, 1, 6],
  [5, 8, 10]
]
```

Má byť výstup

```py
[ 2.0, 3.33333333, 7.66666666]
```


### Bonus (1bod)

Naprogramujte funkciu, ktorá má jeden parameter, maticu `M`. Funkcia spočíta stopu `trace` matice. Stopa je súčet všetkých prvkov na diagonále. Definícia je tu <https://en.wikipedia.org/wiki/Trace_(linear_algebra)>. Musíte aj skontrolovať, či je matica naozaj štvorcová, inak totiž stopa neexistuje a funkcia má vtedy vrátiť `None`.
 