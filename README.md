#-AUTOR-#
#Autorem skryptu jest iStworus, modyfikacja dozwolona, zakaz rozpowszechniania bez informacji o autorze!
#YouTube: youtube.com/istworus | Prosze o lajka, subskrybcje jeśli Ci się podoba :D
#-AUTOR-#
 
#-FRAGMENT INFORMACYJNY-#
#Skrypt testowany byl na najnowszej wersji Skript: https://github.com/SkriptLang/Skript/releases
#Zainstalowane dodatki na serwerze: SkQuery, skUtilities, skRayFall, Skellet //Jesli cos nie dziala sproboj, zainstalowac te dodatki..
#-FRAGMENT INFORMACYJNY-#
 
#-PERMISJE-#
#istwfarmer.give -> Dostep do komeny /dajfarmer
#-PERMISJE-#
 
command /dajfarmer [<text=help>] [<number=1>]:
	permission: istwfarmer.give
	trigger:
		if arg 1 is "help":
			send "&cPoprawne uzycie: /dajfarmer <nick> <ilosc>"
			stop
		set {_x} to arg-1 parsed as player
		set {_y} to arg-2
		give {_y} of gold ore named "&fâ—Ź &eSand Farmer &fâ—Ź" to {_x}
		give {_y} of coal ore named "&fâ—Ź &5Boy Farmer &fâ—Ź" to {_x}
		give {_y} of iron ore named "&fâ—Ź &aKopacz fosy &fâ—Ź" to {_x}
 
 
on script load:
    register new shaped recipe for gold ore named "&fâ—Ź &eSand Farmer &fâ—Ź" using sand, sand, sand, sand, golden apple item, sand, sand, sand, sand
 
on place of gold ore:
    if player's tool is gold ore named "&fâ—Ź &eSand Farmer &fâ—Ź":
        loop blocks under event-block:
            if loop-block is bedrock:
                stop
            set loop-block to sand
 
on script load:
    register new shaped recipe for coal ore named "&fâ—Ź &5Boy Farmer &fâ—Ź" using obsidian, obsidian, obsidian, obsidian, golden apple item, obsidian, obsidian, obsidian, obsidian
 
on place of coal ore:
    if player's tool is coal ore named "&fâ—Ź &5Boy Farmer &fâ—Ź":
        loop blocks under event-block:
            if loop-block is bedrock:
                stop
            set loop-block to obsidian
 
on script load:
    register new shaped recipe for iron ore named "&fâ—Ź &aKopacz fosy &fâ—Ź" using cobblestone, cobblestone, cobblestone, cobblestone, golden apple item, cobblestone, cobblestone, cobblestone, cobblestone
 
on place of iron ore:
    if player's tool is iron ore named "&fâ—Ź &aKopacz fosy &fâ—Ź":
        loop blocks under event-block:
            if loop-block is bedrock:
                stop
            set loop-block to air
