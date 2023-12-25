alias:: None, NoneType

- `None` is niets.
  title:: data types/None
- `None` is niet niets.
- `None` is een zogenoemde nul-pointer, een wijzer die naar niets toewijst.
- Dit is heel nuttig, want het spaart geheugen.
- Vergeet niet dat `None` altijd met een hoofdletter begint.
- En dat de operatie `iets == None` niet betrouwbaar is: gebruik **altijd** `iets is None` om een waar-fout-vergelijking met `None` te maken.
- `None` is van de [[datatype]] `NoneType`, wat je soms in de [[error traceback]] kan lezen.
- Oefening: Wat is aan de volgende code fout?
  ```python
  def InvertString(tekst = "None"):
      if tekst is None:
          raise IOError("Geen tekst gegeven!")
      return tekst[::-1]
  ```