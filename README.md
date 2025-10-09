# 2D RPG HRA

## Anotace

Jedná se o 2D RPG HRA jménem Páťasy vytvořené podle mé fantasie. Dokumentace se skládá
z rešerše, kde jsou obrázky, podle kterých jsem se inspiroval, z technologií, se kterými jsem pracoval.
V praktické části mám produktivizaci, do níž jsem vybral věci z práce, na které jsem nejvíce pyšný a
uvedl jsem zde popis, jak by se měla hra hrát. Na závěr tu jsou nějaké obrázky ze hry.

## Klíčová slova

gameplay, krajina, survival, útok, život, boj, příroda, lesy, jezera, nepřátelští mobové


## Obsah

- Úvod
- 1 Rešerše
- 2 Technologie
- 3 Praktická část
   - 3.1 Produktizace
   - 3.2 Popis pro uživatele
- Závěr
- Použitá literatura
- Seznam obrázků
- Obsah média


## Úvod

Rozhodl jsem se ve své práci udělat 2D RPG hru a budu se inspirovat Final Fantasy I. a WOW. Vybral
jsem si to, protože se od mala zajímám o hry a jejich grafiku. Hru udělám ve 2D platformě ve Windows.
Jedná se o single-playerovou hru, jíž jsem pojmenoval Páťasy. Hra je vytvořená na základě mé fantasie.

Jako engine jsem si vybral Unity Engine, který podporuje c# a přišel mi ideální. Obrázky jsem dělalt a
upravoval v Pixlr editoru.

Na začátku je herní menu. Hráč si má možnost pojmenovat postavu. Hra je doprovázená hudbou. Je
vytvořena mapa, na které se vyskytují lesy, rostliny, cesty, kopce, zámek, jeskyně, jezera a hlavně
příroda, ve které se bude pohybovat hráč a narážet na různé příšery. Každá příšera je jinak silná.
Úkolem hráče je zlikvidovat nepřátele. Příšery jsou rozmístěny po celé mapě náhodně. Ve hře jsou i
efekty.

Postava má svou animaci. Nahoře vpravo je minimapa, která ukazuje polohu. Dolní bar, kde jsou výběry
pro útok, staty postav a příšer, se kterými se bude bojovat, jako je množství hp nebo many. Při
zaútočení se ukáže typ spellu. Hráč útočí mečem. Ve hře se sbírá score za zabíjení nepřátel. Hra se dá
ukládat a nahrávat. Hráč si bude moc doplňovat život lektvary a vylepšovat si svoje staty za nasbírané
body za zabíjení nepřátel u obchodníka.


## 1 Rešerše

**Fotka souboje ze hry FF I.** - Ukázka toho, jak se bojuje s nepřátelskými postavami. HP staty na
postavách. Možnost přetočit souboj. Útoky probíhají střídavě, jednou zaútočí hráč a potom
nepřítel.

**Logo hry FF I.** – Zde je vidět název hry a pod názvem je obraz z FF1.


**Fotka ze hry FF I.** – Fotka gameplaye ze hry Final Fantasy I. Minimapa na které se ukazuje, kde
se hráč zrovna nachází. Zámek, do kterého se dá jít. V hře jsou tlačítka, například pro nápovědu
nebo pro hraní.

**Fotka velkého kusu mapy s ostrovem, který má ve středu sopku.** - Na ostrovem je loď, která
přes něj prolétá a v ní cestuje hráč.


## 2 Technologie

**Pixlr**

Pixlr je sada obrazových nástrojů založených na principu cloudu, vytvořená ve Švédsku, zahrnující
řadu editorů fotografií. Umožňuje jak jednoduché, tak i pokročilé úpravy obrázků.

**Unity**

Unity je multiplatformní herní engine vyvinutý společností Unity Technologies. Unity poskytuje
možnosti vývoje pro 2D i 3D hry libovolného žánru a zaměření. Kromě grafického prostředí pro tvorbu,
podporuje také tvorbu skriptů v jazyce C#. Dnes funguje na více než 15 platformách. Jeho hlavním
konkurentem (především na trhu her pro PC a konzole) je Unreal Engine.

**CSharp**

