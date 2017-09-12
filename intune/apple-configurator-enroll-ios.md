---
title: "iOS-eszközök regisztrálása – az Apple Configurator és a Beállítási asszisztens"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt a céges tulajdonú iOS-eszközöknek az Apple Configurator és a Beállítási asszisztens használatával való regisztrálásáról."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b3ed7fe610f8101d90af044a8ff3849c57146c75
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>iOS-eszközök regisztrálása az Apple Configurator használatával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune támogatja az iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) segítségével történő regisztrálását. A céges regisztrálás Apple Configuratorral való beállításához az adott iOS-eszközt USB-csatlakozóval kell csatlakoztatni egy Mac számítógéphez. Az Apple Configurator használatával kétféle módon lehet regisztrálni az eszközt az Intune-ban:
- **Regisztráció a Beállítási asszisztenssel** – Visszaállítja a gyári beállításokat az eszközön, és felkészíti azt a Beállítási asszisztenssel történő regisztrálásra.
- **Közvetlen regisztrálás** – Ez a folyamat nem állítja vissza az eszközön a gyári beállításokat, és az iOS-beállításokon keresztül regisztrálja azt. Ez a módszer csak a **felhasználói affinitás nélküli** eszközöket támogatja.

Az Apple Configurator regisztrációs módszerei nem használhatók az [eszközregisztráció-kezelővel](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Előfeltételek

- Fizikai hozzáférés iOS-eszközökhöz
- [MDM-szolgáltató beállítása](mdm-authority-set.md)
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- Az eszközök sorozatszámai (csak a Beállítási asszisztenssel történő regisztrálás esetén)
- USB csatlakozókábelek
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) alkalmazást futtató Mac számítógép

## <a name="create-an-apple-configurator-profile-for-devices"></a>Apple Configurator-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza a regisztrálás során alkalmazott beállításokat. Ezek a beállítások csak egyszer kerülnek alkalmazásra. Az iOS-eszközöknek az Apple Configuratorral történő regisztrációjához használt regisztrációs profil létrehozásához kövesse az alábbi lépéseket.

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Válassza a **Eszközök regisztrálása** > **Apple-regisztráció** lehetőséget.
4. **Az Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **AC-profilok** elemet.
5. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.
6. Adminisztratív célból töltse ki a profilhoz tartozó **Név** és **Leírás** mezőt. Ezeket a felhasználók nem fogják látni. A Név mező felhasználásával dinamikus csoportot hozhat létre az Azure Active Directoryban. Használja a profilnevet az enrollmentProfileName paraméter meghatározásához, hogy ezt a regisztrációs profilt rendelhesse hozzá az eszközökhöz. További információk az Azure Active Directory-alapú dinamikus csoportokról.

  ![Képernyőkép a profil létrehozásáról, a felhasználói affinitással történő regisztrálás választásával](./media/apple-configurator-profile-create.png)

7. Adja meg a **Felhasználói affinitást**:
   - **Regisztrálás felhasználói affinitással** – Az eszközt a Beállítási asszisztens használatával össze kell kapcsolni egy felhasználóval, hogy elérhesse a vállalati adatokat és e-maileket. A felhasználói affinitás olyan felügyelet eszközöknél szükséges, amelyek felhasználók tulajdonában vannak, de a céges portált kell rajtuk használni például az alkalmazások telepítéséhez.
   - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni. Közvetlen regisztrálás esetén kötelező.

6. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="setup-assistant-enrollment"></a>Regisztrálás a Beállítási asszisztenssel

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-sorozatszámok hozzáadása

**Apple Configurator-sorozatszámok hozzáadása az Intune-hoz**

1. Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv-fájlt). A bal oldali oszlopban tüntesse fel a sorozatszámot, a jobb oldali oszlopban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor. Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

    F7TLWCLBX196,eszköz adatai</br>
    DLXQPCWVGHMJ,eszköz adatai

   Ismerje meg, [hogyan találhatja meg egy iOS-eszköz sorozatszámát](https://support.apple.com/HT204073).
2. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
3. Az **Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **Apple Configurator-eszközök** lehetőséget.
4. Válassza a **Hozzáadás** elemet.
5. Válassza ki az importált sorozatszámokhoz hozzáadandó **regisztrációs profilt**. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza a **Meglévő azonosítók adatainak felülírása** lehetőséget.
6. Keresse meg a sorozatszámokat tartalmazó .csv-fájlt, és válassza a **Hozzáadás** lehetőséget.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Profil újbóli hozzárendelése eszközök sorozatszámaihoz

Az Apple Configurator-regisztrációhoz szükséges iOS-sorozatszámokhoz azok importálása során hozzárendel egy regisztrációs profilt. Az Intune-ban a profilok hozzárendelése az Azure Portal két helyén is elvégezhető:
- **Apple Configurator-eszközök**
- **AC-profilok**

#### <a name="assign-from-apple-configurator-devices"></a>Hozzárendelés az Apple Configurator-eszközök panelről
1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
3. Az **Apple Configurator-eszközök** panelen válassza ki azokat a sorozatszámokat, amelyekhez profilt szeretne rendelni, majd válassza a **Profil hozzárendelése** lehetőséget.
4. A **Profil hozzárendelése** panelen válassza az **Új profil**, majd a **Hozzárendelés** lehetőséget.

#### <a name="assign-from-profiles"></a>Hozzárendelés a profilok közül
1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. Válassza az **AC-profilok** elemet, majd válassza ki azt a profilt, amelyet a sorozatszámokhoz szeretne rendelni.
3. A profil panelen válassza a **Hozzárendelt eszközök**, majd a **Hozzárendelés** lehetőséget.
4. Keresse meg a profilhoz hozzárendelni kívánt eszközök sorozatszámait a szűrő segítségével, válassza ki az eszközöket, majd válassza a **Hozzárendelés** lehetőséget.

### <a name="export-the-profile"></a>Profil exportálása
Miután létrehozta a profilt és hozzárendelte a sorozatszámokat, egy URL-címként exportálnia kell a profilt az Intune-ból. Ezt követően az eszközökön történő telepítéshez importálja ezt a profilt az Apple Configuratorban egy Mac számítógépen.

1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása** > Apple-regisztráció** > **AC-profilok** lehetőséget, majd válassza ki az exportálni kívánt profilt.
2. A profil panelén válassza a **Profil exportálása** lehetőséget.
3. Másolja a profil URL-címét a vágólapra. A címet később hozzáadhatja az Apple Configuratorban az iOS-eszközök által használt Intune-profil meghatározásához.

  Ezt követően importálja ezt a profilt az Apple Configuratorban az alábbi eljárással, hogy meghatározza az iOS-eszközök által használt Intune-profilt.

### <a name="enroll-devices-with-setup-assistant"></a>Eszközök regisztrálása a Beállítási asszisztenssel

1.  A Mac-számítógépen nyissa meg az **Apple Configurator 2** eszközt. A menüsávban válassza az **Apple Configurator 2**, majd a **Beállítások** elemet.
  > [!WARNING]
  > A regisztrációs folyamat során az eszközök visszaállnak a gyári beállításokra. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. Az eszközön az **üdvözlőképernyőnek** kell látszania az eszköz csatlakoztatásakor.

2. Válassza a **Beállítások** panelen a **Servers** (Kiszolgálók) elemet, majd az MDM-kiszolgálói varázsló elindításához válassza a „+” szimbólumot. Kattintson a **Tovább** gombra.
3. Írja be a Beállítási asszisztens segítségével a Microsoft Intune-ban történő iOS-eszközregisztrációhoz megadott MDM-kiszolgáló **állomásnevét vagy URL-címét** (Host name or URL) és **regisztrációs URL-címét** (Enrollment URL) a megfelelő mezőkbe. Az Enrollment URL (Regisztrációs URL-cím) mezőnél az Intune-ból exportált regisztrációs profil URL-címét adja meg. Kattintson a **Tovább** gombra.  

  Ha a rendszer figyelmezteti, hogy nincs ellenőrizve a kiszolgáló URL-címe, nyugodtan figyelmen kívül hagyhatja. Kattintson minden megjelenő oldalon a **Next** (Tovább) gombra, amíg be nem fejeződik a varázsló.
4.  Az iOS-mobileszközöket csatlakoztassa a Mac számítógéphez egy USB-adapterrel.
5.  Válassza a **Prepare** (Előkészítés) lehetőséget. A **Prepare iOS Device** (iOS-eszköz előkészítése) panelen válassza a **Manual** (Manuális) elemet, majd a **Next** (Tovább) gombot.
6. Az **Enroll in MDM Server** (Regisztrálás MDM-kiszolgálón) panelen válassza ki a létrehozott kiszolgáló nevét, majd válassza a **Next** (Tovább) gombot.
7. A **Supervise Devices** (Eszközök felügyelete) panelen válassza ki a felügyelet szintjét, majd válassza a **Next** (Tovább) gombot.
8. A **Create an Organization** (Szervezet létrehozása) panelen válassza ki a szervezetet az **Organization** mezőben, vagy hozzon létre új szervezetet, majd válassza a **Next** gombot.
9. A **Configure iOS Setup Assistant** (iOS-es Beállítási asszisztens konfigurálása) panelen válassza ki a felhasználó számára megjelenő lépéseket, majd válassza a **Prepare** (Előkészítés) gombot. Ha a rendszer kéri, végezzen hitelesítést a megbízhatósági beállítások frissítése érdekében.  
10. Az iOS-eszköz előkészítésének befejezésekor válassza le az USB-kábelt.  

### <a name="distribute-devices"></a>Eszközök terjesztése
Az eszközök most már készen állnak a vállalati regisztrációra. Kapcsolja ki az eszközöket, és ossza ki őket a felhasználóknak. Amikor a felhasználók bekapcsolják az eszközüket, elindul a Beállítási asszisztens.

Miután a felhasználók megkapják az eszközeiket, el kell végezniük a Beállítási asszisztens lépéseit. A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez.

## <a name="direct-enrollment"></a>Közvetlen regisztráció
Amikor közvetlenül regisztrál iOS-eszközöket az Apple Configurator használatával, anélkül regisztrálhat egy eszközt, hogy lekérné annak sorozatszámát. Az eszközt el is nevezheti azonosítási célból, mielőtt az Intune rögzítené az eszköz nevét a regisztráció alatt. A Céges portál alkalmazás nem támogatott a közvetlen módon regisztrált eszközökön. A művelethez nincs szükség a gyári beállítások visszaállítására.

Nem telepíthetők a felhasználói kapcsolatot igénylő alkalmazások, többek között az üzletági alkalmazások telepítéséhez használt Céges portál alkalmazás sem.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>A profil exportálása iOS-eszközökre .mobileconfig fájlként
1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. A **Profil exportálása** panelen töltse le a regisztrációs profilt az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), majd küldje le a profilt az iOS-eszközökre közvetlenül, felügyeleti profilként.
4. Készítse elő az eszközt az Apple Configuratorral az alábbi lépések segítségével.
  1. Egy Mac számítógépen nyissa meg az Apple Configurator 2.0 eszközt.
  2. Csatlakoztassa az iOS-eszközt a Mac számítógéphez egy USB-kábellel. Zárja be a Fotók, az iTunes és más alkalmazásokat, amelyek megnyílnak az eszközhöz annak észlelésekor.
  3. Az Apple Configuratorban válassza ki a csatlakoztatott iOS-eszközt, majd kattintson az **Add** (Hozzáadás) gombra. Az eszközhöz adható lehetőségek a legördülő listában jelennek meg. Válassza a **Profilok** lehetőséget.
  4. A fájlkiválasztóval válassza ki az Intune-ból exportált .mobileconfig fájlt, majd válassza az **Add** (Hozzáadás) gombot. Ezzel a profil hozzá lesz adva az eszközhöz. Ha az eszköz Felügyeletlen, a telepítést el kell fogadni az eszközön.
