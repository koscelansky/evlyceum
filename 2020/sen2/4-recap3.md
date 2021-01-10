# Opakovanie (3/3)

## Grafika

```python
import tkinter 

root = tkinter.Tk()

c = tkinter.Canvas(bg='red', width=640, height=480)
c.pack()

root.mainloop()
```

Prvý riadok naimportuje `tkinter`, v podstate nám to sprístupní všetku funkcionalitu, ktorú nám poskytuje *Tk* *inter*face. 

Druhý riadok vytvorý top level inštanciu `Tk`. Potom vytvoríme `Canvas`, čo je plátno, do ktorého vieme kresliť. Pomocou funkcie `pack` toto plátno vykreslíme na obrazovku. 

Posledný riadok `mainloop` začne hlavnú loopu programu, ktorá čaká na udalosti. 

## Úlohy

1. Napíšte funkciu `dec2bin`, ktorá dostane na vstupe číslo `n` a vypíše ako výstup binárnu reprezentáciu tohoto čísla.

2. Urobte program, ktorý si na začiatku zvolí náhodné číslo z rozsahu 0..100 (0 vrátane, 100 nie) a potom bude pýtať čísla až pokiaľ číslo netrafíme. O procese nás informuje. 

3. Zmente program tak, aby nás informoval, či je číslo menšie alebo väčšie ako zadané. 

4. Naprogramujte funkciu `medzera`, ktorá dostane reťazec a vráti reťazec, ktorý má všetky medzery nahradené troma medzerami. Teda reťazec `a a  bb` transformuje `a   a      bb`.

5. Naprogramujte funkciu `odstran_faktory`, ktorá dostane na vstupe pole a číslo `n`, potom odstráni z tohto poľa všetky čísla ktoré delia `n` bezo zvyšku. Teda pre pole `[1, 2, 3, 4, 5, 6, 7, 8]` a číslo `16` bude výsledok `[3, 5, 6, 7]`. 

5. Urobte program, ktorý do stredu plátna nakreslí sústredný terč s 10 kružnicami, kde sa strieda farba z červenej na bielu, najmenšia kružnica bude mať polomer 10 a potom sa bude zvačšovať vždy o 10.

## Domáca úloha

Deadline utorok 20. október 2020 (23:59)

1. Naprogramujte funkciu `hex2bin`, ktorá na vstup dostane reťazec v šesťnástkovej sústave a vypíše toto číslo v binárnej sústave. Takze napríklad 
   * `hex2bin('a') == '1010'`
   * `hex2bin('deadbeef') == '1101 1110 1010 1101 1011 1110 1110 1111'`
   * `hex2bin('bad') == '1011 1010 1101'`
   * `hex2bin('badc0ffe') == '1011 1010 1101 1100 0000 1111 1111 1110'`

2. Naprogramujte program, ktorý do canvasu nakreslí desať kruhov náhodnej veľkosti (max. 100) na náhodnú pozíciu. Urobte to tak aby bola využiteľná celá plocha. 
