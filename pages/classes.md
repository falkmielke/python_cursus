alias:: klassen, klas, class

- ![image.jpg](../assets/objects.jpg){:width 500}
- `class` is een andere woord voor [[datatype]].
- We gebruiken in python het signaalwoord `class` om een eigen datatype aan te maken:
  ```python
  class Robot(object):
      def __init__(self, name):
          self.name = name
  ```
- Pseudocode-voorbeeld:
  :LOGBOOK:
  CLOCK: [2024-04-25 Thu 21:24:21]
  :END:
  ``` python
  class Gitaar(Snaarinstrument):
      def __init__(self, stemming = ['E', 'A', 'D', 'G'], materiaal = 'hout')
          self.materiaal = materiaal
          self.Stemmen(stemming)
  
      def Spelen(self, melodie):
          for klank in melodie:
              Afspelen(klank)
  
      def __str__(self):
          return f"Een {self.materiaal}en gitaar."
  
  mijn_gitaar = Gitaar()
  seven_nation_army = ['E', 'E', 'G', 'E', 'D', 'C', 'B'] * 12
  mijn_gitaar.Spelen(seven_nation_army)
  
  ```
- signaalwoord “`class`” + inschuiving: maakt een eigen “datatype” aan.
- klassen-hierarchie bv. “`Snaarinstrument`” (optioneel): overerving.
- signaalwoord “`self`”: om eigenschappen/functies van de class te bereiken; eerste argument in alle klas-functies.
- speciaal-functie `__init__(self, ...)`: “constructur”; deze functie wordt automatisch uitgevoerd als je een nieuwe instantie van de “class” aanmakt.
- “punt”-notatie: functies oproepen met
- magic functions: https://realpython.com/python-magic-methods
- zie verder: [[OOP]]