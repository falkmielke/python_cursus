alias:: datatypes, data type, datatype, datatypen, gegevenstypen

- **TL;DR**
	- De computer moet voor alle [[variabelen]] die we defineren de type kennen. In python gaat dit meestal automatisch.
	- Door de type is gedefineerd wat je met een variable kan doen ([[functies]]), welke eigenschappen ze heeft, hoe operatoren werken, enzoverder.
	- Met de ingebouwde functie `type()` kan je de type van een variable vragen.
-
- **Motivering**
	- Neem als voorbeeld deze twee instrumenten:
		- ![image.jpg](../assets/instrument1.jpg){:width 256} ![image.jpg](../assets/instrument2.jpg){:width 256}
		- Uiterlijk verschillen die niet echt. Het zijn snareninstrumenten, gemaakt van gestreepte ebbehout, met een klankgat in het midden, en pick-ups onder de brug. Allebei zijn Ukuleles van de merk "Kala".
		- Maar als je goed kijkt zie je snaren van nylon (boven) en polyurethaan/silikoon (beneden). De grootte van het instrument is ook verschillend. De eerste is een tenor-ukulele, de onderste een bas-ukulele (UBass). De klank en de ordening van de snaren is dus helemaal verschillend.
		- Vergelijk dit met een elektrische basgitar, zoals deze Cort A4: 
		  ![image.jpg](../assets/instrument3.jpg){:width 256}
		  Die heeft metaalomwondene snaren en draaiknopjes, geen klankholte, en andere pick-ups.
		- De UBass lijkt qua uiterlijk veel meer op de eerste Ukulele, maar je zou ze niet automatisch allebei kunnen spelen. Maar je kan een UBass even goed als een EBass spelen.
		- Om dit eens te kaderen, dit is nog een instrument: een [Kpanlogo drum](https://en.wikipedia.org/wiki/Kpanlogo_(drum)) uit Ghana.
		  ![image.jpg](../assets/instrument4.jpg){:width 256}
		  Fun fact: je kan [een basgitar ook bijna zoals een percussie-instrument gebruiken](https://www.youtube.com/watch?v=En1U1P9di64).
		- Misschien kan je ook op de snaren blazen, zoals een trompet?
		  ![image.jpg](../assets/instrument5.jpg){:width 256}
	- **Wat heeft dit met programmeren te maken?**
		- Misschien heb je er nog nooit over nagedacht, maar **ons hersenen plaatst alles in categorieën**. 
		  Categorieën hier zijn bv. "instrument", "snareninstrument", "percussie", "zangstem", "materiaal", "uiterlijk", "kan ik spelen of niet"... Door die categorieën weten we wat er met elk ding te doen is.
		- De computer kan dit in principe niet: **we moeten expliciet vermelden met welk ding we willen werken, en wat we daarmee kunnen doen.** We geven elke variabele daarom een *datatype*.
		- Elk datatype brengt dus zijn eigen set aan [[functies]] mee, werkt op een eigen manier met operatoren, en heeft specifieke eigenschappen (bv. geheugenbehoefde).
-
- **Overzicht**
	- De belangrijkste datatypen die we in Python gebruiken:
		- [[boolean]]
		- [[numerieke datatypes]]
		- [[string-datatypes]]
		- [[lijst]]
		- [[dictionary]]
	- De type van een [[variabele]] kan je vragen met de functie `type()`:
	  ```python
	  a = 1
	  b = 2.
	  print(type(a), type(b))
	  ```
	  geeft `<class 'int'> <class 'float'>`.
	- Zie ook: [[classes]].
- **Theorie**
	- Een computer "denkt" niet. Hij volgt een [[controlestroom]] en kan tussendoor [[variabelen]] in zijn geheugen opslaan. Met die geheugen-pakjes zijn heel beperkte operaties mogelijk (zie [[boolean]]: `or`, `and`, `xor`, en bit-verschuiving). Dit is alles. Daarop bouwt alles op.
	- Wij gebruiken wel iets abstractere datatypen. De computer waarop je een basis-python installeerd weet ermee om te gaan. Elke datatype brengt zijn eigen [[functies]] mee. Bijvoorbeeld kan je een lijst sorteren met `lijst.sort()`, een enkele getalwaarde (`1.sort()`) niet.
	- Operatoren kunnen verschillen afhankelijk van de datatype: bijvoorbeeld kan je strings verbinden met het `+`:
	  ```python
	  zin = "Dit "+"is "+"een "+"onzin. "
	  print (zin)
	  ```
	- TODO call by reference, call by value
	- TODO typische fouten [[exception handling]]
-
- **Eigen Datatypes**
	- zie [[objectgeoriënteerd programmeren]] .
-
- Mentale categorieën zijn overal. Ze zijn niet logisch, ze overlappen, maar ze zijn onvermijdelijk. Voorbeeld:
  ![image.jpg](../assets/frog.jpg){:width 256}
  
  Bij het programmeren worden de categorieën expliciet, en je moet goed doordacht definiëren wat je met welk stukje opslagruimte in het computergeheugen kan doen.