---
title: iOS-eszközök regisztrálása – Készülékregisztrációs program
titleSuffix: Microsoft Intune
description: Céges tulajdonú iOS-es eszközök regisztrálása az Apple készülékregisztrációs programjával (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: db9f15fd021cecc3f160e85be7a1a6cb7d1656a6
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897646"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Beállíthatja az Apple keretében vásárolt iOS-eszközök regisztrálása az Intune- [Készülékregisztrációs Program (DEP)](https://deploy.apple.com). A DEP lehetővé teszi nagy számú eszközt regisztrálni anélkül, hogy kézbe venné őket. Eszközök, például iPhone-okhoz és Ipadekhez közvetlenül a felhasználók számára is szállításra. Amikor a felhasználó bekapcsolja az eszközt, a Beállítási asszisztens az előre konfigurált beállítások szerint fut, és regisztrálja az eszközt a felügyeleti szolgáltatásban.

DEP-regisztráció engedélyezéséhez az Intune- és az Apple DEP-portált is használnia kell. Ahhoz, hogy az eszközök felügyeletét az Intune-hoz rendelhesse, szükség van a sorozatszámok vagy a beszerzési rendelésszámok listájára. Olyan DEP-regisztrációs profilokat hoz létre, amelyek tartalmazzák a regisztráció során az eszközre vonatkozó beállításokat.

DEP-regisztráció egyébként nem működik együtt a [készülékregisztráció-kezelő](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>A felügyelt mód ismertetése
Az Apple az iOS 5-tel vezette be a felügyelt módot. A felügyelt módon futtatott iOS-eszközök (készülékek) működése nagyobb mértékben felügyelhető. Mint ilyen akkor különösen hasznos a vállalat által birtokolt eszközök. Az Intune az Apple készülékregisztrációs program (DEP) keretében biztosít lehetőséget az eszközök felügyelt módú üzemeltetésének beállítására. 

A nem felügyelt DEP-eszközök támogatása megszűnt az iOS 11-ben. Az iOS 11-es és újabb verzióiban a DEP-konfigurációval rendelkező eszközöknek mindig felügyeltnek kell lenniük. Egy későbbi iOS-kiadásban a DEP is_supervised jelölőjét nem veszi figyelembe a rendszer.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Előfeltételek
- [Apple készülékregisztrációs program](http://deploy.apple.com) keretében vásárolt eszközök
- [Mobileszköz-felügyelet (MDM) szolgáltatóként](mdm-authority-set.md)
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Apple DEP-token beszerzése

Az iOS-eszközök DEP-regisztrációjához először is egy Apple-től származó DEP-tokenre (.p7m) van szükség. Ez a token (jogkivonat) teszi lehetővé az Intune számára a vállalat által birtokolt DEP-eszközök adatainak szinkronizálását. Azt is engedélyezi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és eszközöket rendeljen ezen profilokhoz.

A DEP-tokent az Apple DEP-portálon hozhatja létre. Szintén a DEP-portál használatával rendelheti hozzá az eszközök felügyeletét az Intune-hoz.

> [!NOTE]
> Ha törli a tokent a klasszikus Intune-portálról az Azure-ba történő migrálás előtt, előfordulhat, hogy az Intune visszaállít egy korábban törölt Apple DEP-tokent. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>1. lépés Töltse le a nyilvános kulcsú Intune-tanúsítványt, amelyre szükség van a token létrehozásához.

1. Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > **Hozzáadás** elemet.

    ![Szerezzen be egy készülékregisztrációs programbeli tokent.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Engedélyezze a Microsoftnak az **Elfogadom** lehetőség választásával a felhasználó- és eszközadatok Apple-nek való elküldését.

   ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Kattintson a **Nyilvános kulcs letöltése** elemre a titkosításikulcs-fájl (.pem) letöltéséhez és helyi mentéséhez. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>2. lépés Töltsön le a kulcsa segítségével egy tokent az Apple-től.

1. A **Token létrehozása az Apple Készülékregisztrációs programjában** elemre kattintva nyissa meg az Apple Központi Telepítési Program portálját, és jelentkezzen be a cége Apple-azonosítójával. A későbbiekben ezt az Apple ID-t használhatja a DEP-token megújításához.
2.  Az Apple [Központi Telepítési Program portálján ](https://deploy.apple.com) válassza a**Készülékregisztrációs program** **Első lépések** elemét.

3. A **Kiszolgálók kezelése** lapon válassza az **MDM-kiszolgáló hozzáadása** lehetőséget.
4. Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, A neve vagy URL-címét a Microsoft Intune-kiszolgáló nem.

5. Megjelenik a **Hozzáadás:&lt;Kiszolgálónév&gt;** párbeszédablak, és kéri **a nyilvános kulcs feltöltését**. Válassza ki **fájl kiválasztása...** a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

6. Válassza a **Deployment Programs** (Telepítési programok) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget.
7. Az **Eszközök kiválasztásának szempontja** alatt adja meg az eszközök azonosításának módját:
    - **Sorozatszám**
    - **Sorszám**
    - **CSV-fájl feltöltése**.

   ![Képernyőkép – Eszközök kiválasztásának beállítása: sorozatszám alapján. Választott tevékenység: hozzárendelés kiszolgálóhoz. Kiszolgálónév megadása.](./media/enrollment-program-token-specify-serial.png)

8. A **Választott tevékenység** területen jelölje ki a **Hozzárendelés kiszolgálóhoz** elemet, válassza Microsoft Intune-hoz megadott &lt;Kiszolgálónevet&gt;, majd kattintson az **OK** gombra. Az Apple-portál az Intune-kiszolgálóhoz rendeli a megadott eszközök kezelését, majd megjeleníti a **Hozzárendelés kész** üzenetet.

   Az Apple-portál **Központi telepítési programok** &gt; **Készülékregisztrációs program** &gt; **Hozzárendelési előzmények** menüpontjában jeleníthető meg az eszközök és a hozzájuk tartozó MDM-kiszolgálók listája.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>3. lépés. Mentse a token létrehozásához használt Apple ID-t.

Az Azure-beli Intune-portálon adja meg az Apple ID azonosítót későbbi felhasználásra.

![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>4. lépés. Töltse fel a tokent, és válassza ki a hatókörcímkék.

1. Az a **Apple-token** mezőben keresse meg a tanúsítványfájlt (.pem), válassza a **nyílt**.
2. Ha a alkalmazni kívánt [címkék hatókör](scope-tags.md) a DEP-token, válassza a **hatókör (címkék)**, és válassza ki a kívánt hatókörcímkék. Hatókörcímkék egy jogkivonatot a alkalmazni örökli profilokat, és ezt a jogkivonatot a hozzáadott eszközök.
3. Válassza a **Létrehozás** lehetőséget.

A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével. Az Intune automatikusan szinkronizálja az Apple-lel a regisztrációs programfiók adatait.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása

Most, hogy telepítette a jogkivonatot, létrehozhatja a regisztrációs profilt a DEP-eszközökhöz. A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

> [!NOTE]
> Eszköz le lesz tiltva, ha nem elegendő egy VPP-token céges portál-licenccel, vagy ha a jogkivonat lejárt. Az Intune jelenít meg riasztást, ha a jogkivonat érvényessége hamarosan lejár vagy licencek kevés.
 

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** elemet.
2. Válasszon egy tokent, és válassza a **Profilok**, majd a **Profil létrehozása** lehetőséget.

    ![Készítsen egy képernyőképet a profilról.](./media/device-enrollment-program-enroll-ios/image04.png)

3. A **Profil létrehozása** panelen adminisztrációs célból adja meg a profil **Nevét** és **Leírását**. A felhasználók nem látják ezeket az adatokat. A **Név** mező felhasználásával dinamikus csoportot hozhat létre az Azure Active Directoryban. Használja a profilnevet az enrollmentProfileName paraméter meghatározásához, hogy ezzel a regisztrációs profillal rendelhesse hozzá az eszközöket. További információk az [Azure Active Directory-alapú dinamikus csoportokról](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![A profil neve és leírása.](./media/device-enrollment-program-enroll-ios/image05.png)

4. A **Felhasználói affinitást** aszerint állítsa be, hogy a profilhoz tartozó eszközöket hozzárendelt felhasználóval vagy anélkül szükséges-e regisztrálni.
    - **Regisztráció felhasználói affinitással** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek a felhasználók tulajdonában vannak, de egyes szolgáltatásokhoz, például alkalmazások telepítéséhez, a Céges portált kívánják használni. Ha ADFS van használatban, és a **Hitelesítés a Céges portállal a Beállítási asszisztens helyett** **Nem** értékre van állítva, akkor a [WS-Trust 1.3 Felhasználónév/Vegyes végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) szükséges.

    - **Regisztráció felhasználói affinitás nélkül** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek nincsenek egy adott felhasználóhoz társítva. Ezt a lehetőséget olyan eszközökhöz használja, amelyek a helyi felhasználói adatokhoz való hozzáférés nélkül végeznek feladatokat. Egyes alkalmazások, mint például a Céges portál alkalmazás, nem működnek.

5. Ha úgy döntött **felhasználói affinitással való regisztrálást**, a felhasználók számára az Apple beállítási asszisztens helyett a céges portál a hitelesítéshez.

    ![Végezzen hitelesítést a Céges portállal.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Ha az alábbiak valamelyikét szeretné elvégezni, állítsa a **Hitelesítés a Céges portállal a Beállítási asszisztens helyett** értékét az **Igen** lehetőségre.
    >    - Többtényezős hitelesítés használata
    >    - A felhasználók figyelmeztetése a jelszó módosítására az első bejelentkezéskor
    >    - A felhasználók figyelmeztetése a lejárt jelszó helyetti új jelszó kérésére a regisztráció során
    >
    > Ezek az Apple Beállítási asszisztenssel végzett hitelesítéskor nem támogatottak.

6. Ha úgy döntött **Igen** a **hitelesítés az Apple beállítási asszisztens helyett a céges portál**, a Volume Purchase Program (VPP) token használatával automatikusan telepíteni a vállalati portál az eszközön. Ebben az esetben a felhasználónak nem kell megadnia egy Apple ID azonosítóját. A Céges portál VPP-jogkivonattal való telepítéséhez válasszon egy jogkivonatot a **Céges portál telepítése a VPP-vel** résznél. Fontos, hogy a jogkivonat ne járjon le, és hogy elég eszközlicenccel rendelkezzen a Céges portál alkalmazáshoz. Ha a jogkivonat lejár, illetve licencek elfogy, az Intune inkább telepíti az App Store vállalati portál, és kérni fogja az Apple ID azonosítóját.

    ![Képernyőkép a céges portál telepítése VPP.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Ha úgy döntött, hogy egy token **céges portál telepítése a VPP-**, zárolhatja az eszközt egyetlen alkalmazás mód (pontosabban a céges portál alkalmazás) jobb a beállítási asszisztens befejezése után. Ennek a lehetőségnek a beállításához válassza az **Igen** értéket a **Céges portál futtatása egyalkalmazásos módban a hitelesítésig** beállításhoz. Az eszköz használatához a felhasználónak először hitelesítenie kell magát a Céges portál használatával.
    Ez a funkció csak akkor támogatott iOS 11.3.1-es és újabb verziók.

   ![Egyetlen alkalmazás mód képernyőképe.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

8. Válasszon **Eszközfelügyeleti beállítások** , és adja meg, ha a jelen profilt használó felügyelt eszközök.

    ![Az Eszközkezelési beállítások képernyőképe.](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    A **felügyelt** eszközök esetében több felügyeleti lehetőséget érhet el, és az Aktiválási zár funkció alapértelmezés szerint le van tiltva. A Microsoft javasolja, hogy a DEP használatával üzemeltetés lehetővé tételéhez a felügyelt mód, különösen akkor, ha nagy számú iOS-eszközökre telepít.

    A rendszer kétféle módon is tudatja a felhasználókkal, hogy az eszközük felügyelet alatt áll:

   - A zárolási képernyő szerint: "Az iPhone-on a Contoso kezeli."
   - A **beállítások** > **általános** > **kapcsolatos** képernyő szerint: "Ez egy felügyelt iPhone. A Contoso figyelheti az internetes forgalmat és megállapíthatja a készülék helyét.” figyelmeztetés.

     > [!NOTE]
     > A felügyelet nélkül regisztrált eszközöket csak az Apple Configurator segítségével tudja átállítani felügyelt eszközzé. Az eszköz ily módon való átállításához csatlakoztatnia kell az iOS-eszközt egy Mac számítógéphez USB-kábellel. Ezzel kapcsolatban az [Apple Configurator dokumentációjában](http://help.apple.com/configurator/mac/2.3) talál további információkat.

9. Válassza ki, ha azt szeretné, ezt a profilt használó eszközök esetében zárolt regisztráció. A **Zárolt regisztráció** letiltja azokat az iOS-beállításokat a **Beállítások** menüből, amelyek segítségével eltávolítható a felügyeleti profil. Az eszköz regisztrálása után ez a beállítás nélkül az eszköz adatainak törlésekor nem módosítható. A zárolt regisztrációjú eszközökön a **Felügyelt** felügyeleti módot az *Igen* értékre kell beállítani. 

10. Adja meg, ha szeretné ezt a profilt használó eszközök **szinkronizálást számítógépekkel**. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

11. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta az előző lépésben, válasszon egy importálandó Apple Configurator-tanúsítványt.

12. Megadhatja a rendszer automatikusan alkalmazza, amikor regisztrálják eszközök elnevezési formátum. Hozzon létre egy elnevezési sablont, válassza a **Igen** alatt **eszköz neve sablon alkalmazása**. Ezt követően a a **eszköz neve a sablon** adja meg a jelen profilt használó nevét használni kívánt sablont. Megadhatja, hogy a sablon formátuma, amely tartalmazza az eszköz típusa és sorozatszáma.

13. Válassza az **OK** gombot.

14. Válasszon **beállítási asszisztens testreszabása** a következő profilbeállítások konfigurálásához: ![A beállítási asszisztens testreszabása.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Részlegbeállítások | Leírás |
    |---|---|
    | <strong>Részleg neve</strong> | Akkor jelenik meg, ha a felhasználó az aktiválás során a <strong>Konfiguráció névjegye</strong> elemre koppint. |
    |    <strong>Részleg telefonszáma</strong>     | Akkor jelenik meg, ha a felhasználó az aktiválás során a <strong>Segítségre van szüksége?</strong> gombra kattint. |

  Ha szeretné az eszközt a beállítási asszisztens képernyők elrejtése a felhasználói telepítés során.
  - Ha az **Elrejtés** lehetőséget választja, az adott képernyő nem fog megjelenni a beállítás során. Az eszköz beállítását követően a felhasználó a **Beállítások** menüben továbbra is beállíthatja az érintett funkciót.
  - Ha a **Megjelenítés** lehetőséget választja, az adott képernyő megjelenik a beállítás során. A felhasználó egyes esetekben átugorhat egy-egy képernyőt anélkül, hogy bármit is tenne. A kihagyott funkciókat később az eszköz **Beállítások** menüjében állíthatja be. 


    | Beállítási asszisztens képernyőinek beállításai | Ha a **Megjelenítés** lehetőséget választja, a telepítés során az eszköz... |
    |------------------------------------------|------------------------------------------|
    | <strong>PIN-kód</strong> | Elkéri a felhasználótól a PIN-kódot. Mindig szükség van PIN-kód nem biztonságos eszközök esetében, kivéve, ha van elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt). |
    | <strong>Helyalapú szolgáltatások</strong> | Elkéri a felhasználó tartózkodási helyét. |
    | <strong>Visszaállítás</strong> | Megjeleníti az **Alkalmazások és adatok** képernyőt. Ezen a képernyőn az eszköz beállításakor a felhasználónak lehetősége van adatok visszaállítására vagy átvitelére az iCloudos biztonsági mentésből. |
    | <strong>iCloud és Apple ID</strong> | Lehetőséget nyújt a felhasználónak arra, hogy bejelentkezzen az **Apple ID**-jével, és használja az **iCloud** szolgáltatást.                         |
    | <strong>Feltételek és kikötések</strong> | Felkéri a felhasználót, hogy fogadja el az Apple használati feltételeit. |
    | <strong>Touch ID</strong> | Lehetőséget nyújt a felhasználónak ujjlenyomat-azonosítás beállítására az eszközön. |
    | <strong>Apple Pay</strong> | Lehetőséget nyújt a felhasználónak az Apple Pay beállítására az eszközön. |
    | <strong>Nagyítás</strong> | Lehetőséget nyújt a felhasználónak a képernyő nagyítására az eszköz beállításakor. |
    | <strong>Siri</strong> | Lehetőséget nyújt a felhasználónak a Siri beállítására. |
    | <strong>Diagnosztikai adatok</strong> | Megjeleníti a **Diagnosztika** képernyőt. Ezen a képernyőn a felhasználó diagnosztikai adatokat küldhet az Apple-nek. |
    | <strong>Megjeleníti a képviselő hangvételét</strong> | Lehetővé teheti a felhasználó, kapcsolja be a megjelenítendő képviselő hangvételét. |
    | <strong>Adatvédelem</strong> | Az adatvédelmi képernyő megjelenítése a felhasználónak. |
    | <strong>Android-áttelepítés</strong> | A felhasználónak, elvégezhető a migrálás egy Android-eszközön az a dátum. |
    | <strong>iMessage és a facetime engedélyezése</strong> | Lehetővé teheti a felhasználó iMessage és FaceTime beállítani. |
    | <strong>Előkészítés</strong> | Bevezetési tájékoztató képernyők felhasználói képzés, például fedőlap és többfeladatos feldolgozáshoz és a vezérlőközpont megjelenítése. |
    | <strong>Tekintse meg a Migrálás</strong> | Lehetővé teheti a felhasználó, eszköz tekintse meg az adatok áttelepíthetők. |
    | <strong>Képernyő idő</strong> | A képernyő idő képernyő megjelenítéséhez. |
    | <strong>Szoftverfrissítés</strong> | A kötelező frissítés képernyő megjelenítéséhez. |
    | <strong>SIM-telepítő</strong> | Lehetővé teheti a felhasználó mobil csomag hozzáadásához. |

15. Válassza az **OK** gombot.

16. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az eszközei felügyeletére, szinkronizálhatja az Intune-t az Apple-lel, hogy megtekinthesse a felügyelt eszközöket az Azure-beli Intune-portálon.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, válasszon egy tokent a listából, majd válassza az **Eszközök** > **Szinkronizálás** lehetőséget. ![Képernyőkép – a Készülékregisztrációs programba felvett eszközök és a szinkronizálás hivatkozás.](./media/device-enrollment-program-enroll-ios/image06.png)

   Kövesse az Apple elfogadható regisztrációs programforgalomra vonatkozó feltételeinek, az Intune a következő céljából korlátozásokat írja elő:
   - Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune beolvassa az Intune-hoz csatlakoztatott Apple MDM-kiszolgálóhoz rendelt sorozatszámok frissített teljes listáját. Ha olyan DEP-eszköz törlése az Intune-portálról a DEP-portálon az Apple MDM-kiszolgáló a ki nem osztott kell lennie. Ha még nincs hozzá nem rendelt, azt nem lehet kérdezve az Intune mindaddig, amíg a teljes szinkronizálás futtatása.   
   - A szinkronizálás futtatása automatikusan történik 24 óránként. A **Szinkronizálás** gombra kattintva is végezhet szinkronizálást (legfeljebb 15 percenként egyszer). Az összes szinkronizálási kérelemnek 15 percen belül kell befejeződnie. A szinkronizálás befejeződéséig a **Szinkronizálás** gomb letiltott. A szinkronizálás frissíti a meglévő eszközök állapotát, és a importálja az Apple MDM-kiszolgálóhoz rendelt új eszközöket.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Regisztrálási profil eszközökhöz rendelése
Ahhoz, hogy egy eszközt regisztrálni lehessen, először hozzá kell rendelni egy regisztrációs programprofilt.

>[!NOTE]
>A profilokhoz sorozatszámok is hozzárendelhetők az **Apple-sorozatszámok** panelen.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, és válasszon egy tokent a listából.
2. Válassza az **Eszközök** lehetőséget, válasszon eszközöket a listából, majd válassza a **Profil hozzárendelése** elemet.
3. A **Profil hozzárendelése** területen válasszon egy profilt az eszközökhöz, majd válassza a **Hozzárendelés** lehetőséget.

### <a name="assign-a-default-profile"></a>Alapértelmezett profil hozzárendelése

Választhat egy alapértelmezett profilt, amelyet a rendszer az adott tokennel regisztráló összes eszközre alkalmaz.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, és válasszon egy tokent a listából.
2. Válassza az **Alapértelmezett profil beállítása** lehetőséget, válasszon egy profilt a legördülő listából, majd válassza a **Mentés** lehetőséget. A választott profil alkalmazva lesz az adott tokennel regisztráló összes eszközre.

## <a name="distribute-devices"></a>Eszközök terjesztése
Az eddigiekben engedélyezte az eszközfelügyeletet és a szinkronizálást az Apple és az Intune között, valamint a DEP-eszközök regisztrálása céljából hozzárendelt egy profilt. Az eszközök ekkor már kioszthatók a felhasználóknak. Felhasználói affinitással rendelkező eszközök esetén minden felhasználóhoz hozzá kell rendelni egy Intune-licencet. A felhasználói affinitás nélküli eszközökhöz licenc szükséges. Egy aktivált eszközön nem lehet alkalmazni egy regisztrációs profilt, amíg a rendszer törölné az eszközt.

Lásd: [iOS-eszköz regisztrálása az Intune-ban a Készülékregisztrációs programmal](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>DEP-token megújítása  
1. Ugrás a deploy.apple.com címre.  
2. A **Manage Servers** (Kiszolgálók kezelése) területen válassza ki a megújítani kívánt token-fájlhoz társított MDM-kiszolgálót.
3. Válassza a **Generate New Token** (Új token létrehozása) lehetőséget.

    ![Képernyőkép új token generálásáról.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Válassza a **Your Server Token** (Saját kiszolgálói token) lehetőséget.  
5. Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, és válasszon ki a tokent.
    ![Képernyőkép a regisztrációs program jogkivonatairól.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Válassza a **Jogkivonat megújítása** lehetőséget, majd adja meg az eredeti jogkivonat létrehozásához használt Apple ID-t.  
    ![Képernyőkép új token generálásáról.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Töltse fel az újonnan letöltött tokent.  
9. Válassza a **Token megújítása** lehetőséget. Látni fogja a token megújításáról szóló megerősítő üzenetet.   
    ![Képernyőkép a megerősítésről.](./media/device-enrollment-program-enroll-ios/confirmation.png)
