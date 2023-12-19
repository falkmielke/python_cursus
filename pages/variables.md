alias:: variabelen, variabele, variable

- Alles wat de computer moet memoriseren gaat hij opslaan in zijn geheugen (ofwel: werkgeheugen, of: haarde schrijf). Om dit terug te kunnen vinden moeten we het aan een naam koppelen.
- Als we geen naam aan een waarde hechten, gaat die dus verloren. Bijvoorbeeld:
  ```
  sum([5, 8]) # tegenover
  s = sum([5, 8])
  print (s)
  
  # of ineens opvangen en gebruiken:
  print(sum([5, 8]))
  ```
- **Vuistregel:** als je een waarde meer dan één keer gebruikt, is het goed om het aan een variable toetewijzen (dus een naam eraan te hechten).
- In de achtergrond moet het programma een variabele eerst declareren, dan een een waarde toewijzen, voordat het hergebruikt kan worden. In python gebeuren declaratie en toewijzing tegelijkertijd.
- Voorbeeld: de variabele `a` woord aangemaakt en de waarde `1` toegewezen met de operator `=`
  ```
  a = 1 # hier is 1 een natuurlijk getal, "integer"
  ```
- python weet de [[datatypes]] van variabelen meestal uit de context: 
  ```
  a = 1.0 # hier is de variabele a een decimaalcijfer
  ```
  (zie ook [[numerieke datatypes]])
- Variabelen hebben een beperkte [[scope]].
- https://nl.wikipedia.org/wiki/Variabele_(informatica)
-
- **Goede Naamgeving!**
	- De naam `a` is geen goede variablenaam.
	- Kies altijd betekenisvolle, eenduidige variabelennamen, dit verbeterd de leesbaarheid van uw programma en spaart soms een commentaar.
	- voorbeeld, vergelijk:
	  ```
	  rho = m/v  # welke v is dit nu?
	  massadichtheid_kg_m3 = massa_kg / volume_m3
	  ```
-