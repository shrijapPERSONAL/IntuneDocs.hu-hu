---
title: "iOS-eszközök regisztrálása – az Apple Configurator és a Beállítási asszisztens"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt a céges tulajdonú iOS-eszközöknek az Apple Configurator és a Beállítási asszisztens használatával való regisztrálásáról."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>iOS-eszközök regisztrálása az Apple Configurator használatával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune támogatja a vállalat által birtokolt iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) segítségével történő regisztrálását. A céges regisztrálás Apple Configuratorral való beállításához az adott iOS-eszközt USB-csatlakozóval kell csatlakoztatni egy Mac számítógéphez. Az Apple Configurator használatával kétféle módon lehet regisztrálni az eszközt az Intune-ban:
- **Regisztrálás a Beállítási asszisztenssel** – ez a folyamat visszaállítja az eszközt gyári alaphelyzetbe, felkészíti az eszközt a Beállítási asszisztens futtatására, és telepíti a cég szabályzatait az eszköz új felhasználójának. Az iOS-eszközre alkalmazott szabályzatnak általában felhasználói affinitást kell tartalmaznia az Intune Céges portál alkalmazás használatának engedélyezése érdekében.
- **Közvetlen regisztrálás** – ez a folyamat nem állítja vissza az eszközt gyári alaphelyzetbe, és előre definiált szabályzattal regisztrálja azt. A módszer **felhasználói affinitás nélküli** eszközökkel használható.

>[!NOTE]
>Ezt a regisztrációs módszert nem lehet használni az [eszközregisztráció-kezelői](device-enrollment-manager-enroll.md) módszerrel.

Az iOS-eszközök regisztrálásának további lehetőségeiről [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md) című témakörben olvashat.

## <a name="prerequisites"></a>Előfeltételek

Az iOS-eszközök regisztrációjának beállítása előtt teljesítse az alábbi előfeltételeket:

- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- Fizikai hozzáférés iOS-eszközökhöz
- Eszközök sorozatszáma (lásd: [Az iOS-eszközök sorozatszámának megkeresése](https://support.apple.com//HT204308))
- USB csatlakozókábelek
- Mac PC [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) alkalmazással
- [Apple Configurator-sorozatszámok hozzáadása](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Regisztrálás a Beállítási asszisztenssel

### <a name="create-an-apple-configurator-profile-for-devices"></a>Apple Configurator-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt az Apple Configurator eszközzel regisztrált iOS-eszközök számára.

1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. **Az Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **AC-profilok** elemet.
3. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.
4. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.
5. A **Felhasználói affinitás** beállítással adja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül lesznek-e regisztrálva.

   - **Regisztrálás felhasználói affinitással** – Az eszközt össze kell kapcsolni egy felhasználóval a kezdeti beállítás során, majd engedélyezhető számára a vállalati adatok és e-mailek elérése. A felhasználói affinitást azoknál a felügyelt eszközöknél kell beállítani, amelyek felhasználók tulajdonában állnak, és a Céges portált kell rajtuk használni (például eszközök telepítéséhez).
   - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

6. A **Létrehozás** elemet választva mentse a profilt.

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-sorozatszámok hozzáadása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kövesse az alábbi lépéseket, ha sorozatszámokat szeretne hozzáadni az Intune-hoz [vállalati iOS-eszközök Apple Configuratorrel és a Beállítási asszisztenssel való regisztrálásakor](apple-configurator-setup-assistant-enroll-ios.md). A sorozatszámokat egyenként is hozzáadhatja, vagy feltölthet egy vesszővel tagolt értékekből álló (CSV-) fájlt, amely a sorozatszámokat tartalmazza. A sorozatszámok feltöltése után profilt rendelhet hozzájuk. A profil olyan felügyeleti beállításokat tartalmaz, amelyeket eszközökre alkalmazhat.

Az iOS-eszközök regisztrálásának további módjairól [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md) című témakörben olvashat.

**Apple Configurator-sorozatszámok hozzáadása az Intune-hoz**

1. Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv-fájlt). A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor. Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

    F7TLWCLBX196,eszköz adatai</br>
    DLXQPCWVGHMJ,eszköz adatai

2. Az Azure Portalon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
3. Az **Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **Apple Configurator-sorozatszámok** lehetőséget.
4. Az **Apple Configurator-sorozatszámok** panelen válassza a **Hozzáadás** elemet.
5. A **Sorozatszámok hozzáadása** panelen válassza ki az importált sorozatszámokhoz hozzáadandó profilt. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza az Adatok felülírása lehetőséget a meglévő azonosítókra, így az új adatok felülírják a jelenlegieket.
6. Keresse meg a sorozatszámokat tartalmazó .csv-fájlt, és válassza a **Hozzáadás** lehetőséget.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Profil hozzárendelése meghatározott sorozatszámokhoz

Az Intune-ban a profilok hozzárendelése az Azure Portal két különféle helyén is elvégezhető. A hozzárendelést végezheti Apple Configurator-profil vagy eszközök alapján.

#### <a name="assign-by-devices"></a>Hozzárendelés eszközök alapján
1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
3. Az **Apple Configurator-eszközök** panelen válassza ki azokat a sorozatszámokat, amelyekhez profilt szeretne rendelni, majd válassza a **Profil hozzárendelése** lehetőséget.
4. A **Profil hozzárendelése** panelen válassza ki a hozzárendelendő profilt, majd válassza a **Hozzárendelés** lehetőséget.

#### <a name="assign-by-profiles"></a>Hozzárendelés profilok alapján
1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. Válassza az **AC-profilok** elemet, majd válassza ki azt a profilt, amelyhez sorozatszámokat szeretne rendelni.
3. A profil nevét viselő panelen válassza a **Sorozatszámok** > **Hozzárendelés** lehetőséget.
4. Jelölje ki a profilhoz rendelni kívánt sorozatszámokat, majd kattintson a **Hozzárendelés** gombra.

### <a name="export-the-profile-to-ios-devices"></a>Profil exportálása iOS-es eszközökre
Miután létrehozta a profilt, és hozzárendelte a sorozatszámokat, ki kell exportálnia a profilt az Intune-ból URL-ként vagy az alább ismertetett formátumban. Ezt követően manuálisan importálhatja egy Mac gépen az Apple Configuratorba, és utána azzal telepítheti az eszközökre.

1. Az Intune-portál **Apple Configurator-regisztrációs profilok** paneljén válassza ki az exportálandó profilt.
2. A profil panelén válassza a **Profil exportálása** lehetőséget.
3. Csatlakoztassa az iOS-eszközt, és másolja a profil URL-címét az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). A címet később fel kell töltenie az Apple Configurator eszközbe az iOS-eszközök által használt Intune profil meghatározásához.

  Az alábbi eljárás során az Apple Configurator segítségével kell feltöltenie a profil URL-címét az Apple szolgáltatásába, és ezzel meghatározhatja az iOS-eszközök által használandó Intune-profilt.
4. Az Apple Configurator segítségével töltse fel a profil URL-címét az Apple szolgáltatásába, és ezzel meghatározhatja az iOS-eszközök által használandó Intune-profilt.
 1.  A Mac-számítógépen nyissa meg az **Apple Configurator 2** eszközt. A menüsávban válassza az **Apple Configurator 2**, majd a **Beállítások** elemet.
  > [!WARNING]
  > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. Az eszközön az **üdvözlőképernyőnek** kell látszania az eszköz csatlakoztatásakor.
  2. Válassza a **Beállítások** panelen a **Servers** (Kiszolgálók) elemet, majd az MDM-kiszolgálói varázsló elindításához válassza a „+” szimbólumot. Kattintson a **Tovább** gombra.
  3. Írja be a Beállítási asszisztens segítségével a Microsoft Intune-ban történő iOS-eszközregisztrációhoz megadott MDM-kiszolgáló **állomásnevét vagy URL-címét** (Host name or URL) és **regisztrációs URL-címét** (Enrollment URL) a megfelelő mezőkbe. Az Enrollment URL (Regisztrációs URL-cím) mezőnél az Intune-ból exportált regisztrációs profil URL-címét adja meg. Kattintson a **Tovább** gombra.  

    Ha a rendszer figyelmezteti, hogy nincs ellenőrizve a kiszolgáló URL-címe, nyugodtan figyelmen kívül hagyhatja. Kattintson minden megjelenő oldalon a **Next** (Tovább) gombra, amíg be nem fejeződik a varázsló.
  4.  Az iOS-mobileszközöket csatlakoztassa a Mac számítógéphez egy USB-adapterrel.
  > [!WARNING]
  > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. A Beállítási asszisztens indításakor az eszközön az **üdvözlőképernyőnek** kell látszania.
  5.  Válassza a **Prepare** (Előkészítés) lehetőséget. A **Prepare iOS Device** (iOS-eszköz előkészítése) panelen válassza a **Manual** (Manuális) elemet, majd a **Next** (Tovább) gombot.
  6. Az **Enroll in MDM Server** (Regisztrálás MDM-kiszolgálón) panelen válassza ki a létrehozott kiszolgáló nevét, majd válassza a **Next** (Tovább) gombot.
  7. A **Supervise Devices** (Eszközök felügyelete) panelen válassza ki a felügyelet szintjét, majd válassza a **Next** (Tovább) gombot.
  8. A **Create an Organization** (Szervezet létrehozása) panelen válassza ki a szervezetet az **Organization** mezőben, vagy hozzon létre új szervezetet, majd válassza a **Next** gombot.
  9. A **Configure iOS Setup Assistant** (iOS-es Beállítási asszisztens konfigurálása) panelen válassza ki a felhasználó számára megjelenő lépéseket, majd válassza a **Prepare** (Előkészítés) gombot. Ha a rendszer kéri, végezzen hitelesítést a megbízhatósági beállítások frissítése érdekében.  
  10. Az iOS-eszköz előkészítésének befejezésekor válassza le az USB-kábelt.  
6.  **Eszközök terjesztése**:
    Az eszközök most már készen állnak a vállalati regisztrációra. Kapcsolja ki az eszközöket, és ossza ki őket a felhasználóknak. Amikor a felhasználók bekapcsolják az eszközüket, elindul a Beállítási asszisztens.

## <a name="direct-enrollment"></a>Közvetlen regisztráció
Amikor közvetlenül regisztrál iOS-eszközöket az Apple Configurator használatával, anélkül regisztrálhat egy eszközt, hogy lekérné annak sorozatszámát. Az eszközt el is nevezheti azonosítási célból, mielőtt az Intune rögzítené az eszköz nevét a regisztráció alatt. A Céges portál alkalmazás nem támogatott a közvetlen módon regisztrált eszközökön. Ez az útmutató feltételezi, hogy az Apple Configurator 2.0 verzióját használja egy Mac-gépen.

1. Az Intune-portálon válassza az **Eszközök regisztrálása**, az **Apple-regisztráció**, majd az **AC-profilok** elemet.
2. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.
3. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.
4. A **Felhasználói affinitás** lehetőségnél válassza a **Regisztráció felhasználói affinitás nélkül** elemet annak biztosítása érdekében, hogy az eszköz ne legyen a felhasználóhoz kapcsolva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.
5. Válassz a **Létrehozás** elemet a profil mentéséhez.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>A profil exportálása iOS-eszközökre .mobileconfig fájlként

1. A **Profil exportálása** panelen töltse le a regisztrációs profilt az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), majd küldje le a profilt közvetlenül felügyeleti profilként egy csatlakoztatott iOS-eszközre. A művelethez nincs szükség a gyári beállítások visszaállítására.
2. Készítse elő az eszközt az Apple Configuratorral az alábbi lépések segítségével.
  1. Egy Mac számítógépen nyissa meg az Apple Configurator 2.0 eszközt.
  2. Csatlakoztassa az iOS-eszközt a Mac számítógéphez egy USB-kábellel. Zárja be a Fotók, az iTunes és más alkalmazásokat, amelyek megnyílnak az eszközhöz annak észlelésekor.
  3. Az Apple Configuratorban válassza ki a csatlakoztatott iOS-eszközt, majd kattintson az **Add** (Hozzáadás) gombra. Az eszközhöz adható lehetőségek a legördülő listában jelennek meg. Válassza a **Profilok** lehetőséget.
  4. A fájlkiválasztóval válassza ki az Intune-ból exportált .mobileconfig fájlt, majd válassza az **Add** (Hozzáadás) gombot. Ezzel a profil hozzá lesz adva az eszközhöz. Ha az eszköz Felügyeletlen, a telepítéshez az eszköz elfogadására van szükség.
