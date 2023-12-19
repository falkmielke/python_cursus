alias:: flow

- **TL;DR**
	- De computer verwerkt een programma van boven naar beneden, van binnen haakjes naar buiten, en van links naar rechts.
	- Er zijn uitzonderingen, bv.: [[lussen]], [[voorwaarden]] , [[functies]] en [[klassen]].
-
- **Pannekoeken**
	- ![image.png](../assets/pannekoeken.jpg)
	- Je wilt pannekoeken eten, en volgt het recept vanuit een kookboek (hier: "Koken voor elke dag", Manteau, 2016).
		- Meng de bloem met het bicarbonaat.
		- Klop de melk met de boter, eieren en honing.
		- Meng de bloem met het melkmengsel en roer glad.
		- Laat het beslag 15 minuten rusten.
		- ...
	- Dit is een recept. Er horen ingredienten bij (die zou je als [[variabelen]] kunnen beschouwen). En er zit een **stappenplan**, een lijst met dingen die je moet doen om pannenkoeken te krijgen.
	- Als je die stappenplan volgt, van boven naar beneden, dan krijg je lekker eten.
	- Noot dat sommige werkwoorden in de lijst [[functions]] zijn die er niet verder uitgelegd staan; bijvoorbeeld "*klop de melk met boter, eieren en honing*" zou iets raars kunnen zijn om te doen, als je niet weet wat "kloppen" in die context betekent.
	- En je moet de stappen in de juiste volgorde uitvoeren: als je nog geen melkmengsel hebt, kan je het niet mengen; als je alles eerst laat rusten en dan mengt, zou er wel een pannenkoeken uit komen, maar misschien minder lekker.
-
- **Flow**
	- Dit is precies wat de computer doet zodra hij een programma krijgt.
	- ``` 
	  a = 1
	  b = 1
	  c = a + b
	  print ("Het resultaat is: c = ", c)
	  ```
	- In dit voorbeeld defineren we twee [[variabelen]], `a` en `b`, en wijzen hen de waarde `1` ("één") toe. Dan defineren we de variable `c` en wijzen de waarde `a+b` toe. Het resultaat printen we af.
	- De computer zou niet kunnen afprinten zonder `c` te kennen. Ook de som van `a` en `b` kan je pas berekenen nadat je die variabelen gedefineerd heeft. Anders geeft de computer een [[foutmelding]].
	- De volgende drie algemene kenmerken van de Flow van een script of programma zijn belangrijk, in die volgorde:
		- Verwerken **van boven naar beneden**.
		- Verwerken **van binnen de haakjes** naar buiten.
		- Verwerken **van links naar rechts**.
	- Er zijn uitzonderingen, waar de computer een commando niet direct uitvoerd, of een commando herhaald uitvoerd. Dit noemen we dan "control flow".
-
- **Control Flow**
	- Wij gaan hier beginnen met twee manieren om de uitvoeringsvolgorde van een programma aan te passen: loops (lusjes) en conditionals (voorwaarden). Later gaan we ook nog zien hoe we een programma in [[functions]] en [[classes]] structureren.
	- [[loops]]
	- [[conditionals]]
-