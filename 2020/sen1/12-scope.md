# Scope

Názvy premenných sa v Pythone hladajú najprv v *lokálnom scope* vo funkcii, teda to sú všetky premenné, ktoré sú prvý krát definované vo funkcii a jej parametre. Potom v "enclosing scope", toto nás zatiaľ nemusí vôbec trápiť. Ďalej v *globálnom scope* (premenné, ktoré sú definované, len tak v súbore mimo toho aby boli vo funkcii) a nakoniec *built-in* premenné. 

Oveľa viacej sa dá o tejto téme dočítať na stránke <https://sebastianraschka.com/Articles/2014_python_scope_and_namespaces.html>.

## Funkcie `locals()` a `globals()`

Funkcia `locals()` nám vráti všetky aktuálne lokálne premenné, nemôžeme ich modifikovať, iba čítať. Pomocou `print(locals())` si ich vieme všetky zobraziť. Funkcia `globals()` funguje podobne pre globálne premenné. 

## Globálne premenné vo funkcii

Čítať globálne premenné z funkcie vieme bez problémov. Ak sa ju ale pokúsime zapísať Python sa bude stažovať. Na to aby sme to vedeli musíme niekde pred prvé použitie globálnej premennej napísať `global`, asi takto. 

```py
x = 1

def modify():
  print(x) # OK
  # x = 1 # not OK
  global x
  x = 1 # OK

modify()
```

## Domáca úloha

Deadline utorková skupina 13. december (nedeľa) 2020 23:59.

Deadline stredajšia skupina 14. december (pondelok) 2020 23:59.

Naprogramujte aplikáciu, ktorá bude mať dve globálne premenné `owner` a `balance`. Vrámci aplikácie potom urobte tieto štyri funkcie. 

* `create_account`, ktorá bude mať jeden parameter a to meno vlastníka účtu, výsledok funkcie bude, že `owner` bude nastavený na toto meno a `balance` bude 0.
* `deposit`, táto funkcia bude mať jeden parameter, ktorý bude hovoriť o koľko sa má hodnota `balance` zvýšiť. 
* `withdrawal`, podobne ako `deposit`, ale hodnotu odčíta.
* `print_balance`, funkcia bez parametrov, ktorá vypíše meno vlastníka (teda premennú `owner`) a potom sumu (teda premennú `balance`), ak je suma záporná, tak za celý výpis pridá ešte výkričník (`!`). 

Kľúčové slovo `global` použite iba tam kde naozaj musíte, nedávajte ho všade. 