3. Az alábbi lépések segítségével telepítse a profilt az iOS-eszközön. Az eszköz elvileg elvégezte a Beállítási asszisztens lépéseit, és készen áll a használatra. Ha a regisztrációba alkalmazástelepítések tartoznak, az eszközhöz be kell állítani egy Apple ID-t, mert az alkalmazástelepítésekhez Apple ID-vel kell bejelentkezni az Apple Store áruházba.
   1. Oldja fel az iOS-eszköz zárolását.
   2. A **Felügyeleti profil** **Profil telepítése** párbeszédpanelén kattintson a **Telepítés** gombra.
   3. Adja meg az Eszköz PIN-kódját vagy az Apple ID-t, ha szükséges.
   4. Fogadja el a **Figyelmeztetést**, és válassza a **Telepítés** gombot.
   5. Fogadja el a **Távoli figyelmeztetést**, és válassza a **Megbízható** gombot.
   6. Amikor a **Profil telepítve** mező megerősíti, hogy a profil Telepítve van, válassza a **Kész** gombot.

    4. Az iOS-eszközön nyissa meg a **Beállítások** alkalmazást, majd válassza az **Általános** > **Eszközkezelés** > **Felügyeleti profil** lehetőséget. Ellenőrizze, hogy a profiltelepítés szerepel-e a listán, valamint ellenőrizze az iOS-házirend korlátozásait és a telepített alkalmazásokat. A házirend-korlátozások és alkalmazások megjelenítése az eszközön akár 10 percet is igénybe vehet.

    5. Eszközök terjesztése. Az iOS-eszköz most már felügyelt, és regisztrálva van az Intune-nal.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>A Vállalati portál telepítése és használata a felhasználók által

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, végre kell hajtaniuk az alább ismertetett további lépéseket a Beállítási asszisztens befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.