C# je vysokoúrovňový objektově orientovaný programovací jazyk vyvinutý firmou Microsoft zároveň s
platformou .NET Framework. Používám ho pro programování v unity.

**Visual Studio Code**

Visual Studio Code je editor zdrojového kódu vyvíjený společností Microsoft pro operační
systémy Windows, Linux a macOS.


## 3 Praktická část

### 3.1 Produktizace

**Vytváření nabídky** – Menu nabídku ve hře jsem vytvořil obrázky. Dělal jsem spoustu tlačítek, texty a
vylaďoval jsem to možnostmi.

**Animace boje** – Zde jsem vytvořil v Pixlr editoru animace boje hráče tím, že jsem postavě dal meč a
udělal jsem obrázky podle toho, jak útočí.


**Animace** – Zde jsem v animátoru v Unity enginu vytvářel způsob animace hráče ze 12 různých
animací. Idle slouží k tomu, když se hráč zastaví a má 4 animace podle toho na jakou stranu se
zrovna hýbe, a to i movement, když se hráč hýbe. Čtyři attack triggery se spouštějí podle toho, na
jaké straně zrovna hráč je, hráč také při útoku stojí. Speed float slouží k nastavení způsobu a rychlosti
přechodu. Horizontal a Vertical floaty jsou u movementu. Last move floaty jsou u Idle, když hráč stojí.






**Hráč** – Tento kód s celkem asi 350 řádky obsahuje pohyb hráče, animaci, život, staty, zvukové efekty,
souboj hráče a ukládání v jednom skriptu. Hodně práce jsem si dal s animacemi pohybu a útoku, jako
je např. načasování útoku, aby vypadaly dobře. Do tohoto kódu vstupují textová pole pro život, pro
souboj, pro množství damage, pro scóre, text ukazující množství ubraného damage s animací.
Vstupují do něj také objekty, které se ukazují při smrti jako je GameOver a potom mě to pošle zpět do
menu. Je tam detekce pohybu nepřítele, kdy script detekuje nepřítele a přes název stringu najde
objekt a potom se připojí na něm k všude stejnému scriptu Hit a ubere danému nepřítelovi damage.
Má animaci i zvuk útoku. Jsou zde funkce, které přičítají nebo vrací scóre. Nakonec má i udělané
ukládání a načítání, kdy se dají načíst uložená data hráče a nepřátel a uložit aktuální data o hráči a
nepřátelích. Přidal jsem funkce, přes které se dají přičítal a vracet body.

### 3.2 Popis pro uživatele

Ovládání pohybu je W,A,S,D. Útočí se klikem myši nebo mezerníkem. Hráč chodí po mapě a zabíjí moby

a jeho úkolem je nasbírat co nejvíc scóre. Stisknutím escapu se zobrazí herní nabídka.


## Závěr

Projekt byl pro mě celkem náročný. Nastavoval a designoval jsem menu, mnoho objektů, doplňků a
také herní menu a nabídku. Hodně času jsem také věnoval obrázkům. Vyplnil jsem mapu velkým
množstvím objektů jako jsou květiny, tráva, stromy, hrad, jezero, cesta, kopce. Tytp objekty jsem
v editoru fotografií buď vytvořil, vystřihnul, nebo upravil. Udělal jsem ikonu hry. Přidal jsem několik
textů, které se umí automaticky updatovat. Texty jsem dělal přes textmesh zadarmo. Vytvořil jsem HP
bary nad hráčem a nepřáteli. Dále jsem jim udělal stat, který ukazuje jejich aktuální HP. Při útoku se
nad hráčem nebo nepřítelem ukáže ubrané množství HP s animací. Udělal jsem jim slider, který je
vyplněný podle aktuálního množství HP. Přidal jsem hudbu do menu a do hry, která se dá ovládat
pomocí sliderů v nastavení, které ukazují i procenta. Udělal jsem přechod z menu do hry.

