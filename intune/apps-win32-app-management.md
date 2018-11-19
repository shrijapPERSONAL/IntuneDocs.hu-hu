---
title: Win32-alkalmazások hozzáadása a Microsoft Intune-hoz
titlesuffix: ''
description: Ismerje meg, hogyan adhat hozzá, továbbítására és Win32-alkalmazások Microsoft Intune-nal kezelheti. E témakör áttekintést nyújt a Win32-alkalmazások telepítési és kezelési lehetőségeiről az Intune-ban, valamint a Win32-alkalmazásokkal kapcsolatos hibák elhárításával kapcsolatban.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e152e3dc5bc42545bf8bee8595b7bbca2fab0eb
ms.sourcegitcommit: 618c3076a7973b3b54ce3038ee007a33aa82efeb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51830117"
---
# <a name="intune-standalone---win32-app-management-public-preview"></a>Különálló Intune – Win32-alkalmazáskezelés (nyilvános előzetes verzió)

Az Intune különálló verziója több lehetőséget biztosít a Win32-alkalmazások kezelése terén. Bár a felhőhöz csatlakozó ügyfelek használhatják a Konfigurációkezelőt a Win32-alkalmazások kezeléséhez, a kizárólag Intune-nal rendelkező ügyfelek számára több lehetőség érhető el az üzletági (LOB) Win32-alkalmazások kezeléséhez. E témakör áttekintést nyújt a Win32-alkalmazások Intune-ban elérhető kezelési funkcióiról, valamint a hibaelhárítással kapcsolatos lehetőségekről.

## <a name="prerequisites-for-public-preview"></a>A nyilvános előzetes verzió használatának előfeltételei

- Windows 10, 1607-es vagy újabb verzió (Enterprise)
- A Windows 10-ügyfélnek: 
    - Azure Active Directory- (ADD) vagy hibrid Azure Active Directory-csatlakozással kell rendelkeznie, valamint
    - regisztrálva kell lennie az Intune-ban (MDM által felügyelt)
- A Windows-alkalmazások egyenkénti mérete a nyilvános előzetes verzióban nem haladhatja meg a 8 GB-ot. 

> [!NOTE]
> A Windows 10 1607-es verziójának Pro és Education kiadásai jelenleg tesztelés alatt állnak, ezért minden visszajelzést örömmel fogadunk.


## <a name="prepare-the-win32-app-content-for-upload"></a>A Win32-alkalmazás tartalmának előkészítése a feltöltéshez

Használja a [Microsoft Intune Win32-alkalmazások feltöltéséhez készült előkészítő eszközét](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) a Win32-alkalmazások előfeldolgozásához. A csomagolási eszköz *.intunewin* formátumba konvertálja az alkalmazástelepítési fájlokat. A csomagolási eszköz emellett észlel az Intune által megkövetelt bizonyos attribútumokat is, amelyeket az alkalmazástelepítés állapotának meghatározásához használ fel. Miután használta ezt az eszközt az alkalmazástelepítési mappában, létrehozhat egy Win32-alkalmazást az Intune-konzolon.

A [Microsoft Intune Win32-alkalmazások feltöltéséhez készült előkészítő eszközét](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) a GitHubról töltheti le.

### <a name="available-command-line-parameters"></a>Elérhető parancssori paraméterek 

|    **Parancssori paraméter**    |    **Leírás**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Súgó    |
|    `-c <setup_folder>`     |    Telepítőmappa az összes telepítőfájllal.    |
|   ` -s <setup_file>`     |    Telepítőfájl (például *setup.exe* vagy *setup.msi*).    |
|    `-o <output_folder>`     |    Kimeneti mappa a létrehozott *.intunewin* fájl számára.    |
|    `-q`       |    Csendes mód    |

### <a name="example-commands"></a>Példaparancsok

