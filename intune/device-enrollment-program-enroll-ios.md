---
title: iOS-eszközök regisztrálása – Készülékregisztrációs program
titleSuffix: Microsoft Intune
description: Céges tulajdonú iOS-es eszközök regisztrálása az Apple készülékregisztrációs programjával (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b03de8b2c5fca0f41a792e5004d74fe82e4a861d
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a témakör az Apple [készülékregisztrációs programja (DEP)](https://deploy.apple.com) keretében vásárolt iOS-eszközök regisztrálásához nyújt segítséget. Nagyszámú eszköz DEP-regisztrálását végezheti el anélkül, hogy kézbe venné őket. Közvetlenül a felhasználóknak küldhet el olyan eszközöket, mint az iPhone vagy az iPad. Amikor a felhasználó bekapcsolja az eszközt, a Beállítási asszisztens az előre konfigurált beállítások szerint fut, és regisztrálja az eszközt a felügyeleti szolgáltatásban.

DEP-regisztráció engedélyezéséhez az Intune- és az Apple DEP-portált is használnia kell. Ahhoz, hogy az eszközök felügyeletét az Intune-hoz rendelhesse, szükség van a sorozatszámok vagy a beszerzési rendelésszámok listájára. Olyan DEP-regisztrációs profilokat hoz létre, amelyek tartalmazzák a regisztráció során az eszközre vonatkozó beállításokat.

A DEP-regisztráció egyébként nem működik az [eszközregisztráció-kezelővel](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>A felügyelt mód ismertetése
Az Apple az iOS 5-tel vezette be a felügyelt módot. A felügyelt módon futtatott iOS-eszközök (készülékek) működése nagyobb mértékben felügyelhető. Így kifejezetten hasznos céges tulajdonú készülékek üzemeltetése esetén. Az Intune az Apple készülékregisztrációs program (DEP) keretében biztosít lehetőséget az eszközök felügyelt módú üzemeltetésének beállítására. 

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
- [MDM-szolgáltató ](mdm-authority-set.md)
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Apple DEP-token beszerzése

Az iOS-eszközök DEP-regisztrációjához először is egy Apple-től származó DEP-tokenre (.p7m) van szükség. Ez a token (jogkivonat) teszi lehetővé az Intune számára a vállalat által birtokolt DEP-eszközök adatainak szinkronizálását. Azt is engedélyezi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és eszközöket rendeljen ezen profilokhoz.

A DEP-tokent az Apple DEP-portálon hozhatja létre. Szintén a DEP-portál használatával rendelheti hozzá az eszközök felügyeletét az Intune-hoz.

> [!NOTE]
> Ha törli a tokent a klasszikus Intune-portálról az Azure-ba történő migrálás előtt, előfordulhat, hogy az Intune visszaállít egy korábban törölt Apple DEP-tokent. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról.

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
4. Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

5. Megjelenik a **Hozzáadás:&lt;Kiszolgálónév&gt;** párbeszédablak, és kéri **a nyilvános kulcs feltöltését**. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

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

### <a name="step-4-upload-your-token"></a>4. lépés. Töltse fel a tokent.
Az **Apple-token** mezőben keresse meg tallózással a tanúsítványfájlt (.pem), és válassza a **Megnyitás**, majd a **Létrehozás** lehetőséget. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével. Az Intune automatikusan szinkronizálja az Apple-lel a regisztrációs programfiók adatait.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása

Most, hogy telepítette a jogkivonatot, létrehozhatja a regisztrációs profilt a DEP-eszközökhöz. A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** elemet.
2. Válasszon egy tokent, és válassza a **Profilok**, majd a **Profil létrehozása** lehetőséget.
    ![Képernyőkép a profil létrehozásáról.](./media/device-enrollment-program-enroll-ios/image04.png)
3. A **Profil létrehozása** panelen adminisztrációs célból adja meg a profil **Nevét** és **Leírását**. Ezeket a felhasználók nem fogják látni. A **Név** mező felhasználásával dinamikus csoportot hozhat létre az Azure Active Directoryban. Használja a profilnevet az enrollmentProfileName paraméter meghatározásához, hogy ezzel a regisztrációs profillal rendelhesse hozzá az eszközöket. További információk az [Azure Active Directory-alapú dinamikus csoportokról](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).
    ![A profil neve és leírása.](./media/device-enrollment-program-enroll-ios/image05.png)

4. A **Felhasználói affinitást** aszerint állítsa be, hogy a profilhoz tartozó eszközöket hozzárendelt felhasználóval vagy anélkül szükséges-e regisztrálni.
    - **Regisztráció felhasználói affinitással** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek a felhasználók tulajdonában vannak, de egyes szolgáltatásokhoz, például alkalmazások telepítéséhez, a céges portált kívánják használni. Ez a beállítás emellett arra is lehetőséget nyújt a felhasználóknak, hogy a céges portál segítségével hitelesítsék az eszközüket. A felhasználói affinitáshoz [WS-Trust 1.3 Username/Mixed végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) szükséges. [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Regisztráció felhasználói affinitás nélkül** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek nincsenek egy adott felhasználóhoz társítva. Olyan eszközökhöz használja, amelyek a helyi felhasználói adatokhoz való hozzáférés nélkül végeznek feladatokat. Egyes alkalmazások, mint például a Céges portál alkalmazás, nem működnek.

5. A **Regisztráció felhasználói affinitással** lehetőség választásakor engedélyezheti a felhasználóknak, hogy az Apple beállítási asszisztens helyett a Céges portál alkalmazással végezzenek hitelesítést.

    ![Végezzen hitelesítést a Céges portállal.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > A többtényezős hitelesítés (MFA) nem működik a DEP-regisztráció során, ha a **Regisztráció felhasználói affinitással** beállítást választja a profiltulajdonságokhoz. A regisztráció végeztével az MFA az elvárásoknak megfelelően működik. Az első bejelentkezéskor az eszközök nem tudják figyelmeztetni a felhasználókat a jelszó módosítására. Továbbá a lejárt jelszóval rendelkező felhasználók sem kapnak felszólítást a jelszó alaphelyzetbe állítására a regisztráció alatt. A felhasználóknak egy másik eszköz használatával kell alaphelyzetbe állítani a jelszavukat.

6. Válassza az **Eszközkezelési beállítások** lehetőséget, és adja meg, hogy felügyelve legyenek-e az adott profilt használó eszközök.
    A **felügyelt** eszközök esetében több felügyeleti lehetőséget érhet el, és az Aktiválási zár funkció alapértelmezés szerint le van tiltva. A felügyelt módú üzemeltetés lehetővé tételéhez a Microsoft a DEP használatát javasolja, különösen olyan szervezeteknél, amelyeknél nagy mennyiségű iOS-eszközt használnak.

    A rendszer kétféle módon is tudatja a felhasználókkal, hogy az eszközük felügyelet alatt áll:

   - A zárolási képernyőn a következő felirat látható: „Ezt az iPhone-t a Contoso kezeli.”
   - A **Beállítások** > **Általános** > **Névjegy** képernyőn a következő felirat látható: „Ez egy felügyelt iPhone. A Contoso figyelheti az internetes forgalmat és megállapíthatja a készülék helyét.” figyelmeztetés.

     > [!NOTE]
     > A felügyelet nélkül regisztrált eszközöket csak az Apple Configurator segítségével tudja átállítani felügyelt eszközzé. Az eszköz ily módon való átállításához csatlakoztatnia kell az iOS-eszközt egy Mac számítógéphez USB-kábellel. Ezzel kapcsolatban az [Apple Configurator dokumentációjában](http://help.apple.com/configurator/mac/2.3) talál további információkat.

7. Adja meg, hogy zárolt regisztrációt kíván-e beállítani a jelen profilt használó eszközökhöz. A **Zárolt regisztráció** letiltja azokat az iOS-beállításokat a **Beállítások** menüből, amelyek segítségével eltávolítható a felügyeleti profil. Az eszköz regisztrálása után ez a beállítás nem módosítható az eszköz gyári beállításainak visszaállítása állítása nélkül. A zárolt regisztrációjú eszközökön a **Felügyelt** felügyeleti módot az *Igen* értékre kell beállítani. 

8. Adja meg, hogy a jelen profilt használó eszközök végezhetnek-e **Szinkronizálást számítógépekkel**. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

9. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta az előző lépésben, válasszon egy importálandó Apple Configurator-tanúsítványt.

10. Válassza az **OK** gombot.

11. Válassza **A beállítási asszisztens beállításai** elemet, és konfigurálja az alábbi profilbeállításokat: ![A beállítási asszisztens testreszabása.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    |                 Beállítás                  |                                                                                               Description                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Részleg neve</strong>     |                                                             Akkor jelenik meg, ha a felhasználó az aktiválás során a <strong>Konfiguráció névjegye</strong> elemre koppint.                                                              |
    |    <strong>Részleg telefonszáma</strong>     |                                                          Akkor jelenik meg, ha a felhasználó az aktiválás során a <strong>Segítségre van szüksége?</strong> gombra kattint.                                                          |
    | <strong>Beállítási asszisztens – Beállítások</strong> |                                                     Ezeknek a beállításoknak a megadása nem kötelező, és az iOS <strong>Beállítások</strong> menüjében később is konfigurálhatók.                                                      |
    |        <strong>PIN-kód</strong>         | PIN-kód kérése aktiváláskor. PIN-kód megadására mindig szükség van, kivéve, ha az eszköz biztonságát, illetve elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt). |
    |    <strong>Helyalapú szolgáltatások</strong>    |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                  |
    |         <strong>Visszaállítás</strong>         |                                                                Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során iCloud-alapú biztonsági mentést fog kérni.                                                                 |
    |   <strong>iCloud és Apple ID</strong>   |                         Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens kéri a felhasználót, hogy jelentkezzen be egy Apple ID azonosítóval, és az Alkalmazások és adatok képernyőn lehetőség lesz majd az eszköz iCloud-alapú biztonsági mentésből való visszaállítására.                         |
    |  <strong>Feltételek és kikötések</strong>   |                                                   Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során arra fogja kérni a felhasználót, hogy fogadja el az Apple használati feltételeit.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                 |
    |          <strong>Nagyítás</strong>           |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                 |
    |     <strong>Diagnosztikai adatok</strong>     |                                                                 Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.                                                                 |


12. Válassza az **OK** gombot.

13. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az eszközei felügyeletére, szinkronizálhatja az Intune-t az Apple-lel, hogy megtekinthesse a felügyelt eszközöket az Azure-beli Intune-portálon.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, válasszon egy tokent a listából, majd válassza az **Eszközök** > **Szinkronizálás** lehetőséget. ![Képernyőkép – A Szinkronizálás hivatkozás választása a Készülékregisztrációs programba felvett eszközök mező kijelölése után.](./media/device-enrollment-program-enroll-ios/image06.png)

   Az Apple elfogadható regisztrációs programforgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
   - Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune minden Intune-hoz rendelt Apple-sorozatszámot frissít. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
   - A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.
   - Az Intune 24 óránként szinkronizálja az új vagy eltávolított eszközöket az Apple-lel.

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
Az eddigiekben engedélyezte az eszközfelügyeletet és a szinkronizálást az Apple és az Intune között, valamint a DEP-eszközök regisztrálása céljából hozzárendelt egy profilt. Az eszközök ekkor már kioszthatók a felhasználóknak. Felhasználói affinitással rendelkező eszközök esetén minden felhasználóhoz hozzá kell rendelni egy Intune-licencet. A felhasználói affinitás nélküli eszközökhöz licenc szükséges. Regisztrációs profil csak akkor léptethető érvénybe egy aktivált eszközön, ha előtte visszaállítják az eszköz gyári beállításait.

Lásd: [iOS-eszköz regisztrálása az Intune-ban a Készülékregisztrációs programmal](/intune-user-help/enroll-your-device-dep-ios).


