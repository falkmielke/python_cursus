alias:: foutmelding, errors, traceback, bugs, debugging

- ![image.jpg](../assets/error.jpg){:width 450} 
  *Er was iets mis met deze tijger op 1/1/2024 in "Tierpark Stendal". Een dierenarts zou moeten kijken wat er fout was (="error traceback"). Foto by Falk Mielke.*
-
- *... Shit happens.* Laat je niet teleurstellen!
- Lees altijd goed de "error stack", of "traceback": je kan direct zien waar de fout ligt en welke type fout gebeurt is.
-
- **Fouten**
    - ... in de [[syntaxis]]. Dit gebeurt vaak. De python-[[interpreter]] vindt deze problemen normaal gezien goed en geeft een descriptieve foutmelding. Omdat de interpreter het opvangt noemen we dit ook een fout tijdens de *compile-time*.
    - ... in de programma-logica. Bijvoorbeeld een rekenfout of voortekenfout, vaak ook fouten met de data-types. De interpreter kan deze niet vinden, maar het uitvoer-resultaat is fout. Omdat die tijdens het lopen van het programma gaat optreden (looptijd) noemen we het een *runtime* error.
    - Goede [[compiler]]/ [[interpreter]] vinden zo veel mogelijk fouten in de compile-tijd. Goede programmeer-stijl is een programma zo te ontwerpen dat mogelijks veel fouten al tijdens de compile-time tevoorschijn komen (bv. door [[exception handling]]).
-
- *Disambiguation:* bij [[exception handling]] roepen we zelf foutmeldingen op en vangen die later op.