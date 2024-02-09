alias:: recursie

- ![image.jpg](../assets/recursion.jpg){:width 300}
  *Visual recursion; Judge Magazine Cover (19/01/1918), [bron](https://i.pinimg.com/474x/b6/85/2b/b6852b41e5cef4ec7009d615b6770edd--montgomery-james-darcy.jpg), [via](https://commons.wikimedia.org/wiki/File:JudgeMagazine19Jan1918.png)*
- Als een functie zich zelf oproept, noemen we dit "recursion".
- Recursie is niet altijd de meest efficiente manier om een probleem op te lossen (zie [[complexiteit]]). *Maar* soms is het een heel elegante manier, en soms zelf de enige manier om problemen op te lossen.
- Een zogenoemde "tail recursion", dus waar de recursie-stap op het einde komt, kan je altijd ook vertalen in een [[lus]].
- Recursie een een typische strategie in het kader van [[functional programming]].
-
- **Voorbeeld**
    - Het klassieke voorbeeld van [[recursie]] is de [faculteit](https://nl.wikipedia.org/wiki/Faculteit_(wiskunde)):
      ``` python
      def faculteit(n):
          return 1 if (n == 0) or (n == 1) else faculteit(n-1)
      ```