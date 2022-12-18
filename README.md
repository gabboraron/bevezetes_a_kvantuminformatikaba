# Bevezetés a kvantuminformatikába
A kvantuminformatika napjainkban egyre nagyobb teret hódít. Cél a kvantuminformatika, és a benne rejlő lehetőségek megismertetése a hallgatókkal. Betekintés a kvantum számításokat lehetővé tevő architektúrákba, a kvantum elmélet alapjaiba, a kvantum kriptográfiába, a jelenlegi kvantum programozási környezetekbe.  Bevezetés a kvantuminformatikába. Kvantum mechanika elméleti alapjai, kvantum kriptográfia alapjai, poszt-kvantumkriptográfia. Legfontosabb kvantum számítástechnikai hardverek, architektúrák, kvantum programozási környezetek, programok.


## Qubit
megvalósítások:
- mikrohullám
- topológikus qubit
- ioncsapda
- gyémánttal

**lényege:** kvantumpárhuzamosságot ad, ellentétben a soros megoldással amit a hagyományos gépek adnak

[zuchongzhi](https://www.sciencealert.com/china-s-latest-56-qubit-computer-marks-another-quantum-milestone) programozható kvantum processzor, jelenlelegi kínai kvantum fölényt biztosítja

Egy qubit sok értéket vehet fel, 2^n állapotot párhuzamosan képes felvenni. [meetiqm chet sheet - pdf](https://meetiqm.com/uploads/files/cheat-sheet-circuit-magicians-hm.pdf)

A kvantuminternet egy olyan hálózat, amely a kvantummechanika törvényein alapuló és azokat kihasználó technológiával teszi lehetővé az információcserét ami qubiteken valósul meg. A küldő és fogadó felek egy kvantumrendszerből nyernek véletlen, de egymással összefüggő adatokat, ezáltal tudnak egy megosztott kulcspárt létrehozni. A  kulcsokat tudják utána biztonságos klasszikus kommunikációra felhasználni, ez a kvantum kulcselosztás.



![[meetiqm chet sheet - kép](https://meetiqm.com/uploads/files/cheat-sheet-circuit-magicians-hm.pdf)](https://www.meetiqm.com/imager/images/74720/cheat-sheet-circuit-magicians_2023319427f4081f6d74a91ada0584b8.jpg)

- törölhetetlen qubitek
- logikai értékeknek megfelelő kubitek
- egy vagy több kubites kapu megoldások
- NP teljes problémák egy részhalmazát lehet megoldani [D-Wave](https://www.dwavesys.com/) megoldásokkal

kvantumpontokról bővebben: https://fizipedia.bme.hu/index.php/Kvantump%C3%B6tty%C3%B6k

- elvileg zaj ellen jobban védett topologikus kvantumszámítási modellek, nagyobb és stabilabb rendszereket lehet épíeni [Majorana részecskék](https://www.youtube.com/watch?v=LTatUEj3oG4)en alapuló gépekkel.
- OpenSuperQ: https://opensuperq.eu/


## Fizikai alapok

![Stern-Gerlach kísérlet](https://upload.wikimedia.org/wikipedia/commons/2/29/Stern-Gerlach_experiment.PNG)

> A Stern–Gerlach-kísérlet lényege: egy inhomogén mágneses téren keresztül ezüstatomokból álló részecskesugarat küldenek át és közben figyelik a részecskék eltérülését. Az eredmények azt mutatták, hogy a részecskék egy ún. belső impulzusmomentummal rendelkeznek, amely igen hasonló a klasszikus forgó testek impulzusmomentumához, de csak bizonyos értékeket vehet fel. 

fényhullám energiája: `e = h * ν` (Pauli) ahol `h` egy kis szám, `ν` a fény frekvenciája, `e` az energiája a fénynek, tehát a foton súlya függ a frekvenciájától.

Két hullámfüggvény öszege is hullámfüggvény így két hullám állapot összege is lineáris változóktól függ, így az határozza meg, hogy melyiket tudjuk kimérni

Így ha a kísérletbe két ellentétes spinű részecskék keletkeznek akkor ha egyiket megmérjük akkor a másikat is tudjuk, csak ellentétes értékkel. Az értékek braket jelölésben adva komplex számok.


operátorok:
- ha olyan operátorokat használunk amivel nem változik meg a mozgás egyenlet akkor szimetriáról beszélünk
- eltolás
- forgatás
- ha az operátor nem változtatja meg a függvény alakját akkor az sajátfüggvény
- unitér megoldások

Mechanika:
- Hamilton függvény: a rendszer teljes mozgási energiája
- Hamilton mechanika: a Hamilton függvény parciális deriváltja => sebesség arányos az impulzussal => gyorsulás arányos az erővel

Ezek megadják az állapotokat:
- az állapotokat egy Bloch gömbön ábrázolhatjuk
- normálással kivehetünk egy szabadsági fokot
- forgatás után még egy szabadsági fok kiesik
- így 2 szbadsági fokú, két állapotú rendszert kell reprezentálnunk csupán => van két állapot: 0/1 -> a többi átmenetet a gömb felülete adja

de egy qubit egyszerre két állapotban lehet, azaz egyszerre 0 és 1, amiről sok mérés után egy arányt modnhatunk, hogy melyik jött ki többször.

Bell állapotok:
- egy qubit mérés határozatlan
- de ha a másikat megmérjük akkor az előbbi ezzel korrellál
- ezek mindig összefonódott állapotú qubitek
- négy Bell állapot imsert

kvantumteleportáció: egyik kvantum rendszerből a msáikba való qubit átjuttatás, úgy, hogy köztük nincs kvantuminternet. Ez hagyományos bitekkel oldható meg.

szupersűrű kódolás:
- két klasszikus bitet viszünk át úgy, hogy egy qubit formájában küldjük át egy kvantumcsatornán.
- a küldő megfelelő állapotba alakítja a qubitet
- a qubit eljut a célba
- a célban a qubitet fel kell bontani a megfelelő módszernek megflelően amit a a küldő adott meg

nem klónozhatósági tétel:
- azonos qubit állapotok esetén nincs unitér transzformáció


## kriptográfia
- bizalmasság
- sértetlenség integritás: igazolható a harmadik fél kihagyása
- feladó azonosítás
- letagadhatatlanság

algoritmusok:
- szimetrikus: ugyanaz a kulcs kódol és dekódol
- aszimetrikus: egy kulcs titkosít egy dekódol

támadások:
- MiM:
 - passzív: a támadó rejtve van
 - aktív: a támadó úgy változtatja meg az üzenet forrássát, hogy nem fedi fel magát 
 - csalás

## kvantumkriptográfia:
- Diffie Helmann kulcs csere: X9.42 szabvány
- RSA
- ECC: egy irányba könnyű kiszámítani,  visszafelé azomban nehéz

kvantumkonjugált tárolás: hogy tárolható anyagban információ tárolása => BB84 módszer az információ átadására

A QKD esetében a kriptográfiai kulcsot qubitek segítségével juttatják el a másik személynek, aki a kulcsérték megszerzése érdekében megméri a qubitet.

### BB84
- első QKD protokoll
- tenzor szorzatként tárolja az infromációt *(a tenzor szorzás: gráfok rendezett párjaihoz új gráfot rendel)*
- fotonok polarizációs szögével adható meg

Qubit nem csak foton, lehet ion vagy [kvázirészecske](https://hu.wikipedia.org/wiki/Roton) is.

**titkosíás kritériumai:**
1. Ha egy rendszer elméletileg (matematikailag) nem feltörhetetlen, akkor a gyakorlatban legyen az.
2. A titkosított rendszer egy részének megismerésével ne lehessen a rendszer egészét megismerni.
3. Az alkalmazott kulcsnak könnyen megjegyezhetőnek és megváltoztathatónak kell lennie.
4. A titkosított szöveg táviratban is továbbítható legyen. (A 19. század gyors és hatékony üzenetküldő megoldása a távirat volt)
5. A titkosító rendszer legyen hordozható és nem kell az üzemeltetéséhez és kezeléséhez több személyre szükség.
6. A rendszer legyen könnyen és stresszmentesen kezelhető, ne igényelje hosszú listányi szabályok betartását.

## programozás
- https://oreilly-qc.github.io/
- https://qiskit.org/
- https://quantum-computing.ibm.com/
