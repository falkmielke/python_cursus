alias:: domein

- Ook: reikwijdte, werkingsgebied
- Het onderbereik van een programma waarin een variabele of functie opvindbaar is.
- Voorbeeld: `global` betekent dat een variabele in het hele programma geldig is.
- Het volgende voorbeeld leverd **een foutmeldint** op:
  ```python
  import numpy as NP
  def Euclid(vector):
      return NP.sqrt(NP.sum(NP.power(vector, 2)))
  
  vectorlengte = Euclid(NP.array([1, 2]))
  print(vector) # vector bestaat alleen maar binnen de functie.
  ```
- Soms is niet duidelijk of een globale of lokale variable bedoelt is. De lokale variable heeft altijd voorrang! Let dus goed op met herhaald gebruik van dezelfde variabelennamen.