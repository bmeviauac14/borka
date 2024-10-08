# Git, GitHub, GitHub Classroom

A tárgy keretében nem célunk a Git és GitHub részletes megismerése, csak a legszükségesebb lépésekre szorítkozunk, valamint a legfontosabb parancsokat használjuk ahhoz, hogy a házi feladat(ok) kiindulási programvázát hallgatóként egy dedikált GitHub repository-ból le tudjuk tölteni, illetve a kész munkát GitHubra fel tudjuk tölteni.

## Git

A Git egy sok szolgáltatással rendelkező, rendkívül népszerű és elterjedt, ingyenesen letölthető és telepíthető, elosztottan is használható verziókezelő rendszer. A központosított rendszerekhez képest (TFS, CVS, SVN) a GIT esetében nem egyetlen központi repository-ba dolgoznak a fejlesztők, hanem mindenki egy saját lokális repository példánnyal rendelkezik.

Egy Git **repository** (becenevén repó) nem más, mint egy közönséges könyvtár a fájlrendszerben, benne állományokkal (pl. forráskód) és alkönyvtárakkal, illetve egy ".git" alkönyvtárral, melyben minden, a verziókezeléshez kapcsolódó extra információ megtalálható.

A Git alapú munkafolyamat legfontosabb lépései - némi egyszerűsítéssel - a következők (feltéve, hogy létezik egy központi repository, ahol a verziókezelt kód adott változata már elérhető):

1. A fejlesztő klónozza (`clone`) az adott központi repository-t, melynek során egy azzal megegyező helyi repository jön létre a saját számítógépén. Ezt a műveletet elég egyszer elvégezni.
2. A fejlesztő a helyi repository-hoz tartozó munkakönyvtárban (working directory) változtatásokat végez a kódon: új fájlokat vesz fel, meglévőket módosít és töröl.
3. Ha elkészül egy érdemi részfeladat, akkor a fejlesztő a változtatásokat `commit`-olja a számítógépén levő helyi repository-ba. Ennek során a commit-ot célszerű egy a változtatások jellegét jól összefoglaló megjegyzéssel ellátni.
4. A helyi repository-ból egy `push` művelettel a fejlesztő felölti a változásokat a központi repository-ba, ahol így változtatásai mások számára is láthatóvá válnak.

Minden egyes **commit** tulajdonképpen egy időbélyeggel, a fejlesztő felhasználónevével és e-mail címével ellátott kódot érintő változáshalmaz. A repositoryban ezek "egymásutániságából" áll össze a teljes verziótörténet.
Mivel a legtöbb esetben a fejlesztők csapatban dolgoznak, időnként szükség van arra, hogy mások által a központi repository-ba `push`-olt változtatásokat a fejlesztők a saját lokális repository-jukba letöltsék és belemerge-eljék: erre szolgál a `pull` művelet. Fontos szabály, hogy `push`-olni csak akkor lehet a központi repository-ba (a Git csak akkor engedi), ha előtte mások változtatásait a saját lokális repository-nkba egy `pull` művelettel előtte belemerge-eltük.
A Szoftvertechnikák tárgy keretében a `pull` műveletet nem kell használni, mert mindenki önállóan, saját repository-ba dolgozik. Megjegyzés: ha esetleg a GitHub felületén közvetlen változtatunk fájlokon (vagy több clone-ban is dolgozunk), akkor szükség van a `pull` használatára ez esetben is.
A fentieken túlmenően a Git számos további szolgáltatást biztosít (pl. teljes verziótörténet megtekintése minden fájlra, commit történet megtekintése, tetszőleges múltbeli verzióra visszaállás, ágak kezelése stb.).

## GitHub

