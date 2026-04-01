# RAENIR - prototyp D&D/deck stolní hry

## ÚVOD

> help: pull first, push last, tag pouze na verzování minor jinak commit
> 
> git add .
> 
> git commit -m "verze"
> 
> git tag x.x.0 -m "název"
> 
> git push --tags
> 
> Poznámky a TODO jsou označny `takto`

#### Historie verzí:

###### v0.0.1

- Vytvořen první dokument pravidel

###### v0.0.2

- Vytvořena kostra pravidel

---

## PRAVIDLA

#### Cíl

Hra s deckbuilding kartami a vyprávěným příběhem podobně jako v D&D, kde se vypravěč aktivněji účastní soubojů proti ostatním hráčům a zároveň jim vede hru.

#### Vypravěč

Vede příběh, situace a ovládá nepřátele. Vytváří konflikty a udává následky. Hráči reagují pomocí roleplaye, v případě konfliktu vypravěč přechází do "režimu hráče" a vede souboj.

Vypravěč má tedy dvojí roli. Jednak vede příběh a jednak řídí obtížnost a tempo hry. Neměl by se snažit hráče „porazit“, ale vytvářet zajímavé situace.
Důležité je, že má nástroje, jak reagovat na hráče i mimo čistý boj. Může upravit svět, změnit reakce NPC, přidat postih ve formě negativního traitu a nebo naopak přidat pozitivní trait za kvalitní řešení situací stran hráčů. Má také možnost rozdávat speciální traity za určité milníky ve výpravě družiny nebo skupinové a dočasné traity.

#### Postavy

Nejsou definované a tvořené jako v klasickém D&D, ale pomocí (pasivních) traitů (pozitivní/negativní/speciální). Tyto traity - malé kartičky - ovlivňují chování postavy vůči světu a naopak. Jsou jak soubojové tak příběhové.

#### Souboje

Jsou vedeny kartami, které si do balíčku skládají hráči sami (tzv. deckbuilding). Hráči bojují proti vypravěčovi, který má pro každý encounter připravenou speciální kartu protivníka, která má efekty a fáze dle tabulky. Souboj probíhá po kolech, dokud jedna strana nevyhraje nebo se situace nevyřeší jinak.

###### Iniciativa

Začínají určením iniciativy. Každý hráč hodí kostkou a přičtou se bonusy z traitů (pakliže nějaké jsou). Hráč s největší iniciativou lízne v prvním kole o 1 kartu navíc. Během souboje se nemění (pakliže speciální karta neřekne jinak).

###### Nepřátelé

Jednodušší než hráči. Nemají plnohodnotný balíček. Všichni nepřátelé mají stejné základní karty. Na každou fázi (po ukončení jednotlivých tahů všech hráčů - kol) útočí specifickými schopnostmi ze své karty dle `tabulky`.

###### Tah

Ve svém tahu hráč lízne `X` karet ze svého balíčku do ruky a zahraje `X` počet z nich. Vyhodnotí jejich efekt, případně hází kostkami. Na konci svého tahu musí hráč odhodit všechny (pakliže trait neříká jinak) své nepoužité karty do odhazovacího balíčku. Pakliže hráč svůj příští tah nemůže líznout `X` karet, odhodí vše do svého balíčku a zamíchá ho. Poté hraje vypravěč za nepřítele.

Vypravěč se hráče snaží porazit dle své speciální karty nepřítele a pokud se mu to podaří, přichází porážka hráče.

###### Porážka

Porážka hráče znamená, že dostane negativní nebo speciální trait (zvolený dle tabulky encountrů na kartě protivníka). Ve svém tahu takový hráč může hrát pouze jednu kartu a to kartu typu GAMBLE. Nesmí lízat nové karty. Pakliže padne celá výprava mohou si hráči zvolit ukončení hry nebo "vzkříšení".

* **Vzkříšení**: Při vzkříšení hráči ožijí na posledním záchytném bodě.
  
  + **Záchytný bod**: Vytváří hráči dle "přesvědčení" (povinný speciální trait) buď "obětováním" nebo "rozjímáním". Hráči, který takový bod vytvořil se přidá dočasný negativní trait (tento má vypravěč u sebe).
    
    
