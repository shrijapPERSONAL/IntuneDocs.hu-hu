---
title: "Az Apple School Manager programba való regisztrálás beállítása iOS-eszközök esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt az Apple School Manager programba való regisztrálás Intune-beli beállításáról céges tulajdonú iOS-eszközök esetén"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8197e03e8a3eb42c6a5be3b6357d959ed9428454
ms.sourcegitcommit: 0e012f25fb22124f66193f20f244362493c6b8bb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/07/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>iOS-eszközök regisztrálásának engedélyezése az Apple School Manager programban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az [Apple School Manager](https://school.apple.com/) program keretében vásárolt iOS-eszközök regisztrálásához nyújt segítséget. Az Intune használatával nagy számú iOS-eszközt regisztrálhat az Apple School Manager programba anélkül, hogy kézbe venné az eszközökhöz. Amikor egy tanuló vagy a tanár bekapcsolja az eszközt, a Beállítási asszisztens az előre konfigurált beállítások szerint indul el, és regisztrálja az eszközt a felügyeleti szolgáltatásban.

Az Apple School Manager programba történő regisztráció az Intune és az Apple School Manager portálok együttes használatával kapcsolható be. Ahhoz, hogy az eszközök felügyeletét az Intune-hoz rendelhesse, szükség van a sorozatszámok vagy a beszerzési rendelésszámok listájára. Olyan DEP-regisztrációs profilokat hoz létre, amelyek tartalmazzák a regisztráció során az eszközre vonatkozó beállításokat.

Egyébként az Apple School Manager programba történő regisztráció nem használható együtt az [Apple Készülékregisztrációs programjával](device-enrollment-program-enroll-ios.md) és az [eszközregisztráció-kezelővel](device-enrollment-manager-enroll.md).

**Előfeltételek**
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- [MDM-szolgáltató ](mdm-authority-set.md)
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- A felhasználói affinitáshoz [WS-Trust 1.3 Username/Mixed végpont](https://technet.microsoft.com/library/adfs2-help-endpoints) szükséges. [További információ](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Az [Apple School Management](http://school.apple.com) program keretében vásárolt eszközök

**Az Apple School Manager programba történő regisztráció lépései**
1. [Az Apple School Manager jogkivonatának (token) beszerzése és az eszközök hozzárendelése](#get-the-apple-token-and-assign-devices)
2. [Beléptetési profil létrehozása](#create-an-apple-enrollment-profile)
3. [A School Data Sync csatlakoztatása ](#connect-school-data-sync) (nem kötelező)
4. [Apple School Manager által felügyelt eszközök szinkronizálása](#sync-managed-devices)
5. [Apple School Manager-profil hozzárendelése az eszközökhöz](#assign-a-profile-to-devices)
6. [Eszközök terjesztése a felhasználóknak](#distribute-devices-to-users)

>[!NOTE]
>A többtényezős hitelesítés (MFA) nem működik az Apple School Manager-eszközök felhasználói affinitással történő regisztrálása során. A regisztrációt követően az ilyen eszközökön is az elvárásoknak megfelelően működik az MFA. A regisztráció végeztével az MFA az elvárásoknak megfelelően működik. Az első bejelentkezéskor az eszközök nem tudják figyelmeztetni a felhasználókat a jelszó módosítására. Továbbá a lejárt jelszóval rendelkező felhasználók sem kapnak felszólítást a jelszó alaphelyzetbe állítására a regisztráció alatt. A felhasználóknak egy másik eszköz használatával kell alaphelyzetbe állítani a jelszavukat.


## <a name="get-the-apple-token-and-assign-devices"></a>Az Apple-token beszerzése és az eszközök hozzárendelése

A céges tulajdonú iOS-eszközök regisztrálását csak akkor végezheti el az Apple School Manager programban, ha rendelkezésére áll egy Apple-től származó tokenfájl (.p7m). Ez a token teszi lehetővé, hogy az Intune szinkronizálja az Apple School Manager programban részt vevő eszközök adatait. A jogkivonat ezen felül lehetővé teszi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és a feltöltött profilokhoz eszközöket rendeljen hozzá. Az Apple portálján egyúttal a felügyelendő eszközök sorozatszámának hozzárendelését is elvégezheti.

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt, amelyre szükség van az Apple-token létrehozásához.**<br>
1. Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása**, majd a **Készülékregisztrációs programbeli token** lehetőséget.

  ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/enrollment-program-token-download.png)

2. A **Készülékregisztrációs programbeli token** panelen válassza a **Nyilvános kulcs letöltése** lehetőséget a titkosításikulcs-fájl (.pem) letöltéséhez és helyi mentéséhez. A .pem-fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple School Manager portálról.

**2. lépés Töltsön le egy tokent és végezze el az eszközök hozzárendelését.**<br>
1. Válassza a **Token létrehozása az Apple School Manager programon keresztül** lehetőséget, és jelentkezzen be céges Apple ID azonosítójával. A későbbiekben ezt az Apple ID-t használhatja az Apple School Manager-token megújításához.
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

**3. lépés Adja meg az Apple School Manager-token létrehozásához használt Apple ID azonosítót.**<br>Ugyanerre az azonosítóra lesz szükség az Apple School Manager-token megújításához is, ezért a későbbi felhasználás céljából őrizze meg.

![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/enrollment-program-token-apple-id.png)

**4. lépés Keresse meg és töltse fel a tokent.**<br>
Keresse meg a tanúsítványfájlt (.p7m), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. Az Intune automatikusan szinkronizálja az Apple-től származó Apple School Manager-eszközöket.

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása
A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. A **Készülékregisztrációs program** szakaszban válassza a **Készülékregisztrációs programbeli profilok** elemet.
3. A **Készülékregisztrációs programbeli profilok** panelen válassza a **Létrehozás** elemet.
4. A **Regisztrációs profil létrehozása** panelen adja meg az Intune-ban megjelenő profil **nevét** és **leírását**.
5. A **Felhasználói affinitás** beállítással adhatja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül legyenek-e regisztrálva.

 - **Regisztrálás felhasználói affinitással** – A telepítés során egy adott felhasználóhoz társítja az eszközt.

  Az Apple School Manager megosztott iPadeket kezelő üzemmódja felhasználói affinitás nélküli regisztrálást igényel.

 - **Regisztráció felhasználói affinitás nélkül** – Ezt a lehetőséget olyan eszközökhöz válassza, amelyeket nem egy adott felhasználóhoz társítottak, például megosztott eszközök esetében. Olyan eszközökhöz használja, amelyek a helyi felhasználói adatokhoz való hozzáférés nélkül végeznek feladatokat. Egyes alkalmazások, mint például a Céges portál alkalmazás, nem működnek.

6. Válassza az **Eszközkezelési beállítások** lehetőséget. A rendszer ezeket az elemeket az aktiválás során állítja be, és a módosításhoz a gyári beállítások visszaállítására van szükség. Konfigurálja az alábbi profilbeállításokat, majd válassza a **Mentés** lehetőséget:

  ![Képernyőkép ‒ Felügyeleti mód kiválasztása. Az eszköz a következő beállításokkal rendelkezik: Felügyelt, Zárolt regisztráció és Párosítás engedélyezése „Az összes elutasítása” értékkel. Az Apple Configurator-tanúsítványok lehetőség új regisztrációs programprofiloknál szürkén jelenik meg.](./media/enrollment-program-profile-mode.png)

    - **Felügyelt** – olyan felügyeleti mód, amely több felügyeleti funkciót engedélyez, és alapértelmezés szerint tiltja az Aktiválási zár funkciót. Ha a jelölőnégyzetet üresen hagyja, a felügyeleti lehetőségek korlátozva lesznek.

    - **Zárolt regisztráció** – (Felügyelt felügyeleti mód szükséges hozzá) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását. Ha a jelölőnégyzetet üresen hagyja, lehetővé teszi a felügyeleti profil eltávolítását a Beállítások menüből.

  - **Megosztott iPad** – (**Felhasználói affinitás nélküli regisztrálást** és **Felügyelt** üzemmódot igényel.) Egy felügyelt Apple ID azonosító használatával több felhasználónak teszi lehetővé a regisztrált iPadekre való bejelentkezést. A felügyelt Apple ID-k létrehozása az Apple School Manager portálján történik.

  >[!NOTE]
  >Ha a **Felhasználói affinitás** a **Felhasználói affinitással** lehetőségre van állítva, vagy a **Felügyelt** üzemmód **ki** van kapcsolva, a rendszer letiltja a Megosztott iPad üzemmódot a regisztrációs profilban.

  - **Gyorsítótárazott felhasználók maximális száma** – (a **Megosztott iPad** üzemmód  = **Igen** állapota kötelező) létrehoz egy partíciót az eszközön az egyes felhasználóknak. A javasolt érték azon diákok száma, akik egy meghatározott időtartamra vonatkozóan valószínűleg használják az eszközt. Például ha hat diák használja rendszeresen az eszközt egy adott héten, állítsa ezt a számot hatra.  

    - **Párosítás engedélyezése** – meghatározza, hogy az iOS-eszközök szinkronizálhatók-e a számítógéppel. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

    - **Apple Configurator-tanúsítványok** – Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választotta a **Párosítás engedélyezése** területen, válassza ki az importálandó Apple Configurator-tanúsítványt.

7. Válassza a **Beállítási asszisztens beállításai** lehetőséget, és a következő profilbeállítások konfigurálása után válassza a **Mentés** gombot:

    - **Részleg neve** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.

    - **Részleg telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a Segítségre van szüksége? gombra kattint.
    - **A Beállítási asszisztens beállításai** – A Beállítási asszisztens beállításaiból való kizárás esetén ezek a beállítások később is konfigurálhatók az iOS **Beállítások** menüjében.
        - **PIN-kód** – PIN-kód kérése aktiváláskor. PIN-kód megadására mindig szükség van, kivéve, ha az eszköz biztonságát, illetve elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt).
        - **Helyalapú szolgáltatások** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja a szolgáltatást.
        - **Visszaállítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során iCloud-alapú biztonsági mentést fog kérni.
        - **Apple ID** – Engedélyezés esetén az iOS kérni fogja a felhasználótól az Apple ID-t, ha a felhasználó annak megadása nélkül próbál alkalmazást telepíteni az Intune-ban. Az App Store-beli iOS-alkalmazások letöltéséhez Apple ID-ra van szükség, az Intune által telepített alkalmazásokat is beleértve.
        - **Feltételek és kikötések** – Ha engedélyezte, a Beállítási asszisztens az aktiválás során arra fogja kérni a felhasználót, hogy fogadja el az Apple használati feltételeit.
        - **Touch ID** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Apple Pay** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Nagyítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Siri** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Diagnosztikai adatok** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást

8. A profilbeállítások mentéséhez a **Regisztrációs profil létrehozása** panelen kattintson a **Létrehozás** elemre.

## <a name="connect-school-data-sync"></a>A School Data Sync csatlakoztatása
(Igény szerint) Az Apple School Manager támogatja az osztálynévsorok Microsoft School Data Sync (SDS) használatával történő szinkronizálását az Azure Active Directoryba (AD). Az alábbi lépések végrehajtásával használhatja az SDS-t az iskolai adatok szinkronizálására.

1. A **Készülékregisztrációs programbeli token** panelen válassza a kék információs szalagot vagy az **SDS-csatlakozás** elemet.
2. **A token használatának engedélyezése a Microsoft School Data Sync számára** beállításnál válassza az **Engedélyezés** lehetőséget. Ez a beállítás teszi lehetővé az Intune csatlakoztatását az Office 365-beli SDS szolgáltatáshoz.
3. Az Apple School Manager és az Azure AD csatlakoztatásához válassza **A Microsoft School Data Sync beállítása** elemet. További információ [a School Data Sync konfigurálásáról](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. A mentéshez és a folytatáshoz kattintson az **OK** gombra.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az Apple School Manager-eszközök felügyeletére, szinkronizálhatja az Intune-t az Apple szolgáltatással, hogy a felügyelt eszközök megjelenjenek az Intune-ban.

1. Az Azure-beli Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. A **Készülékregisztrációs programbeli eszközök** területen kattintson a **Szinkronizálás** elemre. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.
3. A **Szinkronizálás** panelen válassza a **Szinkronizálási kérelem** lehetőséget. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.

  ![Képernyőkép – Szinkronizálási kérelem hivatkozás kiválasztása a Szinkronizálás panelen.](./media/enrollment-program-device-request-sync.png)

  Az Apple elfogadható forgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
   -    Teljes szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
   -    A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.

>[!NOTE]
>Az Apple School Manager sorozatszámait a **Készülékregisztrációs programba felvett eszközök** panelről is hozzárendelheti a profilokhoz.

## <a name="assign-a-profile-to-devices"></a>Profil hozzárendelése az eszközökhöz
Az Intune által felügyelt Apple School Manager-eszközökhöz még a regisztrálás előtt hozzá kell rendelni egy regisztrációs profilt.

1. Az Azure-beli Intune-portálon válassza az **Eszközregisztráció** > **Apple-regisztráció**, majd a **Készülékregisztrációs programbeli profilok** lehetőséget.
2. A **Készülékregisztrációs programbeli profilok** listából válassza ki az eszközhöz hozzárendelni kívánt profilt, majd válassza az **Eszköz-hozzárendelések** elemet.

 ![Képernyőkép – Eszközök hozzárendelése, a Hozzárendelés kijelölésével.](./media/enrollment-program-device-assign.png)

3. Kattintson a **Hozzárendelés** elemre, majd válassza ki a profilhoz hozzárendelni kívánt Apple School Manager-eszközöket. A megjelenített eszközöket az alábbiak szerint szűrheti:
  - **nem hozzárendelt**
  - **bármelyik**
  - **&lt;profilnév&gt;**
4. Válassza ki a hozzárendelni kívánt eszközöket. Az oszlop feletti jelölőnégyzettel legfeljebb 1000 listázott eszköz jelölhető ki. Kattintson a **Hozzárendelés** elemre. Ha több mint 1000 eszközt szeretne hozzárendelni, ismételje meg a lépéseket, amíg az összes eszközt hozzá nem rendelte egy regisztrációs profilhoz.

  ![Képernyőkép – A DEP-profil hozzárendelésére szolgáló gomb az Intune-ban](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Most már megkezdheti a céges eszközök kiosztását a felhasználóknak. Az iOS rendszerű Apple School Manager-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyeletre. Ha az eszközt már aktiválták és használatban van, a profil csak akkor alkalmazható, ha az eszközön visszaállították a gyári beállításokat.