A GitHub egy online elérhető website és szolgáltatás (https://github.com), mely teljes körű Git szolgáltatást biztosít. Mindezt ráadásul – legalábbis publikus, vagyis mindenki számára hozzáférhető repositoryk vonatkozásában – teljesen ingyenesen biztosítja. Napjainkra a GitHub vált a közösségi kód (verziókezelt) tárolásának első számú platformjává, a legtöbb nyílt forráskódú projekt „otthonává”.

## GitHub Classroom

A GitHub Classroom egy ingyenesen elérhető GitHub-bal integrált szolgáltatás, mely többek között oktatási intézmények számára lehetővé teszi önálló tanulói feladatokhoz tartozó, tanulónként egyedi GitHub repository-k létrehozását, ezáltal a kiindulási kód tanulók számára történő „kiosztását”, valamint az elkészült feladatok „beszedését”.

## Git, GitHub és GitHub Classroom a tárgy kontextusában

A tárgy keretében a GitHub Classroom segítségével kap minden hallgató minden házi feladatához egy dedikált, a GitHub-on hostolt repository-t, mely a megfelelő kiindulási környezettel (kiinduló Visual Studio solution-ök) inicializálásra kerül. Mindenkinek a számára dedikált repository-t kell a saját gépére `clone`-oznia, ebbe a változtatásait `commit`-olni, és a határidőig az elkészült megoldását `push`-olni (hogy GitHub-on is elérhető legyen a megoldás). A pontos lépésekre rövidesen visszatérünk.

## Visual Studio és a Git

A Git egy elosztott verziókezelő rendszer. Ahhoz, hogy a saját gépünkön dolgozni tudjunk vele, a Git-nek telepítve kell lennie. Kétféle módon tudjuk használni:

- A Git önmagában is telepíthető, és parancssorból is ki tudjuk adni a szükséges `clone`, `commit`, `push` stb. parancsokat.
- Használhatunk a parancsok kiadására egy grafikus felülettel rendelkező eszközt. Ilyenek pl. a GitHub Desktop, a GitExtensions, vagy maga a Visual Studio is (mely integrált grafikus Git szolgáltatásokat is biztosít).

A két megközelítést a mindennapokban kombináltan szoktuk használni. Egy repo leklónozása sokszor parancssorból a legegyszerűbb/leggyorsabb. A változások commit-olására, a központi repositoryval való szinkronizációra (push, pull), a verziótörtének megjelenítésére már célszerűbb egy grafikus eszközt használni, különösen akkor, ha még kevésbé vagyunk rutinosak. A tárgy keretében a klónozásra a parancssor vagy a Visual Studio, az egyéb parancsok kiadására a Visual Studio javasolt. A git használatról (a házi feladatok kontextusában) [itt](../hf-folyamat/index.md) található bővebb leírás.

## Git telepítése

Amennyiben a számítógépünkre nincs még a Git telepítve, és szeretnénk azt parancssorból is használni, akkor innen telepíthető Windows operációs rendszerre: https://git-scm.com/download/win. Egyéb operációs rendszerek esetén pedig innen érdemes indulni: https://git-scm.com/downloads.

!!! warning "Git Credential Manager telepítése"
    A GitHub már egy ideje nem támogatja az egyszerű felhasználónév/jelszó alapú hitelesítést. Ha git parancssorban a login során "Support for password authentication was removed." hibaüzenetet kapunk, ez az oka. Két megoldás is létezik a probléma megoldására: 
    
    * A legegyszerűbb megoldás a "Git Credential Manager" telepítése. Ezt fel lehet telepíten a git telepítése során (csak be kell pipálni a telepítőben), de külön is telepíthető [innen](https://github.com/git-ecosystem/git-credential-manager/releases). A telepítést követően nincs teendőnk vele, a git automatikusan használni fogja, és egy böngésző alapú (ún. OAuth) hitelesítési folyamaton vezeti végig a felhasználót, ill. plusz kényelmi funkcióként meg is jegyzi a hitelesítési adatokat.
    * A másik megoldás a PAT (Personal Access Token) használata, erről pl. [itt](https://stackoverflow.com/questions/68775869/message-support-for-password-authentication-was-removed) lehet olvasni.