|    **Példaparancs**    |    **Leírás**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Ez a parancs megjeleníti az eszköz használatára vonatkozó információkat.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    Ez a parancs létrehozza az `.intunewin` fájlt a megadott forrásmappa és telepítőfájl alapján. Az MSI-telepítőfájlhoz az eszköz lekéri az Intune-hoz szükséges adatokat. Ha a `-q` van megadva, a parancs csendes módban fog futni, és ha a kimeneti fájl már létezik, felül fogja írni. Ha a kimeneti mappa még nem létezik, akkor automatikusan létrejön.    |

Létrehozásakor egy *.intunewin* fájlt minden olyan fájlok, a telepítés mappa almappa hivatkoznia kell. Ezután használja a relatív elérési út egy konkrét fájlt kell hivatkoznia. Például:

**Telepítő forrásmappája:** *c:\testapp\v1.0*<br>
**Licencfájl:** *c:\testapp\v1.0\licenses\license.txt*

Tekintse meg a *license.txt* fájl relatív elérési út használatával *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Win32-alkalmazás létrehozása, hozzárendelése és monitorozása

Az üzletági (LOB) alkalmazásokhoz hasonlóan Win32-alkalmazást is hozzáadhat a Microsoft Intune-hoz. Az ilyen alkalmazásokat általában házon belül írják, vagy egy külső féltől származnak. Az alábbi lépések útmutatást nyújtanak a Windows-alkalmazások Intune-hoz való hozzáadásához.

### <a name="step-1-specify-the-software-setup-file"></a>1. lépés: A szoftvertelepítő fájl megadása

