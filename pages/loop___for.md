alias:: "for"-loop

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
	- Loopnummer en increment zijn hier impliciet: de lus gaat gewoon over alle elementen binnen die reeks itereren. Dit noemt **no-index syntax**
	- Daarom zijn ook de begin- en stop-conditie niet zichtbaar: de lus gaat met het eerste element beginnen, en stoppen als de lijst op is.
- Je zou dus kunnen zeggen dat de `for`-lus in python wat veiliger is, want de kans dat je een oneindige lus oploopt is kleiner. Andererzijds moet je een goede iterator voorbereiden.