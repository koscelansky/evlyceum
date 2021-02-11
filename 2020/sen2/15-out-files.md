# Zápis do súboru

Na minulej hodine sme mali spôsob akým čítať dáta zo súboru, dnes sa pozieme na zápis. 

Do funkcie `open` môže ísť druhý parameter, ktorý hovorí o tom akým spôsobom chceme so súborom nakladať. Ak tam nedáme nič, tak to znamená otvorenie na čítanie. Ďalšie možnosti sú 

* `'w'` - súbor otvorí na zápis, ak súbor neexistuje tak ho vytvorí, inak začne prepisovať súbor od začiatku. 
* `'x'` - rovnako ako `'w'`, ale ak súbot existuje tak skončí s chybou (inak povedané očakáva, že súbor neexistuje a musí ho vytvoriť).
* `'a'` - rovnako ako `'w'` akurát súbor neprepisuje ako zapisuje na koniec (*append*)

Znovu môžeme použit zápis s pomocou `with`, teda ako 

```py
with open('subor.txt', 'w') as f:
  pass
```

## Samotný zápis

Zápis sa uskutočňuje volaním funkcie `write`, alebo `writelines`. Prvá berie ako parameter reťazec a druhá pole reťazcov. Obe ale urobia to isté a teda zapíšu reťazce do súboru. 

```py
with open('subor.txt', 'w') as f:
  f.write('Ahoj subor\n')
```

Všimnite si `\n` na konci, štandardne sa do súboru nové riadky nepíšu takže ich tam treba pridať manuálne. 

## Úlohy

1. V súbore `input.txt` máte na prvých dvoch riadkoch mená prvého tímu a druhého tímu. Potom nasledujú riadky, kde každý reprezentuje jeden zápas medzi tímami. Formát je napríklad `'121X112X'`, ktoré hovoria o tom ako hrali jednotlivý hráči. `1` je výhra prvého tímu, `2` je výhra druhého tímu a `X` je remíza. Transformujte tento súbor na súbor `output.txt`, ktorý má na každom riadku uvedené, ktorý tím vyhral daný zápas (prípadne `X` ak to bola remiza). Teda napríklad ak bude vstup. 

   ```
   Tim A
   Team B
   121X112X
   XXXX12
   1112X222
   121221
   111
   ```

   Bude výstup
   ```
   Tim A
   X
   Team B
   X
   Tim A
   ```

## Domáca úloha

Deadline utorok 16. február 2021 (23:59).

V súbore `stringy.txt` sú reťazce znakov, ktoré sú v anglickej abecede (všetko malými písmenkami). Potom na vstupe (pomocou funkcie `input`) načitame ďalší reťazec (`X`). Vypíšte do výstupného súboru (`output.txt`) všetky stringy zo vstupného súboru, ktoré začínajú na zadaný string. Napríklad ak vstup bude

```
kos
buldozer
vlak
evlyceum
buldog
bulharsko
vlecka
veko
```

Potom pre `X = 'vl'` bude výstupný súbor v tvare

```
vlak
vlecka
```

Pre `X = 'buld'` bude výstupný súbor v tvare

```
buldozer
buldog
```

Pre `X = 'v'` bude výstupný súbor v tvare

```
vlak
vlecka
veko
```

### Bonus (1bod)

V súbore `retazce.txt` sa nachádza zoznam slov. Každý obsahujúci jedno slovo zložené z malých písmen anglickej abecedy (`a` - `z`). Vašou úlohou je nájsť a vypísať všetky dvojice anagramov, ktoré sa v tomto súbore nachádzajú. Dvojica slov tvorí anagram, alebo inak prešmyčku, ak vieme písmená v jednom slove preusporiadať tak, aby sme dostali druhé slovo. V tomto prípade uvažujeme, že každé slovo má v súbore buď jeden iný anagram, alebo žiadny.

Vstupný súbor 

```
rozumkar
ubrblanyslimak
pivovinopalenka
babkumylilsnar
pesamacka
mrazroku
povinnapolievka
```

Vypíše dvojice

```
rozumkar mrazroku
ubrblanyslimak babkumylilsnar
pivovinopalenka povinnapolievka
```

### Extra bonus (1bod)

Vedeli by ste to urobiť aj s podporou viacej anagramov ako dva. Teda pre vstup

```
rozumkar
ubrblanyslimak
pivovinopalenka
malariecka
babkumylilsnar
reklamacia
pesamacka
mrazroku
melakacira
povinnapolievka
```

By bol výstup (v posledom riadku až tri anagramy) 
```
rozumkar mrazroku
ubrblanyslimak babkumylilsnar
pivovinopalenka povinnapolievka
malariecka reklamacia melakacira
```

*Všetky anagramy sú zo stránky <https://anagrammer.org/slovensky/>.*