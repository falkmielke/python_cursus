alias:: function arguments, argumenten, functieargumenten, argument, keyword arguments

- [[Functies]] kunnen argumenten binnen krijgen en daarmee iets doen (of niet).
- De argumenten staan binnen de haakjes achter de functienaam in de functie-definitie.
  ```python
  def MijnFunctie(budget, kostprijs):
      if budget < kostprijs: # hebben we nog voldoende cash?
      	raise Exception("Wij kunnen dit niet betalen!")
      return budget - kostprijs # het nieuwe budget
  ```
- We onderscheiden `args` = argumenten en `kwargs` = sleutelwoord-argumenten, afhankelijk van hoe de functie in de code wordt *opgeroepen*.
	- **args:** argumenten die we zonder een sleutelwoord doorgeven komen als [[list]] binnen. Ze moeten altijd in volgorde zijn.
	  ```python
	  MijnFunctie(15, 5)
	  MijnFunctie(2, 4.5) # foutmelding triggert
	  ```
		- **kwargs:** "keyword arguments", worden met een sleutelwoord doorgegeven en komen als een [[dict]] binnen. Ze moeten niet in volgorde zijn.
		  ```python
		  MijnFunctie(kostprijs = 2, budget = 4.5) # triggert geen foutmelding
		  ```
- Argumenten kunnen een **standaard-waarde** krijgen, door gebruik van de `=`-operator in de signatuur.
  ```python
  def Goeiedag(naam = 'allemaal'):
      print(f"Goeiedag, {naam}!")
  ```
- Voor goede documentatie kunnen we de verwachtte [[datatype]] van een variable vermelden.
  ```python
  def Goeiedag(naam: str = 'allemaal'):
      print(f"Goeiedag, {naam}!")
  ```