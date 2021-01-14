# Pexeso

Kód pexesa, ktorý sme stvorili na hodine. 

```py
import tkinter

from random import randint

root = tkinter.Tk()
c = tkinter.Canvas(width = 500, height = 500, background = "white")
c.pack()

SIRKA = 4
HRACIE_POLE = []
ODOKRYTE = []

def generuj_hracie_pole():
    znaky = []
    for i in range(SIRKA * SIRKA):
        znaky.append(chr(ord('a') + i // 2))

    p = []

    podpole = []
    length = len(znaky)
    for i in range(length):
        pos = randint(0, len(znaky) - 1)
        podpole.append(znaky[pos])
        del znaky[pos]
        if len(podpole) == SIRKA:
            p.append(podpole)
            podpole = []

    return p

HRACIE_POLE = generuj_hracie_pole()

def generuj_odokryte():
    p = []
    for i in range(SIRKA):
        temp = []
        for j in range(SIRKA):
            temp.append(False)
        p.append(temp)
    return p

ODOKRYTE = generuj_odokryte()


CISLO_KLIKU = 0
A1, B1 = None, None
A2, B2 = None, None

def klik(event):
    global A1, B1, A2, B2, CISLO_KLIKU
    if A1 != None and B1 != None and A2 != None and B2 != None:
        return

    a = event.x // 50
    b = event.y // 50

    if ODOKRYTE[a][b]:
        return
    
    if CISLO_KLIKU % 2 == 0:
        A1, B1 = a, b
    else:
        if A1 == a and B1 == b:
            return
        A2, B2 = a, b
        overit_policka()

    CISLO_KLIKU += 1

    nakresli()

def zakry_vybrate():
    global A1, B1, A2, B2
    A1, B1 = None, None
    A2, B2 = None, None

    nakresli()

def overit_policka():
    global ODOKRYTE
    if HRACIE_POLE[A1][B1] == HRACIE_POLE[A2][B2]:
        ODOKRYTE[A1][B1] = True
        ODOKRYTE[A2][B2] = True
        zakry_vybrate()
    else:
        c.after(3000, zakry_vybrate)

def nakresli():
    c.delete('all')

    if koniec():
        c.create_text(100, 100, text='Koniec', font="Arial 20")

    for n in range(SIRKA):
        x = 0
        y = 0
        r = 50
        for m in range(SIRKA):
            c.create_rectangle(x+r*n, y+r*m, x+r+r*n, y+r+r*m)
            t = '#'
            if ODOKRYTE[n][m] or (n == A1 and m == B1) or (n == A2 and m == B2):
                t = HRACIE_POLE[n][m]
            c.create_text(x+r*n+r/2, y+r*m+r/2, text=t, font="Arial 10")

def koniec():
    for i in range(SIRKA):
        for j in range(SIRKA):
            if not ODOKRYTE[i][j]:
                return False
    return True

nakresli()

c.bind("<Button-1>", klik)
root.mainloop()
```

# Domáca úloha 

Deadline utorok 19. január 2021 (23:59)

Naprogramujte GUI aplikáciu (Teda pomocou `tkinter`). Ktorý bude zobrazovať počitanie od 0 do 255 binárne na canvas, teda začne s číslom 00000000 a potom postupne každú sekundu sa zvýši o 1. Teda daľšie čísla v poradí budú

* 00000001
* 00000010
* 00000011
* 00000100
* 00000101
* ...

Po dorátaní do 255 (11111111) sa zastaví. 

## Bonus

1. (1bod) Namiesto 0 a 1 budeto zobrazovať obrázky. Tieto konkrétne (prvý bude 0 a druhý 1). Stiahnte si ich, dajte do rovnakého priečinka ako váš python program. Potom použite je ako [PhotoImage z tkinter](https://stackoverflow.com/a/43009579).

   ![Unicorn](./12-pexeso/0.png)
   ![Doomguy](./12-pexeso/1.png)


2. (1bod) Viete to naprogramovať bez toho aby ste počítali v desiatkovej sústave a potom to konvertovali do binárnej sústavy? Viete odvodiť nejaké pravidlo pre to ako z jedného čísla (ako binárny string) odvodíte ďalšie? Potom by ste ho mohli aplikovať a nemuseli by ste nič v aplikácií konvertovať. Ak sa vám to podarí dostanete ďalší bonusový bod. 