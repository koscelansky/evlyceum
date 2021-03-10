# Parsovanie stringov

Chceme vyriešiť nasledovnú úlohu. Na vstupe máme jeden string, ktorý má nasledujúci formát. 

`(ToFoToF)a(ToFoFoT)a(T)`

Je to zápis boolovskej formuly, kde `T` je pravdivý výrok `F` je nepravdivý. `o` je logický or a `a` je logický end. Na stupe sú teda vlastne logickým `and` pospájané výrazy v ktorých sú logické `or`. Našou úlohou je takýto string spracovať a na konci výpísať, či je celá formula `True`, alebo `False`. 

# Domáca úloha

Deadline utorok 16. marec 2021 (23:59).

Aplikácia bude mať na vstupe dátum narodenia vo formáte `DD.MM.RRRR`, teda napríklad `15.5.2010`, `23.7.1987`. Vaša aplikácia najprv zistí, či je daný dátum platný, teda či taký dátum vôbec existuje (tu pozor na priestupne roky a ich pravidlá so 100 a 400). Potom vypíšeme 
* koľko dní sa daný človek dožil.
* za koľko dní dovŕši 75 rokov (znovu pozor na ľudí, ktorý sa narodili presne `29.2.` v rokoch, ktoré nie sú priestupné oslavujú narodeniny `1.3.`). 