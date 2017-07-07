---
title: "Eszközök regisztrálásával kapcsolatos problémák elhárítása"
titleSuffix: Intune on Azure
description: "Az eszközök regisztrálásával kapcsolatos problémák elhárítása."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b7af9168164f1cccf3feae5bbdfd8014f8c7c1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Eszközök regisztrálásával kapcsolatos problémák elhárítása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az eszközök regisztrálásával kapcsolatos problémák megoldásához nyújt segítséget. Ha ezekkel az információkkal nem tudja megoldani a problémát, a [Hogyan kérhet támogatást az Intune-hoz](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) című témakörben talál további részleteket a segítségkéréshez.


## <a name="initial-troubleshooting-steps"></a>Első hibaelhárítási lépések

A hibaelhárítás megkezdése előtt győződjön meg róla, hogy az Intune helyesen van konfigurálva a regisztráláshoz. Az egyes platformokra vonatkozó regisztrációs lépéseket az [Android- és Standard Knox-eszközök regisztrációja](android-enroll.md) című cikkből ismerheti meg.

A felügyelt eszközök felhasználói össze tudják gyűjteni a regisztrációs és diagnosztikai naplókat, hogy átnézhesse őket. A naplók felhasználók általi gyűjtésére vonatkozó utasítások itt találhatók:

