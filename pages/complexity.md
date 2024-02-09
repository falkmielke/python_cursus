alias:: complexiteit

- **Motivativering**
    - ![image.jpg](../assets/microchip.jpg){:width 400}
    - Een computer bestaat uit verschillende bestanddelen. Onder meer zitten erin een *processor* (CPU, eng. "Central Processing Unit"), een *werkgeheugen* (RAM, eng. "Random Access Memory"). Wat er niet in de RAM past of langer moet blijven kan ke op de *harde schrijf* opslaan.
    - Heel simpel geschreven: het werkgeheugen kan gegevens onthouden, bv. twee getalen. De processor doet de berekeningen, bv. bepaalt hij de som van die twee getalen.
    - Niet elke berekening is zo simpel als een gewone som; we hebben de computer precies voor de moeilijke programma's.
    - Processor of werkgeheugen kunnen dus ook bepalend zijn: als er te veel berekeningen zijn, of te ingewikkelde processen, dan gaat hij dit niet in korte **tijd** kunnen oplossen. Als er te veel gegevens moeten opgeslaan worden, dan kan het gebeuren dat er onvoldoende **plaats/ruimte** in het werkgeheugen is.
    - Wat doe *jij* als je iets vanuit je hoofd berekend?
      “Werkgeheugen”: twee getalen onthouden. “Processor”: je weet hoe je de som vormt.
      Wat komt er bij als je de getalen op papier schrijft? “Harde schrijf”: uitbesteding van je werkgeheugen, maar trag. Ons hersenen werkt dus ook een beetje zoals een computer, of omgekeerd.
-
- **Theorie**
    - De last van een algoritme voor de processor kunnen we inschatten met de “[Time Complexity](https://en.wikipedia.org/wiki/Time_complexity)”
    - De last van een algoritme voor het werkgeheugen kunnen we inschatten met de “[Space Complexity](https://en.wikipedia.org/wiki/Space_complexity)”
    - Dit zijn theoretische schattingen. Je kan looptijdbeslissingen niet voorspellen (bv. “conditionals” of user input).
      *De complexiteit is dus een benadering; een soort van “worst case” schatting.*
    - Enkele toevallig gevondene bronnen voor geïnteresseerden
      [[https://towardsdatascience.com/understanding-time-complexity-with-python-examples-2bda6e8158a7]]
      [[https://www.studytonight.com/data-structures/space-complexity-of-algorithms]]
-
- **Praktische Benadering**
    - We gaan de complexiteit praktisch benaderen door de **loopduur** van een programma te meten.
    - We kunnen de looptijd meten, bv. met `time.time()` ([documentatie](https://docs.python.org/3/library/time.html#time.time)):
      
      ``` python
      from time import time
      
      tic = time()
      resultaat = functie(*args, **kwargs)
      toc = time()
      
      looptijd = toc - tic # in seconden
      ```
    - ook het gebruik van **geheugen** kunnen we met een praktisch tool inschatten:
      op windows: gebruik het programma [Resource Monitor](https://en.wikipedia.org/wiki/Resource_Monitor)
      op linux: bv. `htop` ([zie hier](https://linuxhandbook.com/top-vs-htop/))
      
      (Noot: er zijn ook enkele python-oplossingen, [zie hier](https://www.geeksforgeeks.org/monitoring-memory-usage-of-a-running-python-program/))
-
- **Voorbeeld: Fibonacci**
    - De [Rij van Fibonacci](https://nl.wikipedia.org/wiki/Rij_van_Fibonacci) is een rij die gedefinieerd is als een rij van de som van de twee vorige argumenten, of als [[algoritme]]:
        - neem twee getalen in een rij, bv. “0” en “1”. → `[0, 1]`
        - maak het volgende element aan als de som van de vorige twee. Bv. “0 + 1 = 1”.  → `[0, 1, 1]`
        - herhaal de vorige stap → `[0, 1, 1, 2, 3, 5, …]`
    - Een Naïve implementatie gebruikg [[recursion]]:
        - ``` python
          def Fibonacci_recursief(n: int) -> int:
              # berekend het n'de element van de Fibonacci-rij
              
              # base case
              if (n == 0) or (n == 1):
                  return n
                  
              # rij aanvullen: het element n is de som van de vorige twee elementen
              return Fibonacci_recursief(n-1) + Fibonacci_recursief(n-2)
            
          from time import time # gebruikt de functie "time" uit de bibliotheek "time" voor een tijdmeting
          loopduur = [] # gaat de tijd per iteratie opslaan
          for i in range(50):
              starttijd = time() # kijk voor de functie op je horloge
              fib = Fibonacci_recursief(i)
              eindtijd = time() # kijk na de functie op je horloge
              duur = eindtijd - starttijd
              loopduur.append(duur)
              print (i, fib, duur)
              
          # een grafiek aanmaken met de looptijd
          import matplotlib.pyplot as plt
          plt.plot(loopduur)
          plt.show()
          ```
    -
    - Een andere implementatie van de rij gebruikt [[dynamic programming]] (zie ook: [[decorator]]):
        - ``` python
          from time import time
          
          # we gaan het timing hier een beetje professioneler maken: met een "decorator"
          # gevonden hier: https://stackoverflow.com/questions/1622943/timeit-versus-timing-decorator
          def timer(func):
              def wrapper(*arg, **kw):
                  t1 = time()
                  res = func(*arg, **kw)
                  t2 = time()
                  return res, (t2 - t1)
              return wrapper
          
          @timer
          def Fibonacci_dynamisch(n: int) -> int:
              # berekend het n'de element van de Fibonacci-rij
          
              # base case
              if (n == 0) or (n == 1):
                  return n
          
              # aanmaken van een lege rij: een lijst van [0,0,0,...]
              rij = [0]*(n+1)
              rij[1] = 1 # het element 0 blijft 0, het element 1 wordt hier 1
          
              # aanvullen van de rij, op plaats in de lijst
              for i in range(2, n+1):
              	# rij aanvullen: het element n is de som van de vorige twee elementen
                  rij[i] = rij[i-1] + rij[i-2]
              return rij[-1] # het laatste element van de lijst is wat we zoeken.
          
          
          
          loopduur = [] # gaat de tijd per iteratie opslaan
          for i in range(500):
              for _ in range(50):
                  # 50 herhalingen om een goede gemiddelde tijd te krijgen
                  fib, duur = Fibonacci_dynamisch(i)
                  loopduur.append((i, duur))
                  # print (i, fib, duur)
          
          # een grafiek aanmaken met de looptijd
          import matplotlib.pyplot as plt
          plt.scatter(*zip(*loopduur), s = 3, color = 'k', marker = 'x', alpha = 0.05)
          mean = lambda x: sum(x)/len(x)
          plt.plot([i for i in range(500)], [mean([v for k, v in loopduur if k == i]) for i in range(500)] \
                  , lw = 2, alpha = 0.8, color = 'darkred')
          plt.show()
          ```
-
- **Verder Lezen**
    - https://nl.wikipedia.org/wiki/Computationele_complexiteitstheorie
    - https://towardsdatascience.com/understanding-time-complexity-with-python-examples-2bda6e8158a7