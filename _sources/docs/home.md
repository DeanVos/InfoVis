# De statistieken in het WK voetbal
Link naar GitHub page: https://deanvos.github.io/InfoVis/docs/home.html

## Introduction
In deze data story project worden de datasets van het Wereldkampioenschap (WK) van 2018 en 2022 geanalyseerd. Het WK voetbal is een van de meest prestigieuze toernooien in de wereld die maar één keer in de vier jaar wordt georganiseerd. In het project worden de datasets aandachtig geanalyseerd en vergeleken met elkaar om interessante bevindingen te verkrijgen. Met deze twee datasets kunnen we interessante visualisaties creëren om vervolgens inzicht te krijgen op bijvoorbeeld de prestaties en trends tussen deze twee toernooien. In deze data story project zullen we eerst het onderwerp beschrijven met de bijbehorende perspectieven. Vervolgens worden de datasets beschreven, daarnaast wordt er beschreven hoe de datasets zijn bewerkt en gefilterd. In het middendeel van de data story project worden er meerdere visualisaties gegeven die elk een eigen punt en argument illustreren. 

## Topic description
In de data story project staat het vergelijken van statistieken en prestaties van verschillende teams centraal. De datasets die worden gebruikt is de dataset van het WK voetbal van 2018, en de dataset van het WK voetbal 2022. Door de datasets te analyseren en verschillende visualisaties te maken is het mogelijk om te ontdekken welke factoren invloed hebben op het succes in het WK voetbal. De datasets bevatten heel veel variabelen en mogelijke invalshoeken. Niet alleen statistieken zoals schoten op doel of balbezit, maar ook gegevens zoals het aantal lange ballen, aantal pogingen/gelukte liniedoorbraken, etc.

## Dataset description and preprocessing
#### Dataset WK 2018
Link: https://www.kaggle.com/datasets/shikhar07/fifa-2018-dataset

Deze dataset bevat informatie over de prestaties van voetbalteams op het WK voetbal van 2018. Hierbij kan er aan de hand van 27 verschillende variabelen/kolommen gekeken worden naar de prestaties van de teams. Tijdens het WK van 2018 deden er 32 landen mee, waarvan de wedstrijdinformatie verdeeld is over 128 rijen. De gegevens zijn georganiseerd van eerste ronde tot laatste ronde. Zo wordt de winnaar, het balbezit en het aantal gele kaarten bijvoorbeeld benoemd. Daarnaast zijn er heel veel andere variabelen die we kunnen vergelijken, zoals op balbezit en gele/rode kaarten, schoten en doelpunten etc.

In de visualisaties zijn verschillende variabelen gebruikt uit deze dataset. De variabelen ‘aantal overtredingen’, ‘gele kaart’, ‘rode kaart’ en ‘gele & rode kaart’ komen vaak voor. Al de vier variabelen zijn discrete variabelen (ordinale schaal). Naast deze variabelen zijn de gebruikte variabelen ‘pasen’, ‘goals’, ‘pogingen’ en ‘% balbezit' ook discreet (ratioschaal). 

#### Dataset WK 2022
Link: https://www.kaggle.com/datasets/die9origephit/fifa-world-cup-2022-complete-dataset

Deze dataset bevat data over alle gespeelde voetbalwedstrijden die plaats hebben gevonden tijdens het WK 2022 in Qatar. Tijdens het WK van 2022 deden er, net zoals in 2018, 32 landen mee. De dataset bevat 64 rijen, waar informatie valt te vinden over de landen die tegen elkaar hebben gespeeld, de eindscore, tijdsduur en vele andere variabelen. De gegevens zijn georganiseerd van eerste ronde tot laatste ronde. Er valt bijvoorbeeld informatie te vinden over de landen die tegen elkaar hebben gespeeld, de eindscore, tijdsduur en vele andere variabelen. Niet alleen statistieken zoals schoten op doel of balbezit, maar ook gegevens zoals aantal lange ballen, aantal pogingen/gelukte liniedoorbraken, etc.

