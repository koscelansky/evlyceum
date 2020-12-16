# Dvojrozmerné polia pokračovanie

## Úlohy

1. Naprogramujte stopu matice (bonus z minulej domácej úlohy).
2. Naprogramujte funkcia, ktorá sčíta dve matice. 
3. Naprogramujte hru pexeso ako konzolovú aplikáciu. Najpr vyrobíme pole 6*6, do ktorého náhodne podávame dvojice písmen a-z (koľko bude potrebné). Potom sa toto pole vypíše s tým, že nič nebudeme vidieť, teda všetko bude zahalené. Postupne budeme zadávať svojice súradníc, ako napríklad 18 a 14, co bude znamena, že odokryjeme políčko 18 a 14, tie sa nám zobrazia a ak sme trafili, tak ostanú odokryté, inak sa znovu vypíše pole s doteraz odokrytými políčkami a ideme ďalej. Hra končí, keď sa nám podarí odkryť všetky políčka. 
4. Naprogramujte generovanie hracieho plániku pre hru piškvorky 3x3. Na striedačku budeme zadávať hodnoty kam dať krížik, alebo guličku. Vedeli by ste hru rozšíríť na 8x8, prípadne urobiť po každom kole vyhodnocovanie, víťaza?

## Domáca úloha 

Úloha je tentokrát dokopy za 9 bodov.

Deadline utorok 12. január 2021 (23:59)

1. (6bodov) Gui pre hru pexeso, ktorú sme naprogramovali (tú vám nejak sprístupním), musíte vlastne vykresliť do canvasu hraci plán 6x6, potom po kliknutí myšou sa odokryje jedno políčko, po druhom kliknutí sa odokryje druhé (pozor na kliknutie do rovnakého políčka, tu by druhý klik nemal nič robiť). Ak sme trafili rovnaké, tak ostanú odokryté, inak po 3 sekundách zmyznú (teda musíte použiť funkciu `after`). 

2. Naprogramujte konzolovú aplikaciu, ktorej najprv zadavame trojice tovar, množstvo a cena za kus. Potom keď zadáme prázdny riadok, tak sa aplikácia prepne do režimu, kde zadávame meno tovaru a ak sa nájde tak sa vypíše celková cena zásob a ak nie, tak sa vypíše "Tovar sa nenasiel". Po zadaný prázdneho riadku znovu aplikácia skončí. (pozn. na ukladanie môžete použiť napríklad dve polia, v jednom budú mená tovarov a v druhom ceny, potom podľa indexu ich viete previazať). Príklad vstupu (kurzivom je časť, ktorú nezadávam, ale ju vypíše aplikácia)
   * muka 4 0.5
   * cukor 10 1.3
   * bmw 1 35000
   * 
   * parky
   * *Tovar sa nenasiel*
   * cukor
   * *13*
   * muka
   * *2*
   * 
   ```

3. Bonus (2body) Urobte nápovedu, po vybratí prvej karty ak stlačím medzerník, tak sa mi označia 4 karty (červenou bodkou), pod jednou z nich je dvojička ku karte a ostatné sú vybrané náhodne. Nápoveda nefunguje ak sú už iba 4, alebo menej neodkrytých kariet.