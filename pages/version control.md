alias:: git, subversion, mercurial
tags:: uitbreiding

- Één van de meest gebruikte tools van professionele programmeurs is **version control**, bijvoorbeeld met `git`, `mercurial` of `subversion`. De meeste mensen gebruiken `git`.
- Bijvoorbeeld, `git` is een command line tool om de veranderingen van tekstbestanden op te slaan.
- Dit heeft verschillende voordelen:
    - Je houdt een backup bij van tussenstappen in de ontwikkeling van een programma; bijvoorbeeld kan je foutieve aanpassingen terugdraaien.
    - Git is decentraal: je kan heel gemakkelijk kopieën van je code ergens anders opslaan en regelmatig synchroniseren, bv. op een USB-stick of op een webserver.
    - Je kan met een `branch` parallele versies van een programma bijhouden, wat onder meer bij de ontwikkeling van nieuwe features handig is.
- Er zijn programma's met een gebruiker-interface, waarmee je gemakkelijker kan beginnen (bv. [git-cola](https://git-cola.github.io/), [sublime merge](https://www.sublimemerge.com/) en [magit](https://magit.vc)).
- Omdat de versiecontrole alle *veranderingen* opslaat, is `git` niet efficient met binaire bestanden zoals afbeeldingen of word-documenten. Let op dat er alleen maar tekstbestanden in je repo getrackt zitten! (voor de andere is er een bijkomend programma, "git annex").
- Fun fact: deze cursus wordt ook in een `git` repo bewaard: https://github.com/falkmielke/python_cursus.
-
-
- **Repositories**
    - Elke map op jouw computer die je mit git initialiseerd is een git repository. Je kan perfect lokaal werken, zonder met het internet te verbinden.
    - Je kan ook een eigen webserver met een git repo manager laten draaien, bijvoorbeeld met [gogs](https://gogs.io/).
    - Er zijn web-services die een git server ("repository") voor je klaar zetten. Deze worden vaak gebruikt om programma's publiek te delen. De populairste zijn [github](https://github.com) en [gitlab](https://about.gitlab.com).
-
- **Woordenschat**
    - `git init`: het aanmaken van een repository
    - `git clone`: kopieëren van een repo
    - `git status`: toont wat er momenteel in de repo aan de hand is
    - `git log`: toont de versie-geschiedenis van het repo
    - `git add`: toevoegen van bestandveranderingen
    - `git ignore [...]`: veranderingen in een bestand of map worden niet opgevolgd; je kan ook het tekstbestand ".gitignore" aanpassen.
    - `git stage`: voorbereiden van alle toegevoegde bestandsveranderingen tot een nieuwe stap
    - `git commit`: schrijven van alle bestandsveranderingen op de `stage` tot een nieuwe programmaversie.
    - `git branch`: aanmaken van of omschakelen naar een parallele versie van de code
    - `git merge`: vereniging van twee (divergente) branches of commits
    - `git checkout`: verandert de code (of een specifieke bestand) naar de toestand van een eerdere `commit` of een andere `branch`
    - `git remote [...]`: beheer van de remote repo, dus de oorsprongversie van waar je de code gekopiërd hebt.
    - `git pull` / `git push`: synchronisatie met de remote repo
    - *pull request* is de aanvraag van een gebruiker om een code-aanpassing in de mainline code intevoegen; vaak gebruikt om [[bugs]] te verbeteren
    - *fork* is de kopie van een hele repo die een zelfstandige programma wordt.
-
- *Version control is zoals een tijdmachine. En een multiverse. Leer en gebruik het!*
  ![image.jpg](../assets/grammophone.jpg){:width 450}