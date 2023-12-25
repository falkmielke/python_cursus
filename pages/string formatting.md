alias:: f-strings, stringformatering

- Je kan een tekst dynamisch aanpassen als het een "f-string" is. De manier waarop dit in python werkt is heel elegant.
- Voorbeeld:
  ```python
  naam = "Bert"
  pogingen = 3.0
  print(f"{naam} had {aantal_pogingen:.0f} nodig!")
  ```
- Dynamische elementen worden door gekrulde haakjes ingevoegd.
- De formattering van [[numerieke datatypes]] kan je aanpassen door een dubbele punt in de haakjes (zie [hier](https://cheatography.com/brianallan/cheat-sheets/python-f-strings-number-formatting)).
- Er zijn meerdere alternatieven:
  ```python
  print(f"{naam} had {aantal_pogingen:.0f} nodig!")
  print("{naam:%s} had {pogingen:.0f} nodig!".format(naam = naam, pogingen = aantal_pogingen))
  print("{} had {} nodig!".format(name, aantal_pogingen))
  print(f"%s had %.0f nodig!" % (naam, aantal_pogingen))
  ```
  ([verder lezen](https://realpython.com/python-string-formatting))