# Git

Na tejto bonusovej hodine si ukážeme základy práce s git-om. 

## Domáca úloha

Deadline utorková skupina 12. apríl (pondelok) 2021 23:59.

Deadline stredajšia skupina 14. apríl (utorok) 2021 23:59.

"Vizualizácia" eratostenovho sita. Na minulej hodine sme mali implementáciu. Urobte vizualizáciu algoritmu, tada každý jeden krok (aj s číslom kroku). Na začiatku si vypýtate číslo `n` a potom budete robiť vizualizáciu po toto `n`. 

Napríklad pre číslo 20 bude výstup programu nasledobný. (Hviezdičkami sú označené prvočísla a `X` vyškrtnuté čísla)

`1. 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19`
`2. *1* 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19`
`3. *1* *2* 3 X 5 X 7 X 9 X 11 X 13 X 15 X 17 X 19`
`4. *1* *2* *3* X 5 X 7 X X X 11 X 13 X X X 17 X 19`
`5. *1* *2* *3* X *5* X 7 X X X 11 X 13 X X X 17 X 19`
`6. *1* *2* *3* X *5* X *7* X X X 11 X 13 X X X 17 X 19`
`7. *1* *2* *3* X *5* X *7* X X X 11 X 13 X X X 17 X 19`
`8. *1* *2* *3* X *5* X *7* X X X *11* X 13 X X X 17 X 19`
`9. *1* *2* *3* X *5* X 7 X X X *11* X *13* X X X 17 X 19`
`10. *1* *2* *3* X *5* X 7 X X X *11* X *13* X X X *17* X 19`
`11. *1* *2* *3* X *5* X 7 X X X *11* X *13* X X X *17* X 19`