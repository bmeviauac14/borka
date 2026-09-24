# Házi feladat munkafolyamat és a Git/GitHub használata

Ha még nem olvastad, célszerű itt kezdeni: [Git, GitHub, AHK](../git-github-github-classroom/index.md)

## Lépések

Az egyes házi feladatok kiinduló keretét a tanszéki AHK rendszer segítségével, GitHub repository-kban publikáljuk. Az így publikált házi feladatok kiinduló környezet letöltésének és a megoldás beadásának lépései a következők:

1. :exclamation: Az elindulással ne várd meg a határidő közeledtét, legalább a saját repository létrehozásáig juss el mielőbb. Így, ha bármi elakadás lenne, még időben tudunk segíteni.
2. Regisztrálj egy GitHub accountot (<https://github.com/>), ha még nem regisztráltál, és lépj be vele GitHub-ra.
3. A feladathoz tartozó linket nyisd meg. Ez minden feladathoz más lesz, Moodle-ben kerülnek meghirdetésre fokozatosan a félév folyamán. A link az AHK (a tanszéki házi feladat kezelő rendszer) felületére visz.
4. Ha kéri, jelentkezz be, illetve adj engedélyt az AHK-nak, hogy használja a GitHub account adataidat.
5. Látni fogsz egy oldalt, ahol elfogadhatod a feladatot. Kattints az elfogadás ("Accept this assignment") gombra.
6. Várd meg, amíg elkészül a repository. Ha elkészült a repository, az oldal kiírja az új GitHub repository url-jét, melyen (vagy a "Go to the Repository" gombra) kattintva a repository-ra lehet navigálni (ehhez hasonló: <https://github.com/bmeviauac14/hazi2-2026o-neptun>). De nem is feltétlen szükséges az url elmentése, a GitHub nyitóoldalán (https://github.com/) baloldalt a saját repository-k közt bármikor meg lehet később is találni.
7. Klónozd le a repository-t (ennek mikéntjére rövidesen visszatérünk). Ebben találni fogsz egy keretet, vagy kiinduló kódot. Ezen dolgozz, ezt változtasd. Az alapértelmezett git ágon/branchen dolgozz (ha ez nem mond semmit, nem baj: ez csak azoknak szól, akik a git használatában jártasak és több ágon szoktak dolgozni).
8. :exclamation: A kiinduló projektben van egy .github/workflows mappa, ennek tartalmát tilos megváltoztatni, törölni stb.
9. :exclamation: A munka során a kiindulási repóban levő solutionben/projektben kell dolgozni, új projektet/solutiont ne hozz létre.
10. :exclamation: A repository gyökérmappájában található neptun.txt fájlba írd bele a Neptun kódod, csupa nagybetűvel. A fájlban csak ez a hat karakter legyen, semmi más.
11. Oldd meg a feladatot. Pushold a határidőig. Akárhány commitod lehet, a legutolsó állapotot fogjuk nézni.
12. Az eredmények Moodle-ben kerülnek meghirdetésre (a nyitóoldalon kapcsolódó házi feladat oldalát Moodle-ben megnyitva az oldal alján a "Visszajelzés" szekcióban látható). Eredmények az adott feladatra vonatkozó határidőt követő pár napon belül várhatók.
13. A házi feladatot külön explicit beadni nem kell, csak legyen fent GitHub-on határidőre a megoldás.
14.	:exclamation: Amikor a házi feladatod beadottnak tekinted,  célszerű ellenőrizni a böngészőben a GitHub webes felületén a repository-ban a fájlokra való rápillantással, hogy valóban minden változtatást push-oltál-e, és hogy a neptun.txt valóban ki van-e töltve.

A fenti lépések kapcsán két kérdés vár még megválaszolásra:

- Hogyan klónozzuk (clone) a repónkat (mely a házi feladat kiinduló keretét tartalmazza)?
- Hogyan commit-áljunk és push-oljunk a Visual Studio segítségével GitHub-ra?

Az alábbiakban ezekre is kitérünk.

## GitHub repository klónozása

Két lehetőséget nézünk meg alább:

- Klónozás Visual Studioban
- Klónozás parancssorból

### Klónozás Visual Studio-ban

Egy (házi feladathoz tartozó) repository klónozásra számos mód van, egy lehetőség a következő. Nyissuk meg az elkészült repository online oldalát, melyre több módon eljuthatunk. Lehetőségek pl.:

- A repo létrehozásakor megjelenik a GitHub felületen az url, csak kattintani kell rajta.
- A GitHub nyitóoldalon (<https://github.com>) - ha be vagyunk lépve - listázódnak baloldalt azon repository-k, melyekhez van hozzáférésünk, csak kattintsunk a megfelelőn.
- Amikor elkészül a repónk (a feladat AHK-ban történő elfogadása során), e-mail értesítést is kapunk róla, ebben is megtalálható a link.

Az oldal képe nagyjából megfelel a következőnek (az mindenképpen különbség, hogy a repó url végén mindenkinél a saját felhasználóneve szerepel):

![GitHub repo oldal](images/github-repo-page.png)

Indítsuk el a Visual Studiot, és a megjelenő ablak jobb oldalán kattintsunk a "Clone a repository" gombon. Ekkor a következő ablak jelenik meg:

![Repository clone Visual Studionban](images/vs-clone-a-repository.png)

Itt a "Repository location" mezőbe másoljuk be böngészőablak címsorából a repository-nk url-jét. Az útvonal (Path) a létrehozandó projekt útvonala a fájlrendszerünkben, tetszés szerint megadható.

A *Clone*-ra kattintva néhány másodperc alatt a repository a megadott célmappába klónozódik.

A klónozást követően pl. a Windows Fájlkezelőben (File Explorer)-ben meg tudjuk tekinteni a létrehozott mappákat és fájlokat:

![Repo a fájlrendszerben](images/git-folder-in-explorer.png)

Ebből jól látható, hogy egy Git repository nem más, mint mappák és fájlok gyűjteménye, valamint egy a gyökérben található .git mappa, mely - némi egyszerűsítéssel élve - az egyes fájlok verziótörténetét tartalmazza (a .git mappa "rejtett" tulajdonságú, csak akkor látható, ha a fájlkezelőben a rejtett fájlok megjelenítését is engedélyezzük). A munka megkezdéséhez csak meg kell nyissuk az adott házi feladathoz tartozó .sln kiterjesztésű solution fájlt (pl. duplakatt a Fájlkezelőben).

### Klónozás parancssorból

Alternatív lehetőség a parancssor használata. Parancssorban navigáljunk abba a mappába, ahová a forráskódot ki szeretnénk clone-ozni, és itt adjuk ki a következő parancsot:
`git clone <repo url>`
, ahol a `<repo url>` a repositorynk címe (pl. böngésző címsávjából bemásolva, ehhez hasonló: https://github.com/bmeviauac14/hazi1-2022-myusername). A parancs lefutása után egy a repository nevének megfelelő alkönyvtárban találjuk az új helyi repónkat.

!!! note "Parancssori git"
    Ne féljünk a parancssori git-et használni, egy repository clone-ozásának tulajdonképpen ez a legegyszerűbb módja.
    
    Amennyiben a parancs futtatása során azt tapasztaljuk, hogy a git parancsot nem ismeri fel a környezet, annak oka valószínűleg az, hogy nem telepítettünk még a parancssori gitet a gépünkre. Erről bővebben [itt](../git-github-github-classroom/index.md#git-telepitese).

## Napi Git munka Visual Studio segítségével (commit, push)

Miután leklónoztuk az adott házi feladathoz tartozó GitHub repository-t a számítógépünkre, és ennek során létrejött a lokális Git repository-nk, a benne levő .sln fájlokat Visual Studioban megnyitva pont úgy dolgozunk – veszünk fel új fájlokat, módosítunk/törlünk meglévőket – mintha a fájlok nem is tartoznának semmiféle Git repóhoz. Ugyanakkor, legkésőbb a feladat beadásakor a változtatásainkat commit-olni kell, majd push-olni GitHub-ra. A munka során akárhányszor commit-álhatjuk/push-olhatjuk az előző commit óta eszközölt módosításainkat: a házi feladat ellenőrzésekor a határidő pillanatában a GitHub-on található állapot kerül elbírálásra, teljesen mindegy, hány commit tartozik hozzá.
A commit és push műveletek végrehajtásához a Visual Studio *"Git"* menüjében levő parancsokat használjuk.

### Commit

Az előző commit óta eszközölt változtatások megtekintéséhez válasszuk ki a *"View\Git Changes"* menüt. Ennek hatására megjelenik a *"Git Changes"* nézet a változások listájával:
 
![VS Git changes](images/vs-git-changes.png)

A változtatások commit-álásához írjunk a fenti szövegmezőbe egy a változtatásokra jellemző egy-két soros leírást (pl. "Végső megoldás", "Az xyz hiba javítása" stb.). A lehetőségeink ezt követően a következők:

-  **"Commit All"** gomb: Csak helyben commit-olja a változtatásokat (a központi Git repóban mindaddig nem jelenik meg a commit, amíg egy külön Push paranccsal fel nem "toljuk").
- **"Commit All and Push"**, mely a "Commit All" gomb melletti nyíl lenyitásával érhető el. Hatása: commit, majd utána push. Ha a változtatásainkat egyből publikálni is szeretnénk a GitHub-on levő központi repóba, akkor használjuk bátran parancsot. **A házi feladatok tekintetében célszerű is ezt használni, mert ekkor nincs szükség a commit-ot követően külön push műveletre.**
Megjegyzés: ha a parancs az "Unable to push to the remote repository because your local branch is behind the remote branch" hibával zárul, előbb pull-oljuk, majd ismételjük meg a push-t. Erre még alább visszatérünk.
- **"Commit All and Sync"**, mely a "Commit All" gomb melletti nyíl lenyitásával érhető el. Hatása: commit után pull (leszedi a saját helyi repónkba mások esetleges változtatásait a központi repóból), majd push. Így a központi repóban levő esetleges változásokat lehozza a helyi repónkba, az ezt követően a változtatásainkat egyből publikálja is ide.

!!! note
    A git commit-ot mindig meg kell előzze egy ún. **stage** lépés, mely során kiválasztjuk azokat a helyi változtatásokat, melyeket a következő commit-ba be kívánunk tenni. Ez az ún. **staging area** területre teszi az általunk kiválasztott változásokat (a fájlrendszerben nem mozgat semmiféle fájlt, ez csak a git a belső nyilvántartásában jelenik meg). Ez azért jó, mert plusz rugalmasságot biztosít, hiszen nem biztos, mindig minden változtatást bele kívánunk tenni a következő commit-ba. A fenti "Commit all" stb. parancsok nevében nem véletlen van benne az "all": ezek a színfalak mögött a commit előtt egy megfelelő git paranccsal valamennyi változást a git staging area-ra tesznek, így ezt nekünk nem kell külön megtennünk.

### Push, Pull

A commit művelet csak a helyi repository-ban "érvényesíti" a változtatásokat. Ezt követően a változtatásokat a GitHub központi repository-nkba fel kell tölteni a push művelettel. Erre a lépésre csak akkor van szükség, ha a commit során nem használtuk a *"Commit All and Push"* vagy *"Commit All and Sync"* parancsokat. A push művelet VS-ben a *"Git/Push"* menü segítésével indítható. 
Ha többen dolgozunk, a központi repository-ban lehetnek mások által pusholt, hozzánk még le nem töltött commitok (vagy akár olyanok, melyeket mi magunk push-oltunk egy másik lokális clone-ból, vagy ha a GitHub online felületén eszközöltünk a kódon változásokat). Ezeket a pull művelettel tudjuk a helyi repónkba merge-elni (Git/Pull menü). A házi feladat vonatkozásában ezt nem használjuk, hiszen mindenki saját dedikált központi repositoryval rendelkezik, melyben egyedül dolgozik (kivéve, ha esetleg valaki a GitHub felületének segítségével változtatott a kódon, akkor ezt egy pull-lal tudja a helyi repójába lehozni).

!!! note
    A push csak akkor hajtható végre, ha a központi repóban nincs olyan változás, melyet még a pull paranccsal nem hoztunk le és merge-eltünk a saját lokális repónkba. Ha ez nincs így, egy ehhez hasonló hibaüzenet kapunk: "Unable to push to the remote repository because your local branch is behind the remote branch". Ekkor pull-oljunk, utána ismételjük meg a pusht.

!!! note
    A pull művelet csak akkor hajtható végre, ha nincs olyan változtatásunk helyben, melyeket még nem commitáltunk. Ha van ilyen, akkor azokat vagy commitáljuk (vagy ha ezt nem akarjuk megtenni még, akkor stash-eljük a pull idejére).

!!! tip
     A Pull és Push parancsok a „Git Changes” (View/Git Changes menü jeleníti meg) panel tetején elérhető le és fel nyilakkal is végrehajthatók:

    ![VS pull push](images/vs-git-changes-push-pull.png)

### Git history

A Git egy változáskövető rendszer. A változás egysége a commit (melyben tetszőleges számú fájlt érintő változás lehet), a Git historyban a commitok egymásutániságát láthatjuk. A fájlokat érintő változásokon túlmenően minden commithoz tartozik egy egyedi azonosító (commit hash), időbélyeg, illetve egy szerző. A szerző felhasználó, aki a változásokat eszközölte (valójában van külön Author és Commiter, de a kettő általában ugyanaz). Visual Studioban a historyt a View/Git Repository menüvel tudjuk megjeleníteni, de a history természetesen a GitHub online felületén is megjeleníthető.
A Visual Studioban a *"Git Repository"* nézetet a View/Git Repository menüvel tudjuk megjeleníteni.

- Outgoing commits: Megmutatja, hogy milyen, a lokális repository-nkba már létező, de a központi repóba még nem push-olt commitok vannak. Ezeket a Push művelettel tudjuk feltölteni.
- Incoming commits: Megmutatja, hogy a központi repository-ban milyen mások által pusholt, hozzánk még le nem töltött commitok vannak. Ezek akkor jelennek meg, ha a Fetch paranccsal lehozzuk a helyi repóba (ez még nem merge-el). Ezeket a Pull művelettel tudjuk a helyi repónkba merge-elni. A fetch parancsot ritkán használjuk: általában a pullt használjuk magában, ami egy fecth + merge (változások merge-elése a helyi repóba) kombinációja.

Példa:

![VS git history](images/vs-git-history.png)

!!! tip
    Amíg nem vagyunk rutinosak a Visual Studio Git szolgáltatásainak használatában, a push-t követően (legkésőbb akkor, amikor a házi feladatot beadottnak tekintjük) célszerű ellenőrizni a GitHub webes felületén a repository-ban a fájlokra való rápillantással, hogy valóban minden változtatást feltöltöttünk-e.

### Egyéb irányelvek

A Git commit és push során megfigyelhetjük, hogy a solution-jeink köztes és kimeneti állományai (.dll, .exe, stb. fájlok) nem kerülnek bele a commitba, és így nem kerülnek fel GitHubra sem. Ez így is van jól, ezen állományok bármikor reprodukálhatók, a verziókezelő rendszernek nem feladata ezek tárolása, csak felesleges és zavaró helyfoglalók lennének. Felmerül a kérdés, honnan tudja a Git, hogy mely állományokat szükséges figyelmen kívül hagyni a commit során. Erre szolgál a repository-ban (tipikusan annak gyökérmappájában) található **.gitignore** fájl, mely felsorolja azon mappákat, fájlkiterjesztéseket, illetve egyedi fájlokat, melyeket a commit során figyelmen kívül szeretnénk hagyni. A .gitignore fájl tartalma teljes egészében a kezünk alá tartozik, szabadon szerkeszthető/commitálható/pusholható.
A tárgy keretében minden kiinduló repónak része egy .gitignore fájl, ne változtassuk a tartalmát! Így a commit/push során a kimeneti állományok a házi feladatok esetében sem kerülnek fel GitHub-ra, és egy így is van rendjén.

A félévben a feladatok megoldása során az egyes osztályok, interfészek stb. forráskódját külön fájlba kell tenni, vagyis egy C# forrásfájlban egy osztály/interfész/stb. definíciója legyen.

### Git használata parancssorból

Bár sokan ódzkodnak a git parancssori alkalmazásától, az egyszerűbb műveleteket gyakran gyorsabban végre tudjuk hajtani parancssorból, mint a GUI felületeken történő kattintgatásokkal. Az alábbiakban egy egyszerű lépéssorozattal illusztráljuk ezt. Ezeket a tárgy keretében nem kell tudni, de hosszabb távon mindenképpen hasznos (és az iparágban elvárás is) az ismeretük.

1. Repository clone (ezt csak egyszer)

    `git clone https://github.com/bmeviauac14/hazi1-2022-myusername`

2. Változtatások végrehajtása a helyi repóban (fájlrendszerben, fejlesztőeszközben).

3. Változtatások megtekintése, mutatja melyek az új/törölt/módosult fájlok (nem kötelező, csak ha kíváncsiak vagyunk rá)*

    `git status`

4. Minden változtatás feltétele a staging area-ra

    `git add -A`

    Ha ezt követően ismét kiadjuk `git status` parancsot (nem kötelező), látjuk, hogy minden változás stage-elve van.

5. Commit

    `git commit -m "megjegyzés a commithoz"`

6. Push

    `git push`

Megjegyzések:

- Ha többen is dolgozunk az adott git ágon, akkor a 6. push előtt szükség lehet/van egy `git pull`-ra, hogy mások változtatásai megjelenjenek a mi helyi repónkban (enélkül nem fogunk tudni push-olni). A pull-nak célszerű lehet megadni a `--rebase` opciót is, hogy ne szülessen a merge-hez egy plusz merge commit, ennek magyarázatára itt nem térünk ki.
- Mint korábban említettük, a commit során a commithoz hozzárendelődik egy felhasználónév és e-mail cím. Ha ezek nincsenek a git számára bekonfigurálva, akkor a git a commit során ezt hibaüzenetben jelzi. Ekkor az alábbi parancsokkal - értelemszerűen a saját felhasználónevünket és e-mail címünket megadva - tudjuk ezeket a git globális konfigurációjában beállítani (ezt csak egyszer kell megtenni):

    ```
    git config --global user.email "you@example.com"
    git config --global user.name "myusername"
    ```
    
- Windows parancssorban összevonhatunk több parancsot is egy sorba, pl. egy lépésben minden változásra stage/commit/push:
  
    `git add -A & git commit -m "All tests run" & git push`

    Powershell használatakor a `&` helyett `;`-t kell szeparátorként használni.
