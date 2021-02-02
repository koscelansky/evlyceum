# Formátovanie stringov

V tejto kapitole si ukážeme ako sa dajú formátovať stringy, jednoduhšie ako to, že si stringy sami skladáme pomocou operátora `+`, alebo funkcie `print`. 

Funkcia `format` robí samotné formátovanie, ako vstup do nej idú hodnoty, ktoré chceme naformátovať do stringu. Nasledujúce dva programy urobia rovnaký výstup. 

```py
x = 'Ahoj'
y = 'Evlyceum'
z = '!'

s = x + ' ' + y + z
print(s)
```

```py
x = 'Ahoj'
y = 'Evlyceum'
z = '!'

'{0} {1}{2}'.format(x, y, z)
print(s)
```

# Jednoduché pozičné parametre

Všetko čo je mimo `{` a `}` sa použije priamo, teda napríklad v predchádzajúcom príklade je to medzera medzi `{0}` a `{1}`. V kučeravých zátvorkách je potom číselný odkaz na parameter, ktorý sa má namiesto toho `{0}` použiť. Prvý parameter je číslo 0. 

Môžeme ich aj preusporiadať. 

```py
# 'Posledne tri pismena su x, y a z'
'Posledne tri pismena su {2}, {0} a {1}'.format('y', 'z', 'x')
```

Pripadne ich použiť bez pozičných parametrov, iba s `{}`, potom odkazujú v poradí ako sa použité. 

```py
# 'Posledne tri pismena su y, z a x'
'Posledne tri pismena su {}, {} a {}'.format('y', 'z', 'x')
```

## Zarovnanie 

Niekedy potrebujeme aby boli naše stringy aj nejak vyzerali, napríklad chceme aby naše čísla boli zarovnané vľavo, na stred a vpravo. 

```py
# '123          456           789'
'{:<10}{:^10}{:>10}'.format(123, 456, 789)
```

* `{:<20}` spôsobý, že parameter bude zaberať aspoň 20 znakov a ak je kratší, tak bude sprava doplnení medzerami, teda efektívne bude zarovnaký vľavo. `'Ahoj {:<20}!'.format('ziak')`, bude vyzerať takto `'Ahoj ziak                !'`. 
* `{:>20}` podobne ako v predchádzajúcom prípade, akurát budú doplnené medzery zľava a teda efektívne bude string zarovnaný doprava (toto sa používa hlavne s číslami). `'Ahoj {:>20}!'.format('ziak')`, bude vyzerať takto `'Ahoj                 ziak!'`.
* `{:^20}` spôsobí, že string bude rovnomerne doplnení medzerami zľava a sprava, tak aby opticky vyzeral v strede 20 znakov, ktoré má vyhradené. `'Ahoj {:^20}!'.format('ziak')`, bude vyzerať takto `'Ahoj         ziak        !'`.
* `{:_^20}` znak pred `^`, prípadne dá sa použiť aj s `<` a `>`, hovorí o tom aký znakom sa string dopĺňa, štandardne je to medzera. `'Ahoj {:_^20}!'.format('ziak')`, bude vyzerať takto `'Ahoj ________ziak________!'`.

## Číselné sústavy

Ak formátuje číslo, vieme mu aj povedať v akej sústave ho chceme zobraziť. 

```py
# 'desiatkova 57;  hex: 3a;  osmickova: 73;  binarna: 111100'
'desiatkova {:d};  hex: {:x};  osmickova: {:o};  binarna: {:b}'.format(57, 58, 59, 60)

# 'desiatkova 57;  hex: 0x3a;  osmickova: 0o73;  binarna: 0b111100'
'desiatkova {:#d};  hex: {:#x};  osmickova: {:#o};  binarna: {:#b}'.format(57, 58, 59, 60)
```

Použitím `#` nám python automaticky pred číslo dá prefix ako je zvykom pri danej sústave, takže `0x` pre šestnástokvú, žiadny pre desiatkovú a tak podobne. 

Pre desatiné čísla používame formát `f`. 

## Znamienka

Môžeme aj ovplyvniť, či kladné čisla majú znamienka, alebo nie, napríklad nasledujúci príklad vždy pridá pred číslo znamienko. 

```py
# '+3.140000; -3.140000'
'{:+f}; {:+f}'.format(3.14, -3.14)
```

Ak chceme znamienko iba pre záporné, tak namiesto `+` dáme do formátovacieho reťazca `-`. Asi takto. 

```py
# '3.140000; -3.140000'
'{:-f}; {:-f}'.format(3.14, -3.14)
```

## Miesta za desatinnou bodkou

Ak chceme zaokrúhliť desatinné čísla na povedzme dve miesta, tak môžeme použiť. 

```py
# 3.12
'{:.2f}'.format(3.123456)
# 3.46
'{:.2f}'.format(3.456789)
```

## Všetko dokopy

Tieto formátovania sa dajú aj kombinovať. Najlepšie je to skúšať alebo pohľadať na internete, prípadne sa spýtať skúsenejších. Napríklad

```py
# '********2.28********'
'{:*^20.2f}'.format(2.278)
```

## Domáca úloha

Deadline utorková skupina 7. február (nedeľa) 2021 23:59.

Deadline stredajšia skupina 8. február (pondelok) 2021 23:59.

K nasledujúcim trom príkladam napíšte formátovací reťazec, ktorý vytvorí daný výstup, teda napríklad výstup je `********2.28********` a vstup je `format(2.278)`, tak odpoveď je `'{:*^20.2f}'`. 

* `_****************2.286_` a vstup je `format(2.2859)`
* `0x123 100100011` a vstup je `format(291, 291)`
* `+1.23 -1.23 +1.23` a vstup je `format(1.23, -1.23)` (tu si uvedomte, že parametre sa môžu aj opakovať vo formátovacom reťazci)

### Bonus (1bod)

Pamätáte si úlohu *6* z [vnorených cykolov](./8-nested-loops.md)? Asi ani nie :), skúste ju naprogramovať s tým, že využijete centrovanie výpisov pomocou funkcie `format`. 