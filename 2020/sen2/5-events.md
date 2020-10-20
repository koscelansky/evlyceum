# Grafika

V predchádzajúcej hodine sme mali ako [vyrobiť](./4-recap3.md) v `Tk` okno, do ktorého vieme kresliť. 

## Canvas

Zaujimavé funkcie na kreslenie v `canvas`e sú 
  
  * `create_oval`
  * `create_rectangle`
  * `create_text`
  * `create_image`
  * ...

Všetky tieto sú dobre popísané inde a ich opis tu je trochu ako nosenie dreva do lesa. Dobrý tutorial je napríklad <https://www.python-course.eu/tkinter_canvas.php>.

## Udalosti

Na viazanie udalostí sa používa funkcia `bind`. Ma dva parametre, prvý je meno udalosti a druhý je callback funkcia, ktorá sa má zavolať. Napríklad 

```py
import tkinter 

def click(event):
  print(event.x, event.y)

root = tkinter.Tk()

c = tkinter.Canvas(bg='red', width=640, height=480)
c.bind("<Button-1>", click)
c.pack()

root.mainloop()
```

Tu sme zavesili event `click` na udalosť kliknutie ľavým tlačítkom myši. Handler má jeden parameter, čo sú parametre udalosti. Vypisovať všetky udalosti by znovu bolo vyčerpávajúce a až je to urobené inde. Napríklad <https://effbot.org/tkinterbook/tkinter-events-and-bindings.htm> v časti *Event Formats*.

## Úlohy

TODO

## Domáca úloha

TODO