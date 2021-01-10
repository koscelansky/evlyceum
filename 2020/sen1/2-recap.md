# Opakovanie

## Výpis pomocou `print`

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

`print` podporuje aj výpis viacerých hodnôt súčasne (tieto oddelí medzerou), teda napríklad `print('Ahoj', 'svet', 123, '!')` vypíše na konzolu `Ahoj svet 123 !`.

Vypisovať nemusíme iba hodnoty, ale aj obsah premenných. Teda napríklad

```python
x = 2
print('Premenna X =', x)
```

zobrazí `Premenna X = 2`.

## Vstup z príkazového riadku

Vypisovanie je všetko pekné, ale bez vstupov do programu by nám k ničomu moc nebol. Na jednoduchý vstup z konzoly slúži funkcia `input`. Ak program príde na vykonanie tejto funkcie, tak zastane a čaká na náš vstup. Vtedy ho môžeme zadať a potvrdiť s enterom. Výsledok funkcie `input` je potom hodnota, ktorú sme zadali. 

```python
input()
```

Takýto program čaká na vstup a po stlačení enteru program skončí. My si túto hodnotu chceme uložiť aby sme s ňou vedeli pracovať. 

```python
x = input()
print(x)
print(x)
```

Daný program čaká na vstup a keď ho zadáme, tak ho dvakrát vypíše.

Výstup z funkcie `input` je vždy reťazec, takže ak by sme predchádzajúci program modifikovali ako 

```python
x = input()
print(x)
print(x // 2)
```

Po zadaní napríklad čísla `5` je výsledok

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

Funkcia `input` môže dostať jeden parameter, je to string, ktorý sa zobrazí užívateľovi, aby vedel čo sa od neho očakáva. Takže napríklad ak chceme aby zadal číslo môžeme použiť `x = int(input('Enter a number'))` potom sa na konzole zobrazí `Enter a number` a program bude čakať na zadanie čísla. 

## Základné typy a operácie

V Pythone existuje niekoľko základných typov. Základné sú preto, lebo sú v Pythone dosptupné bez akýchkoľvek knižníc. Je ich niekoľko, nás bude zaujímať hlavne `int`, `str` a v obmedzenej miere `float`.

### Celé čísla

Najjednoduchší typ je `int`, teda *integer*. Predstavuje jedno celé číslo. Python umožňuje pracovať s číslami ľubovoľnej dĺžky. 

```python
x = 123456789
print(x)
```

Program vyššie vypíše číslo `123456789`. To samo o sebe nie je veľmi zaujímavé. S číslami vieme pracovať pomocou operátorov. Python ich definuje niekoľko

```python
print(10 + 3) # 13
print(10 - 3) # 7
print(10 * 3) # 30
print(10 // 3) # 3 celočíselné delenie
print(10 / 3) # 3.3333333333333335 delenie s desatinou čiarkou
print(10 % 3) # 1 modulo, zvyšok po delení (10-3*3)
print(10 ** 3) # 1000 umocnovanie
```

Operátory vieme aj skladať, tu ale pozor na poradie vyhodnocovania (násobenie má prednosť pred sčítaním), preto treba používať zátvorky.

```python
print(10+3 * 2) # 16
print((10 + 3)*2) # 26
```

### Desatinné čísla

Typ `float` vie reprezentovat desatinné číslo (*floating point*). Tu už nemáme neobmedzenú veľkosť. Tieto čísla sa zapisujú s bodkou. 

```python
1.2
0.3 
.3 # to isté ako 0.3
1. # to isté ako 1.0, nie je to to isté ako iba 1, to je int
```

Operácie pracujú podobne ako pre `int`. Akurát sa vždy ráta v desatinných číslach. Desatinné čísla budeme najčastejšie vidieť ako výsledok operátoru `/`, ktorý aj na dvoch `int`och vráti `float`.

### Reťazec znakov

Posledný bežný základný typ je `str`, teda *string* znakov. Je to vlastne reprezentácia niečoho ako slova, vety, textu. Hodnoty uvádzame do `''`, alebo `""`. Oba zápisy sú v podstate ekvivalentné. Nikdy nesmieme zabudnúť úvodzovky ukončiť, inak bude zle nedobre. 

```python
print('toto je retazec')
print("aj toto je retazed")
# print("toto nie') # tento riadok je chyba, lebo sme začali " a končíme '
```

Reťazec znakov je napríklad vstup do funkcie `input` a aj výstup z tejto funkcie. 

Operátory na `string`och sú iba dva. 

```python
a = 'ahoj'
b = 'python'
print(a + b) # ahojpython
print(a * 3) # ahojahojahoj
```

### Konverzie

Predstavme si program

```python
a = input('zadaj A')
b = input('zadaj B')
print(a + b)
```

pre vstup `2` a `3` by sme očakávali výstup `5`, v skutočnosti bude výstup `23`, lebo `a` aj `b` sú typu `string` a teda operátor `+` nerobí sčítanie čísel ale reťazcov. Musíme teda tento typ skonvertovať. To sa robí pomocou funkcie `int` (rovnako sú aj funkcie `float` a `str` pre konverziu na desatinné číslo a reťazec). 

```python
a = int(input('zadaj A'))
b = int(input('zadaj B'))
print(a + b)
```

Teraz už program pracuje ako má. 