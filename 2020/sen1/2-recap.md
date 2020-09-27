## Opakovanie

### Výpis pomocou `print`

Výpis na konzolu (príkazový riadok, terminál, shell) je úplne základ asi v každom programovacom jazyku. V Pythone sa spoužíva funkcia `print`. Môžeme si to skúsiť. Nasledujúci program vypíše číslo 1418. 

```python
print(1418)
```

Dobre, môžeme skúsiť aj nejaký text. 

```python
print(Ahoj)
```

Tento program ale nevypíše `Ahoj`, ale `NameError: name 'Ahoj' is not defined`. Je to preto, lebo reťazce znakov (stringy) sa v Pythone uvádzajú buď s `'`, alebo `"`. Teda `'Ahoj'`, alebo `"Ahoj"`. *Tieto dva zápisy sú ekvivalentné, neskôr uvidíme prečo by sme mohli chcieť použiť jeden, alebo druhý, nateraz je nám to jedno.* 

```python
print("Ahoj")
print('Ahoj')
```

Výsledok sú dva totožné riadky s textom `Ahoj`. Všimnime si, že `print` vždy aj zalomí riadok (posunie nás na ďalši riadok), preto ak chceme urobiť prázdny riadok, tak zavoláme `print()` (musia tam byť aj prázdne zátvorky, iba `print` bez zátvoriek by nefungovalo).

```python
print("Hello ")
print()
print("world!")
```

Vypíše 

```
Hello 

world!
```

`print` podporuje aj výpis viacerých hodnôt súčasne (tieto oddeli medzerou), teda napríklad `print('Ahoj', 'svet', 123, '!')` vypíše na konzolu `Ahoj svet 123 !`.

Vypisovať nemusíme iba hodnoty ale aj obsah premenných. Teda napríklad

```python
x = 2
print('Premenna X =', x)
```

zobrazi `Premenna X = 2`.

### Vstup z príkazového riadku

Vypisovanie je všetko pekné, ale bez vstupov do programu by nám k ničomu moc nebol. Na jednoduchý vstup z konzoly slúži funkcia `input`. Ak program príde na vykonanie tejto funkcia, tak zastane a čaká na náš vstup. Vtedy ho môžeme zadať a potvrdiť s enterom. Výsledok funkcie `input` je potom hodnota ktorú sme zadali. 

```python
input()
```

Takýto program čaká na vstup a po stlačený enteru program skončí. My si túto hodnotu chceme uložiť aby sme s ňou vedeli pracovať. 

```python
x = input()
print(x)
print(x)
```

Daný program čaká na vstup a keď ho zadáme, tak ho dva krát vypíše.

Výstup z funcie `input` je vždy reťazec, takže ak by sme predchádzajúci program modifikovali ako 

```python
x = input()
print(x)
print(x // 2)
```

Po zadaci napríklad čísla `5` je výsledok

```
5
5
Traceback (most recent call last):
 ...
TypeError: unsupported operand type(s) for //: 'str' and 'int'
```

Problém je, že string sa dá vypísať, ale nedá sa vydeliť dvoma, to sa nám snaží vysvetliť ten `TypeError`. Preto ak chceme načítať číslo, musíme toto skonvertovať na číslo pomocou `int(input())`. Celý náš program bude 

```python
x = int(input())
print(x)
print(x // 2)
```

Tento program už korektne po zadaní `5` vypíše `5` a potom `2` (lebo `5` po celočíselnom delení `2` je `2`). Mohlo by nás napadnúť čo sa stane ak zadáme nie číslo, napríklad `ahoj`, toto sa nedá skonvertovať na číslo a Python skončí s chybou `ValueError: invalid literal for int() with base 10: 'ahoj'`. To je pre nás akceptovatelné správanie. 

Funkcia `input` môže dostať jeden parameter, je to string, ktorý sa zobrazí užívateľovi, aby vedel čo sa od neho očakáva. Takže napríklad ak chceme aby zacal číslo môžeme použiť `x = int(input('Enter a number'))` potom sa na konzole zobrazí `Enter a number` a program bude čakať na zadanie čísla. 