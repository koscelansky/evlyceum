## Bezpečnost práce pri počítači

Počítače sú zariadenia pod prúdom a tak sa k nim musíme chovať. Nemanipuluje s otvorenými súčasťami. K bezpečnosti pratrí aj správne sedenie, prestávky.

[Pracovisko s počítačom (príručka)](https://www.ip.gov.sk/wp-content/uploads/2017/11/Prirucka1.pdf)

## Prostredie Python

Na programovanie bude používať jazyk Python. Aktuálna verzia je 3.8, odporúčam mať nainštalovanú tú, ale aj o niečo staršia bude fungovať. Štiahnuť sa dá z [Windows Store](https://www.microsoft.com/en-us/p/python-38/9mssztt1n39l) ak používate Windows 10. Prípadne sa dá použiť [inštalátor](https://www.python.org/downloads/). Pre ostatné platformy buď použijete inštalátor, alebo ideálne package manager (napr. *apt-get*). Po nainštalovaný by ste mali mať dostupné prostredie **IDLE**. Je to veľmi jednoduché a vhodné iba na skúšanie. My budeme používať vývojové prostredie [VS Code](https://code.visualstudio.com/Download). Po jeho spustení si treba nainštalovať [rozšírenie na Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python). 

Ak ste všetko správene nainštalovali, tak funkčnosť si overíme jednoduhým *Hello world!* programom.

1. Spustíme VS Code (tip: stačí do command line zadať `code`)
2. Vyberieme `New file`
3. Stlačíme `Ctrl+S` a uložíme súbor ako `hello.py`
4. Napíšeme do editora `print("Hello world!")` a uložime pomocou `Ctrl+S`
5. Stlačíme `F5` a vyberieme `Python file`
6. Počkáme a v konzole by sa malo zobraziť `Hello world!`.

## Kde sa nachádzame?

### Párne/neprárne?

Vytvorte program, ktorý prečíta zo vstupu číslo a vypíše informáciu o tom, či je párne, alebo nepárne. 

### Utriedené čísla

Vytvorte program, ktorý na vstupe prečíta 3 čísla a potom ich vypíše od najväčšieho po najmenšie. 

### Sum of squares

Vytvorte program, ktorý dostane na vstupe číslo `n` a na výstup vypíše súčet všetkých štvorcov po `n`. Teda `1*1 + 2*2 + ... (n-1)*(n-1) + n*n`. Napríklad pre `3` to bude `14` a pre `4` bude výsledok `30`.

### GCD

Pre zadané dve čísla vypočítajte ich najväčší spoločný násobok. Môžete použiť [Euklidov algoritmus](https://en.wikipedia.org/wiki/Euclidean_algorithm#Procedure).

### Palindrom

Pre zadaný string chceme zistiť či je palindrom, teda či sa odpredu aj odzadu píše rovnako.

### Okno s tlačítkom

Vytvorte oknovú aplikáciu, v ktorej umiestnite jedno tlačítko a po jeho kliknutí sa na náhodnom mieste objaví štvorec. 