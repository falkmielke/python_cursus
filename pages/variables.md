alias:: variabelen, variabele, variable

- ![image.jpg](../assets/variables.jpg){:width 400}
- Door gebruik van **variabelen** hechten we een betekenis of een inhoud aan symbolen. Variabelen zijn een manier om gegevens in een programma op te slaan en terug te vinden.
- Achtergrond: alles wat de computer moet memoriseren gaat hij opslaan in zijn geheugen (ofwel: werkgeheugen, of: haarde schrijf). Om dit terug te kunnen vinden moeten we het aan een naam koppelen.
- Variabelen worden aangemaakt door de variabelennaam te schrijven, gevolgd van een `=`:
  :LOGBOOK:
  CLOCK: [2023-12-25 Mon 12:32:06]
  :END:
  ```python
  a = 1 # structuur: "variabelennaam = waarde"
  ```
- Je kan ook meerdere variabelen ineens declareren, maar dit is alleen maar zinvol als die inhoudelijk samen horen. Voorbeeld:
  ```python
  positie_x, positie_y = 4., 5.
  ```
- Als we geen naam aan een waarde hechten, gaat die dus verloren. Bijvoorbeeld:
  ```python
  sum([5, 8]) # tegenover
  s = sum([5, 8])
  print (s)
  
  # of ineens opvangen en gebruiken:
  print(sum([5, 8]))
  ```
- **Vuistregel:** als je een waarde meer dan één keer gebruikt, is het goed om het aan een variable toetewijzen (dus een naam eraan te hechten).
- In de achtergrond moet het programma een variabele eerst declareren, dan een een waarde toewijzen, voordat het hergebruikt kan worden. In python gebeuren declaratie en toewijzing tegelijkertijd.
- Voorbeeld: de variabele `a` woord aangemaakt en de waarde `1` toegewezen met de operator `=`
  ```python
  a = 1 # hier is 1 een natuurlijk getal, "integer"
  ```
- We kunnen de waarde van een variabele overschrijven, bijvoorbeeld:
  ```python
  snelheid = 5 # m/s
  snelheid = 10 # m/s
  print(snelheid) # resultaat: de aangepaste snelheid van 10 m/s
  ```
- python weet de [[datatypes]] van variabelen meestal uit de context: 
  ```python
  a = 1.0 # hier is de variabele a een decimaalcijfer
  ```
  (zie ook [[numerieke datatypes]])
- Variabelen hebben een beperkte [[scope]].
- https://nl.wikipedia.org/wiki/Variabele_(informatica)
-
- **Goede Naamgeving!**
	- Kies altijd betekenisvolle, eenduidige variabelennamen, dit verbeterd de leesbaarheid van uw programma en spaart soms een commentaar.
	- voorbeeld, vergelijk:
	  ```python
	  rho = m/v  # welke v is dit nu?
	  massadichtheid_kg_m3 = massa_kg / volume_m3
	  ```
	- *naamgevingsconventies:*
		- "Camel Case"
		  bv. `eenBetekenisvolleVariable`
		- "Snake Case"
		  bv. `een_betekenisvolle_variable`
		- persoonlijke nota: 
		  ik persoonlijk gebruik voor alle variables de "snake_case"; voor functies gebruik ik "CamelNotation"; vor bibliotheken gebruik ik "AAH" = afkorting mat alles hoofdletters. Het laatste is niet python-standaardconventie, maar ik vind het iets beter om te lezen.
		  ```python
		  import numpy as NP
		  def FindLog(nummer):
		    return NP.log(3)
		  log_van_2 = FindLog(2)
		  ```