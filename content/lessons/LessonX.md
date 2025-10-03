---
numbering:
  title:
    offset: 0
---
# Going local

Lokaal bouwen
Het werken met GitHub, het boek daar laten bouwen, heeft een aantal voordelen: 
- de aanpassingen zijn meteen te zien en beschikbaar voor collega's
- de meeste handelingen voor het bouwen van het boek worden voor je uitgevoerd.

Maar het laten bouwen van het boek op GitHub heeft ook nadelen:
- halffabricaten zijn zichtbaar
- je moet verbonden zijn met het internet
- de output is (veel) sneller te zien

Om het boek niet alleen online te bouwen en te zien, maar ook op je lokale computer te maken heb je het volgende nodig.

<label><input type="checkbox" class="box"> Python, bijv. via [conda](../Software/Anaconda.md).</input></label> 

<label><input type="checkbox" class="box"> Een integrated development environment (IDE) zoals [VSC](../Software/VSC.md).</input></label> 


<label><input type="checkbox" class="box"> De bestanden op de computer.</input></label> 

Wil je ook nog offline het boek kunnen bouwen, dan heb je ook nog nodig: 

<label><input type="checkbox" class="box"> De juiste software packages.</input></label> 

De eerste drie stappen hoef je maar eenmalig uit te voeren. Als je alle benodigdheden hebt geïnstalleerd, volstaat het een volgende keer om direct naar [stap 4](sec:lok) te gaan.

## Stap 1: Miniconda installeren
Hopelijk heb je Miniconda al geïnstalleerd, zo niet dan kun je [deze instructies](../Software/Anaconda.md) volgen. 