1.  Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
2.  Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3.  Az **Intune** panelen válassza az **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** elemet.
4.  Az **Alkalmazás felvétele** panelen válassza a **Windows-alkalmazás (Win32) – előzetes verzió** lehetőséget a legördülő listából.

    ![Képernyőkép: Alkalmazás felvétele – Típus hozzáadása legördülő lista](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>2. lépés: Az alkalmazáscsomag-fájl feltöltése

1.  Az **Alkalmazás felvétele** panelen válassza az **Alkalmazáscsomag-fájl** lehetőséget egy fájl kiválasztásához. Megjelenik az Alkalmazáscsomag-fájl panel.

    ![Képernyőkép: Alkalmazáscsomag-fájl](./media/apps-win32-app-02.png)

2.  Az **Alkalmazáscsomag-fájl** panelen válassza a tallózás gombot. Ezt követően jelölje ki az *.intunewin* kiterjesztésű Windows-telepítőfájlt.
3.  Amikor végzett, válassza az **OK** gombot.

### <a name="step-3-configure-app-information"></a>3. lépés: Az alkalmazás adatainak konfigurálása

1.  Az alkalmazás konfigurálásához az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
2.  Az **Alkalmazás adatai** panelen konfigurálja az alábbi információkat. Lehetséges, hogy ezen a panelen néhány érték automatikusan ki lesz töltve.
    - **Név**: Itt adhatja meg az alkalmazás a Céges portálon megjelenő nevét. Ha ugyanazt az alkalmazásnevet kétszer adja meg, mindkét alkalmazás meg fog jelenni a céges portálon.
    - **Leírás**: Itt adhatja meg az alkalmazás leírását. A leírás megjelenik a Céges portálon.
    - **Gyártó**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Kategória**: Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, de egyénileg létrehozott kategóriát is megadhat. A kategóriákkal megkönnyítheti a felhasználók számára az alkalmazás megkeresését a Céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon**: Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím**: Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Az URL-cím megjelenik a Céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe**: Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Az URL-cím megjelenik a Céges portálon.
    - **Fejlesztő**: Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Igény esetén megadhatja az alkalmazás tulajdonosának nevét. Például **HR részleg**.
    - **Megjegyzések**: Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon**: Itt töltheti fel az alkalmazáshoz társított ikont. Ez az ikon jelenik meg az alkalmazásnál a Céges portálon böngésző felhasználók számára.
3.  Amikor végzett, válassza az **OK** gombot.

### <a name="step-4-configure-app-installation-details"></a>4. lépés: Az alkalmazás telepítési adatainak konfigurálása
1.  Az alkalmazás telepítési és eltávolítási parancsának konfigurálásához az **Alkalmazás felvétele** panelen válassza a **Program** elemet.
2.  Adja meg az alkalmazás telepítéséhez szükséges teljes telepítési parancssort. 

    Ha például az alkalmazás fájlneve a **MyApp123**, adja hozzá a következőt: `msiexec /i “MyApp123.msi”`

3.  Adja meg az alkalmazás eltávolításához szükséges teljes eltávolítási parancssort az alkalmazás GUID-értékei alapján. 

    Például így: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Az adott Win32-alkalmazás telepítését a **Felhasználó** vagy a **Rendszer** környezetben konfigurálhatja. A **Felhasználó** környezet csak az adott felhasználóra vonatkozik. A **Rendszer** környezet az adott, Windows 10-es rendszerű eszköz összes felhasználójára vonatkozik.
    >
    > A végfelhasználóknak nem kell bejelentkezniük az eszközön a Win32-alkalmazások telepítéséhez.

4.  Amikor végzett, válassza az **OK** gombot.

### <a name="step-5-configure-app-requirements"></a>5. lépés: Az alkalmazásokra vonatkozó követelmények konfigurálása

1.  Az alkalmazás telepítéséhez szükséges rendszerkövetelmények beállításához az **Alkalmazás felvétele** panelen válassza a **Követelmények** elemet.
2.  A **Követelmények** panelen konfigurálja az alábbi információkat. Lehetséges, hogy ezen a panelen néhány érték automatikusan ki lesz töltve.
    - **Operációs rendszer architektúrája**: Válassza ki az alkalmazás telepítéséhez szükséges architektúrákat.
    - **Minimális operációsrendszer-verzió**: Válassza ki az operációs rendszer verziószámát, amely minimumkövetelményként szükséges az alkalmazás telepítéséhez.
    - **Szükséges lemezterület (MB)**: Opcionálisan megadhatja, hogy a rendszermeghajtón mekkora szabad lemezterületnek kell rendelkezésre állnia az alkalmazás telepítéséhez.
    - **Szükséges fizikai memória (MB)**: Opcionálisan megadhatja, hogy mekkora fizikai memória (RAM) szükséges az alkalmazás telepítéséhez.
    - **Logikai processzorok szükséges minimális száma**: Opcionálisan megadhatja az alkalmazás telepítéséhez szükséges logikai processzorok minimális számát.
    - **Szükséges minimális processzorsebesség (MHz)**: Opcionálisan megadhatja az alkalmazás telepítéséhez szükséges minimális processzorsebességet.
3.  Amikor végzett, válassza az **OK** gombot.

### <a name="step-6-configure-app-detection-rules"></a>6. lépés: Az alkalmazásészlelési szabályok konfigurálása

1.  Az alkalmazás meglétének észleléséhez szükséges szabályok konfigurálásához az **Alkalmazás felvétele** panelen válassza az **Észlelési szabályok** elemet.
2.  A **Szabályok formátuma** mezőben adja meg, hogyan fogja észlelni a rendszer az alkalmazás meglétét. Választhatja az észlelési szabályok manuális konfigurálását, illetve egyéni szkriptet is használhat az alkalmazás meglétének észleléséhez. Legalább egy észlelési szabályt ki kell választani. 

    > [!NOTE]
    > Az **Észlelési szabályok** panelen, ha szeretne, több szabályt is hozzáadhat. Az alkalmazás észleléséhez az **összes** szabály feltételeinek teljesülnie kell.

    - **Észlelési szabályok manuális konfigurálása** – A következő szabálytípusok egyikét választhatja ki:
        1.  **MSI** – Jóváhagyás MSI-verzióellenőrzés alapján. Ezt a lehetőséget csak egyszer lehet hozzáadni. Ha ezt a szabálytípust választja, kétféle beállítás áll a rendelkezésére:
            - **MSI-termékkód** – Adjon meg egy érvényes MSI-termékkódot az alkalmazáshoz.
            - **MSI-termékverzió ellenőrzése** – Az **Igen** lehetőség kiválasztásával a rendszer az MSI-termékkód mellett az MSI-termékverziót is ellenőrzi.
        2.  **Fájl** – Ellenőrzés a fájl vagy mappa észlelése, dátuma, verziója vagy mérete alapján.
            - **Elérési út** – Az észlelendő fájlt vagy mappát tartalmazó mappa teljes elérési útja.
            - **Fájl vagy mappa** – Az észlelendő fájl vagy mappa.
            - **Észlelési módszer** – Válassza ki az alkalmazás meglétének ellenőrzéséhez használt észlelési módszer típusát.
            - **32 bites alkalmazással társítva 64 bites ügyfeleken** – Ha 64 bites ügyfeleken a „path” környezeti változókat 32 bites környezetben szeretné kibontani, válassza az **Igen** lehetőséget. A **Nem** (ez az alapértelmezett beállítás) kiválasztásakor a rendszer minden „path” változót 64 bites környezetben bontja ki a 64 bites ügyfeleken. A 32 bites ügyfelek mindig a 32 bites környezetet használják.
            
            **Példák a fájlalapú észlelésre**
            1.  Fájl meglétének ellenőrzése.
         
                ![Képernyőkép az észlelési szabály paneljéről – a fájl megléte](./media/apps-win32-app-03.png)
        
            2.  Mappa meglétének ellenőrzése.
         
                ![Képernyőkép az észlelési szabály paneljéről – a mappa megléte](./media/apps-win32-app-04.png)
        
        3. **Beállításjegyzék** – Ellenőrzés érték, sztring, egész szám vagy verzió alapján.
            - **Kulcs elérési útja** – Az észlelendő értéket tartalmazó beállításjegyzék-bejegyzés teljes elérési útja.
            - **Érték neve** – Az észlelendő beállításazonosító neve. Ha ez az érték üres, akkor az észlelés a kulcs alapján történik. A rendszer egy kulcs (alapértelmezett) értékét használja észlelési értékként, ha az észlelési módszer nem a fájl vagy a mappa meglétén alapul.
            - **Észlelési módszer** – Válassza ki az alkalmazás meglétének ellenőrzéséhez használt észlelési módszer típusát.
            - **32 bites alkalmazással társítva 64 bites ügyfeleken** – Ha a 32 bites beállításjegyzékben szeretne keresni a 64 bites ügyfeleken, válassza az **Igen** lehetőséget. A **Nem** (ez az alapértelmezett beállítás) kiválasztásakor a rendszer a 64 bites ügyfeleken a 64 bites beállításjegyzékben fog keresni. A 32 bites ügyfeleknél a keresés mindig a 32 bites beállításjegyzéket érinti.
            
            **Példák a beállításjegyzéken alapuló észlelésre**
            1.  A beállításkulcs meglétének ellenőrzése.
            
                ![Képernyőkép az észlelési szabály paneljéről – van beállításkulcs](./media/apps-win32-app-05.png)    
            
            2.  A beállításazonosító meglétének ellenőrzése (**az előzetes verzióban nem érhető el**).
        
                ![Képernyőkép az észlelési szabály paneljéről – van beállításazonosító](./media/apps-win32-app-06.png)    
        
            3.  A beállításazonosító sztring egyenlőségének ellenőrzése.
        
                ![Képernyőkép az észlelési szabály paneljéről – a beállításazonosító sztring egyenlő](./media/apps-win32-app-07.png)    
     
    - **Egyéni észlelési szkript alkalmazása** – Adja meg az alkalmazás észleléséhez használandó PowerShell-szkriptet. 
    
        1.  **Szkriptfájl** – Válasszon egy PowerShell-szkriptet, amely észleli majd az alkalmazás jelenlétét az ügyfélen. Az alkalmazást a rendszer akkor észleli, ha a szkript egy 0 értékű kilépési kódot ad vissza, és sztringértéket ír az STDOUT elembe.
        2.  **A szkript futtatása 32 bites folyamatként 64 bites ügyfeleken** – Ha az **Igen** lehetőséget választja, a szkriptet a rendszer a bejelentkezett végfelhasználó hitelesítő adataival futtatja. A **Nem** (ez az alapértelmezett beállítás) kiválasztásakor a szkript a rendszerkörnyezetben fut.
        3.  **Szkriptaláírás ellenőrzésének kényszerítése** – Az **Igen** lehetőség kiválasztásával ellenőrizheti, hogy a szkriptet egy megbízható gyártó írta-e alá, így a szkript figyelmeztetések és felszólítások megjelenítése nélkül fog futni. A szkript letiltás nélkül fog futni. A **Nem** (ez az alapértelmezett beállítás) kiválasztásakor a szkript végfelhasználói megerősítéssel, az aláírás ellenőrzése nélkül fut.
    
        Az Intune Sidecar ellenőrzi a szkript eredményeit. Beolvassa a szkript által a standard kimeneti (STDOUT) streambe írt értékeket, a standard hibastreamet (STDERR) és a kilépési kódot. Ha a szkript egyik értéke nem nulla, akkor a szkript futtatása meghiúsul, és az alkalmazásészlelési állapot nem települ. Ha a kilépési kód nulla, és az STDOUT elemben vannak adatok, akkor az alkalmazásészlelési állapot Telepítve lesz. 
    
        > [!NOTE]
        > Ha a szkript értéke 0, a végrehajtása sikeres volt. A második kimeneti csatorna alkalmazás észlelését jelzi – az STDOUT-adatok azt jelzik, hogy az alkalmazás megtalálható az ügyfélen. Most nem egy adott sztringet keresünk az STDOUT-ból.
    
3.  Miután hozzáadta a szabály(ok)at, válassza ki a **Hozzáadás** > **OK** lehetőséget.

### <a name="step-7-configure-app-return-codes"></a>7. lépés: Az alkalmazások visszatérési kódjainak konfigurálása

1.  Az **Alkalmazás felvétele** panelen válassza a **Visszatérési kódok** lehetőséget az alkalmazástelepítés újrapróbálkozási viselkedését vagy a telepítés utáni viselkedést meghatározó visszatérési kódok hozzáadásához. A visszatérési kód bejegyzéseit a rendszer alapértelmezés szerint hozzáadja az alkalmazás létrehozása során. További visszatérési kódokat is megadhat, és a meglévőket is módosíthatja. 
2.  A **Visszatérési kódok** panelen adjon hozzá további visszatérési kódokat, vagy módosítsa a meglévőket.
    - **Sikertelen** – Ez a visszaadott érték azt jelzi, hogy hiba történt az alkalmazás telepítése közben.
    - **Hardveres újraindítás** – A hardveres újraindítás visszatérési kódja nem engedi meg, hogy a további Win32-alkalmazások újraindítás nélkül legyenek telepíthetők az ügyfélen. 
    - **Szoftveres újraindítás** – A szoftveres újraindítás visszatérési kódja lehetővé teszi, hogy a következő Win32-alkalmazás az ügyfél újraindítása nélkül telepíthető legyen. Az aktuális alkalmazás telepítésének befejezéséhez újraindításra van szükség.
    - **Újrapróbálkozás** – Az újrapróbálkozás visszatérési kód háromszor kísérli meg az alkalmazás telepítését. Az egyes kísérletek közötti 5 percet vár. 
    - **Sikeres** – Ez a visszaadott érték azt jelzi, hogy az alkalmazás telepítése sikeresen megtörtént.
3.  Válassza ki az **OK** lehetőséget, miután bővítette vagy módosította a visszatérési kódok listáját.

### <a name="step-8-add-the-app"></a>8. lépés: Az alkalmazás hozzáadása

1.  Az **Alkalmazás hozzáadása** panelen ellenőrizze, hogy helyesen konfigurálta-e az alkalmazásadatokat.
2.  Az alkalmazást a **Hozzáadás** elem kiválasztásával töltheti fel az Intune-ba.

### <a name="step-9-assign-the-app"></a>9. lépés: Az alkalmazás hozzárendelése

1.  Az alkalmazás panelen válassza a **Hozzárendelések** elemet.
2.  Válassza a **Csoport hozzáadása** lehetőséget az alkalmazáshoz kapcsolódó **Csoport hozzáadása** ablaktábla megnyitásához.
3.  Az adott alkalmazáshoz válasszon egy **hozzárendelés-típust**:
    - **Regisztrált eszközök esetében elérhető**: A felhasználók a Céges portál alkalmazásban vagy a Céges portál webhelyen telepítik az alkalmazást.
    - **Szükséges**: A rendszer telepíti az alkalmazást a kiválasztott csoportok eszközeire.
    - **Eltávolítás**: A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.
4.  Válassza ki a **Tartalmazott csoportok** elemet, és rendelje hozzá a csoportokat, amelyek az alkalmazást fogják használni.
5.  Kattintson a **Hozzárendelés** ablaktáblán az **OK** gombra a belefoglalt csoportok kiválasztásának befejezéséhez.
6.  Ha ki szeretne zárni felhasználói csoportokat az alkalmazás-hozzárendelésből, válassza a **Csoportok kizárása** lehetőséget.
7.  A **Csoport hozzáadása** panelen kattintson az **OK** gombra.
8.  Az alkalmazás **Hozzárendelések** ablaktábláján kattintson a **Mentés** gombra.

Ezzel teljesítette a Win32-alkalmazás Intune-hoz történő hozzáadásának lépéseit. Az alkalmazás-hozzárendeléssel és monitorozással kapcsolatos további információ: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](https://docs.microsoft.com/intune/apps-deploy) és [Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban](https://docs.microsoft.com/intune/apps-monitor).

## <a name="install-required-and-available-apps-on-devices"></a>Kötelező és elérhető alkalmazások telepítése az eszközökön

A végfelhasználó megkapja a Windows bejelentési értesítéseit a kötelező és az elérhető alkalmazástelepítésekkel kapcsolatban. Az alábbi képen a bejelentési értesítések egy példája látható, amely szerint az alkalmazás telepítésének befejezéséhez újra kell indítani az eszközt. 

![Képernyőkép – Példa: Windows bejelentési értesítések alkalmazás telepítéséhez](./media/apps-win32-app-08.png)    

A következő kép arról értesíti a végfelhasználót, hogy alkalmazásmódosításokra kerül sor az eszközön.

![Képernyőkép – Példa: a végfelhasználó értesítése arról, hogy alkalmazásmódosításokra kerül sor az eszközön](./media/apps-win32-app-09.png)    

## <a name="troubleshoot-win32-app-issues"></a>A Win32-alkalmazások hibáinak elhárítása
Az ügynöknaplók általában a következő helyen érhetők el az ügyfélgépen: `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. A `CMTrace.exe` segítségével megtekintheti ezeket a naplófájlokat. A *CMTrace.exe* az [SCCM-ügyféleszközök](https://docs.microsoft.com/sccm/core/support/tools) közül tölthető le. 

![Képernyőkép – Az ügynöknaplók](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Néhány megfontolandó hibaelhárítási lépés
- Ellenőrizze a célcsoportkezelést, és győződjön meg arról, hogy az ügynök telepítve van az eszközön – egy olyan Win32-alkalmazás vagy PowerShell-szkript, amelynek csoport a célzottja, ügynöktelepítési szabályzatot hoz létre a biztonsági csoporthoz.
- Ellenőrizze az operációs rendszer verzióját – 1607-es vagy annál újabb Windows 10-re van szükség.  
- Ellenőrizze a Windows 10 termékváltozatát – a Windows 10 S és az S módban futó Windows-verziók nem támogatják az MSI-telepítést.

## <a name="next-steps"></a>További lépések

- További információk az alkalmazások Intune-hoz való hozzáadásáról: [Alkalmazások hozzáadása a Microsoft Intune-hoz](apps-add.md).
