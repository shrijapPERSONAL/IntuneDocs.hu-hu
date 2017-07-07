---
title: "Az Apple School Manager programba való regisztrálás beállítása iOS-eszközök esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt az Apple School Manager programba való regisztrálás Intune-beli beállításáról céges tulajdonú iOS-eszközök esetén"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>iOS-eszközök regisztrálásának engedélyezése az Apple School Manager programban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az [Apple School Manager (ASM)](https://school.apple.com/) program keretében vásárolt iOS-es eszközök regisztrálásában nyújt segítséget a rendszergazdáknak. A Microsoft Intune vezeték nélkül képes telepíteni egy regisztrációs profilt, amely felügyelet alá helyezi az ASM-eszközöket. A rendszergazdának nem kell az egyes felügyelt eszközökhöz személyesen hozzáférnie. Az ASM-profil tartalmazza azokat a felügyeleti beállításokat, amelyeket a rendszer a regisztrálás során az eszközökre alkalmaz, beleértve a Beállítási asszisztens beállításait is.

**Az ASM-regisztráció lépései**
1. [Az ASM-token beszerzése és az eszközök hozzárendelése](#get-the-asm-token-and-assign-devices)
2. [A regisztrációs profil létrehozása](#create-an-apple-enrollment-profile)
3. [A School Data Sync csatlakoztatása ](#connect-school-data-sync) (nem kötelező)
4. [Az ASM által felügyelt eszközök szinkronizálása](#sync-asm-managed-devices)
5. [Az ASM-profil hozzárendelése az eszközökhöz](#assign-an-asm-profile-to-devices)
6. [Eszközök terjesztése a felhasználóknak](#distribute-devices-to-users)

>[!NOTE]
>Az ASM-regisztrációt nem lehet használni az Apple [készülékregisztrációs programjával (DEP)](device-enrollment-program-enroll-ios.md) vagy az Intune [készülékregisztráció-kezelői](device-enrollment-manager-enroll.md) fiókjával.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Az Apple által kiállított ASM-token beszerzése és az eszközök hozzárendelése

A céges tulajdonú iOS-eszközök regisztrálását csak egy, az Apple-től származó ASM-tokenfájl (.p7m) birtokában végezheti el az Apple School Manager (ASM) programban. Ez a token teszi lehetővé, hogy az Intune szinkronizálja az ASM-ben részt vevő eszközök adatait. A token ezen felül lehetővé teszi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és a feltöltött profilokhoz eszközöket rendeljen hozzá. Az Apple portálján egyúttal a felügyelendő eszközök sorozatszámának hozzárendelését is elvégezheti.

**Előfeltételek**
- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)
- Regisztráció az [Apple School Manager](http://school.apple.com) programban

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt (ez szükséges az Apple ASM-tokenjének létrehozásához).**<br>
1. Az Azure-beli [Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása**, majd a **Készülékregisztrációs programbeli token** elemet.
2. A **Készülékregisztrációs programbeli token** panelen válassza a **Nyilvános kulcs letöltése** elemet, és mentse helyben a letöltött titkosításikulcs-fájlt (.pem). A .pem-fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple School Manager portálról.

**2. lépés Töltse le az ASM-tokent, és végezze el az eszközök hozzárendelését.**<br>
Válassza a **Create a token via Apple School Manager** (Token létrehozása az Apple School Manager használatával) elemet, és jelentkezzen be a céges Apple ID-val. A későbbiekben ezt az Apple ID-t használhatja az ASM-token megújításához.

   1.  Az [Apple School Manager portálján](https://school.apple.com) az **MDM Servers** (MDM-kiszolgálók) szakaszban válassza az **Add MDM Server** (MDM-kiszolgáló hozzáadása) elemet (a jobb felső sarokban).
   2.  Adja meg az **MDM-kiszolgálónevet**. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.
   3.  Az Apple portálján válassza az **Upload File...** (Fájl feltöltése...) elemet, keresse meg a .pem-fájlt, és válassza a **Save MDM Server** (MDM-kiszolgáló mentése) elemet (a jobb alsó sarokban).
   4.  Válassza a **Get Token** (Token beszerzése) elemet, majd töltse le a kiszolgálói tokenfájlt (.p7m) a számítógépre.
   5. A **Device Assignments** (Eszköz-hozzárendelések) szakaszban **válassza ki az eszközt** az **eszköz sorozatszámának** (Serial Numbers) vagy **rendelésszámának** (Order Number) kézi bevitelével, illetve **CSV-fájl feltöltésével** (Upload CSV File).
   6.   Válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) műveletet, majd válassza ki a létrehozott **MDM-kiszolgálót**.
   7. Adja meg, hogy miként fogja kiválasztani az eszközöket ( **Choose Devices**), adja meg az eszközinformációkat, és adja meg a részleteket az eszköz sorozatszáma ( **Serial Number**) vagy rendelésszáma ( **Order Number**) alapján, illetve CSV-fájl feltöltésével ( **Upload CSV File**).
   8. Válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra.

**3. lépés Adja meg az Apple ASM-tokenjének létrehozásához használt Apple ID-t.**<br>A későbbiekben ezt az azonosítót használhatja az Apple ASM-tokenjének megújításához, ezért későbbi felhasználás céljából őrizze meg az azonosítót.

**4. lépés Keresse meg és töltse fel a tokent.**<br>
Keresse meg a tanúsítványfájlt (.p7m), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. Az Intune automatikusan szinkronizálja az Apple-től származó ASM-eszközöket.

## <a name="create-an-apple-enrollment-profile"></a>Az Apple-regisztrációs profil létrehozása
A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. A **Készülékregisztrációs program** szakaszban válassza a **Készülékregisztrációs programbeli profilok** elemet.
3. A **Készülékregisztrációs programbeli profilok** panelen válassza a **Létrehozás** elemet.
4. A **Regisztrációs profil létrehozása** panelen adja meg az Intune-portálon megjelenő profil **nevét** és **leírását**.
5. A **Felhasználói affinitás** beállítással adhatja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül legyenek-e regisztrálva.

 - **Regisztrálás felhasználói affinitással** – Az eszközt össze kell kapcsolni egy felhasználóval a kezdeti beállítás során, majd engedélyezhető számára a vállalati adatok és e-mailek elérése. Válassza ki a felhasználói affinitást azon ASM által felügyelt eszközökhöz, amelyeken a felhasználók a saját felügyelt Apple ID-jukkal jelentkeznek be.

 >[!NOTE]
 >A regisztrálás során a többtényezős hitelesítés (MFA) nem működik felhasználói affinitással rendelkező ASM-eszközökön. A regisztrációt követően az ilyen eszközökön is az elvárásoknak megfelelően működik az MFA.

  Az Apple School Manager megosztott iPadeket kezelő üzemmódja megköveteli a felhasználótól a felhasználói affinitással való regisztrálást.

 >[!NOTE]
    >A felhasználói affinitással rendelkező ASM esetén a felhasználói token kérelmezéséhez engedélyezni kell a [WS-Trust 1.3 Username/Mixed végpontot](https://technet.microsoft.com/library/adfs2-help-endpoints). [További információ a WS-Trust 1.3-ról](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói affinitást igénylő alkalmazások (az üzletági alkalmazások telepítésére szolgáló Céges portál alkalmazást is beleértve) nem fognak működni.

6. Válassza az **Eszközkezelési beállítások** lehetőséget. A rendszer ezeket az elemeket az aktiválás során állítja be, és a módosításhoz a gyári beállítások visszaállítására van szükség. Konfigurálja az alábbi profilbeállításokat, majd válassza a **Mentés** lehetőséget:

    - **Felügyelt** – olyan felügyeleti mód, amely több felügyeleti funkciót engedélyez, és alapértelmezés szerint tiltja az Aktiválási zár funkciót. Ha a jelölőnégyzetet üresen hagyja, a felügyeleti lehetőségek korlátozva lesznek.

    - **Zárolt regisztráció** – (Felügyelt felügyeleti mód szükséges hozzá) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását. Ha a jelölőnégyzetet üresen hagyja, lehetővé teszi a felügyeleti profil eltávolítását a Beállítások menüből.

  - **Megosztott iPad** – (**felhasználói affinitással való regisztrálást** és **felügyelt** üzemmódot igényel) Több felhasználónak teszi lehetővé a regisztrált iPadekre való bejelentkezést egy felügyelt Apple ID használatával. A felügyelt Apple ID-k létrehozása az Apple School Manager portálján történik.

  >[!NOTE]
  >Ha a **Megosztott iPad** üzemmód engedélyezve van a profilban, és a **felhasználói affinitás** vagy a **felügyelt üzemmód** **ki** van kapcsolva, a rendszer letiltja a Megosztott iPad üzemmódot a regisztrációs profilban.

  - **Gyorsítótárazott felhasználók maximális száma** – (a **Megosztott iPad** üzemmód  = **Igen** állapota kötelező) létrehoz egy partíciót az eszközön az egyes felhasználóknak. A javasolt érték azon diákok száma, akik egy meghatározott időtartamra vonatkozóan valószínűleg használják az eszközt. Például ha hat diák használja rendszeresen az eszközt egy adott héten, állítsa ezt a számot hatra.  

    - **Párosítás engedélyezése** – meghatározza, hogy az iOS-eszközök szinkronizálhatók-e a számítógéppel. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

    - **Apple Configurator-tanúsítványok** – Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja a **Párosítás engedélyezése** területen, válassza ki az importálandó Apple Configurator-tanúsítványt.

7. Válassza a **Beállítási asszisztens beállításai** lehetőséget és konfigurálja az alábbi profilbeállításokat, majd válassza a **Mentés** gombot:

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

8. A profilbeállítások mentéséhez a **Regisztrációs profil létrehozása** panelen válassza a **Létrehoz** lehetőséget.

## <a name="connect-school-data-sync"></a>A School Data Sync csatlakoztatása
(Nem kötelező) Az ASM támogatja az osztálynévjegyzék-adatok Microsoft School Data Sync (SDS) használatával történő szinkronizálását az Azure Active Directoryba (AD). Az alábbi lépések végrehajtásával használhatja az SDS-t az iskolai adatok szinkronizálására.

1. A **Készülékregisztrációs programbeli token** panelen válassza a kék információs szalagot vagy az **SDS-csatlakozás** elemet.
2. Állítsa **A token használatának engedélyezése a Microsoft School Data Sync számára** beállítást **Engedélyezés** értékre. Ez a beállítás teszi lehetővé az Intune csatlakoztatását az Office 365-beli SDS szolgáltatáshoz.
3. Az ASM és az Azure AD csatlakoztatásához válassza a **Microsoft School Data Sync beállítása** elemet. További információ [a School Data Sync konfigurálásáról](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. A mentéshez és a folytatáshoz kattintson az **OK** gombra.

## <a name="sync-asm-managed-devices"></a>Az ASM által felügyelt eszközök szinkronizálása
Miután az Intune engedélyt kapott az ASM-eszközök felügyeletére, szinkronizálhatja az Intune-t az ASM szolgáltatással, így a felügyelt eszközök megjelennek az Intune-portálon.

1. Az Intune-portálon válassza az **Eszközök regisztrálása**, majd az **Apple-regisztráció** elemet.
2. A **Készülékregisztrációs programba felvett eszközök** szakaszban válassza a **Szinkronizálás** elemet. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.

    Az Apple elfogadható ASM-forgalomra vonatkozó feltételeinek teljesítése céljából az Intune az alábbi korlátozásokat írja elő:
     -  A teljes ASM-szinkronizálás legfeljebb hétnaponta futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérések elbírálása 15 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.

>[!NOTE]
>Az ASM-sorozatszámokat szintén hozzárendelheti a profilhoz az **Készülékregisztrációs programba felvett eszközök** panelről.

## <a name="assign-an-asm-profile-to-devices"></a>Az ASM-profil hozzárendelése az eszközökhöz
Az Intune által felügyelt ASM-eszközöket a regisztrálás előtt ASM-profilhoz kell hozzárendelni.

1. Az Intune-portálon válassza az **Eszközök regisztrálása** > **Apple-regisztráció**, majd a **Készülékregisztrációs programbeli profilok** elemet.
2. A **Készülékregisztrációs programbeli profilok** listából válassza ki az eszközhöz hozzárendelni kívánt profilt, majd válassza az **Eszköz-hozzárendelések** elemet
3. Válassza a **Hozzárendelés** lehetőséget, majd válassza ki a profilhoz hozzárendelni kívánt ASM-eszközöket. A megjelenített ASM-eszközöket az alábbiak szerint szűrheti:
  - **nem hozzárendelt**
  - **bármelyik**
  - **&lt;ASM-profil neve&gt;**
4. Válassza ki a hozzárendelni kívánt eszközöket. Az oszlop feletti jelölőnégyzettel legfeljebb 1000 listázott eszköz jelölhető ki. Kattintson a **Hozzárendelés** elemre. Ha több mint 1000 eszközt szeretne hozzárendelni, ismételje meg a lépéseket, amíg az összes eszközt hozzá nem rendelte az ASM-profilhoz.

## <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Most már megkezdheti a céges eszközök kiosztását a felhasználóknak. Az iOS rendszerű ASM-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyeletre. Ha az eszközt már aktiválták és használatban van, a profil csak akkor alkalmazható, ha az eszközön visszaállították a gyári beállításokat.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>A Vállalati portál telepítése és használata a felhasználók által

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, a Beállítási asszisztens futtatására és a Céges portál alkalmazás telepítésére van szükség.