- [Az Android regisztrálási hibáinak elküldése a rendszergazdának](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Az iOS-hibák elküldése a rendszergazdának](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Eszközök regisztrálásával kapcsolatos általános problémák
Ezek a problémák az összes eszközplatformon előfordulhatnak.

### <a name="device-cap-reached"></a>Eszközök maximális száma elérve
**Probléma:** A regisztráció során hibaüzenet (például **A Vállalati portál átmenetileg nem érhető el**) jelenik meg egy iOS-eszközön, és a Configuration Managerben a DMPdownloader.log a **DeviceCapReached** hibát tartalmazza.

**Megoldás:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>A regisztrált és engedélyezett eszközök számának ellenőrzése

Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Az Azure Portal Intune paneljén keresse meg az **Eszközök regisztrálása** > **Regisztrációs korlátozások** részt, és ellenőrizze, hogy az adott felhasználóhoz nincs-e a maximálisan megengedett 15 eszköznél több hozzárendelve.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

A rendszergazdák az Azure Active Directory portálon törölhetnek eszközöket.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Eszközök törlése az Azure Active Directory portálon

1.  Nyissa meg a [http://aka.ms/accessaad](http://aka.ms/accessaad) weblapot, vagy válassza a **Felügyelet** &gt; **Azure AD** lehetőséget a [https://portal.office.com](https://portal.office.com) portálon.

2.  A lap bal oldalán található hivatkozást használva jelentkezzen be a szervezeti azonosítójával.

3.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (kattintson a **Register your free Azure Active Directory** előfizetési hivatkozásra).

4.  Válassza az **Active Directory** lehetőséget, és jelölje ki a szervezetét.

5.  Válassza a **Felhasználók** fület.

6.  Jelölje ki azokat a felhasználókat, akiknek az eszközeit törölni szeretné.

7.  Válassza az **Eszközök** lehetőséget.

8.  Szükség szerint távolítson el eszközöket, többek között azokat, amelyeket már nem használnak vagy pontatlan definíciókkal rendelkeznek.

> [!NOTE]

> Készülékregisztráció-kezelők használatával elkerülheti a regisztrációk felső korlátjának elérését, az [Eszközök regisztrációja készülékregisztráció-kezelő használatával](device-enrollment-manager-enroll.md) című témakörben leírtaknak megfelelően.
>
> A Készülékregisztráció-kezelők csoportba felvett felhasználói fiók nem tud eszközt regisztrálni, ha az adott felhasználói fiókra feltételes hozzáférési szabályzat érvényes.

### <a name="company-portal-temporarily-unavailable"></a>A Vállalati portál átmenetileg nem érhető el
**Probléma:** Az eszközön **A Vállalati portál átmenetileg nem érhető el** hibaüzenet jelenik meg.

**Megoldás:**

1.  Távolítsa el az eszközről az Intune Vállalati portál alkalmazást.

2.  Nyissa meg a böngészőt az eszközön, keresse meg a [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)portált, és tegyen kísérletet egy felhasználói bejelentkezésre.

3.  Ha a felhasználó nem tud bejelentkezni, próbálkozzon meg egy másik hálózattal.

4.  Ha nem sikerül, ellenőrizze, hogy a felhasználói hitelesítő adatokat megfelelően szinkronizálta-e a rendszer az Azure Active Directoryval.

5.  Ha a felhasználó bejelentkezése sikerül, egy iOS-eszköz kérni fogja, hogy telepítse az Intune Vállalati portál alkalmazást, és regisztráljon. Az Android-eszközökön manuálisan kell telepítenie az Intune Vállalati portál alkalmazást, amelyet követően újból megpróbálkozhat a regisztrációval.

### <a name="mdm-authority-not-defined"></a>Nincs megadva mobileszköz-kezelési szolgáltató
**Hiba:** Megjelenik egy **Nincs megadva mobileszköz-kezelési szolgáltató** hibaüzenet.

**Megoldás:**

1.  Ellenőrizze, hogy a mobileszköz-kezelési szolgáltató megfelelően be van-e állítva a használt Intune szolgáltatáshoz, az Office 365-höz vagy a System Center Configuration Managerbe integrált Intune-hoz. További útmutatásért tekintse meg a [Mobileszköz-felügyeleti szolgáltató megadása](mdm-authority-set.md) című témakört.

    > [!NOTE]    
    > A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információért tekintse meg a [Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) című részt.

2.  Győződjön meg arról, hogy a rendszer megfelelően szinkronizálta a felhasználói hitelesítő adatokat az Azure Active Directoryval. Ehhez ellenőrizze, hogy az egyszerű felhasználónevük megegyezik-e az Active Directory adataival a fiókportálon.
    Ha a felhasználónév nem egyezik meg az Active Directory adataival:

    1.  Kapcsolja ki a DirSync eszközt a helyi kiszolgálón.

    2.  Törölje a nem egyező felhasználót az **Intune-fiókportál** felhasználói listáról.

    3.  Várjon körülbelül egy óráig, amíg az Azure szolgáltatás eltávolítja a helytelen adatokat.

    4.  Kapcsolja be újból a DirSync eszközt, és ellenőrizze, hogy most már megfelelően van-e szinkronizálva a felhasználó.

3.  A System Center Configuration Managerbe integrált Intune használata esetén ellenőrizze, hogy a felhasználó érvényes felhőbeli felhasználói azonosítóval rendelkezik-e:

    1.  Nyissa meg az SQL Management Studiót.

    2.  Csatlakozzon a megfelelő adatbázishoz.

    3.  Nyissa meg az adatbázismappát, és keresse meg, majd nyissa meg a **CM_DBName** mappát, ahol a DBName az ügyféladatbázis neve.

    4.  A lap tetején kattintson az **Új lekérdezés** elemre, majd hajtsa végre az alábbi lekérdezéseket:

        -   Az összes felhasználó megjelenítése: `select * from [CM_ DBName].[dbo].[User_DISC]`.

        -   Adott felhasználók megjelenítéséhez használja a következő lekérdezést, ahol a %testuser1% képviseli a megkeresni kívánt felhasználóhoz tartozó username@domain.com-t: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        A lekérdezés megírása után válassza az **!Execute** lehetőséget.
        Az eredmények visszaadása után keresse meg a felhő felhasználójának azonosítóját.  Ha nem található azonosító, a felhasználó nem rendelkezik Intune-licenccel.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Nem lehet szabályzatot létrehozni vagy eszközöket regisztrálni, ha a vállalat neve speciális karaktereket tartalmaz.
**Hiba:** Nem lehet szabályzatot létrehozni vagy eszközöket regisztrálni.

**Megoldás:** Az [Office 365 felügyeleti központban](https://portal.office.com/) törölje a speciális karaktereket a vállalat nevéből, és mentse a vállalati adatokat.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Nem lehet bejelentkezni vagy eszközöket regisztrálni több ellenőrzött tartomány esetén.
**Hiba:** Amikor a második ellenőrzött tartományt adja hozzá az AD FS-hez, a második tartomány egyszerű felhasználóneves (UPN) utótagjával rendelkező felhasználók nem tudnak bejelentkezni a portálokra vagy nem tudnak eszközöket regisztrálni.


**Megoldás:** Az olyan Microsoft Office 365-ügyfeleknek, akik egyszeri bejelentkezést (SSO) használnak az AD FS 2.0-n keresztül, és a szervezetükben több felső szintű tartomány szerepel az UPN-utótagban (például @contoso.com vagy @fabrikam.com), az AD FS 2.0 összevonási szolgáltatás külön példányát kell telepítenie minden utótag esetében.  Már létezik egy [összegzés az AD FS 2.0-hoz](http://support.microsoft.com/kb/2607496), amelyhez használható a **SupportMultipleDomain** kapcsolóval, hogy az AD FS-kiszolgáló támogassa az ilyen helyzetet anélkül, hogy további AD FS 2.0 kiszolgálókra lenne szükség. További információkat [ebben a blogban](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) talál.


## <a name="android-issues"></a>Android-problémák
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Az eszközök nem tudnak lejelentkezni az Intune szolgáltatásnál, és az Intune felügyeleti konzolján „Nem megfelelő” állapotúként jelennek meg
**Probléma:** Egyes, az Android 4.4.x és 5.x verzióját futtató Samsung-eszközök esetében előfordulhat, hogy egy idő után nem jelentkeznek le újra az Intune szolgáltatásnál. Ha nem jelentkeznek le az eszközök:

- Nem kaphatják meg a szabályzatot, az alkalmazásokat és a távoli parancsokat az Intune szolgáltatástól.
- A felügyeleti konzolon **Nem megfelelő** felügyeleti állapotúnak látszanak.
- A feltételes hozzáférési szabályzattal védett felhasználók elveszíthetik a vállalati erőforrásokhoz való hozzáférésüket.

A Samsung megerősítette, hogy az egyes Samsung-eszközökre előtelepített Samsung Smart Manager szoftver inaktiválhatja az Intune Munkahelyi portált és összetevőit. Ha a Munkahelyi portál inaktív állapotú, nem futhat a háttérben, ezért nem tud kapcsolatot létesíteni az Intune szolgáltatással.

**1. megoldás:**

Kérje meg a felhasználókat, hogy manuálisan indítsák el a Munkahelyi portál alkalmazást. Az alkalmazás az újraindítása után lejelentkezik az Intune szolgáltatásnál.

> [!IMPORTANT]
> A Munkahelyi portál manuális megnyitása átmeneti megoldás, mert a Samsung Smart Manager ismét inaktiválhatja a Munkahelyi portál alkalmazást.

**2. megoldás:**

Kérje meg a felhasználókat, hogy próbáljanak meg frissíteni az Android 6.0-s verziójára. Az Android 6.0 rendszerű eszközökön nem jelentkezik az inaktiválás problémája. A felhasználók a **Beállítások** > **Eszköz névjegye** > **Download updates manually** (Frissítések manuális letöltése) területen ellenőrizhetik, hogy elérhető-e frissítés. A frissítést az eszközön megjelenő útmutatás szerint végezhetik el.

**3. megoldás:**

Ha a 2. megoldás nem működik, kérje a felhasználókat a következő lépések elvégzésére, hogy a Smart Manager ne felügyelje a Munkahelyi portál alkalmazást:

1. Indítsa el az eszközön a Smart Manager alkalmazást.

  ![A Smart Manager ikon kiválasztása az eszközön](./media/smart-manager-app-icon.png)

2. Válassza a **Battery** (Akkumulátor) csempét.

  ![A Battery (Akkumulátor) csempe kiválasztása](./media/smart-manager-battery-tile.png)

3. Válassza az **App power saving** (Alkalmazás energiatakarékossága) vagy **App optimization** (Alkalmazás optimalizálása) terület **Detail** (Részletek) elemét.

  ![Az App power saving (Alkalmazás energiatakarékossága) vagy App optimization (Alkalmazás optimalizálása) terület Detail (Részletek) elemének kiválasztása](./media/smart-manager-app-power-saving-detail.png)

4. Koppintson a **Munkahelyi portál** elemre az alkalmazáslistában.

  ![A Munkahelyi portál kiválasztása az alkalmazáslistából](./media/smart-manager-company-portal.png)

5. Válassza a **Turned off** (Kikapcsolva) beállítást.

  ![A Turned off (Kikapcsolva) beállítás kiválasztása az App optimization (Alkalmazás optimalizálása) párbeszédpanelen](./media/smart-manager-app-optimization-turned-off.png)

6. Győződjön meg róla az **App power saving** (Alkalmazás energiatakarékossága) vagy az **App optimization** (Alkalmazás optimalizálása) területen, hogy a Munkahelyi portál ki van kapcsolva.

  ![Annak ellenőrzése, hogy a Munkahelyi portál ki van-e kapcsolva](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Profiltelepítési hiba
**Hiba:** **Profiltelepítési hiba** üzenet jelenik meg egy Android-eszközön.

**Megoldás:**

1.  Ellenőrizze, hogy az Ön által használt Intune szolgáltatás verziójának megfelelő licenc van-e hozzárendelve a felhasználóhoz.

2.  Győződjön meg arról, hogy az eszköz még nincs egy másik MDM szolgáltatóhoz regisztrálva, vagy még nincs hozzá felügyeleti profil telepítve.

3.  Ellenőrizze, hogy az Androidhoz készült Chrome az alapértelmezett böngésző-e, és a cookie-k engedélyezettek-e.

### <a name="android-certificate-issues"></a>Android-tanúsítványokkal kapcsolatos problémák

**Probléma:** A felhasználó eszköze a következő üzenetet mutatja: *Nem tud bejelentkezni, mert az eszközön hiányzik egy szükséges tanúsítvány.*

**1. megoldás**:

Kérje meg a felhasználót, hogy kövesse az [eszközről hiányzó tanúsítvány problémájának kezelését ismertető cikk](https://docs.microsoft.com/intune-user-help/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) útmutatását. Ha a hiba ezt követően sem szűnik meg, kérje meg a felhasználókat, hogy próbálkozzanak a 2. megoldással.

**2. megoldás**:

Ha a felhasználók a vállalati hitelesítő adatok megadását, illetve az összevont bejelentkezési oldalra való átirányítást követően is a hiányzó tanúsítványra utaló hibát látják, elképzelhető, hogy az Active Directory összevonási szolgáltatások (AD FS) kiszolgálójáról hiányzik egy közbenső tanúsítvány.

A tanúsítványhiba azért lép fel, mivel az Android rendszerű eszközöknél szükség van rá, hogy az [SSL Server hello](https://technet.microsoft.com/library/cc783349.aspx) tartalmazzon egy közbenső tanúsítványt, de jelenleg az alapértelmezett AD FS-kiszolgálók és AD FS-proxykiszolgálók csak az AD FS szolgáltatás SSL-tanúsítványát küldik el az SSL-ügyfél hello üzenetére adott SSL-kiszolgálói hello válasz részeként.

A probléma megoldásához importálja a tanúsítványt az AD FS-kiszolgálón vagy a proxykon található személyes számítógép-tanúsítványok tárába a következő módon:

1.  Indítsa el a helyi számítógép tanúsítványkezelő konzolját az AD FS- és a proxykiszolgálókon. Kattintson jobb gombbal a **Start** gombra, válassza a **Futtatás** lehetőséget, majd írja be: **certlm.msc**.
2.  Bontsa ki a **Személyes** elemet, majd válassza a **Tanúsítványok** lehetőséget.
3.  Keresse meg az AD FS szolgáltatással való kommunikációhoz szükséges tanúsítványt (ez egy nyilvános aláírású tanúsítvány), és kattintson rá duplán a tulajdonságok megjelenítéséhez.
4.  Válassza a **Tanúsítványlánc** lapfület a tanúsítvány szülőtanúsítványának/-tanúsítványainak megjelenítéséhez.
5.  Az összes szülőtanúsítványnál válassza a **Tanúsítvány megtekintése** lehetőséget.
6.  Válassza a **Részletek** lapot, majd a **Másolás fájlba** lehetőséget.
7.  A varázsló utasításait követve exportálja vagy mentse a tanúsítvány nyilvános kulcsát a kívánt helyre.
8.  Importálja a 3. lépésben exportált szülőtanúsítványokat a Helyi számítógép\Személyes\Tanúsítványok mappába. Ehhez kattintson a jobb gombbal a **Tanúsítványok** elemre, válassza a **Minden feladat** > **Importálás** lehetőséget, majd a varázsló utasításait követve importálja a tanúsítvány(oka)t.
9.  Indítsa újra az AD FS-kiszolgálókat.
10. Ismételje meg a fenti lépéseket az összes AD FS- és proxykiszolgálón.
A felhasználó ezután már be kell, hogy tudjon jelentkezni a Vállalati portál alkalmazásba az Android-eszközről.

**A tanúsítványok megfelelő telepítésének ellenőrzése**:

A következő lépésekben csupán a tanúsítvány megfelelő telepítésének ellenőrzésére rendelkezésre álló számos módszer és eszköz egyikét mutatjuk be.

1. Nyissa meg az [ingyenes Digicert eszközt](ttps://www.digicert.com/help/).
2. Adja meg az AD FS-kiszolgáló teljes tartománynevét (például sts.contoso.com), majd válassza a **CHECK SERVER** (Kiszolgáló ellenőrzése) lehetőséget.

Ha a kiszolgálótanúsítványt megfelelően telepítette, az eredményeknél csak pipák jelennek meg. Ha a fenti probléma továbbra sem szűnt meg, piros X jelenik meg a jelentés „Certificate Name Matches” (Tanúsítványnév-egyezések) és „SSL Certificate is correctly Installed” (Az SSL-tanúsítvány megfelelő telepítése) részében.


## <a name="ios-issues"></a>iOS-problémák

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük
**Probléma:** Az iOS-eszközök nem jelentkeznek be az Intune szolgáltatásba. Az eszközök csak a szolgáltatásba való rendszeres bejelentkezéssel őrizhetik meg a vállalati erőforrásokhoz való hozzáférési jogosultságukat. Ha az eszközök rendszeres bejelentkezése nem történik meg:

- Nem kaphatják meg a szabályzatot, az alkalmazásokat és a távoli parancsokat az Intune szolgáltatástól.
- A felügyeleti konzolon **Nem megfelelő** felügyeleti állapotúnak látszanak.
- A feltételes hozzáférési szabályzattal védett felhasználók elveszíthetik a vállalati erőforrásokhoz való hozzáférésüket.

**Megoldás:** Az alábbi megoldások megosztásával segíthet a végfelhasználóknak visszaszerezni a vállalati erőforrásokhoz való hozzáférési jogosultságukat.

Amikor a felhasználók elindítják a Vállalati portál iOS-alkalmazást, megállapítható, hogy az eszköz kapcsolata megszakadt-e az Intune-nal. Ha az alkalmazás azt észleli, hogy nincs kapcsolat, automatikusan megpróbál szinkronizálni az Intune-nal az újrakapcsolódáshoz, és a felhasználók a következő értesítést fogják látni: **A szinkronizálási kísérlet folyamatban van...** beágyazott értesítés.

  ![A szinkronizálási kísérlet folyamatban van – értesítés](./media/ios_cp_app_trying_to_sync_notification.png)

Ha a szinkronizálás sikeres, a **Sikeres szinkronizálás** beágyazott értesítés jelenik meg a Vállalati portál iOS-alkalmazásban, amely azt jelzi, hogy az eszköz kifogástalan állapotban van.

  ![Sikeres szinkronizálás – értesítés](./media/ios_cp_app_sync_successful_notification.png)

Ha a szinkronizálás sikertelen, a felhasználók a **Nem lehet szinkronizálni** beágyazott értesítést fogják látni a Vállalati portál iOS-alkalmazásban.

  ![Nem lehet szinkronizálni – értesítés](./media/ios_cp_app_unable_to_sync_notification.png)

A probléma elhárításához a felhasználóknak a **Nem lehet szinkronizálni** értesítés jobb oldalán lévő **Beállítás** gombot kell használniuk. A Beállítás gomb használatával a felhasználók a Vállalati hozzáférés beállítása folyamatképernyőre kerülnek, ahol a képernyőn megjelenő utasítások követésével regisztrálhatják az eszközüket.

  ![A Vállalati hozzáférés beállítása képernyő](./media/ios_cp_app_company_access_setup.png)

Regisztráció után az eszközök ismét kifogástalan állapotba kerülnek, és visszakapják a vállalati erőforrásokhoz való hozzáférési jogosultságukat.

### <a name="profile-installation-failed"></a>Profiltelepítési hiba
**Hiba:** **Profiltelepítési hiba** üzenet jelenik meg egy iOS-eszközön.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Sikertelen profiltelepítés hibaelhárításának lépései

1.  Ellenőrizze, hogy az Ön által használt Intune szolgáltatás verziójának megfelelő licenc van-e hozzárendelve a felhasználóhoz.

2.  Győződjön meg arról, hogy az eszköz még nincs egy másik MDM szolgáltatóhoz regisztrálva, vagy még nincs hozzá felügyeleti profil telepítve.

3.  Nyissa meg a [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) portált, és amikor a rendszer kéri, telepítse a profilt.

4.  Ellenőrizze, hogy az iOS-hez készült Safari az alapértelmezett böngésző-e, és a cookie-k engedélyezettek-e.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>A regisztrált iOS-eszköz nem jelenik meg a konzolon a System Center Configuration Managerbe integrált Intune használata esetén
**Hiba:** A felhasználó regisztrálja az iOS-eszközt, de az nem jelenik meg a Configuration Manager felügyeleti konzolon. Az eszköz nem jelzi, hogy már regisztrálva van. Lehetséges okok:

- Előfordulhat, hogy az Intune-összekötőt az egyik fiókba regisztrálta, majd egy másik fiókba is regisztrálta.
- Előfordulhat, hogy az MDM-tanúsítványt az egyik fiókból töltötte le, és egy másik fiókban használta.


**Megoldás:** Hajtsa végre a következő lépéseket:

1. Tiltsa le az iOS rendszert a Windows Intune-összekötőben.
    1. Kattintson a jobb gombbal az Intune-előfizetésre, és válassza a **Tulajdonságok** lehetőséget.
    1. Az „iOS” lapon törölje a jelet az „iOS-eszközök regisztrációjának engedélyezése” jelölőnégyzetből.



2. Az SQL-ben futtassa a következő lépéseket a CAS-adatbázison:

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
3. Indítsa újra az SMS Executive szolgáltatást vagy a CM-kiszolgálót.

4. Szerezzen be egy új APN-tanúsítványt, majd töltse fel. Ehhez kattintson a jobb gombbal az Intune-előfizetésre a Configuration Manager bal oldali ablaktáblájában. Válassza az **APN szolgáltatás tanúsítványkérésének létrehozása** parancsot, és kövesse az utasításokat.
5.
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problémák a System Center Configuration Managerbe integrált Intune használatakor

### <a name="mobile-devices-disappear"></a>Mobileszközök tűnnek el

**Hiba:** Miután sikeresen regisztrált egy mobileszközt a Configuration Managerbe, az eszköz eltűnik a mobileszköz-gyűjteményből, de továbbra is rendelkezik felügyeleti profillal, és szerepel a CSS-átjáróban.

**Megoldás:** Ez a hiba akkor fordulhat elő, ha egyedi eljárást használ a tartományhoz nem csatlakozó eszközök eltávolítására, vagy a felhasználó kivonta az eszközt az előfizetésből. Ha meg szeretné állapítani, hogy melyik eljárás vagy felhasználói fiók távolította el az eszközt a Configuration Manager konzolból, az alábbi lépések végrehajtásával megtudhatja, hogyan történt az eszköz eltávolítása.

1.  A Configuration Manager felügyeleti konzolban válassza a **Figyelés** &gt; **Rendszer állapota** &gt; **Állapotüzenet-lekérdezések** elemet.

2.  Kattintson a jobb gombbal a **Manuálisan törölt gyűjtemény tagerőforrások** elemre, és válassza az **Üzenetek megjelenítése** parancsot.

3.  Válasszon ki egy megfelelő időpontot vagy dátumot, vagy az elmúlt 12 óra lehetőséget.

4.  Keresse meg a kérdéses eszközt, és ellenőrizze, hogy miként történt az eltávolítása. Az alábbi példában az SCCMInstall nevű fiók törölte az eszközt egy ismeretlen alkalmazással.

    ![Képernyőfelvétel az eszköztörlési diagnózisról](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Ellenőrizze, hogy a Configuration Manager nem tartalmaz-e olyan ütemezett feladatot, szkriptet vagy egyéb folyamatot, amely automatikusan kiürítheti a tartományhoz nem csatlakozó, a mobil-, illetve a kapcsolódó eszközöket.




### <a name="other-ios-enrollment-errors"></a>Egyéb iOS-beléptetési hibák

[Az iOS beléptetési hibái](https://docs.microsoft.com/intune-user-help/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) listában áttekintheti, hogy a felhasználók milyen hibaüzenetekkel találkozhatnak. A lista információkat nyújt azokkal a hibaüzenetekkel kapcsolatban, amelyeket a felhasználók láthatnak, továbbá tartalmazza az adott probléma megoldásához szükséges lépéseket is.

## <a name="pc--issues"></a>PC-kkel kapcsolatos problémák

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>A gép már regisztrálva van – hibakód: hr 0x8007064c
**Hiba:** A regisztrálás sikertelen **A gép már regisztrálva van** hibaüzenettel. A regisztrálási napló a **hr 0x8007064c** hibakódot tartalmazza.

Ennek a hibának az lehet az oka, hogy a számítógép korábban már volt regisztrálva, vagy olyan számítógép klónozott lemezképét tartalmazza, amely már volt regisztrálva. Az előző fiók fióktanúsítványa továbbra is megtalálható a számítógépen.

**Megoldás:**

1. A **Start** menüben használja a **Futtatás** -> **MMC** parancsot.
1. Válassza a **Fájl** > **Beépülő modulok hozzáadása/eltávolítása** parancsot.
1. Kattintson duplán a **Tanúsítványok** elemre, válassza a **Számítógépfiók** >  lehetőséget, kattintson a **Tovább** gombra, végül válassza a **Helyi számítógép** lehetőséget.
1. Kattintson duplán a **Tanúsítványok (Helyi számítógép)** elemre, majd válassza a **Személyes/Tanúsítványok** lehetőséget.
1. Keresse meg az Sc_Online_Issuing által kiadott Intune-tanúsítványt, és ha létezik, törölje.
1. Ha létezik, törölje a következő beállításkulcsot és az összes alkulcsát: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Kísérelje meg újból a regisztrációt.
1. Ha a számítógépet továbbra sem lehet regisztrálni, keresse meg a következő beállításkulcsot, és ha létezik, törölje: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Kísérelje meg újból a regisztrációt.

    > [!IMPORTANT]
    > Ez a szakasz, módszer vagy feladat olyan lépéseket tartalmaz, amelyekkel módosítja a beállításjegyzéket. A beállításjegyzék nem megfelelő módosítása azonban súlyos hibákat okozhat. Ezért ügyeljen arra, hogy pontosan kövesse a leírtakat. További biztonsági intézkedésként a módosítások végrehajtása előtt készítsen biztonsági másolatot a beállításjegyzékről. Így probléma esetén helyreállíthatja a beállításjegyzéket.
    > Ha további tájékoztatásra van szüksége a beállításjegyzék biztonsági mentéséről és visszaállításáról, olvassa el [A beállításjegyzék biztonsági mentése és visszaállítása Windows rendszerben](https://support.microsoft.com/kb/322756) című témakört.

## <a name="general-enrollment-error-codes"></a>Általános beléptetési hibakódok

|Hibakód|Lehetséges probléma|Javasolt megoldás|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |Az ügyfélszámítógép órája nem a helyes időre van beállítva.|Győződjön meg róla, hogy az ügyfélszámítógép órája és időzónája a helyes értékre van beállítva.|
|0x80240438, 0x80CF0438, 0x80CF402C|Nem lehet kapcsolódni az Intune szolgáltatáshoz. Ellenőrizze az ügyfél proxybeállításait.|Ellenőrizze, hogy az Intune támogatja-e az ügyfélszámítógép proxybeállításait, és hogy az ügyfélszámítógépnek van-e internetkapcsolata.|
|0x80240438, 0x80CF0438|Az Internet Explorer és a helyi rendszer proxybeállításai nincsenek konfigurálva.|Nem lehet kapcsolódni az Intune szolgáltatáshoz. Ellenőrizze az ügyfél proxybeállításait, és győződjön meg arról, hogy az Intune támogatja őket, illetve hogy az ügyfélszámítógépnek van internetkapcsolata.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|A beléptetési csomag elavult.|Töltse le és telepítse az aktuális ügyfélszoftvercsomagot a Felügyelet munkaterületen.|
|0x80043002, 0x80CF3002|A fiók karbantartási módban van.|Nem tud új ügyfélszámítógépeket beléptetni, ha a fiók karbantartási módban van. A fiókbeállítások megtekintéséhez jelentkezzen be a fiókba.|
|0x80043003, 0x80CF3003|A fiókot törölték.|Ellenőrizze, hogy az Intune-fiókja és -előfizetése aktív-e. A fiókbeállítások megtekintéséhez jelentkezzen be a fiókba.|
|0x80043005, 0x80CF3005|Az ügyfélszámítógépet eltávolították.|Várjon néhány órát, távolítsa el az ügyfélszoftver minden régebbi verzióját a számítógépről, majd próbálja meg újból telepíteni az ügyfélszoftvert.|
|0x80043006, 0x80CF3006|Elérte a fiók számára engedélyezett maximális munkaállomásszámot.|A szervezetnek további munkaállomásokat kell vásárolnia, mielőtt további ügyfélszámítógépeket léptethet be a szolgáltatásba.|
|0x80043007, 0x80CF3007|A tanúsítványfájl nem található abban a mappában, amelyben a telepítőprogram van.|A telepítés kezdete előtt az összes fájlt csomagolja ki. Ne nevezze át és ne helyezze át a kicsomagolt fájlokat: az összes fájlnak ugyanabban a mappában kell lennie, különben a telepítés sikertelen lesz.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|A szoftvert nem lehet telepíteni, mert függőben van az ügyfélszámítógép újraindítása.|Indítsa újra a számítógépet, majd próbálja meg újból az ügyfélszoftver telepítését.|
|0x80070032|Az ügyfélszámítógép nem felel meg az ügyfélszoftver telepítéséhez szükséges egy vagy több előfeltételnek.|Gondoskodjon róla, hogy minden szükséges frissítés telepítve legyen az ügyfélszámítógépen, majd próbálja meg újból az ügyfélszoftver telepítését.|
|0x80043008, 0x80CF3008|Nem sikerült elindítani a Microsoft Online Management Updates szolgáltatást.|Lépjen kapcsolatba a Microsoft ügyfélszolgálatával a [Hogyan kérhet támogatást az Intune-hoz](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) című szakaszban leírtak szerint.|
|0x80043009, 0x80CF3009|Az ügyfélszámítógép már be van léptetve a szolgáltatásba.|Az ügyfélszámítógépet el kell távolítania, mielőtt újból beléptetheti a szolgáltatásba.|
|0x8004300B, 0x80CF300B|Az ügyfélszoftver telepítési csomagja nem futtatható, mert az ügyfélen futó Windows-verzió nem támogatott.|Az Intune nem támogatja az ügyfélszámítógépen futó Windows-verziót.|
|0xAB2|A Windows Installer nem tud hozzáférni a VBScript futtatókörnyezethez egy egyéni művelet végrehajtásához.|A hibát egy egyéni művelet okozza, amely dinamikus kötésű kódtárakon (DLL-eken) alapul. Előfordulhat, hogy a DLL hibáinak elhárításához a következő témakörben ismertetett eszközöket kell használnia: [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Hasznos eszközök csomag- és telepítési problémák esetére).|
|0x80cf0440|Megszakadt a kapcsolat a szolgáltatásvégponttal.|A próbafiók vagy a díjköteles fiók fel van függesztve. Hozzon létre egy új próbafiókot vagy díjköteles fiókot, és végezze el újból a regisztrálást.|




### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) című témakörben leírtak szerint.
