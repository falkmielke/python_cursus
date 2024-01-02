alias:: FP, functioneel programmeren, lambda calculus
tags:: uitbreiding

- Functional programming is een programmeerstijl waarbij het proces van data (van input naar output) in de focus staat. Zoals de naam zegt gaat het over het uitvoeren van [[functies]].
- Binnen functional programming wordt vermeden om de toestand van [[variabelen]] te veranderen; in plaats daarvan wordt een nieuwe, andere variabele aangemaakt. (voorkeur voor "immutable" [[data types]])
- De uitkomst van een functie is deterministisch; het resultaat van de functie gaat met dezelfde data altijd ook hetzelfde zijn (bijvoorbeeld functies uit de wiskunde, zoals `sum()`).
- Het gebruik van [[anonieme functies]] is ook typisch voor FP.
- Omvat ook meer ingewikkelde strategien zoals
	- **first class functions**, **higher order functions**, **pure functions**
	- **lazy evaluation**
	- **recursie**
	- **nested functions**
	- **function transformations**
	- **currying**
	- **decorators** (python)
- verder lezen: https://nl.wikipedia.org/wiki/Functioneel_programmeren
- FP en [[OOP]] zijn complementair, je mag ze allebei gebruiken!
-
- **voorbeelden**
	- Het gebruiken van de volgende functies is een typische voorbeeld van een "functional approach":
		- `map()`
		  ```python
		  Square = lambda x: x * x
		  
		  nums = [1, 2, 3, 4, 5]
		  squared_nums = map(Square, nums)
		  print(list(squared_nums))
		  # [1, 4, 9, 16, 25]
		  ```
		- `filter()`
		  ```python
		  isEven = lambda x: x % 2 == 0
		  
		  nummers = [1, 2, 3, 4, 5, 6]
		  evens = list(filter(isEven, nummers))
		  print(evens)
		  # [2, 4, 6]
		  ```
		- `reduce()`
		  ```python
		  import functools
		  Mal = lambda x, y: x * y
		  
		  def factorial(n):
		      return functools.reduce(Mal, range(1, n + 1))
		  ```
		- `zip()`
		  ```python
		  letters = ['a', 'b', 'c']
		  nummers = [1, 2, 3]
		  
		  letternummer = list(zip(letters, nummers))
		  print(letternummer)
		  # [('a', 1), ('b', 2), ('c', 3)]
		  ```