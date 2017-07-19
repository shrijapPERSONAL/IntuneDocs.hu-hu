---
title: "iOS-eszközök regisztrálása – Készülékregisztrációs program"
titleSuffix: Intune on Azure
description: "Céges tulajdonú iOS-es eszközök regisztrálása az Apple eszközbeléptetési programjával (DEP)"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f509f5332b2f8b5f6745816f8795a9a54c10ce2d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Az Apple készülékregisztrációs programmal (DEP) történő iOS-es eszközregisztráció beállítása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az Apple [készülékregisztrációs programja (DEP)](https://deploy.apple.com) keretében vásárolt iOS-es eszközök regisztrálásában nyújt segítséget a rendszergazdáknak. A DEP-en keresztül megvásárolt eszközökre a Microsoft Intune “vezeték nélkül” telepíthet egy regisztrációs profilt. A rendszergazdának nem kell az egyes felügyelt eszközökhöz személyesen hozzáférnie. A DEP-profil tartalmazza azokat a felügyeleti beállításokat, amelyeket a rendszer a regisztrálás során az eszközökre alkalmaz, beleértve a Beállítási asszisztens beállításait is.

DEP-regisztráció engedélyezéséhez az Intune- és az Apple DEP-portált is használnia kell. A DEP-eszközök azonosítóinak listája vagy a beszerzési rendelés száma is szükséges, hogy az Intune-hoz rendelhesse őket kezelésre az Apple portálján.

>[!NOTE]
>A DEP-regisztrációt nem lehet használni az [eszközregisztráció-kezelővel](device-enrollment-manager-enroll.md).

**Az Apple regisztrációs programjainak engedélyezése lépésről lépésre**
1. [Apple DEP-jogkivonat beszerzése és az eszközök hozzárendelése](#get-the-apple-dep-certificate)
2. [Beléptetési profil létrehozása](#create-anapple-enrollment-profile)
3. [DEP által felügyelt eszközök szinkronizálása](#sync-dep-managed-devices)
4. [DEP-profil hozzárendelése eszközökhöz](#assign-a-dep-profile-to-devices)
5. [Eszközök terjesztése a felhasználóknak](#distribute-devices-to-users)

## <a name="get-the-apple-dep-token"></a>Apple DEP-token beszerzése

A vállalati tulajdonú iOS-es eszközöket csak egy, az Apple-től származó DEP-jogkivonat (.p7m-fájl) birtokában regisztrálhatja az Apple készülékregisztrációs programjában. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A jogkivonat ezen felül lehetővé teszi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

> [!NOTE]
> Ha az Intune-bérlőt a klasszikus Intune-konzolról migrálták az Azure Portalra, és a migráció során Ön törölt egy Apple DEP-jogkivonatot az Intune felügyeleti konzolról, akkor lehet, hogy a DEP-jogkivonat vissza lett állítva az Intune-fiókba. Ilyenkor a DEP-tokent ismét törölheti az Azure Portalról.

**Előfeltételek**
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- Regisztráció az [Apple Készülékregisztrációs programjában](http://deploy.apple.com)

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt (ez szükséges az Apple DEP-token létrehozásához).**<br>
1. Az Intune-portálon válassza a **Készülékregisztráció**, az **Apple-regisztráció**, majd a **Készülékregisztrációs program tokenje** elemet.
![Képernyőkép – A Készülékregisztrációs program (DEP) tokenje panel az Apple tanúsítványok munkaterületen.](./media/enrollment-program-token-add.png)
2. Válassza a **Nyilvános kulcsú tanúsítvány letöltése** elemet, és mentse helyben a letöltött titkosításikulcs-fájlt (.pem). A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.
![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/enrollment-program-token-download.png)

**2. lépés Hozzon létre és töltsön le egy Apple DEP-jogkivonatot.**<br>
A **Token létrehozása az Apple Készülékregisztrációs programjában** lehetőséget választva nyissa meg az Apple Telepítési program portálját és jelentkezzen be vállalata Apple-azonosítójával. A későbbiekben ezt az Apple ID-t használhatja a DEP-token megújításához.
  ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen.](./media/enrollment-program-token-create.png)

  ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/enrollment-program-token-sign.png)
   1.  Az Apple [Telepítési program portálján](https://deploy.apple.com), válassza az **Első lépések** lehetőséget a **Készülékregisztrációs program** mellett.
   ![Képernyőkép – Regisztrációs program – Kattintás az Első lépések linkre a Készülékregisztrációs programnál.](./media/enrollment-program-token-started.png)
   2. A **Kiszolgálók kezelése** lapon válassza az **MDM-kiszolgáló hozzáadása** lehetőséget.
   3. Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

   ![Képernyőkép – MDM-kiszolgáló nevének megadása a DEP-hez, majd kattintás a Tovább gombra.](./media/enrollment-program-token-add-server.png)
   4.  Megjelenik a **Hozzáadás:&lt;Kiszolgálónév&gt;** párbeszédablak, és kéri **a nyilvános kulcs feltöltését**. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.
   ![Képernyőkép – A nyilvános kulcs kiválasztására szolgáló gomb, majd a Tovább gomb.](./media/enrollment-program-token-choose-file.png)
   4.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépre, majd válassza a **Done**(Kész) lehetőséget.
   ![Képernyőkép – A nyilvános kulcs kiválasztására szolgáló gomb, majd a Tovább gomb.](./media/enrollment-program-token-your-token.png)
   5. Válassza a **Deployment Programs** (Telepítési programok) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget.
   6. Az **Eszközök kiválasztásának szempontja** alatt adja meg az eszközök azonosításának módját:
    - **Sorozatszám**
    - **Sorszám**
    - **CSV-fájl feltöltése**.

   ![Képernyőkép – Eszközök kiválasztásának beállítása: sorozatszám alapján. Választott tevékenység: hozzárendelés kiszolgálóhoz. Kiszolgálónév megadása.](./media/enrollment-program-token-specify-serial.png)

   7. A **Választott tevékenység** mellett válassza a **Hozzárendelés kiszolgálóhoz** elemet, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra. Az Apple-portál az Intune-kiszolgálóhoz rendeli a megadott eszközök kezelését, majd megjeleníti a **Hozzárendelés kész** üzenetet.

   Az Apple-portál **Központi telepítési programok** &gt; **Készülékregisztrációs program** &gt; **Hozzárendelési előzmények** menüpontjában jeleníthető meg az eszközök és a hozzájuk tartozó MDM-kiszolgálók listája.

**3. lépés Adja meg az Apple DEP-tokenjének létrehozásához használt Apple ID-t.**<br>Adja meg az Apple ID-t az Intune-portálon későbbi felhasználásra. Ezzel az ID-val megújítható a regisztrációs program tokenje, így nem lesz szükség az összes eszköz újraregisztrálására.
![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/enrollment-program-token-apple-id.png)
**4. lépés Keresse meg a feltöltendő DEP-tokent.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével. Az Intune automatikusan szinkronizálja az Apple-lel a regisztrációs programfiók adatait.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása

A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. Az **Apple Regisztrációs Program** alatt válassza a **Regisztrációs programprofilok** lehetőséget, majd a **Regisztrációs programprofilok** panelen válassza a **Létrehozás** elemet.
![Képernyőkép – A az új regisztrációs programprofilt létrehozó hivatkozás kiválasztása.](./media/enrollment-program-profile-create.png)
3. A **Regisztrációs profil létrehozása** panelen adja meg a profil adminisztrációs célra szolgáló **Nevét** és **Leírását**. Ezeket a felhasználók nem fogják látni.
![Képernyőkép – Név és leírás megadása és a felhasználói affinitással történő regisztráció kiválasztása új regisztrációs programprofilhoz.](./media/enrollment-program-profile-name.png)
A **Felhasználói affinitás** beállítással adhatja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül legyenek-e regisztrálva.

 - **Regisztrálás felhasználói affinitással** – Az eszközök a kezdeti beállítás során felhasználókhoz lesznek társítva, így kaphatnak engedélyt a vállalati adatok és e-mailek elérése. A **felhasználói affinitást** olyan eszközöknél kell választani, amelyek felhasználók tulajdonában vannak, de a Céges portált kell rajtuk használni például az alkalmazások telepítéséhez.

<<<<<<< HEAD
 > [!NOTE]
 > A regisztrálás során a többtényezős hitelesítés (MFA) nem működik a regisztrációs program által kezelt, felhasználói affinitással rendelkező eszközökön. A regisztrációt követően az ilyen eszközökön is az elvárásoknak megfelelően működik az MFA. Az első bejelentkezéskor jelszómódosításra kötelezett új felhasználók nem kaphatnak értesítést az eszközökön történő regisztráció során. Ezen túlmenően a lejárt jelszavú felhasználók nem kapnak értesítést a jelszó visszaállításáról a regisztráció során, és a jelszó visszaállítását egy másik eszközről kell végrehajtaniuk.

 >[!NOTE]
 >A regisztrációs program felhasználói affinitással történő kezeléséhez engedélyezni kell a [WS-Trust 1.3 Username/Mixed végpontot](https://technet.microsoft.com/library/adfs2-help-endpoints) a felhasználói token kérelmezése céljából. [További információ a WS-Trust 1.3-ról](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
=======
    >[!NOTE]
    >A felhasználói affinitással rendelkező DEP funkció esetében a felhasználói jogkivonat kérelmezéséhez engedélyezni kell a [WS-Trust 1.3 Username/Mixed végpontot](https://technet.microsoft.com/library/adfs2-help-endpoints). [További információ a WS-Trust 1.3-ról](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
>>>>>>> 0c3fe0dee88e8ef4d8ad8ad28c0f8957831dd5b3

 - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

4. Válassza az **Eszközfelügyeleti beállítások** menüt a következő profilbeállítások konfigurálásához: ![Képernyőkép – Felügyelt felügyeleti mód kiválasztása zárolt regisztrációval, párosítás teljes tiltásával és az Apple Configurator-tanúsítvány szürke mezőjével új regisztrációs programprofil esetén.](./media/enrollment-program-profile-mode.png)
    - **Felügyelt** – olyan felügyeleti mód, amely több felügyeleti funkciót engedélyez, és alapértelmezés szerint tiltja az Aktiválási zár funkciót. Ha a jelölőnégyzetet üresen hagyja, a felügyeleti lehetőségek korlátozva lesznek.

    - **Zárolt regisztráció** – (Felügyelt felügyeleti mód szükséges hozzá) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását. Ha a jelölőnégyzetet üresen hagyja, lehetővé teszi a felügyeleti profil eltávolítását a Beállítások menüből. Ezt aktiválás közben lehet beállítani, és a gyári beállítások visszaállítása nélkül nem módosítható.

    - **Párosítás engedélyezése** – meghatározza, hogy az iOS-eszközök szinkronizálhatók-e a számítógéppel. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

    - **Apple Configurator-tanúsítványok** – Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja a **Párosítás engedélyezése** területen, válassza ki az importálandó Apple Configurator-tanúsítványt.

  Válassza a **Mentés** elemet.

5. Válassza a **Beállítási asszisztens beállításai** lehetőséget a következő profilbeállítások konfigurálásához: ![Képernyőkép – Az új regisztrációs programprofil esetén lehetséges beállítások konfigurálása.](./media/enrollment-program-profile-settings.png)
    - **Részleg neve** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.

    - **Részleg telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a Segítségre van szüksége? gombra kattint.
    - **Beállítási asszisztens – Beállítások** – Ezeknek a beállításoknak a megadása nem kötelező, és az iOS **Beállítások** menüjében később is konfigurálhatók.
        - **PIN-kód** – PIN-kód kérése aktiváláskor. PIN-kód megadására mindig szükség van, kivéve, ha az eszköz biztonságát, illetve elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt).
        - **Helyalapú szolgáltatások** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja a szolgáltatást.
        - **Visszaállítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során iCloud-alapú biztonsági mentést fog kérni.
        - **Apple ID** – Engedélyezés esetén az iOS kérni fogja a felhasználótól az Apple ID-t, ha a felhasználó annak megadása nélkül próbál alkalmazást telepíteni az Intune-ban. Az App Store-beli iOS-alkalmazások letöltéséhez Apple ID azonosító szükséges, az Intune által telepített alkalmazásokat is beleértve.
        - **Feltételek és kikötések** – Ha engedélyezte, a Beállítási asszisztens az aktiválás során arra fogja kérni a felhasználót, hogy fogadja el az Apple használati feltételeit.
        - **Touch ID** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Apple Pay** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Nagyítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Siri** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Diagnosztikai adatok** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást

    Válassza a **Mentés** elemet.
9. A profilbeállítások mentéséhez a **Regisztrációs profil létrehozása** panelen válassza a **Létrehoz** lehetőséget. A regisztrációs profil megjelenik az Apple Regisztrációs Program Regisztrációs profillistájában.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az eszközei felügyeletére, szinkronizálhatja az Intune-t az Apple-lel, így a felügyelt eszközök megjelennek az Intune-portálon.

1. Az Intune-portálon válassza az **Eszközök regisztrálása** &gt;  **Apple-regisztráció** &gt; **Készülékregisztrációs programba felvett eszközök** elemet.
2. A **Készülékregisztrációs programba felvett eszközök** szakaszban válassza a **Szinkronizálás** elemet. Megjelenik a **Szinkronizálás** panel.
![Képernyőkép – A Szinkronizálás hivatkozás választása a Készülékregisztrációs programba felvett eszközök mező kijelölése után.](./media/enrollment-program-device-sync.png)
3. A **Szinkronizálás** panelen válassza a **Szinkronizálási kérelem** lehetőséget. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.
![Képernyőkép – Szinkronizálási kérelem hivatkozás kiválasztása a Szinkronizálás panelen.](./media/enrollment-program-device-request-sync.png)
    Az Apple elfogadható regisztrációs programforgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
     -  Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.
4. Az új eszközeit a **Frissítés** gombra kattintva jelenítheti meg a Regisztrációs programba felvett eszközök munkaterületen.

## <a name="assign-an-enrollment-profile-to-devices"></a>Regisztrálási profil eszközökhöz rendelése
Az Intune által felügyelt eszközökhöz a regisztrálás előtt regisztrációs programprofilt kell hozzárendelni.

>[!NOTE]
>A profilokhoz sorozatszámok is hozzárendelhetők az **Apple-sorozatszámok** panelen.

1. Az Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció**, majd a **Készülékregisztrációs programbeli profilok** elemet.
2. A **Készülékregisztrációs programprofilok** listából válassza ki az eszközhöz hozzárendelni kívánt profilt, majd válassza az **Eszközök hozzárendelése** elemet.
![Képernyőkép – Szinkronizálási kérelem hivatkozás kiválasztása a Szinkronizálás panelen.](./media/enrollment-program-device-assign.png)
3. Válassza a **Hozzárendelés** lehetőséget, majd válassza ki az eszközöket, amelyekhez ezt a profilt kívánja hozzárendelni. A megjelenített eszközöket az alábbiak szerint szűrheti:
  - **nem hozzárendelt**
  - **bármelyik**
  - **&lt;profilnév&gt;**
4. Válassza ki a hozzárendelni kívánt eszközöket. Az oszlop fölötti jelölőnégyzettel legfeljebb 1000 eszközt választhat ki, majd kattintson a **Hozzárendel** gombra. Ha több mint 1000 eszközt szeretne hozzárendelni, ismételje meg a lépéseket, amíg az összes eszközt hozzá nem rendelte egy regisztrációs profilhoz.

  ![Képernyőkép – A DEP-profil hozzárendelésére szolgáló gomb az Intune-portálon](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Végfelhasználói feladatok a felügyelt eszközökkel

Az eszközök ekkor már kioszthatók a felhasználóknak. Felhasználói affinitással rendelkező eszközök esetén minden felhasználóhoz hozzá kell rendelni egy Intune-licencet. Ha az eszközt már aktiválták és használatban van, a profil csak akkor alkalmazható, ha az eszközön visszaállították a gyári beállításokat. Amikor egy regisztrációs program által kezelt iOS-eszközt bekapcsolnak, a felhasználó a következőket látja:  

1. **iOS-eszköz beállítása** – A felhasználó az alábbi lehetőségek közül választhat:
  - **Beállítás új eszközként**
  - **iCloud biztonsági másolat visszaállítása**
  - **iTunes biztonsági másolat visszaállítása**
2. A felhasználók üzenetet kapnak arról, hogy **a Microsoft automatikusan konfigurálja az eszközt.** Elérhetők még az alábbi részletes konfigurációs információk:

  **A konfiguráció engedélyezi, hogy a Microsoft távolról kezelje ezt az eszközt.**

  **A rendszergazdák távolról segíthetnek e-mail- ás hálózati fiókok beállításában, alkalmazások telepítésében és konfigurálásában és a beállítások kezelésében.**

  **A rendszergazdák funkciókat tilthatnak le, alkalmazásokat telepíthetnek és távolíthatnak el, megfigyelhetik és korlátozhatják az internetes forgalmat és távolról törölhetik az eszköz tartalmát.**

  **A konfigurációt biztosítja:<br> MicrosoftIntune iOS Team<br> One Microsoft Way, Redmond, WA 98052 (USA)**

3. A rendszer kéri a felhasználóktól a munkahelyi vagy iskolai felhasználónevet és jelszót.
4. A rendszer kéri a felhasználóktól az Apple ID-t. Az Intune Céges portál és más alkalmazások telepítéséhez Apple ID szükséges. A hitelesítő adatok megadása után az eszköz telepíti a felügyeleti profilt, amely nem távolítható el. Az Intune felügyeleti profil az eszköz **Beállítások** > **Általános** > **Eszközkezelés** menüjében jelenik meg.

A felhasználók az Intune Céges portál vagy az Apple beállítási asszisztens használatával fejezhetik be a vállalati tulajdonú eszköz beállítását.
