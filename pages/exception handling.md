alias:: exception, exceptions, raise, try, try catch, exceptie

- *Disambiguation:* Hier gaat het niet over [[debugging]] / het vinden van fouten in je eigen code.
-
- **TL;DR:**
    - Het is is te verwachten dat in de *runtime* iets met jouw programma fout kan gaan. Jij moet fouten anticiperen en aan het programma leren om met deze problemen om te gaan.
    - Excepties zijn zoals het spelen met een bal: je moet ze gooien (*throw*), vangen (*catch*) en je moet ermee kunnen omgaan (*handling*).
    - In python gebruiken we de `try`... `except` omgeving.
-
- **Theorie**
    - In de woorden van een (over het algemeen slechte) cursus die ik ooit volgde:
        - """
          Softwareapplicaties zijn niet perfect (bv. gebruikersinvoer en netwerkconnectiviteit zijn verre van voorspelbaar). Ondanks intensief debuggen en unit-testen zullen applicaties nog steeds storingsgevallen tegenkomen wanneer ze in de echte wereld worden uitgevoerd.
          Verlies van netwerkconnectiviteit, ontbrekende databaserijen, problemen met onvoldoende geheugen en onverwachte gebruikersinvoer kunnen er allemaal voor zorgen dat een applicatie niet "normaal" functioneert. 
          **Het is jouw taak om alle fouten op een correcte manier op te sporen en af te handelen, zodat jouw toepassing naar verwachting presteert.** 
          Wanneer je kunt vaststellen dat er iets mis is, moet je zelf de fouten genereren, naast de "standaard"-fouten die de interpreter genereert.
          """
    - Een duidelijk betere aanpak vindt je in deze cursus hier: https://youtu.be/ttbu9L4RdYs?t=1505
-
- **Toepassing**
    - Voorbeeld:
      ```python
      try:
          print(x)
      except NameError:
          print("Variabele x is niet gedefinieerd!")
      except Error as err:
          print("Iets anders is fout gegaan. Hier de foutmelding:", err) 
      ```
    - Je kan je eigen fouten aanmaken met `Exception("foutmelding")`:
      ```python
      def KringOmvang(r: float) -> float:
          if r < 0:
              raise IOError("We gebruiken alleen maar positieve radii!")
          pi = 3.00 # pi is precies 3
          return 2*pi*r
      ```
-
    - Er zijn verschillende types: `IOError`, `ValueError`, `NameError`, ... 
      (Noot: dit zijn allemaal [onderklassen](OOP) van `Error`.)