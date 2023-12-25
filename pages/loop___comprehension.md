alias:: loop comprehension, list comprehension, dict comprehension, comprehension
tags:: uitbreiding

- Je kan de "no-index syntax" van een [["for"-loop]] nog een stukje verder brengen: door het werken met een lijst kan je het binnen één lijn omzetten.
- Voorbeeld: je hebt een lijst met namen en wilt er alleen maar de voornamen van hebben.
  ```python
  namen = ["Bob A.", "Mary B.", "Tom C."]
  voornamen = [naam.split(" ")[0] for naam in namen]
  ```
- Dit gaat ook met dictionaries, bv.
  ```python
  nummer_naam = {nr: naam for nr, naam in enumerate(namen)}
  ```
- Zelf een [[conditional]] kan je erin zetten:
  ```python
  voornamen = [naam.split(" ")[0] \
               for naam in namen \
               if 'o' in naam.lower() \
              ]
  ```
- In principe is dit heel duidelijke en elegante syntaxis, als je niet overdrijft met "nested list comprehension": het moet goed leesbaar blijven!