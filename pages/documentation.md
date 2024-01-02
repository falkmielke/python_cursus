alias:: commentaren, comment, commentaar, documentatie, comments, docstring

- **Expliciete Commentaren en Docstrings**
	- Schrijf goede commentaren in jouw code! Goed = "to the point", kort, maar voldoend.
	- Commentaren in python zet je op verschillende manieren:
	  ```python
	  # (1) één-lijn-commentaren met een "hashtag"
	  
	  "(2) of je zet er gewoon een tekst in."
	  
	  """
	  (3) Maar een string gebruiken we gewoonlijk alleen maar voor commentaren over
	      meerdere lijnen.
	      Als je een string niet aan een variabelennaam toewijst, is het een 
	      "noop", voor "no operation" of "geen operatie", dus het doet niets.
	  """
	  ```
	- De derde manier noemen we ook een "docstring", als die tekst als eerste binnen een functie-definitie volgt. Docstrings zijn oeral goed om te hebben.
-
- Er zijn manieren om de workload van [documentatie te verminderen](https://www.youtube.com/watch?v=Bf7vDBBOBUA):
	- **Descriptieve Variabelennamen**
		- Het is een heel goed idee om je [[variabelen]] een duidelijke naam te geven, ipv. afkortingen en letters te gebruiken.
	- **Expliciete Variabelentypen**
		- Maak duidelijk welke types je voor [[variabelen]] verwacht:
		- ```python
		  vruchten: list[str] = ['appel', 'banaan', 'pompelmoes']
		  ```
	- **Expliciete Functie-Signatuur**
		- Maak de [[datatypen]] in de definitie van jouw [[functies]] duidelijk!
		- ```python
		  def SayHello(recipient: str, message: str = None, repetities: int = 1) -> str:
		      """
		      Hier staat normaal gezien een docstring.
		      """
		  	
		  	return "\n".join([f"Hello, {recipient}! {message}" \
		                        for rept in range(repetities)])
		  ```