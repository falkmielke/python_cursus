alias:: lijst, list, list data type

- Een lijst is een geordende, veranderlijke versameling van data.
- Ze wordt aangeduidt met de functie `list()` of door rechte haakjes:
  ```python
  mijn_lijst = ["Alice", "Bob", "Charlie", "Doris"]
  print(mijn_lijst[2]) # Charlie
  print(mijn_lijst[-1]) # Doris
  ```
- zie ook: [[list comprehension]]
- Je kan binnen een lijst van alles opslaan. Het is wel goed advies om alle elementen binnen een lijst van dezelfde datatype en structuur te houden.
- Verdere [[functies]] van `list`:
  ```python
  mijn_lijst.append("Eric")
  eric = mijn_lijst.pop() # haalt Eric er weer uit, hij zit dan niet meer in de lijst
  print(mijn_lijst.index("Bob")) # 1
  len(mijn_lijst) # lengte; hier: 4
  del mijn_lijst[0] # verwijderd Alice (sorry, Alice!)
  ```