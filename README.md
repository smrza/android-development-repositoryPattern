Implementace Repository Pattern
======================
* podstatou cvičení je implementace aplikace dle tutoriálu: https://developer.android.com/codelabs/kotlin-android-training-repository/#0 
* Architektura aplikace využívá třídu Repository, skrze kterou získává ViewModel data
* Repository může získávat data buď z SQLite (Room) nebo ze sítě (Retrofit)
  * V aplikaci jsou datové entity reprezentovány následujícími třídami:
  * datová entita načtená ze sítě je označena jako tzv. NetworkModel
  * datová entita získaná z SQLite databáze je označena jako tzv. DatabaseModel
  * datová entita se kterou reálně pracuje mobilní aplikace a je výstupem z Repository je označena jako tzv. DomainModel
  * výše uvedená architektura umožňuje jednoduché mapování vlastností datových entit získaných ze sítě na datové entity databázové a dále využívané přímo v mobilní aplikaci
  * aby byla zajištěna dostupnost dat i v případě offline, ViewModel pracuje s doménovým modelem, který je vždy naplněn z databáze... je-li dostupná komunikace se sítí, je databázový model aktualizován síťovým modelem
