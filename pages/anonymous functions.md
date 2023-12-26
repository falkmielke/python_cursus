alias:: lambda, lambda-functies, lambda functions, anonieme functies
tags:: uitbreiding
title:: anonymous functions

- Lambda-functies zijn een manier om heel korte [[functies]] in één lijn te schrijven. Ze krijgen geen bepaalde naam ("anoniem"), maar worden in een variabele opgeslaan.
- Bijvoorbeeld:
  ```
  MijnPolynoom = lambda x: x**3 -2*x**2 +4*x -1
  print(MijnPolynoom(4))
  ```
  vervangt de volgende functie:
  ```
  def MijnPolynoom(x):
  	return x**3 -2*x**2 +4*x -1
  print(MijnPolynoom(4))
  ```
- Handig, hé?
-
- [[syntaxis]]:
	- het signaalwoord `lambda`
	- gevolgd van de input-argumenten,
	- een dubbele punt (`:`)
	- en de functie; de `return` gebeurt automatisch met de uitkomst van het commando achter de `:`.