+ **Shopnost vypravěče PÁKA**: Pakliže má vypravěč na své kartě schopnost Páky, může ji ve svém tahu aktivovat. V tom případě se skupina musí vzdát, jinak poražená postava zemře nadobro. Vypravěč tuto schopnost využívá jako RP nástroj v případě nevyváženého souboje nebo postupu v příběhu.

###### Vítězství

Vítězství znamená, že souboj přežil alespoň jeden hráč. Hráči místo klasických expů dostanou dočasný skupinový pozitivní trait "Euforie" a body znalostí.

* **Body znalostí**: Mohou hráči proměnit v deckbuildingu za nové karty nebo se nějakých karet z balíčku zbavit.

###### Následky a postup

Po každém souboji nebo důležité události dochází k posunu. Hráči mohou získat nové karty, upravit balíček nebo získat traity. Stejně tak mohou nést následky svých rozhodnutí.

#### Karty a balíčky

Každý hráč má vlastní balíček o 15ti kartách. Karty reprezentují akce v boji (útoky, obrana, efekty). Hráč si na začátku svého tahu líže max. do 5ti karet v ruce a z nich hraje. 

- **Repurposed**: Každá nepoužitá karta co hráčovi na konci tahu (před odhozením do balíčku) zůstane v ruce, dá +`1` dmg na JEDNU útočnou kartu příštího tahu.

Každá karta má pevně daný základní efekt (útok, obrana, efekt (heal apod.)). Některé karty mají i hod kostkou. Kostka ovšem neurčuje zda akce uspěje, ale modifikuje její sílu nebo efekt. Existují tedy riskantní a stabilní karty a hráč se musí rozhodnout, zda bude chtít větší bonus při hodu kostkou a nebo stabilní base staty.

###### Hromadný balík - deckbuilding

**Krok 1 - Draft karet**

Vypravěč lízne X počet hráčů + 10 karet z hromadného balíku karet.
Hráči si berou v pořadí iniciativy souboje po jedné, dokud každý nemá 2 nové karty. Zbytek se vrátí na dno balíku.

**Krok 2 - Body znalostí**

Každý hráč dostane 2 body. Vypravěč může přidat 1 bod za výjimečný RP.

Utratit je lze ihned a nebo si je nechat na později:

- Extra karta z balíku navíc = 3 body (Lízne 3 karty a vybere 1 kartu)

- Odstranění karty z vlastního balíčku = 1 bod



#### Kostky

Kostky slouží jako variace výsledku. Standardně se používá d6, ale může se objevit také d12. `Zatím jsem se nerozhodl, zda se převádí na bonus nebo přímo z toho co pande.`

Používají se taktéž jako vypravěčův nástroj pro rozhodnutí a souboje. `Toto bude potřeba lépe specifikovat (např. hráč má trait na přesvědčování - háže k tomu vypravěč?)`

#### Průběh hry

Hra se stříédá mezi vyprávěním a mechanikou. Vypravěč popisuje situaci, ve které se hráči nachází, ti reagují slovně a přitom mohou využít své traity. Pokud dojde ke konfliktu, přechází se do souboje, který je řízen kartami a kostkami. Výsledek se promítne do příběhu a zlepšování postav a hra pokračuje dál.

---

## KARTY

<img title="" src="file:///C:/Users/alfre/AppData/Roaming/marktext/images/2026-04-01-04-07-27-image.png" alt="" width="475">

#### Útočné

#### Obranné

#### Speciální

#### Záchranné

###### GAMBLE

- Max. 1x v balíčku

- Použitelná pouze po porážce, ve svém tahu

- Hod d12: 9-12 -> návrat do hry

- Návrat = 0 životů, hraje normálně, další porážka = porážka bez GAMBLE šance

#### Karty protivníka

<img src="file:///C:/Users/alfre/AppData/Roaming/marktext/images/2026-04-01-04-07-59-image.png" title="" alt="" width="545">

---

## TRAITY

<img title="" src="file:///C:/Users/alfre/AppData/Roaming/marktext/images/2026-04-01-04-06-54-image.png" alt="" width="544">

#### POZITIVNÍ

###### Euforie

#### NEGATIVNÍ

#### SPECIÁLNÍ