5. Az alábbi lépések segítségével telepítse a profilt az iOS-eszközön. Az eszköz elvileg elvégezte a Beállítási asszisztens lépéseit, és készen áll a használatra. Ha a regisztrációba alkalmazástelepítések tartoznak, az eszközhöz be kell állítani egy Apple ID azonosítót, mert az alkalmazástelepítésekhez ezzel kell bejelentkezni az Apple Store áruházba.
   1. Oldja fel az iOS-eszköz zárolását.
   2. A **Felügyeleti profil** **Profil telepítése** párbeszédpanelén kattintson a **Telepítés** gombra.
   3. Ha szükséges, adja meg az eszköz PIN-kódját vagy az Apple ID azonosítót.
   4. Fogadja el a **Figyelmeztetést**, és válassza a **Telepítés** gombot.
   5. Fogadja el a **Távoli figyelmeztetést**, és válassza a **Megbízható** gombot.
   6. Amikor a **Profil telepítve** mező megerősíti, hogy a profil Telepítve van, válassza a **Kész** gombot.

6. Az iOS-eszközön nyissa meg a **Beállítások** alkalmazást, majd válassza az **Általános** > **Eszközkezelés** > **Felügyeleti profil** lehetőséget. Ellenőrizze, hogy a profiltelepítés szerepel-e a listán, valamint ellenőrizze az iOS-házirend korlátozásait és a telepített alkalmazásokat. A házirend-korlátozások és alkalmazások megjelenítése az eszközön akár 10 percet is igénybe vehet.

7. Eszközök terjesztése. Az iOS-eszköz most már felügyelt, és regisztrálva van az Intune-ban.
