# Raentir — briefing pro Claude Chat

Toto je instrukční dokument pro pokračování vývoje stolní hry Raentir v Claude Chat.

---

## Kdo jsem a co děláme

Jmenuji se Sundeon. Navrhuji originální stolní hru **Raentir** — mix D&D a deckbuildingu. Komunikujeme česky. Pomáháš mi navrhovat herní systém, karty a pravidla.

---

## Jak se mnou pracovat

- Piš krátce a věcně. Žádné AI frázování, žádné em-dash (—).
- Pravidla a drafty píšeš do separátních souborů nebo bloků — já si přebírám co chci.
- Neupravuj můj hlavní dokument bez instrukce.
- Poznámky/TODO označuji `takto`.
- Pokud navrhneš mechaniku, dej mi na výběr varianty nebo se ptej — nerozhoduj za mě.

---

## Struktura hry

**Raentir** je D&D-like deckbuilding s vypravěčem. Svět: fantasy/sci-fi, 80/20.

- **Vypravěč** vede příběh a ovládá nepřátele. Dvojí role — příběh + souboj. Nesnaží se hráče porazit, ale vytvářet situace.
- **Postavy** jsou definované traity (ne statblocks jako v D&D).
- **Souboje** jsou kartové. Hráči bojují jako tým proti kartě nepřítele s fázemi.
- **Čas je nepřítel** — souboj eskaluje přirozeně každým kolem (fáze nepřítele).

---

## Soubojový systém (aktuální stav)

### Volba tahu

Každý tah hráč volí:

- **Střet** — lízne 5 karet z Variabilního balíčku, nepřítel útočí
- **Odpoutání** — nelíže karty, může hrát jen Speciální/Záchranné z Konstantního balíčku, nepřítel neútočí, může se přesouvat nebo dělat RP akce

### Průběh tahu (Střet)

1. Volební fáze (Střet nebo Odpoutání)
2. Akční fáze — hráč hraje karty, efekty ihned
   - Obranné karty se NEHRAJÍ v akční fázi — drží se na reaktivní obranu
3. Fáze nepřítele — DM oznámí damage, hráč **reaktivně** zahraje obranu (nebo nechá pro Repurposed)
4. Repurposed — za každou nepoužitou odhozenou kartu = 1 žeton, žetony = +1 dmg na útočné karty, resetují se po souboji

### Timing efektů

Efekty platí od aktuálního tahu. „Nepřítel má -2 útok" = platí hned v téže fázi nepřítele.

### Zóny boje

- **Blízko** — max 3 nepřátelé, jejich damage se **sečte do jednoho čísla**, hráč se brání jednou reakcí. Hráč volí primární cíl pro útok.
- **Daleko** — nepřátelé neútočí, pokud nemají střelecký útok. Střelecký útok míří na hráče **právě na tahu** (ne všechny), damage se přičte k blízkému damage.
- Rozmístění určuje DM.
- **Přesun** = tah v Odpoutání. Hráč popíše jak se přesouvá, DM schválí nebo upraví.
- **Útěk z boje** = opustit zónu Daleko, musí celá družina najednou.

### Více nepřátel

- Každý má vlastní kartu s fázemi.
- Fáze se posouvají **společně** po každém kole.
- Damage se cílí na jednoho konkrétního nepřítele (pokud karta neříká jinak).
- Padlý nepřítel odpadne, zbylí pokračují.

### Balíčky

- **Konstantní balíček (Spell bar)** — 5 karet vybraných před soubojem (při odpočinku). Vždy k dispozici. Po zahrání se vrátí zpět do Konstantního balíčku (ne do odhazu). Každá karta má **limit použití za souboj** (napsaný na kartě) — po vyčerpání se otočí rubem nahoru. Silné karty = nízký limit (1–2), utility = vyšší (3+).
- **Variabilní balíček** — zbytek karet, lízá se z něj normálně (5 karet ve Střetu).
- **Zahrané karty** — separátní hromádka během tahu, po Repurposed jdou do odhazu.
- Konstantní balíček se skládá mimo souboj, během souboje se nemění.

### Iniciativa

- Každý hodí d6 + bonusy z traitů. Remíza = reroll.
- Nejvyšší iniciativa = +1 karta v prvním kole.
- Nepřátelé se v iniciativě neřeší.

### Porážka hráče

- HP na 0 = poražen. Dostane negativní/speciální trait.
- Poražený nesmí lízat, může jen hrát „Kostky osudu".
- Spoluhráči ho mohou zachránit Záchrannou kartou.
- Celá výprava padne = konec nebo Vzkříšení (záchytný bod, negativní trait tomu kdo ho vytvořil).
- **PÁKA** = schopnost na kartě nepřítele. DM ji aktivuje: vzdejte se nebo padlý zemře nadobro.