#### Preprocessing
Preprocessing: 
Stap 1: De dataset van het WK van 2018 heeft de kolommen: ‘Team’ en ‘Opponent’ om de teams mee aan te duiden. De dataset van het WK van 2022 heeft de kolommen: ‘team1’ en 'team 2' om de teams aan te duiden. Allereerst hebben we de kolomnamen van de 2018 dataset veranderd van ‘Team’ naar ‘team1’ en ‘Opponent’ naar ‘team2’.
- df_2018 = df_2018.rename(columns = {'Team': 'team1'})
- df_2018 = df_2018.rename(columns = {'Opponent': 'team2'})

Stap 2: Nu hebben deze twee kolommen in beide datasets dezelfde naam, op deze kolommen hebben we de datasets samengevoegd.
- merged_df = df_2022.merge(df_2018, on = ['team1', 'team2'], how = 'outer')



## Perspectives
#### Deel 1
In het eerste perspectief gaan we kijken naar de intensiviteit van de WK wedstrijden. 'Wordt er in het ene WK ruiger gespeeld dan in het andere WK?' of 'Wordt er in de knock-outfase feller gespeeld dan in de groepsfase?' zijn vragen die bij ons opkomen bij dit perspectief. Bij de eerste stelling gaan we vooral variabelen analyseren zoals overtredingen en gele/rode kaarten. Dit perspectief wordt opgedeeld in twee stellingen.

- Perspectief 1: Tijdens het WK van 2022 zijn er minder kaarten gegeven dan in het WK van 2018 doordat spelers zich bewust zijn geworden van de VAR en strenge scheidsrechters, en daardoor voorzichtiger en bewuster zijn gaan spelen.

Om dit te analyseren gaan we eerst kijken naar het totaal aantal overtredingen per WK. Als er in het WK van 2022 minder intensief en ruig wordt gespeeld, zullen er vanzelfsprekend ook minder overtredingen zijn gemaakt. In figuur 1 is te zien dat er in het WK van 2018 iets meer overtredingen zijn gemaakt dan in het WK van 2022, 134 overtredingen meer om precies te zijn. Echter geeft figuur 1 niet goed de trends en ontwikkelingen weer wat betreft het aantal overtredingen per wedstrijd. Om te kijken of de trends wat betreft het aantal overtredingen per WK te vergelijken, gaan we kijken naar de trend van het aantal overtredingen per wedstrijd. Dit is mooi weer te geven in een box plot, die geeft van het WK van 2018 en 2022 de statistieken wat betreft het aantal overtredingen per WK. De box plot in figuur 2 geeft bijvoorbeeld het maximale en minimale aantal overtredingen per wedstrijd, het gemiddelde, de kwartielen, etc. Figuur 2 geeft goed weer dat er in het WK van 2018 meer overtredingen zijn gemaakt. Het gemiddelde is hoger in 2018, daarnaast zijn de kwartielen en 'upper fence' hoger in 2018. Echter kan je ook zien dat er in het WK van 2022 drie outliers zijn (de drie blauwe stipjes boven in de grafiek). Deze outliers zijn te verklaren, want dit zijn de felle finale wedstrijden, de twee kwartfinales (punt 46 en 48) en de finale (punt 45) om precies te zijn.

Nu we een inzicht hebben van hoeveel overtredingen er waren in het WK van 2018 en in het WK van 2022, gaan we nu analyseren hoeveel kaarten er zijn gevallen in de twee toernooien. Echter figuur 3 laat zien dat er nauwelijks een verschil is te zien in het aantal gegeven kaarten. Het aantal gegeven rode kaarten (4) zijn gelijk en in tegenstelling met de gemaakte overtredingen, zijn er in het WK van 2022 meer gele kaarten gegeven dan in het WK van 2018. Dus met deze bevindingen kunnen we concluderen dat er in het WK van 2018 meer overtredingen zijn gemaakt (over het algemeen en per wedstrijd) dan in het WK van 2022. Echter heeft dit geen invloed gehad op het aantal gegeven kaarten. Want in het WK van 2022 zijn er 134 minder overtredingen gemaakt dan in het WK van 2018, maar in het WK van 2022 zijn er wel iets meer kaarten gegeven. Met deze bevindingen kunnen we de eerste stelling ontkrachten. Hoewel er 2022 minder overtredingen zijn gemaakt, zijn er wel meer kaarten gegeven dan in 2018.

