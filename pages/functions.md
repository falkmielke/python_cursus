alias:: functies, functie, function, method, methods, methode

- **TL;DR**
	- Functies splitsen je programmacode op in kleine, hergebruikbare eenheiden. Dit is enorm handig.
	- Good practice: splits je programma altijd zo klein mogelijk op in zinvolle, begrijpelijke werkpakjes.
	- Gebruik duidelijke en zinvolle functie-namen, gebruik uitvoerlijke [[documentatie]].
-
- **Motivering**
	- ![image.jpg](../assets/waschmaschine.jpg){:width 600}
	- Dit is een wasmachine. Die heeft een draaiknop met verschillende **functies**. Je kan er bijvoorbeeld "Katoen/Eco" kiezen en de machine weet dan misschien dat ze alternerend drie keer moet spoelen en centrifugeren.
	- "Speed" is geen "snelheid", maar een andere functie: hier gaat ze misschien maar één keer centrifugeren en spoelen.
	- Op het einde van elk van die programma's komt er een "stop", en de machine geeft meer of minder propere kleren terug. (Noot: ik kan die kleren van buiten niet aanraken terwijl de was bezig is, zie [[scope]].)
	- "Spoelen", "Centrifugeren", "Stop" enz. zijn voor zich ook functies; sommige daarvan hebben parameters die ik mag kiezen (bv. de snelheid van het centrifugeren, de temperatuur). "Krimpen" is geen functie van de machine, maar een ongewenst effect van mijn keuzes; maar het kan gebeuren (zie [[errors]]).
-
- **Eigenschappen van Functies**
	- We **definieren** in python een functie met het signaalwoord `def`:
	  ```python
	  def SayHello(recipient):
	  	print(f"Hello, {recipient}!")
	      return 
	  ```
	  Dit werkt net zo als de declaratie van een [[variabele]]: pas als we er achteraf iets mee doen wordt de functie opgeroepen.
	- **Calling:** De functie is dus *de blauwdruk of stappenplan*, uitvoeren gaan we de instructies pas als we ze oproepen met gewone hakjes:
	  ```python
	  SayHello("teacher")
	  ```
	- **Name:** elke functie heeft een naam, zoals elke [[variabele]] die we bijhouden een naam heeft. Fun fact: functies zijn ook maar wijzers naar een geheugenplaats (waar de functie-instructies opgeslaan zijn).
	- **Signature:** functies hebben ook een zogenoemde signatuur. Dit omvat naast de naam ook alle [[argumenten]] die de functie /binnen krijgt/ en hun standaardwaardes. Voorbeeld:
	  ```python
	  def SayHello(recipient: str, message: str = None, repetities: int = 1):
	  	for rept in range(repetities):
	  		print(f"Hello, {recipient}! {message}")
	  ```
	- **Scope:** Elke functie brengt haar eigen [[scope]] mee: variabelen die binnen de functie gedefinieerd zijn zijn alleen maar binnen die functie geldig. Bijvoorbeeld:
	  ```python
	  def Aanmaken(waarde):
	      variabele = waarde
	  Aanmaken(5)    
	  print (variabele) # geeft een fout
	  ```
	- **Return:** wil je dus iets van binnen de functie ook buiten gebruiken, moet de functie het achteraf teruggeven met een `return`. Je kan één of meerdere variabelen teruggeven. Let op: als je kiest om niets terug te geven door `return` weg te laten, dan gaat de functie een [[None]] terug geven.
	- Een synoniem voor "functie" is **"method"**.
-
- **Trucjes met Functies**
	- Als je de functienaam heen- en weergeeft, zonder de haakjes, dan kan je de instructies dus meegeven en ergens anders of later gebruiken.
	  ```python
	  ## Voorbeeld: berekening met een string-input
	  
	  def Sum(a, b):
	      return a+b
	  def Min(a, b):
	      return a-b
	  def Maal(a, b):
	      return a*b
	  def Door(a, b):
	      return a/b
	  
	  operatie = {'+': Sum, '-': Min, '*': Maal, '/': Door}
	  
	  def Berekening(instructie):
	      c1, operator, c2 = instructie.split(' ')
	      return operatie[operator](float(c1), float(c2))
	  
	  Berekening("5 + 4")
	  ```
	- Recursion: Een functie kan zich zelf oproepen. Dit is een mooi concept voor gevorderden, zoek het graag online op.
	- [[functional programming]] is een specifieke manier/stijl van programmeren die nadruk op eigenstandige functies legd.