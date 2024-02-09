alias:: decorators

- Een trucje uit de koffer van [[functional programming]], en een bijzonderheid van python.
- Je moet een functie aanmaken die een functie binnen krijgt. Deze functie wordt in een "wrapper" gebruikt, en het resultaat kan eventjes aangepast worden.
- Bijvoorbeeld kan je een functie-oproep omgeven met het meten van de loopduur:
  ``` python
  def timer(func):
      def wrapper(*arg, **kw):
          t1 = time()
          res = func(*arg, **kw)
          t2 = time()
          return res, (t2 - t1)
      return wrapper
  ```
- Je gebruikt die functie dan als wrapper voor een andere functie door de `@`-operator:
  ``` python
  @timer
  def faculteit(n):
      if n == 0:
          return 0
      resultaat = 1
      for i in range(2, n+1):
          resultaat *= i
      return resultaat # noot: de functie geeft eigenlijk maar het resultaat
  ```
- Als je dan deze functie gebruikt is de `return`-waarde verandert:
  ``` python
  fac, duur = faculteit(100) # noot: de "duur" komt van de decorator boven
  ```
-
- Een heel gedetailleerde introductie is [hier](https://realpython.com/primer-on-python-decorators/) te vinden.
-