alias:: regex, re, reguliere expressie

- "Regular expressions" is een specifieke [[syntaxis]] voor het vinden van patronen in tekst.
- zie [hier](https://nl.wikipedia.org/wiki/Reguliere_expressie)
- in python met de [[bibliotheek]] `re`.
- Voorbeeld ([van hier](https://docs.python.org/3/howto/regex.html)):
  ```python
  import re
  p = re.compile(r'\d+')
  p.findall('12 drummers drumming, 11 pipers piping, 10 lords a-leaping')
  # geeft ['12', '11', '10']
  ```