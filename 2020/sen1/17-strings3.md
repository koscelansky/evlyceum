# Reťazce 2

Na predposlednej hodine sme mali funkcie, ktoré vedia zmeniť string (v skutočnosti vracajú nový string). Napríklad `tolower`, ktorá zmení string na všetko malé písmená (mínusky). Na poslednej sme riešili formátovanie pomocou funkcie `format`. Posledná často používaná operácia je extrakcia podreťazcou. Na túto operáciu sa používa systém, ktorému sa v Pythone hovorí [slicing](https://railsware.com/blog/python-for-machine-learning-indexing-and-slicing-for-lists-tuples-strings-and-other-sequential-types/). 

Ďalej v príkladoch uvažujeme, že 

```py
s = 'ABCDEFGHIJ'
```

## Indexovanie

Najjednoduhší prípad slicu je obyčajné indexovanie. Takže napríklad

```py
s[0] # A
s[2] # C
s[-1] # J
s[10] # error
```

Ako vidíme záporné indexy berú vlastne indexy odzadu. 

| -     | A |	B | C | D | E |
|-------|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 |
| Alt.  |-5 |-4 |-3 |-2 |-1 | 

Všetky indexy mimo `-5..4` skončia s errorom. 

## Slice

Najčastejšie sa používajú slice so začiatkom a koncom. Syntax je `[start:end]`, ktorá znamená, že chceme časť stringu od indexu `start` po index `end`, pričom `end` tam už nepratrí. Ak vynecháme `start`, tak je to akoby `start` bol rovný `0`. Rovnako ak vynecháme `end`, tak je to po koniec stringu, teda akoby tam bolo zadané `len(s)`. Napríklad

```py
print(s[1:4]) # BCD
print(s[1:]) # BCDEFGHIJ
print(s[1:len(s)]) # BCDEFGHIJ
print(s[:4]) # ABCD
print(s[0:4]) # ABCD
```

## Záporné indexy

Záporné indexy fungujú veľmi podobne ako v jednoduchom prípade vyššie. V podstate si to môžeme prestaviť takto. `s[start:end]` je ekvivalentné tomuto. 

```py
def func(s, start, end):
  x = ''
  if start < 0:
    start = len(s) + start
  if end < 0:
    end = len(s) + end
  for i in range(start, end):
    x += s[i]
  return x
```

Napríklad 

```py 
print(s[-2:4]) # empty string
print(func(s, -2, 4))

print(s[4:-2]) # EFGH
print(func(s, 4, -2))

print(s[-3:-4]) # empty string
print(func(s, -3, -4))

print(s[-5:-3]) # FG
print(func(s, -5, -3))

print(s[-5:]) # FGHIJ
print(s[:-3]) # ABCDEFG
```

## Úlohy

1. Aký slice musíme použiť aby sme dostali nasledujúce stringy zo stringu `s = '123456789'`
   * `234`
   * `3456789`
   * `34567`
2. Aký bude výsledok nasledujúcich sliceov ak `s = '123456789'`
   * `s[:2]`
   * `s[-4:]`
   * `s[-4:len(s)]`
   * `s[len(s):]`
3. Naprogramujte program, ktorý vypíše nasledujúci útvar a môže na to použiť iba slice zo stringu `s = '123456789'` (teda žiadne iné zreťazovania, alebo iné stringy)
   ```
   1
   12
   123
   1234
   12345
   123456
   1234567
   12345678
   123456789
   ```

## Domáca úloha

Deadline utorková skupina 14. február (nedeľa) 2021 23:59.

Deadline stredajšia skupina 15. február (pondelok) 2021 23:59.

Podobne ako v úlohe *3*, máte k dispozícií string `s = '123456789'` a pomocou sliceov z neho naprogramujte nasledujúci útvar

```plain
9
89
789
6789
56789
456789
3456789
23456789
123456789
```

### Bonus (1bod)

Ako v úlohe *3* máte k dispozícií string `s = 98765432123456789`, urobte pomocou slice a funkcie `format` (žiadne nové stringy, okrem formátovacieho reťazca do funkcie `format`) nasledujúci útvar. 

```plain
         0
        101
       21012
      3210123
     432101234
    54321012345
   6543210123456
  765432101234567
 87654321012345678
9876543210123456789
```