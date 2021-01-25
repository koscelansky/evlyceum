# Reťazce

O reťazcoch (stringoch) sme sa už trochu [./6-strings.md](učili v prvom polroku). Na dnešnej hodine sa pozrieme na ďalšie zaujímavé funkcie, ktoré nám pomôžu pri práci s reťazcami. Všetky nasledujúce funkcie vracajú novú hodnotu, nemodifikujú tú pôvodnú. 

## strip

Funkcia `strip` odstráni zo začiatku a z konca reťazca medzery. 

```py
s = "   ahoj    "
print('"' + s.strip() + '"') # "ahoj"
```

## upper a lower

Skonvertuje string buď do formy so samými veľkými, alebo malými písmenami.

```py
s = "Ahoj"
print(s.lower()) # ahoj
print(s.upper()) # AHOJ
```

## zfill

Pridá na začiatok nuly aby mal reťazec aspoň zadaný počet znakov. Užitočné hlavne s číslami ak ich chceme mať zarovnané na jednu veľkosť. 

```py
s = "ahoj"
print(s.zfill(7)) # 000ahoj
```

## find

Vráti index (teda pozíciu) zadaného stringu. Tieto pozície začínajú ako je zvykom od 0. Ak sa reťazec nenachádza, tak vráti -1. Existuje aj funkcia `index`, tá je skoro taká istá, akurát vyhodí výnimku (spadne nám aplikácia), ak sa reťazec nenachádza, takže pre naše úcely je `find` lepší. 

```py
s = "ahoj evlyceum"
print(s.find("evl")) # 5
print(s.find("Ahoj")) # -1
```

## count

Vráti nám koľkokrát sa daný string nachádza v stringu. 

```py
s = "python je moj oblubeny programovaci jazyk"
print(s.count("mo")) # 2 (nachadza sa v MOj aj v prograMOvaci)
```

## Úlohy

1. Naprogramujte funkciu `strip` bez jej použitia. 
2. Naprogramujte funkciu `upper` bez jej použitia. Stačí aby fungovala pre reťazce, ktoré obsahujú iba a-z, A-Z a 0-9.
3. Naprogramujte funkciu `zfill` bez jej použitia. 
4. Naprogramujte funkciu `find` bez jej použitia. 
5. Naprogramujte funkciu `count` bez jej použitia. 

## Domáca úloha (3body)

Deadline utorková skupina 31. január (nedeľa) 2021 23:59.

Deadline stredajšia skupina 1. február (pondelok) 2021 23:59.

1. Existuje funkcia `swapcase`, ktorá veľké písmená vymení za malé a naopak. Naprogramujte ju bez jej použitia. Stačí aby fungovala pre reťazce, ktoré obsahujú iba a-z, A-Z a 0-9. `def swapcase(x):`
2. Funkcia `startswith`, ktorá vráti true ak string začína iným stringom. Naprogramujte ju bez jej použitia. Pre vás to bude teda vyzerať takto 
   * startswith("string", "str") == True
   * startswith("string", "tr") == False