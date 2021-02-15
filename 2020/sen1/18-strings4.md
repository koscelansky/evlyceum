# Reťazce 3

Opakovanie reťazcov. Čo by sme mali vedieť 

* Reťazce sú postupnosti znakov (indexujú sa od 0)
* Reťazce sa zapisujú buď pomocou obyčajných úvodzoviek `'`, alebo dvojitých `"`
* K `i`temu znaku v reťazci `s` sa dostaneme ako `s[i]`
* Stringy sa meniť v Pythone nedajú vieme iba vyrobiť nové
* Dva stringy zreťazíme pomocou operácie `+`
* Python poskytuje veľa zaujímavých funkcie nad reťazcami. Ak napríklad chceme vrátiť string s rovnakým obsahom ako `s`, iba všetko malými písmenami, tak použijeme `s.lower()`
* Každý znak má svoje číslo, toto číslo získame pomocou funkcie `ord`, číslo späť na znak prevedieme pomocou `chr`
* Python podporuje formátovanie pomocou funkcie `format`
* Dĺžku reťazca získame pomocou funkcie `len`
* Vrátenie podreťazca sa robí pomocou sliceov, teda napríklad notácia `s[2:4]`

# `in` operátor

Ak chceme len zistiť, či sa jeden string nachádza v druhom, tak možeme použiť operátor `in`. Napríklad takto

```py
haystack = 'Hello world!'
needle = 'world'

if needle in haystack:
  print('OK')
```

# Krok v slice

Slice podobne ako range podporuje aj zápis s tromi hodnotami. Tretia hodnota je potom krok. Napríklad 

```py
s = "string"
print(s[3:1:-1]) # ir

print(s[::2]) # srn

print(s[::-1]) # gnirts (vlastne orotuje string, vypise ho odzadu)
```

## Úlohy

1. Urobte funkciu `insert(s, i, t)`, ktorá na pozíciu `i` v stringu `s` "vloží" string `t`. Vloží preto v úvodzovkách, lebo ako vieme stringy sú v Pythone nemenitelné, takže táto funkcia musí vrátiť nový string. 

   ```py
   s = "oj!"
   t = "Ah"
   print(insert(s, 0, t)) # Ahoj!

   print(insert(s, 1, t)) # oAhj!

   s = "Trochu dlhsi string"
   print(insert(s, 10, t)) # Trochu dlhAhsi string
   ```

2. Urobte funkciu `addSpace(s, i)`, ktorá každých `i` znakov v stringu `s` vloží medzeru.

   ```py
   s = "Trochudlhsistring"
   print(addSpace(s, 4)) # Troc hudl hsis trin g
   ```

3. Urobte funkciu `rotate(s, n)`, ktorá v stringu `s` orotuje každých `n` znakov. Povedzme, že na začiatok môžeme predpokladať, že dĺžka stringu je delitelná `n`. Ďalej, ak dĺžka nebude deliteľná, tak na konci sa orotuje toľko koľko sa dá (ako v príklade).
   
   ```py
   s = "Trochu dlhsi string"
   print(rotate(s, 4)) # corTd uhishlrts gni
   ```

## Domáca úloha

Deadline utorková skupina 21. február (nedeľa) 2021 23:59.

Deadline stredajšia skupina 22. február (pondelok) 2021 23:59.

Urobte funkciu `replace(s, i, t)`, ktorá na pozíciu `i` v stringu `s` "nahradi" string `t`. Nahradí preto v úvodzovkách, lebo ako vieme stringy sú v Pythone nemenitelné, takže táto funkcia musí vrátiť nový string. Ak by sa náhrada do stringu už nezmestila, tak sa použije koľko sa dá, aby string mal rovnakú dĺžku (ako v príklade)

```py
s = "Trochu dlhsi string"
t = "nahrada"
print(replace(s, 0, t)) # nahradadlhsi string
print(replace(s, 1, t)) # Tnahradalhsi string
print(replace(s, 7, t)) # Trochu nahradatring

# ak sa nahrada nezmesti
print(replace(s, 15, t)) # Trochu dlhsi stnahr

# index je uplne mimo, nic sa nestane
print(replace(s, 25, t)) # Trochu dlhsi string
```

### Bonus (1bod)

Urobte funkciu `rotateWords(s)`, ktorá orotuje vsetky slová, slová sú časti stringu oddelené medzerov. 

```py
print(rotateWords("string")) # gtirns

print(rotateWords("string je retazec")) # gtirns ej cezater

print(rotateWords("string j ret azec")) # gtirns j ter ceza
```