# De statistieken in het WK voetbal
Link naar GitHub page: https://deanvos.github.io/InfoVis/docs/home.html

## Introduction
In deze data story project worden de datasets van het Wereldkampioenschap (WK) van 2018 en 2022 geanalyseerd. Het WK voetbal is een van de meest prestigieuze toernooien in de wereld die maar één keer in de vier jaar wordt georganiseerd. In het project worden de datasets aandachtig geanalyseerd en vergeleken met elkaar om interessante bevindingen te verkrijgen. Met deze twee datasets kunnen we interessante visualisaties creëren om vervolgens inzicht te krijgen op bijvoorbeeld de prestaties en trends tussen deze twee toernooien. In deze data story project zullen we eerst het onderwerp beschrijven met de bijbehorende perspectieven. Vervolgens worden de datasets beschreven, daarnaast wordt er beschreven hoe de datasets zijn bewerkt en gefilterd. In het middendeel van de data story project worden er meerdere visualisaties gegeven die elk een eigen punt en argument illustreren. Ten slotte wordt er in de afsluiting een reflectie gegeven met de verkregen feedback van de TA’s  en andere studenten. In de afsluiting wordt ook de werkdistributie in de groep vermeld.

## Topic description
In de data story project staat het vergelijken van statistieken en prestaties van verschillende teams centraal. De datasets die worden gebruikt is de dataset van het WK voetbal van 2018, en de dataset van het WK voetbal 2022. Door de datasets te analyseren en verschillende visualisaties te maken is het mogelijk om te ontdekken welke factoren invloed hebben op het succes in het WK voetbal. De datasets bevatten heel veel variabelen en mogelijke invalshoeken. Niet alleen statistieken zoals schoten op doel of balbezit, maar ook gegevens zoals het aantal lange ballen, aantal pogingen/gelukte liniedoorbraken, etc.

## Dataset description and preprocessing
#### Dataset WK 2018
Link: https://www.kaggle.com/datasets/shikhar07/fifa-2018-dataset

Deze dataset bevat informatie over de prestaties van voetbalteams op het WK voetbal van 2018. Hierbij kan er aan de hand van 27 verschillende variabelen/kolommen gekeken worden naar de prestaties van de teams. Zo wordt de winnaar, het balbezit en het aantal gele kaarten bijvoorbeeld benoemd. Daarnaast zijn er heel veel andere variabelen die we kunnen vergelijken, zoals op balbezit en gele/rode kaarten, schoten en doelpunten etc.

#### Dataset WK 2022
Link: https://www.kaggle.com/datasets/die9origephit/fifa-world-cup-2022-complete-dataset

Deze dataset bevat data over alle gespeelde voetbalwedstrijden die plaats hebben gevonden tijdens het WK 2022 in Qatar. Er valt bijvoorbeeld informatie te vinden over de landen die tegen elkaar hebben gespeeld, de eindscore, tijdsduur en vele andere variabelen. Niet alleen statistieken zoals schoten op doel of balbezit, maar ook gegevens zoals aantal lange ballen, aantal pogingen/gelukte liniedoorbraken, etc.

## Perspectives
#### Deel 1
In het eerste perspectief gaan we kijken naar de intensiviteit van de WK wedstrijden. 'Wordt er in het ene WK ruiger gespeeld dan in het andere WK?' of 'Wordt er in de knock-outfase feller gespeeld dan in de groepsfase?' zijn vragen die bij ons opkomen bij dit perspectief. Bij de eerste stelling gaan we  vooral variabelen analyseren zoals overtredingen en gele/rode kaarten. 
Perspectief 1: Tijdens het WK van 2022 zijn er minder kaarten gegeven dan in het WK van 2018 doordat spelers zich bewust zijn geworden van de VAR en strenge scheidsrechters, en daardoor voorzichtiger en bewuster zijn gaan spelen.

Om dit te analyseren gaan we eerst kijken naar de cijfers van het aantal overtredingen per wedstrijd. Dit is mooi weer te geven in een boxplot, die geeft van het WK van 2018 en 2022 de statistieken wat betreft het aantal overtredingen per jaar. De boxplot in figuur 1 geeft bijvoorbeeld het maximale en minimale aantal overtredingen per wedstrijd, het gemiddelde, etc. (als deze plot af is kunnen we beargumenteren dat het aantal overtredingen tussen de 2 WK's gelijk of verschillend is.)

Nu we een inzicht hebben van hoeveel overtredingen er waren in het WK van 2018 en in het WK van 2022, gaan we nu analyseren hoeveel kaarten er zijn gevallen in de twee toernooien. Figuur 2 laat zien dat er nauwelijks een verschil is te zien in het aantal gegeven kaarten. 

Perspectief 2: In de knock-outfase van het toernooi zijn er meer overtredingen en kaarten omdat teams feller spelen.
Om dit te onderzoeken gaan we kijken naar het aantal overtredingen per groep/ronde. Om dit te visualiseren hebben we een bar chart gemaakt (figuur 3), waarmee elke staaf een ronde/groep representeert. Je ziet dat er in de kwartfinales en in de finale flink wat kaarten zijn uitgedeeld, tot drie keer toe zijn er 45+ kaarten uitgedeeld. 

(Nog 1 plot/visualisatie zou dit argument kunnen versterken, want het lijkt erop dat er in de knock-outfases meer kaarten worden gegeven, maar nog een chart zou dit argument/visualsatiecomponent helemaal compleet maken!) 

Perspectief 3: Teams met het meeste aantal passes hebben een grotere kans op het maken van doelpunten.

## Schetsen en plannen voor de rest van de visualisaties
- Een plot die lijkt op figuur 4, maar dan met doelpunten en passnauwkeurigheid. Deze visualisatie wordt in een andere chart gemaakt dan de variant in figuur 4. Deze grafiek zal hetzelfde doen als de grafiek hiervoor en zal makkelijk kunnen visualiseren wat de impact is van de nauwkeurigheid van de passes op het aantal doelpunten die gescoord worden. Deze zullen ook voor beide wk’s gemaakt worden, zodat ook hier de verschillen bekeken kunnen worden. Ook zou eventueel de Pearson’s R berekend kunnen worden. Ook zou er nog gekeken kunnen worden naar een andere vergelijkbare grafiek, maar dit hangt af van het resultaat van de visualisatie.
- Een mooie parralel plot die 4/5 variabelen meet en dan kunnen we kijken welke situaties het beste zijn voor goals (zoals de laatste opdracht van assignment 2). Met deze plot kunnen we dan beargumenteren welke (samenhang van) situaties geschikt is voor veel doelpunten.