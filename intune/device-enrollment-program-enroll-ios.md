---
title: "iOS-eszközök regisztrálása – Készülékregisztrációs program"
titlesuffix: Azure portal
description: "Céges tulajdonú iOS-es eszközök regisztrálása az Apple eszközbeléptetési programjával (DEP)"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f472c144e9bcda965486f8e88d38aa9d27df165
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

> [!NOTE]
> A többtényezős hitelesítés (MFA) nem működik a felhasználói affinitással beállított DEP-regisztráció során. A regisztráció végeztével az MFA az elvárásoknak megfelelően működik. Az első bejelentkezéskor az eszközök nem tudják figyelmeztetni a felhasználókat a jelszó módosítására. Továbbá a lejárt jelszóval rendelkező felhasználók sem kapnak felszólítást a jelszó alaphelyzetbe állítására a regisztráció alatt. A felhasználóknak egy másik eszköz használatával kell alaphelyzetbe állítani a jelszavukat.

## <a name="get-the-apple-dep-token"></a>Apple DEP-token beszerzése

Az iOS-eszközök DEP-regisztrációjához először is egy Apple-től származó DEP-tokenre (.p7m) van szükség. Ez a token (jogkivonat) teszi lehetővé az Intune számára a vállalat által birtokolt DEP-eszközök adatainak szinkronizálását. Azt is engedélyezi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és eszközöket rendeljen ezen profilokhoz.

A DEP-tokent az Apple DEP-portálon hozhatja létre. Szintén a DEP-portál használatával rendelheti hozzá az eszközök felügyeletét az Intune-hoz.

> [!NOTE]
> Ha törli a tokent a klasszikus Intune-portálról az Azure-ba történő migrálás előtt, előfordulhat, hogy az Intune visszaállít egy korábban törölt Apple DEP-tokent. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról.

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt (ez szükséges az Apple DEP-token létrehozásához).**<br>

1. Az Azure-beli Intune-portálon válassza az**Eszközök regisztrálása** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** elemet.

  ![Képernyőkép – A Készülékregisztrációs programbeli token panel az Apple-tanúsítványok munkaterületen.](./media/enrollment-program-token-add.png)

2. Kattintson a **Nyilvános kulcs letöltése** elemre a titkosításikulcs-fájl (.pem) letöltéséhez és helyi mentéséhez. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

  ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/enrollment-program-token-download.png)

