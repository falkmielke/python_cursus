alias:: function arguments, argumenten, functieargumenten, argument, keyword arguments

- [[Functies]] kunnen argumenten binnen krijgen en daarmee iets doen (of niet).
- De argumenten staan binnen de haakjes achter de functienaam in de functie-definitie, als deel van de signatuur.
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
-
- **Trucjes**
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
	- Je kan het aantal van input-argumenten open laten en binnen halen met `*args` en `**kwargs`:
	  ```python
	  def MyFunction(*args, **kwargs):
	      print(args) # een list van alle argumenten zonder keyword
	      print(kwargs) # een dict van alle argumenten met keyword
	  ```
	- Je [[list]]s (zoals `args`) en [[dicts]] (zoals `kwargs`) gebruiken om een aandere functie met argumenten te bedienen:
	  ```python
	  import matplotlib.pyplot as PLT
	  x = [0, 0.5, 1., 1.5, 2., 2.5, 3.]
	  y1 = [y for y in map(lambda x: x, x)]
	  y2 = [y for y in map(lambda x: x**2, x)]
	  lineair = [x, y1]
	  quadraat = [x, y2]
	  plot_kwargs = {'ls': '-', 'lw': 1., 'alpha': 0.8, 'zorder': 0}
	  
	  PLT.plot(*lineair, color = 'k', **plot_kwargs, label = 'plot1')
	  PLT.plot(*quadraat, color = 'darkred', **plot_kwargs, label = 'plot1')
	  PLT.show()
	  ```