- Perspectief 2: In de knock-outfase van het toernooi zijn er meer overtredingen omdat teams feller spelen.

Om deze stelling te onderzoeken gaan we kijken naar het aantal overtredingen per groep/ronde in het WK van 2022. In de knock-outfase gaan we niet kijken naar het aantal overtredingen van de 'Play-off for third place'. Deze wedstrijd wordt gezien als troostfinale, aangezien teams minder fanatiek spelen omdat ze al zijn uitgeschakeld voor de finale. Dit leidt tot een wedstrijd waarin twee gedemotiveerde teams spelen. Om deze stelling te visualiseren hebben we een bar chart gemaakt (figuur 4), waarmee elke staaf een ronde/groep representeert. Elke staaf is opgedeeld in een aantal vlakken, elke vlak representeert een wedstrijd uit de groep/fase. Je ziet dat er in de kwartfinales en in de finale flink wat overtredingen zijn gemaakt, tot drie keer toe zijn er 45+ kaarten uitgedeeld. 

Maar figuur 4 laat niet duidelijk zien of er nou in de knock-outfase meer overtredingen zijn gemaakt dan in de groepsfase. Om dit beter te analyseren hebben we figuur 5 gemaakt. Figuur 5 is een histogram die iets meer de diepte in gaat dan figuur 4, want figuur 5 visualiseert het gemiddelde aantal overtredingen per wedstrijd per ronde/fase. Zo kan je goed de trends zien wat betreft het gemiddelde aantal overtredingen per wedstrijd per ronde. Daarnaast is er een gestippelde rode lijn die het gemiddelde aantal overtredingen per wedstrijd van het gehele toernooi representeert. Van de acht groepsfases komen alleen groep A en groep C iets boven de gestippelde rode lijn (het gemiddelde aantal overtredingen per wedstrijd van het hele toernooi). Als we kijken naar de knock-outfase (en de 'Play-off for third place' achterwege laten), zien we dat twee van de vier rondes flink boven de gestippelde lijn komen (de kwartfinale en de finale). Vooral in de finale is het er ruig aan toe gegaan, daar zijn er maar liefst 45 overtredingen gemaakt. Dus met deze figuren kunnen we concluderen dat er in de knock-outfase meer overtredingen zijn gemaakt dan in de groepsfase. In de groepsfase komen maar 2/8 groepen boven het gemiddelde, terwijl er in de knock-outfase 2/4 fases boven het gemiddelde komen. Dit is ook te verklaren als je kijkt naar de fase van het toernooi, in de knock-outfase is het alles of niets. Als je verliest, lig je uit het toernooi.

#### Deel 2

#### Deel 3
In het derde perspectief wordt er onderzocht over de traditionele grootmachten in zowel 2018 als 2022 inderdaad meer scoren dan de rest van de teams. Verschillende factoren hebben hier mee te maken, bijvoorbeeld het aantal schoten op het doel en het balbezit. Als er gekeken wordt naar het balbezit, dan zou men denken dat meer balbezit verbonden is met meer doelpunten. Hetzelfde zou gezegd kunnen worden over het aantal schoten op het doel, wat in figuur 5 aan de orde komt. 

- Perspectief : De traditionele grootmachten Frankrijk, Argentinië en Brazilië scoren meer door een betere training, een hogere prestatiedruk en betere coaching. 

Om rekening te houden met alle traditionele grootmachten en resterende teams in de figuren zou niet praktisch zijn. Hierom representeren Frankrijk, Argentinië en Brazilië de traditionele grootmachten en representeren Senegal, Tunesië en Denemarken de rest van de teams.
Als er gekeken wordt naar figuur 5, dan valt er duidelijk te zien dat de traditionele grootmachten inderdaad meer hebben gescoord dan de rest van de teams. Aan de landen Senegal, Tunesië en Denemarken valt te zien dat zij minder vaak de poging hebben gekregen om op het doel te schieten, wat uiteindelijk ook voor minder doelpunten heeft gezorgd. Als er gesproken wordt over een betere training, een hogere prestatiedruk en betere coaching, dan zou er zowel in 2018 als 2022 meer gescoord moeten worden door de traditionele grootmachten, wat zoals eerder genoemd, inderdaad ook het geval is. 
