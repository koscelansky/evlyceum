# Podmienený príkaz `if`

Zatiaľ vieme, že program sa skladá z príkazov (angl. *statement*, v podstate ide o jeden riadok v Pythonovom programe), ktoré idú za sebou. To znamená, že interpreter Pythonu ich vykonáva jeden za druhým v poradí v akom sú zapísané. 

```python
name = input('Enter a name ')
print('Hello', name)
age = int(input('Please enter your age '))
print(name, 'is', age, 'years old.')
```

Tento program si najprv vypýta meno, potom ho vypíše, potom si vypýta vek a nakoniec ho vypíše. Ak chceme vykonanie nejakého príkazu podmieniť (vykonať ho iba ak je splnená nejaká podmienka) môžeme na to použiť kľúčové slovo `if` a `else`.

*Kľúčové slovo znamená, že dané slovo je rezervované a nemôže sa vyskytovať ako názov premennej. `if = 5` je syntax error.*

Ak chceme napríklad pokračovať v zadávaní veku iba ak je meno `'Juraj'` môžeme program upraviť. 

```python
name = input('Enter a name ')
if name == 'Juraj':
  print('Hello', name)
  age = int(input('Please enter your age '))
  print(name, 'is', age, 'years old.')
else:
  print('You are not Juraj!')
```

Za `if` ide podmienka, takže napríklad číselné porovnanie (napríklad `x == 3`, `x != 3`, `x < 3`, `x >= 3`), alebo porovnanie reťazcov. A potom dvojbodka. Ďalšie odsadené (Python je veľmi striktný pri zarovnaní programu, riadky patriace pod `if` musia mať na začiatku tabulátor, alebo rovnako veľa medzier) riadky sú príkazy, ktoré sa vykonajú ak je podmienka splnená. Potom následuje `else` s dvojbodkou (pozor to už má rovnaké zarovnanie ako `if`) a znovu odsadené príkazy, ktoré sa vykonajú ak je podmienka nesplnená.

## Zložitejšie podmienky

Logické výrazy sa môžu skladať z viacerých podmienok spojených buď pomocou `and` (a), alebo `or` (alebo). Nasledujúca podmienka je splnená ak `x` je väčšie rovné `0` a zároveň je menšie ako `10`. 

```python
if x >= 0 and x < 10:
  print('x je v intervali [0-9]')
else:
  print('x nie je v intervali [0-9]')
```

Obdobne môžeme rovnaký program zapísať ako

```python
if x < 0 or x >= 10:
  print('x nie je v intervali [0-9]')
else:
  print('x je v intervali [0-9]')
```

Tu sme vlastne podmienku otočili, ak `x` je menšie ako `0` alebo je väčšie rovné ako `10`, tak nemôže byť v intervali `[0-10]`.

## Úlohy

1. Napíšte program, ktorý načíta dve čísla. Ak je prvé menšie ako druhé, tak vypíše `mensie` inak vypíše `vacsie alebo rovne`. 

2. Napíšte program, ktorý načíta rok a vypíše, či je, alebo nie je priestupný (zatiaľ pre naše účely je priestupný rok, taký ktorý je deliteľný 4).

3. Napíšte program, ktorý načíta dve čísla a vypíše väčšie z nich.

4. Napíšte program, ktorý pri zadaní koeficientov `a`, `b` a `c` kvadratickej rovnice vypíše `ma realne korene` ak rovnica má aspoň jeden reálny koreň. *(Má reálne korene ak diskriminant je väčší alebo rovný ako 0).*

5. Napíšte program, ktorý prečíta tri čísla a vypíše najmenšie z nich.

6. Napíšte program, ktorý prečíta mesiac (číslom) a rok a vypíše počet dní v danom mesiaci.

   ```
   Zadaj mesiac 1
   Zadaj rok 2021
   Mesiac 1 v roku 2021 ma 31 dni
   ```

## Domáca úloha (3 body)

Deadline utorková skupina 5. októbra 2020 23:59.

Deadline stredajšia skupina 6. októbra 2020 23:59.

1. Naprogramujte program, ktorý načíta dve čísla a vydelí ich. Ak sú súdeliteľné (teda ak zvyšok po delení je `0`), vypíše 

   cislo1 / cislo2 = vysledok

   Ak sú nesúdeliteľné (teda zvyšok po delení nie je `0`), vypíše

   cislo1 / cislo2 = vysledok zvysok je nejake_dalsie_cislo

   Teda napríklad ak zadám čísla `10` a `2`, vypíše to `10 / 2 = 5` 

   Ak zadám čísla `10` a `3`, vypíše to `10 / 3 = 3 zvysok 1`.