**2. lépés Hozzon létre és töltsön le egy Apple DEP-jogkivonatot.**<br>
1. A **Token létrehozása az Apple Készülékregisztrációs programjában** elemre kattintva nyissa meg az Apple Központi Telepítési Program portálját és jelentkezzen be a cége Apple-azonosítójával. A későbbiekben ezt az Apple ID-t használhatja a DEP-token megújításához.
2.  Az Apple [Központi Telepítési Program portálján ](https://deploy.apple.com) válassza a**Készülékregisztrációs program** **Első lépések** elemét.

3. A **Kiszolgálók kezelése** lapon válassza az **MDM-kiszolgáló hozzáadása** lehetőséget.
4. Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

   ![Képernyőkép – MDM-kiszolgáló nevének megadása a DEP-hez, majd kattintás a Tovább gombra.](./media/enrollment-program-token-add-server.png)

5. Megjelenik a **Hozzáadás:&lt;Kiszolgálónév&gt;** párbeszédablak, és kéri **a nyilvános kulcs feltöltését**. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.  


7. Válassza a **Deployment Programs** (Telepítési programok) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget.
8. Az **Eszközök kiválasztásának szempontja** alatt adja meg az eszközök azonosításának módját:
    - **Sorozatszám**
    - **Sorszám**
    - **CSV-fájl feltöltése**.

   ![Képernyőkép – Eszközök kiválasztásának beállítása: sorozatszám alapján. Választott tevékenység: hozzárendelés kiszolgálóhoz. Kiszolgálónév megadása.](./media/enrollment-program-token-specify-serial.png)

9. A **Választott tevékenység** területen jelölje ki a **Hozzárendelés kiszolgálóhoz** elemet, válassza Microsoft Intune-hoz megadott &lt;Kiszolgálónevet&gt;, majd kattintson az **OK** gombra. Az Apple-portál az Intune-kiszolgálóhoz rendeli a megadott eszközök kezelését, majd megjeleníti a **Hozzárendelés kész** üzenetet.

   Az Apple-portál **Központi telepítési programok** &gt; **Készülékregisztrációs program** &gt; **Hozzárendelési előzmények** menüpontjában jeleníthető meg az eszközök és a hozzájuk tartozó MDM-kiszolgálók listája.

**3. lépés Adja meg az Apple DEP-tokenjének létrehozásához használt Apple ID-t.**<br>Az Azure-beli Intune-portálon adja meg az Apple ID azonosítót későbbi felhasználásra. Ha a jövőben ezzel az azonosítóval újítja meg a regisztrációs program tokenjét, nem lesz szükség az összes eszköz újraregisztrálására.

![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/enrollment-program-token-apple-id.png)

**4. lépés Keresse meg a feltöltendő DEP-tokent.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével. Az Intune automatikusan szinkronizálja az Apple-lel a regisztrációs programfiók adatait.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása

Most, hogy telepítette a jogkivonatot, létrehozhatja a regisztrációs profilt a DEP-eszközökhöz. A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása** > **Apple-regisztráció** elemet.
2. Az **Apple készülékregisztrációs programon** belül válassza a **Készülékregisztrációs programbeli profilok**  > **Létrehozás** elemet.
3. A **Regisztrációs profil létrehozása** panelen adminisztrációs célból adja meg a profil **Nevét** és **Leírását**. Ezeket a felhasználók nem fogják látni. A **Név** mező felhasználásával dinamikus csoportot hozhat létre az Azure Active Directoryban. Használja a profilnevet az enrollmentProfileName paraméter meghatározásához, hogy ezzel a regisztrációs profillal rendelhesse hozzá az eszközöket. További információk az [Azure Active Directory-alapú dinamikus csoportokról](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

  A **Felhasználói affinitást** aszerint állítsa be, hogy a profilhoz tartozó eszközöket hozzárendelt felhasználóval vagy anélkül kívánja-e regisztrálni.

 - **Regisztráció felhasználói affinitással** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyek a felhasználók tulajdonában vannak, de egyes szolgáltatásokhoz, mint például az alkalmazások telepítése, a céges portált kell használniuk. A felhasználói affinitáshoz [WS-Trust 1.3 Username/Mixed végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) szükséges. [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Regisztráció felhasználói affinitás nélkül** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyeket nem társítottak adott felhasználóhoz. Olyan eszközökhöz használja, amelyek a helyi felhasználói adatokhoz való hozzáférés nélkül végeznek feladatokat. Egyes alkalmazások, mint például a Céges portál alkalmazás, nem működnek.

4. Az **Eszközfelügyeleti beállítások** lehetőség választásával konfigurálja a következő profilbeállításokat:

  ![Képernyőkép ‒ Felügyeleti mód kiválasztása. Az eszköz a következő beállításokkal rendelkezik: Felügyelt, Zárolt regisztráció és Párosítás engedélyezése „Az összes elutasítása” értékkel. Az Apple Configurator-tanúsítványok lehetőség új regisztrációs programprofiloknál szürkén jelenik meg.](./media/enrollment-program-profile-mode.png)
    - **Felügyelt** – olyan felügyeleti mód, amely több felügyeleti funkciót engedélyez, és alapértelmezés szerint tiltja az Aktiválási zár funkciót. Ha a jelölőnégyzetet üresen hagyja, a felügyeleti lehetőségek korlátozva lesznek. A felügyelt módú üzemeltetés lehetővé tételéhez a Microsoft a DEP használatát javasolja, különösen olyan szervezeteknél, amelyeknél nagy mennyiségű iOS-eszközt használnak.

 > [!NOTE]
 > Regisztráció után már nem lehet az eszközöket felügyelt módra állítani az Intune-t használva. Ha a regisztráció már megtörtént, az iOS-eszközt egy USB-kábelt használva össze kell kötni egy Mac számítógéppel, és az Apple Configuratort használva engedélyezni kell rajta a felügyelt módot. Ennek hatására a rendszer először alaphelyzetbe állítja az eszközt, majd beállítja rajta a felügyelt módot. Ezzel kapcsolatban az [Apple Configurator dokumentációjában](http://help.apple.com/configurator/mac/2.3) talál további információkat. A felügyelt készülékeken meg fog jelenni az „Ezt az iPhone-t a Contoso kezeli.” felirat a zárolási képernyőn, valamint az „Ez egy felügyelt iPhone. A Contoso figyelheti az internetes forgalmat és megállapíthatja a készülék helyét.” figyelmeztetés. a **Beállítások** > **Általános** > **Névjegy** menüpontban.

    - **Zárolt regisztráció** – (Felügyelt felügyeleti mód szükséges hozzá) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását. Ha a jelölőnégyzetet üresen hagyja, lehetővé teszi a felügyeleti profil eltávolítását a Beállítások menüből. Az eszköz regisztrálása után ez a beállítás nem módosítható az eszköz gyári beállításainak visszaállítása állítása nélkül.

  - **Megosztott iPad engedélyezése** – Az Apple Készülékregisztrációs programja nem támogatja a megosztott iPadeket.

    - **Párosítás engedélyezése** – meghatározza, hogy az iOS-eszközök szinkronizálhatók-e a számítógéppel. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

    - **Apple Configurator-tanúsítványok** – Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta a **Párosítás engedélyezése** területen, válassza ki az importálandó Apple Configurator-tanúsítványt.

  Válassza a **Mentés** elemet.

5. Kattintson a **Beállítási asszisztens beállításai** elemre, és konfigurálja az alábbi profilbeállításokat:

  ![Képernyőkép ‒ A beállítások konfigurálásának választása és az új regisztrációs programprofil létrehozásához elérhető beállítások.](./media/enrollment-program-profile-settings.png)
    - **Részleg neve** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.

    - **Részleg telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a **Segítségre van szüksége?** gombra kattint.
    - **Beállítási asszisztens – Beállítások** – Ezeknek a beállításoknak a megadása nem kötelező, és az iOS **Beállítások** menüjében később is konfigurálhatók.
        - **PIN-kód**
        - **Helyalapú szolgáltatások**
        - **Visszaállítás**
        - **Apple ID**
        - **Feltételek és kikötések**
        - **Touch ID**
        - **Apple Pay**
        - **Nagyítás**
        - **Siri**
        - **Diagnosztikai adatok**

    Válassza a **Mentés** elemet.

9. A profilbeállítások mentéséhez a **Regisztrációs profil létrehozása** panelen kattintson a **Létrehozás** elemre. A regisztrációs profil megjelenik az Apple Regisztrációs Program Regisztrációs profillistájában.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az eszközei felügyeletére, szinkronizálhatja az Intune-t az Apple-lel, hogy megtekinthesse a felügyelt eszközöket az Azure-beli Intune-portálon.

1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása** > **Apple-regisztráció** > **Készülékregisztrációs programbeli eszközök** > **Szinkronizálás** lehetőséget. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.

  ![Képernyőkép – A Szinkronizálás hivatkozás választása a Készülékregisztrációs programba felvett eszközök mező kijelölése után.](./media/enrollment-program-device-sync.png)
  
2. A **Szinkronizálás** panelen válassza a **Szinkronizálási kérelem** lehetőséget. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.

  ![Képernyőkép – Szinkronizálási kérelem hivatkozás kiválasztása a Szinkronizálás panelen.](./media/enrollment-program-device-request-sync.png)

  Az Apple elfogadható regisztrációs programforgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
     -  Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune minden Intune-hoz rendelt Apple-sorozatszámot frissít. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.
     - Az Intune 24 óránként szinkronizálja az új vagy eltávolított eszközöket az Apple-lel.

3. Az új eszközeit a **Frissítés** gombra kattintva jelenítheti meg a Regisztrációs programba felvett eszközök munkaterületen.

## <a name="assign-an-enrollment-profile-to-devices"></a>Regisztrálási profil eszközökhöz rendelése
Ahhoz, hogy egy eszközt regisztrálni lehessen, először hozzá kell rendelni egy regisztrációs programprofilt.

>[!NOTE]
>A profilokhoz sorozatszámok is hozzárendelhetők az **Apple-sorozatszámok** panelen.

1. Az Azure-beli Intune-portálon válassza az **Eszközregisztráció** > **Apple-regisztráció**, majd a **Készülékregisztrációs programbeli profilok** lehetőséget.
2. A **Készülékregisztrációs programbeli profilok** listájáról válassza ki azt a profilt, amelyet az eszközökhöz kíván rendelni, majd kattintson az **Eszközök hozzárendelése** elemre.

 ![Képernyőkép – Eszközök hozzárendelése, a Hozzárendelés kijelölésével.](./media/enrollment-program-device-assign.png)

3. Kattintson a **Hozzárendelés** elemre, majd válassza ki a profilhoz rendelendő eszközöket. A megjelenített eszközöket az alábbiak szerint szűrheti:
  - **nem hozzárendelt**
  - **bármelyik**
  - **&lt;profilnév&gt;**
4. Válassza ki a hozzárendelni kívánt eszközöket. Az oszlop fölötti jelölőnégyzettel legfeljebb 1000 eszköz választható ki. Ezután kattintson a **Hozzárendel** gombra. Ha több mint 1000 eszközt szeretne hozzárendelni, ismételje meg a lépéseket, amíg az összes eszközt hozzá nem rendelte egy regisztrációs profilhoz.

  ![Képernyőkép – A DEP-profil hozzárendelésére szolgáló gomb az Intune-ban](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Eszközök terjesztése
Az eddigiekben engedélyezte az eszközfelügyeletet és a szinkronizálást az Apple és az Intune között, valamint a DEP-eszközök regisztrálása céljából hozzárendelt egy profilt. Az eszközök ekkor már kioszthatók a felhasználóknak. Felhasználói affinitással rendelkező eszközök esetén minden felhasználóhoz hozzá kell rendelni egy Intune-licencet. A felhasználói affinitás nélküli eszközökhöz licenc szükséges. Regisztrációs profil csak akkor léptethető érvénybe egy aktivált eszközön, ha előtte visszaállítják az eszköz gyári beállításait.

Lásd: [iOS-eszköz regisztrálása az Intune-ban a Készülékregisztrációs programmal](/intune-user-help/enroll-your-device-dep-ios). 
