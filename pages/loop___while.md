alias:: "while"-loop

- We gaan nu onze pannenkoeken-bak-robot programmeren, met een `while`-loop.
- ```python
  beslaghoeveelheid = 10 # lepels
  while beslaghoeveelheid > 0:
  	Verhit_Olie()
      
      pannenkoek = Schep_Lepel()
      beslaghoeveelheid -= 1
      
      Bak_GedurendeMinuten(pannenkoek, 2)
      Draai(pannenkoek)
      Bak_GedurendeMinuten(pannenkoek, 2)
      
      Opeten(pannenkoek)
      
  Opruimen()
  ```
-
- Vindt jij erin de iterator, de begin- en stop-conditie, en het increment terug?
- Let goed op de [[syntaxis]] van dit stukje code:  een lus heeft altijd het signaalwoord (`while`), dan een [[conditional]], en ten slote een dubbele punt `:`. Het herhaalde blok code is ingeschoven (zie [[indentatie]]).
	- het blokje begint met `while <conditie>:`; de conditie moet een [[data types/boolean]] of waarheidswaarde uitgeven.
	- de "increment" is hier een "decrement": we gaan aftellen zolang er nog lepels beslag in de kom zitten.
	- De beginsituatie en het increment zitten er niet mee in de lijn met `while`, maar zijn apart gedefineerd.
	- Zoals altijd in python is de [[inschuiving]] belangrijk voor de computer om te weten waar een blok code eindigd. Noot: de *lus* eindigd als het beslag op is. De code eindigt naar lijn 12: `Opeten()` (maar die blok wordt herhaald).