### Vítězství

- Přežije aspoň 1 hráč = výhra. Dočasný trait „Euforie" + body znalostí.

---

## Karty — typy

| Typ       | Barva   | Efekt                                                   |
| --------- | ------- | ------------------------------------------------------- |
| Útočné    | Červená | Damage nepříteli, base hodnota, boost Repurposed žetony |
| Obranné   | Modrá   | Snižují incoming damage, reaktivní (ne v akční fázi)    |
| Speciální | Žlutá   | Buff/debuff/manipulace, hratelné ve Střetu i Odpoutání  |
| Záchranné | Zelená  | Heal, pomoc poraženým, hratelné ve Střetu i Odpoutání   |
| Třídní    | Bílá    | Jen pro dané povolání                                   |

Každá karta má: **Jméno** (flavor) + **AbilityName** (mechanika, vždy přítomno) + **Base** (hlavní stat) + **Efekt** (speciální schopnost, ne opakování base statu) + případně **Dice** (d6/d12 modifikátor).

---

## CSV soubory (pipeline: CSV → Google Sheets → Figma)

Soubory v `E:/Data/Raentir/Raentir/content/karty/`:

- `Raentir_attack.csv` — sloupce: `Jméno,Typ,Dice,AbilityName,Efekt,Text2,Image,RP,Base`
- `Raentir_defend.csv` — stejné sloupce
- `Raentir_save.csv` — stejné sloupce
- `Raentir_special.csv` — sloupce: `Jméno,Typ,Dice,AbilityName,Efekt,Podmínka,Image,Footer`
- `Raentir_classes.csv` — sloupce: `Jméno,Typ,Dice,AbilityName,Efekt,Text2,Image,RP,Base,logo`
- `Raentir_enemy.csv` — karta nepřítele s fázemi (22 sloupců)
- `Raentir_trait.csv` — sloupce: `Skupina,NázevTrait,Typ,Rarita,Efekt,Efekt2,Trvání,Footer,,,TraitImage`

Každý soubor má poslední řádek `END` (placeholder pro Figma plugin — jinak přepíše poslední kartu).

Aktuální karty v classes CSV:

```
Drtivý úder (Válečník) — Rozmáchnutí, base 4
Bojový pokřik (Válečník) — Nezdolnost
Inspirující melodie (Bard) — Inspirace
Rozptýlení (Bard) — Klamný tón, d6: Vedle: -2 útok tento tah
```

---

## Traity

- **Permanentní** — na character sheetu, definují postavu (povolání, přesvědčení, zásadní události)
- **Dočasné** — kartičky na stole, max 5 najednou, mají trvání. Skupiny: Soubojové / Fyzické / Mentální / Prostředí

---

## Deckbuilding (draft mezi souboji)

- Start: 8 základních + 2 třídní karty
- Obecný draft: vypravěč lízne (hráči+10) karet, každý si bere po 1 v pořadí iniciativy dokud nemá 2 nové
- Třídní draft: hráč lízne 3 ze svého třídního balíčku, vybere 1
- Body znalostí: každý dostane 2 (+ 1 za RP). Utrácí: 3 body = extra obecná karta, 5 bodů = extra třídní karta, 1 bod = vyhodit kartu z balíčku

---

## Co je otevřené / TODO

- `Počet karet v Konstantním balíčku` — výchozí 5, potřeba playtestovat (zkusit 3 a 7)
- `Limit použití na kartě` — přidat na grafiku karty (formát TBD)
- `Base HP` — rozsah asi 15–20, není finální
- `Max velikost balíčku` — není definováno (X)
- `Kostky jako nástroj vypravěče` — není dořešeno
- **Balance HP nepřátel** při více nepřátelích — multiplier pravděpodobně potřebuje zvýšit
- **RP vrstva v souboji** — odloženo na později, připomenout až bude hotová základní mechanika

---

## Soubory projektu

- `raentir-pravidla.md` — hlavní dokument pravidel (verze 0.1.1)
- `nova-pravidla.md` — draft nových pravidel ze session (zóny, Constant deck, opravy)
- `storyline.md` — lore (Tarogg, Saarští válečníci, starý svět)
- `README.md` — popis hry pro GitHub repo
- `content/karty/` — CSV soubory karet
- `content/karty/_Playtest/` — exportované PNG karty, TTS koláže, print PDF
