alias:: lussen, lus, loops, iteratie, iteration

- ![image.jpg](../assets/loop.jpg)
-
- **TL;DR**
	- We gebruiken twee soorten loops in python: `for ... in ...:` en `while ...:`
	- Elke loop heeft vier dingen nodig: een iterator, een begin-conditie, een increment, en een stop-conditie. In python zijn die dingen niet altijd zichtbaar.
	- Pas op met "infinite loops".
-
- **Motivering**
	- Terug naar het pannekoeken-voorbeeld van [[control flow]]: je hebt er deeg aangemaakt en wilt de pannenkoeken nu in de pan zetten. Wat vindt jij aan de volgende instructies niet goed?
	  collapsed:: true
		- **0e pannenkoek:**
		- verhit olie of vetstof
		- schep er een lepel beslag in
		- bak pancake van de eerste zij
		- draai de pannenkoek
		- bak de tweede zij
		- warm serveren
		-
		- **1e pannenkoek:**
		- verhit olie of vetstof
		- schep er een lepel beslag in
		- bak pancake van de eerste zij
		- draai de pannenkoek
		- bak de tweede zij
		- warm serveren
		-
		- **2de pannenkoek:**
		- verhit olie of vetstof
		- schep er een lepel beslag in
		- bak pancake van de eerste zij
		- draai de pannenkoek
		- bak de tweede zij
		- warm serveren
		-
		- **3e pannenkoek:**
		- [...]
		-
	- Je ziet duidelijk: dit is heel veel tekst voor drie pannenkoeken. Het wordt een hele boek met instructies als je een grote hoeveelheid pannenkoeken wilt bakken. En stel je voor dat je dan een schrijffout in de instructies vindt om aan te passen!
	- Maar je ziet ook: het lukt wel! Je zou op die manieren kookboeken kunnen schrijven. Alleen is het niet handig.
	- Daarom hebben we **loops** nodig!
-
- **Ingredienten**
	- Als we **herhaalde stukjes programmacode** zien, ookal zijn die soms lichtjes gewijzigd, dan is het meestal beter om voor de code een *loop* te gebruiken (engels: "loop" betekend lus).
	- Boven valt op dat niet duidelijk is wanneer je stopt met pannenkoeken bakken. Elke lus heeft een duidelijke **stop-conditie** nodig.
	- De pannenkoeken zijn wel genummerd, met een gewone volgnummer of teller (0e, 1e, 2de, 3e...). In het algemeen noemen we dit een **iterator**, we itereren bij een iteratie over een aantal elementen. Het is hier heel duidelijk om met de eerste pannenkoek te beginnen. In python zou die uiteraard de volgnummer nul hebben (0e pannenkoek). Maar je kan ook kiezen om bij de eerste pannenkoek te beginnen. We noemen dit een **begin-conditie**, de computer moet weten waar hij moet beginnen.
	- Ten slot moeten we van begin naar einde geraken, en daarvoor bijvoorbeeld de volgnummer omhoog tellen. We noemen dit een **increment**. Zonder increment lopen we op de plek en de loop gaat eindeloos vooruit.
	- Vaak gebruikte hulpfuncties om in python een iterator aan te maken zijn `range`, `enumerate`, `zip`, en bij [[dicts]] de functies `dict.keys()`, `dict.values()` en `dict.items()`.
-
- **While-loops**
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
	  collapsed:: true
		- het blokje begint met `while <conditie>:`; de conditie moet een [[data types/boolean]] of waarheidswaarde uitgeven.
		- de "increment" is hier een "decrement": we gaan aftellen zolang er nog lepels beslag in de kom zitten.
		- De beginsituatie en het increment zitten er niet mee in de lijn met `while`, maar zijn apart gedefineerd.
		- Zoals altijd in python is de [[inschuiving]] belangrijk voor de computer om te weten waar een blok code eindigd. Noot: de *lus* eindigd als het beslag op is. De code eindigt naar lijn 12: `Opeten()` (maar die blok wordt herhaald).
	-
- **For-loops**
	- Stel dat je het beslag niet in één grote kom hebt, maar al netjes voorbereidt in hoeveelheiden voor telkens één pannenkoek. Muffin-voormpjes met pannenkoek-beslag, bijvoorbeeld.
	- Je zou dan de loop op de volgende manier kunnen toepassen:
	- ```python
	  def Bakken(pannenkoek):
	      # deze keer gebruiken we een functie om het bakproces te vereenvoudigen.
	  	Bak_GedurendeMinuten(pannenkoek, 2)
	      Draai(pannenkoek)
	      Bak_GedurendeMinuten(pannenkoek, 2)
	  
	  beslagreeks = [1, 1, 1, 1, 1, 1, 1, 1, 1, 1] # dit is een lijst
	  for beslag in beslagreeks:
	  	Verhit_Olie()
	      
	      pannenkoek = Schep(beslag)
	      
	  	Bakken(pannenkoek)
	      Opeten(pannenkoek)
	  Opruimen()
	  ```
	- Huiswerk: vindt hier opnieuw de iterator, de begin- en stop-conditie, en het increment terug!
	- Opnieuw de [[syntaxis]]:
		- Een reeks van data is vooraf aangemaakt, hier een lijst met tien keer de nummer `1`.
		- De lus begint met het signaalwoord `for ... in ...:`.
		- Een increment is hier impliciet: de lus gaat gewoon over alle elementen binnen die reeks itereren.
		- Daarom zijn ook de begin- en stop-conditie niet zichtbaar: de lus gaat met het eerste element beginnen, en stoppen als de lijst op is.
	- Je zou dus kunnen zeggen dat de `for`-lus in python wat veiliger is, want de kans dat je een oneindige lus oploopt is kleiner. Andererzijds moet je een goede iterator voorbereiden.
-
- **Loop Control**
	- Je kan er de [[control flow]] binnen een loop verder controleren met de volgende signaalwoorden:
		- `continue`: springt naar de volgende iteratie
		- `break`: breekt de lus af
		- `return <iets>`: binnen een functie kan je hiermee de hele functie eindigen.
	- Dit is wel enig zinvol als je [[conditionals]] binnen de loop gebruikt.
	-
- **Typische Fouten**
	- Als je de stop-conditie niet zet of het increment vergeet, kom je soms in een **oneindige lus** terecht. Je computer gaat dan voor alle tijden met die berekening bezig blijven.
	- ![image.jpg](../assets/infinite_loop.jpg)
	- Zie ook: [[error traceback]]
-
-