Heb je meer informatie nodig over Miniconda? Kijk dan eens [hier](https://teachbooks.io/learn-programming/install/python/miniconda.html).


## Stap 2: Installeren van een IDE
Om bestanden te kunnen bewerken en (een deel van) de output te kunnen zien, is het nodig om een IDE te installeren, bijvoorbeeld [VSC](../Software/VSC.md). Als je dat nog niet gedaan hebt, volg de instructies voor het installeren van VSC en de betreffende extensies.

Ook hier geldt, heb je meer informatie nodig, kijk dan [hier](https://teachbooks.io/learn-programming/install/ide/vsc.html).

## Stap 3: Installeren Jupyter-Book (optioneel)
Om de boeken lokaal te kunnen bouwen (van markdown files omzetten naar functionele HTML pagina's) heb je nog een aantal packages nodig, zie bijv. [Jupyter book](https://jupyterbook.org/en/stable/start/overview.html#install-jupyter-book). Dat kun je zelf handmatig doen, maar de Teachbooks tool voorziet daar ook in. Heb je dat nog niet gedaan, bekijk dan de sectie over de [requirements](seq:req) en volg de stappen die daar beschrijven staan. Dan ben je als het goed is klaar om ook op de eigen computer het boek te bouwen en bekijken.

(sec:lok)=
## Stap 4: Boek lokaal opslaan
Het boek staat nu alleen nog online, op GitHub. We moeten alles downloaden (clonen). Dat kan zoals [hier beschreven met VSC](https://learn.microsoft.com/en-us/azure/developer/javascript/how-to/with-visual-studio-code/clone-github-repository?tabs=activity-bar). Maar we kiezen er hiervoor om dat te doen via GitHub Desktop.

1. Open op GitHub de repository die je wilt klonen. Bovenin vind je de groene knop genaamd `<> code`

``` {figure} ./figures/gitdesktop1.png
```

2. Kopieer de link en open Github Desktop.

3. In GitHub Desktop, klik linksboven op `file` en vervolgens `Clone Repository`. Dat levert, als het goed is het volgende scherm op: 

``` {figure} ./figures/gitdesktop2.png
---
width: 50%
---
```

4. Klik vervolgens op URL, plak de gekopieerde link van de repository en specificeer waar de map naartoe gekloond moet worden. 

``` {figure} ./figures/gitdesktop3.png
---
width: 50%
---
```

De bestanden worden nu gekopieerd en je hebt een lokale (exacte) kopie van de repository.

## Stap 5: Aanpassing maken in VSC
1. Open VSC en open de folder waarin het *boek* staat. Je kunt dezelfde folder structuur herkennen die op GitHub stond. 

2. Open de file `overview.md` en pas deze naar eigen wens aan, bijvoorbeeld door de inhoud van een document dat je mee hebt genomen kopieert (let op! Headings en figuren worden natuurlijk niet meteen omgezet). Sla de bewerkingen op. Je kunt een preview krijgen van de output door op ![](./figures/vscpreview.PNG) te klikken.

```{figure} figures/vscpreviewscreen.png
---
width: 100%
name: fig_previewscreen
---
Bewerken in VSC, links de folder structuur, in het midden de code in de markdown file, rechts een preview van de output.
```

3. Navigeer in VSC naar de `some_content folder`, en creëer in die map een nieuwe markdown file (bijv. `nieuwe pagina.md`) (linksboven new file). Zet in de die file een titel (bijv. `# Mijn eerste hoofdstuk`).

Nu heb je een eigen hoofdstuk aangemaakt, maar die is nog niet in het boek opgenomen. Dat moet je melden in de table of contents. 

4. Zoek de `_toc.yml` file en open deze. Voeg het hoofdstuk toe (`- file: some_content/nieuwe_pagina`). Let op, je moet op de juiste wijze inspringen anders krijg je foutmeldingen.

```{figure} figures/toc.PNG
---
width: 50%
name: fig_toc
---
Het nieuwe hoofdstuk is toegevoegd in de table of contents
```

5. Sla alle aangepaste documenten op. (`ctrl + s`)

6. Laat een van de workshopleiders even controleren.

## Stap 6: Synchroniseren met GitHub
Je hebt nu aanpassingen gedaan maar die staan nog niet op GitHub. Ga weer terug naar GitHub Desktop. Daar zie je de aangepaste bestanden. Geef een bijbehorende summary in de tekstbalk links onder, druk op `commit to main` en vervolgens op `Push origin`. De bestanden worden nu geüpload naar GitHub alwaar het boek weer gebouwd wordt. 

```{figure} figures/gitdesktopedits.PNG
---
width: 80%
---
Alle aangepaste bestanden zie je links in GitHub Desktop.
```

```{note}
Al bovenstaande stappen kunnen ook via de terminal of via VSC, maar dat vraagt net iets meer uitleg.
```

Bekijk online het resultaat van je aangepaste boek.

````{tip}
:class:dropdown
Een goede aanpak in werken met GitHub is als je weer verder werkt met aan je project je eerst een `pull` doet, het werk van eventuele collega's die aan hetzelfde wordt dan gekopieerd. Na het werken `commit` en `push` je je wijzigingen naar GitHub. Als de collega's op dezelfde manier werken, heeft iedereen altijd de laatste versie.

```{note}
Een stap verder is dat iedereen werkt in een eigen `branche` en deze later `merged` met de `main branch`  
```
````

## Stap 7: Het lokaal bouwen van het boek (optioneel)
Met behulp van `conda prompt` kunnen we het boek ook lokaal bouwen. 

1. Open conda prompt en navigeer naar de folder waar je `book` folder staat.

2. Type `jupyter-book build book` en druk enter. Nu is het proces van het bouwen van het boek te zien - eventueel met errors. Het resultaat vind je in de folder `books/_build/html`. 

De eerste keer duurt het bouwen even, alle bestanden moeten immers gemaakt worden. Als je aanpassingen doet en bovenstaande wijze weer toepast is het boek sneller gebouwd. Er wordt namelijk alleen gekeken naar welke bestanden aangepast zijn. Wil je toch alle pagina's laten herbouwen, type dan `jupyter-book build book --all`. 

Meer over de commando's voor het lokaal bouwen vind je [hier.](https://jupyterbook.org/en/stable/start/build.html#build-your-books-html)

```{exercise} Lokaal bouwen
Voer de bovenstaande stappen uit om het boek lokaal te bouwen. Bekijk de output.
```