Při startu hry se dá hráč libovolně pojmenovat. Přidal jsem zvukové efekty, jako je chůze, seknutí nebo
kliknutí. Nahoře je scóre text, při zabití se přičtou body a ukáže se to v textu. Přidal jsem více nepřátel,
podle jejich druhu jsem jim v určitém úseku vygeneroval náhodné množství HP. Udělal jsem víc kolizí
po mapě, dále jsem udělal pohyb a animace nepřátel ze stažených spritů z internetu, pohyb a animace
hráče a animaci jeho útoků. Nepřátelé mají náhodný pohyb a také určitý čas, kdy změní svůj směr. Když
se hráč přiblíží příliš blízko k nepříteli, tak na něj nepřítel zaútočí. Po celé mapě se generují přes script
random nepřátelé na random pozicích. Boss umí udeřit do hráče bleskem, vytvoří line mezi hráčem a
bossem a nad Bossem bar s bleskem. Udělal jsem vrstvy, které jsou přímo pro nepřátele, nebo pro
hráče. Některé animace, jako je útok nebo pohyb Bosse, jsem si vytvářel sám. Udělal jsem souboj hráče
s nepřítelem, hráč může udeřit jakéhokoli nepřítele na mapě. Dále jsem vytvořil načasování útoku, kdy
hráč nepřítele i nepřítel hráče může udeřit až za určitý čas po útoku. Při úderu jsem udělal efekt, že se
na půl sekundy začervená.

Vpravo nahoře jsem vytvořil minimapu, kde je hráč označen zeleným puntíkem a nepřátelé červeným
puntíkem. Ve hře jsem také udělal ukládání hry, kdy stav hry, jako jsou informace o hráčovi nebo o
počtu nepřátel a jejich pozicích, se dá uložit do souboru a zase potom načíst. Uložené hry se zobrazují
přes script, který zobrazí a vytvoří seznam všech uložených her. Uložené hry se i dají mazat, a když
zvolím nějaké uložení, tak se zabarví. Při smazání nebo uložení se i nahoře ukáže text, že se hra smazala
nebo uložila. Ve hře mám udělaného obchodníka, u kterého se dají vylepšovat sklily nebo kupovat
lektvary na život. Celkově jsem udělal přes 20 různých skriptů a každý z nich slouží k nějaké funkci nebo
funkcím ve hře.

Mohu říci, že jsem se svým projektem celkově spokojený. V tomto projektu jsem se naučil programovat
v CSharpu a dělat Unity Enginu. Do budoucna bych chtěl, aby vznikla i nějaká česká RPG hra. Za to, co
jsem byl schopen vytvořit, chci poděkovat mým vyučujícím, jim za to vděčím, panu učiteli Jakubu
Pokornému, Michalu Benešovi a Vratislavu Medřickému.


## Použitá literatura

_1.cs.wikipedia.org: Pixlr (Editor Fotografií)_ [online]. 2008 [cit. 2022- 07 - 03 ]. Dostupné z:
https://cs.wikipedia.org/wiki/Pixlr

_2.cs.wikipedia.org: Unity (Herní engine)_ [online]. 200 5 [cit. 2022- 07 - 03 ]. Dostupné z:
https://cs.wikipedia.org/wiki/Unity_(herní_engine)

_3.cs.wikipedia.org: C# (Programovací jazyk)_ [online]. 200 0 [cit. 2022- 07 - 03 ]. Dostupné z:
https://cs.wikipedia.org/wiki/C_Sharp

_4.cs.wikipedia.org: Visual Studio Code (Editor zdrojového kódu)_ [online]. 2015 - 4 - 28 [cit. 2022-
07 - 03 ]. Dostupné z:
https://cs.wikipedia.org/wiki/Visual_Studio_Code

## Seznam obrázků

**Ukázka ze hry**

<img width="702" height="396" alt="jcWseAAAABklEQVQDABSK4v6z9nuFAAAAAElFTkSuQmCC" src="https://github.com/user-attachments/assets/50a9efaf-f081-41e7-97f1-2fc2851f87b5" />

**Ukládání hry**

<img width="759" height="429" alt="FYvGYwAAAAZJREFUAwBI+M5ZFNsqRAAAAABJRU5ErkJggg==" src="https://github.com/user-attachments/assets/d5c9e9b5-040e-4f2b-8f9e-7450d43b436b" />

**Game over**

<img width="735" height="411" alt="LBPEjAAAABklEQVQDACAiXAA7l0SGAAAAAElFTkSuQmCC" src="https://github.com/user-attachments/assets/bbb9fb06-0450-470f-bddc-e698dc1091c8" />

**Souboj s bosem**

