alias:: sorteeralgoritmen, sorting, sorteren

- Om een reeks van gegevens te sorteren (bv. van het "kleinste" naar het "grootste", of alfabetisch) hebben we een aantal algoritmes ter beschikking.
- Afhankelijk van de [[gegevenstypen]] in de reeks varieerd de performance van verschillende algoritmes.
- In de praktijk kom je meestal vooruit met **`sorted(<reeks>)`** in python. Maar de [[algoritmen]] beneden zijn goed om bv. [[complexiteit]], [[recursie]] en [[divide and conquer]] te begrijpen.
-
- Een goede overzicht hier: https://en.wikipedia.org/wiki/Sorting_algorithm
  Een interessante video hier: https://www.youtube.com/watch?v=kPRA0W1kECg
- Beneden enkele voorbeelden.
-
- **Bubble Sort**
    - De meest intuitieve manier van sorteren (bron: [wikipedia](https://nl.wikipedia.org/wiki/Bubblesort)):
        - 1. Loop door de te sorteren rij van n elementen en vergelijk elk
          element met het volgende. Verwissel beide als ze in de verkeerde 
          volgorde staan. Schuif dan een stapje op.
        - 2. Loop opnieuw door de rij, maar ga nu door tot het voorlaatste element, omdat het laatste element het grootste in de rij was.
        - 3. Nog een keer, maar negeer dan de twee laatste elementen.
        - 4. Ga zo door.
        - *n*. Nog een keer, maar negeer dan de laatste *n*−1 getallen.
        - *n*+1. Klaar.
-
- **Merge Sort**
    - Een "[[divide and conquer]]" algoritme:
        - de gegevensreeks wordt er eerst opgesplitst, tot dat de kleine onderdelen triviaal te verwerken zijn.
        - Daarna worden de deelreksen op een slimme manier weer samengevoegd ("merge").
    - bron: https://en.wikipedia.org/wiki/Merge_sort
      bron: https://stackoverflow.com/questions/18761766/mergesort-with-python
    - ``` python
      def mijnMergeSort(reeks: list) -> list:
          ## aangepast, maar gebaseerd op https://stackoverflow.com/a/39683605
      
          # de "base case": als er maar eentje overblijft, is het gesorteerd.
          if len(reeks) == 1:
              return reeks
          else:
              ## Fase 1: "Split", het opsplitsen
              # ... anders: splits het op in twee evenmatige reksen
              mid = int(len(reeks) / 2) # vind het middelpunt
              left = mijnMergeSort(reeks[:mid]) # merge de linke helft
              right = mijnMergeSort(reeks[mid:]) # merge de rechte helft
      
          ## Fase 2: "Merge", het samenvoegen
          # hier gaan we dan de overige twee sorteren
      
          # twee indices aanmaken, eentje voor de "linke" helft, eentje voor "rechts"
          l = 0 # links
          r = 0 # rechts
      
          # maak er een lege "result" list
          result = []
      
          # het samenvoegen van de twee arrays
          # dubbele "while" loop: gaa door de
          while l < len(left) and r < len(right):
      
              # vergelijk de elementen links en rechts
              # als het element links kleiner is dan rechts,...
              if left[l] < right[r]:
                  # voeg het aan het resultaat
                  result.append(left[l])
                  l += 1
              else:
                  # anders voeg het rechte element aan
                  result.append(right[r])
                  r += 1
      
          # en dan de rest nog aanvoegen
          result += left[l:]
          result += right[r:]
      
          return result
      ```
-
- **Gnome Sort**
    - [https://en.wikipedia.org/wiki/Gnome_sort](https://en.wikipedia.org/wiki/Gnome_sort)
    - Dick Grune described the sorting method with the following story:
    - > Gnome Sort is based on the technique used by the standard Dutch Garden Gnome (Du.: tuinkabouter).
      Here is how a garden gnome sorts a line of flower pots. Basically, he looks at the flower pot next to him and the previous one; if they are in the right order he steps one pot forward, otherwise, he 
      swaps them and steps one pot backward. Boundary conditions: if there is no previous pot, he steps forwards; if there is no pot next to him, he is done.
      
      — “Gnome Sort - The Simplest Sort Algorithm”. Dickgrune.com
    -