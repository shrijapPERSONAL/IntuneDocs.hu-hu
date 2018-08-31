---
title: Az Apple School Manager programba való regisztrálás beállítása iOS-eszközök esetén
titleSuffix: Microsoft Intune
description: A cikk tájékoztatást nyújt az Apple School Manager programba való regisztrálás Intune-beli beállításáról céges tulajdonú iOS-eszközök esetén.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59449efd592f3c47bdf2350b495f81c23f442999
ms.sourcegitcommit: 165c1e48891e386f9f75b0ef7a6826b67695dbb7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2018
ms.locfileid: "42751802"
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>iOS-eszközök regisztrálásának engedélyezése az Apple School Manager programban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk az [Apple School Manager](https://school.apple.com/) program keretében vásárolt iOS-eszközök regisztrálásához nyújt segítséget. Az Intune használatával nagy számú iOS-eszközt regisztrálhat az Apple School Manager programba anélkül, hogy kézbe venné az eszközökhöz. Amikor egy tanuló vagy a tanár bekapcsolja az eszközt, a Beállítási asszisztens az előre konfigurált beállítások szerint indul el, és regisztrálja az eszközt a felügyeleti szolgáltatásban.

Az Apple School Manager programba történő regisztráció az Intune és az Apple School Manager portálok együttes használatával kapcsolható be. Ahhoz, hogy az eszközök felügyeletét az Intune-hoz rendelhesse, szükség van a sorozatszámok vagy a beszerzési rendelésszámok listájára. Olyan DEP-regisztrációs profilokat hoz létre, amelyek tartalmazzák a regisztráció során az eszközre vonatkozó beállításokat.

Az Apple School Manager programba történő regisztráció nem használható együtt az [Apple Készülékregisztrációs programjával](device-enrollment-program-enroll-ios.md) és a [Készülékregisztráció-kezelővel](device-enrollment-manager-enroll.md).

**Előfeltételek**
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- [MDM-szolgáltató ](mdm-authority-set.md)
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- ADFS használata esetén a felhasználói affinitáshoz [WS-Trust 1.3 Username/Mixed végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) szükséges. [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Az [Apple School Management](http://school.apple.com) program keretében vásárolt eszközök

## <a name="get-an-apple-token-and-assign-devices"></a>Az Apple-token beszerzése és az eszközök hozzárendelése

A céges tulajdonú iOS-eszközök regisztrálását csak akkor végezheti el az Apple School Manager programban, ha rendelkezésére áll egy Apple-től származó tokenfájl (.p7m). Ez a token teszi lehetővé, hogy az Intune szinkronizálja az Apple School Manager programban részt vevő eszközök adatait. A jogkivonat ezen felül lehetővé teszi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és a feltöltött profilokhoz eszközöket rendeljen hozzá. Az Apple portálján egyúttal a felügyelendő eszközök sorozatszámának hozzárendelését is elvégezheti.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>1. lépés Töltse le a nyilvános kulcsú Intune-tanúsítványt, amelyre szüksége lesz az Apple-token létrehozásához.

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Regisztrációs programbeli tokenek** > **Hozzáadás** lehetőséget.

   ![Szerezzen be egy készülékregisztrációs programbeli tokent.](./media/device-enrollment-program-enroll-ios/image01.png)

2. A **Készülékregisztrációs programbeli token** panelen válassza a **Nyilvános kulcs letöltése** lehetőséget a titkosításikulcs-fájl (.pem) letöltéséhez és helyi mentéséhez. A .pem-fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple School Manager portálról.
     ![Készülékregisztrációs programbeli token panel.](./media/device-enrollment-program-enroll-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>2. lépés Töltsön le egy tokent, és végezze el az eszközök hozzárendelését.
1. Válassza a **Token létrehozása az Apple School Manager programon keresztül** lehetőséget, és jelentkezzen be az Apple School rendszerbe a céges Apple ID azonosítójával. A későbbiekben ezt az Apple ID-t használhatja az Apple School Manager-token megújításához.
2.  Az [Apple School Manager portálján](https://school.apple.com) az **MDM-kiszolgálók** szakaszban válassza az **Új MDM-kiszolgáló hozzáadása** elemet (a jobb felső sarokban).
3.  Adja meg az **MDM-kiszolgálónevet**. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.
   ![Képernyőfelvétel az Apple School Manager portálról, amelyen a Sorozatszám lehetőség van kijelölve](./media/asm-server-assignment.png)

4.  Az Apple portálján válassza a **Fájl feltöltése...** elemet, keresse meg a .pem-fájlt, és válassza az **MDM-kiszolgáló mentése** elemet (a jobb alsó sarokban).
5.  Válassza a **Token letöltése** elemet, majd töltse le a kiszolgálói tokenfájlt (.p7m) a számítógépre.
6. A **Device Assignments** (Eszköz-hozzárendelések) szakaszban **válassza ki az eszközt** az **eszköz sorozatszámának** (Serial Numbers) vagy **rendelésszámának** (Order Number) kézi bevitelével, illetve **CSV-fájl feltöltésével** (Upload CSV File).
     ![Képernyőfelvétel az Apple School Manager portálról, amelyen a Sorozatszám lehetőség van kijelölve](./media/asm-device-assignment.png)
7.  Válassza a **Hozzárendelés kiszolgálóhoz** műveletet, majd válassza ki a létrehozott **MDM-kiszolgálót**.
8. Adja meg az eszközkiválasztás **(Choose Devices)** módját, majd az eszközhöz kapcsolódó információkat és adatokat.
9. Válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>3. lépés. Mentse a token létrehozásához használt Apple ID-t.

Az Azure-beli Intune-portálon adja meg az Apple ID azonosítót későbbi felhasználásra.

![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>4. lépés. Töltse fel a tokent.
Az **Apple-token** mezőben keresse meg tallózással a tanúsítványfájlt (.pem), és válassza a **Megnyitás**, majd a **Létrehozás** lehetőséget. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével. Az Intune automatikusan szinkronizálja az Apple-től származó Apple School Manager-eszközöket.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása
Most, hogy telepítette a jogkivonatot, létrehozhatja a regisztrációs profilt az Apple School-eszközökhöz. A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget.
2. Válasszon egy tokent, és válassza a **Profilok**, majd a **Profil létrehozása** lehetőséget.

3. A **Profil létrehozása** panelen adminisztrációs célból adja meg a profil **Nevét** és **Leírását**. Ezeket a felhasználók nem fogják látni. A **Név** mező felhasználásával dinamikus csoportot hozhat létre az Azure Active Directoryban. Használja a profilnevet az enrollmentProfileName paraméter meghatározásához, hogy ezzel a regisztrációs profillal rendelhesse hozzá az eszközöket. További információk az [Azure Active Directory-alapú dinamikus csoportokról](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![A profil neve és leírása.](./media/device-enrollment-program-enroll-ios/image05.png)

4. A **Felhasználói affinitást** aszerint állítsa be, hogy a profilhoz tartozó eszközöket hozzárendelt felhasználóval vagy anélkül szükséges-e regisztrálni.
    - **Regisztráció felhasználói affinitással** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek a felhasználók tulajdonában vannak, de egyes szolgáltatásokhoz, például alkalmazások telepítéséhez, a céges portált kívánják használni. Ez a beállítás emellett arra is lehetőséget nyújt a felhasználóknak, hogy a céges portál segítségével hitelesítsék az eszközüket. ADFS használata esetén a felhasználói affinitáshoz [WS-Trust 1.3 Username/Mixed végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) szükséges. [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Az Apple School Manager megosztott iPadeket kezelő üzemmódja felhasználói affinitás nélküli regisztrálást igényel.

    - **Regisztráció felhasználói affinitás nélkül** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek nincsenek egy adott felhasználóhoz társítva, például közös használatú eszközökhöz. Ezt a lehetőséget olyan eszközökhöz használja, amelyek a helyi felhasználói adatokhoz való hozzáférés nélkül végeznek feladatokat. Egyes alkalmazások, mint például a Céges portál alkalmazás, nem működnek.

5. A **Regisztráció felhasználói affinitással** lehetőség választásakor engedélyezheti a felhasználóknak, hogy az Apple beállítási asszisztens helyett a Céges portál alkalmazással végezzenek hitelesítést.

    ![Végezzen hitelesítést a Céges portállal.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Ha az alábbiak valamelyikét szeretné elvégezni, állítsa a **Hitelesítés a Céges portállal a Beállítási asszisztens helyett** értékét az **Igen** lehetőségre.
    >    - Többtényezős hitelesítés használata
    >    - A felhasználók figyelmeztetése a jelszó módosítására az első bejelentkezéskor
    >    - A felhasználók figyelmeztetése a lejárt jelszó helyetti új jelszó kérésére a regisztráció során
    >
    > Ezek az Apple Beállítási asszisztenssel végzett hitelesítéskor nem támogatottak.

6. Válassza az **Eszközkezelési beállítások** lehetőséget, és adja meg, hogy felügyelve legyenek-e az adott profilt használó eszközök.
    A **felügyelt** eszközök esetében több felügyeleti lehetőséget érhet el, és az Aktiválási zár funkció alapértelmezés szerint le van tiltva. A felügyelt módú üzemeltetés lehetővé tételéhez a Microsoft a DEP használatát javasolja, különösen olyan szervezeteknél, amelyeknél nagy mennyiségű iOS-eszközt használnak.

    A rendszer kétféle módon is tudatja a felhasználókkal, hogy az eszközük felügyelet alatt áll:

   - A zárolási képernyőn a következő felirat látható: „Ezt az iPhone-t a Contoso kezeli.”
   - A **Beállítások** > **Általános** > **Névjegy** képernyőn a következő felirat látható: „Ez egy felügyelt iPhone. A Contoso figyelheti az internetes forgalmat és megállapíthatja a készülék helyét.” figyelmeztetés.

     > [!NOTE]
     > A felügyelet nélkül regisztrált eszközöket csak az Apple Configurator segítségével tudja átállítani felügyelt eszközzé. Az eszköz ily módon való átállításához csatlakoztatnia kell az iOS-eszközt egy Mac számítógéphez USB-kábellel. Ezzel kapcsolatban az [Apple Configurator dokumentációjában](http://help.apple.com/configurator/mac/2.3) talál további információkat.

7. Adja meg, hogy zárolt regisztrációt kíván-e beállítani a jelen profilt használó eszközökhöz. A **Zárolt regisztráció** letiltja azokat az iOS-beállításokat a **Beállítások** menüből, amelyek segítségével eltávolítható a felügyeleti profil. Az eszköz regisztrálása után ez a beállítás nem módosítható az eszköz gyári beállításainak visszaállítása állítása nélkül. A zárolt regisztrációjú eszközökön a **Felügyelt** felügyeleti módot az *Igen* értékre kell beállítani. 

8. Ha szeretné engedélyezni, hogy egy felügyelt Apple ID azonosítóval több felhasználó is bejelentkezzen a regisztrált iPadekre, válassza az **Igen** lehetőséget a **Megosztott iPad** beállításnál (ez beállítás **Felhasználói affinitás nélküli regisztrálást** és **Igen** értékre állított **Felügyelt** üzemmódot igényel). A felügyelt Apple ID-k létrehozása az Apple School Manager portálján történik. További információ a [megosztott iPadekről](education-settings-configure-ios-shared.md) és az [Apple megosztott iPadekre vonatkozó követelményeiről](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Adja meg, hogy a jelen profilt használó eszközök végezhetnek-e **Szinkronizálást számítógépekkel**. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

10. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta az előző lépésben, válasszon egy importálandó Apple Configurator-tanúsítványt.

11. Válassza az **OK** gombot.

12. Válassza **A beállítási asszisztens beállításai** elemet, és konfigurálja az alábbi profilbeállításokat: ![A beállítási asszisztens testreszabása.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


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


13. Válassza az **OK** gombot.

14. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="connect-school-data-sync"></a>A School Data Sync csatlakoztatása
(Nem kötelező) Az Apple School Manager támogatja az osztálynévsorok Microsoft School Data Sync (SDS) használatával történő szinkronizálását az Azure Active Directoryba (AD). Az SDS segítségével csak egy tokent tud szinkronizálni. Ha beállítja egy másik tokenhez a School Data Syncet, az SDS el lesz távolítva a korábbi tokenből. Ekkor egy új kapcsolat veszi át a jelenlegi token szerepét. Az alábbi lépések végrehajtásával használhatja az SDS-t az iskolai adatok szinkronizálására.

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget.
2. Válasszon egy Apple School Manager-tokent, majd válassza a **School Data Sync** lehetőséget.
3. A **School Data Sync** területen válassza az **Engedélyezés** lehetőséget. Ez a beállítás teszi lehetővé az Intune csatlakoztatását az Office 365-beli SDS szolgáltatáshoz.
4. Az Apple School Manager és az Azure AD csatlakoztatásához válassza **A Microsoft School Data Sync beállítása** elemet. További információ [a School Data Sync konfigurálásáról](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Kattintson a **Mentés** > **OK** gombra.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása

Miután az Intune engedélyt kapott az Apple School Manager-eszközök felügyeletére, szinkronizálja az Intune-t az Apple szolgáltatással, hogy a felügyelt eszközök megjelenjenek az Intune-ban.

Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, válasszon egy tokent a listából, majd válassza az **Eszközök** > **Szinkronizálás** lehetőséget. ![Képernyőkép – A Szinkronizálás hivatkozás választása a Készülékregisztrációs programba felvett eszközök mező kijelölése után.](./media/device-enrollment-program-enroll-ios/image06.png)

  Az Apple elfogadható regisztrációs programforgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
  - Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune minden Intune-hoz rendelt Apple-sorozatszámot frissít. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
  - A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.
  - Az Intune 24 óránként szinkronizálja az új vagy eltávolított eszközöket az Apple-lel.

>[!NOTE]
>Az Apple School Manager sorozatszámait a **Készülékregisztrációs programba felvett eszközök** panelről is hozzárendelheti a profilokhoz.

## <a name="assign-a-profile-to-devices"></a>Profil hozzárendelése az eszközökhöz
Az Intune által felügyelt Apple School Manager-eszközökhöz még a regisztrálás előtt hozzá kell rendelni egy regisztrációs profilt.

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget, majd válasszon egy tokent a listából.
2. Válassza az **Eszközök** lehetőséget, válasszon eszközöket a listából, majd válassza a **Profil hozzárendelése** elemet.
3. A **Profil hozzárendelése** területen válasszon egy profilt az eszközökhöz, majd válassza a **Hozzárendelés** lehetőséget.

## <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Az eddigiekben engedélyezte az eszközfelügyeletet és a szinkronizálást az Apple és az Intune között, valamint az Apple School-eszközök regisztrálása céljából hozzárendelt egy profilt. Az eszközök ekkor már kioszthatók a felhasználóknak. Az iOS rendszerű Apple School Manager-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyeletre. Ha az eszközt már aktiválták és használatban van, a profil csak akkor alkalmazható, ha az eszközön visszaállították a gyári beállításokat.
