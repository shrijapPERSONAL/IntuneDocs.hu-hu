---
title: Eszközök regisztrálásával kapcsolatos problémák elhárítása
description: Javaslatok az eszközök regisztrálásával kapcsolatos problémák megoldásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b540cd2b2751712604c0ae7172015cb109c9c1d8
ms.sourcegitcommit: 024cce10a99b12a13f32d3995b69c290743cafb8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2018
ms.locfileid: "39039437"
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Eszközök regisztrálásával kapcsolatos problémák elhárítása az Intune-ban

Ez a cikk az eszközök regisztrálásával kapcsolatos problémák megoldásához nyújt segítséget. Ha ezekkel az információkkal nem tudja megoldani a problémát, a [Hogyan kérhet támogatást az Intune-hoz](get-support.md) című témakörben talál további részleteket a segítségkéréshez.


## <a name="initial-troubleshooting-steps"></a>Első hibaelhárítási lépések

A hibaelhárítás megkezdése előtt ellenőrizze, hogy az Intune megfelelően van-e konfigurálva a regisztráláshoz. Ezekről a konfigurációs követelményekről itt olvashat:

-   [Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](setup-steps.md)
-   [iOS- és Mac-eszközök kezelésének beállítása](ios-enroll.md)
-   [Windowsos eszközök kezelésének beállítása](windows-enroll.md)
-   [Android-eszközök kezelésének beállítása](android-enroll.md) – nincs szükség további lépésekre

Azt is biztosíthatja, hogy a felhasználó eszközén megfelelően legyen beállítva a dátum és az idő:

1. Indítsa újra az eszközt.
2. Győződjön meg arról, hogy a dátum és az idő a végfelhasználó időzónájához képest a GMT-szabványokhoz közeli (+ vagy - 12 óra) értékre van beállítva.
3. Távolítsa el, majd telepítse újra az Intune Céges portált (ha ez alkalmazható).

A felügyelt eszközök felhasználói össze tudják gyűjteni a regisztrációs és diagnosztikai naplókat, hogy átnézhesse őket. A naplók felhasználók általi gyűjtésére vonatkozó utasítások itt találhatók:

- [Az Android regisztrálási hibáinak elküldése a rendszergazdának](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Az iOS-hibák elküldése a rendszergazdának](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Eszközök regisztrálásával kapcsolatos általános problémák
Ezek a problémák az összes eszközplatformon előfordulhatnak.

### <a name="device-cap-reached"></a>Eszközök maximális száma elérve
**Probléma:** A regisztráció során hibaüzenet (például **A Vállalati portál átmenetileg nem érhető el**) jelenik meg egy iOS-eszközön, és a Configuration Managerben a DMPdownloader.log a **DeviceCapReached** hibát tartalmazza.

**Megoldás:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>A regisztrált és engedélyezett eszközök számának ellenőrzése

Ellenőrizze az alábbi lépések követésével, hogy a felhasználóhoz nincs-e hozzárendelve több eszköz a legfeljebb megengedettnél:

1. Az Intune-ban válassza az **Eszközök beléptetése** > **Regisztrációs korlátozások** > **Eszközszámkorlátok** lehetőséget. Jegyezze fel az **Eszközszámkorlát** oszlopban látható értéket.

2. Válassza az Intune-ban a **Felhasználók** > **Minden felhasználó** > válassza ki a felhasználót > **Eszközök** lehetőséget. Jegyezze fel a regisztrált eszközök számát.

3. Ha a felhasználó regisztrált eszközeinek száma már megegyezik az eszközszámkorlát értékével, további eszközöket csak akkor regisztrálhat, ha:
    - [eltávolít meglévő eszközöket](devices-wipe.md), vagy
    - növeli az eszközszámkorlátot az [eszközkorlátozások beállításával](enrollment-restrictions-set.md#set-device-limit-restrictions).

Az eszközszámkorlát elérésének elkerüléséhez mindig távolítsa el a már nem használt eszközök rekordjait.

> [!NOTE]
> 
> Az eszközregisztráció-kezelői fiók használatával elkerülheti a maximális szám elérését az eszközregisztráció során. Lásd: [Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel a Microsoft Intune-ban](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
> 
> Az eszközregisztráció-kezelői fiókba felvett felhasználói fiók nem tud regisztrálást végrehajtani, ha az adott felhasználói bejelentkezéshez a Feltételes hozzáférés szabályzat van érvényben.

### <a name="company-portal-temporarily-unavailable"></a>A Vállalati portál átmenetileg nem érhető el
**Probléma:** Az eszközön **A Vállalati portál átmenetileg nem érhető el** hibaüzenet jelenik meg.

**Megoldás:**

1.  Távolítsa el az eszközről az Intune Vállalati portál alkalmazást.

2.  Nyissa meg a böngészőt az eszközön, keresse meg a [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) oldalt, és tegyen kísérletet egy felhasználói bejelentkezésre.

3.  Ha a felhasználó nem tud bejelentkezni, egy másik hálózattal kell próbálkoznia.

4.  Ha nem sikerül, ellenőrizze, hogy a felhasználói hitelesítő adatokat megfelelően szinkronizálta-e a rendszer az Azure Active Directoryval.

5.  Ha a felhasználó bejelentkezése sikerül, egy iOS-eszköz kérni fogja, hogy telepítse az Intune Vállalati portál alkalmazást, és regisztráljon. Az Android-eszközökön manuálisan kell telepítenie az Intune Vállalati portál alkalmazást, amelyet követően újból megpróbálkozhat a regisztrációval.

### <a name="mdm-authority-not-defined"></a>Nincs megadva mobileszköz-kezelési szolgáltató
**Hiba:** Megjelenik egy **Nincs megadva mobileszköz-kezelési szolgáltató** hibaüzenet.

**Megoldás:**

1.  Győződjön meg arról, hogy a Mobileszköz-felügyeleti szolgáltató [megfelelően be van állítva](mdm-authority-set.md).
    
2.  Győződjön meg arról, hogy a rendszer megfelelően szinkronizálta a felhasználói hitelesítő adatokat az Azure Active Directoryval. Ehhez ellenőrizze, hogy az egyszerű felhasználónév megegyezik-e az Active Directory adataival az Office 365 portálon.
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

### <a name="unable-to-sign-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Nem lehet bejelentkezni vagy eszközöket regisztrálni több ellenőrzött tartomány esetén
**Hiba:** Amikor a második ellenőrzött tartományt adja hozzá az AD FS-hez, a második tartomány egyszerű felhasználóneves (UPN) utótagjával rendelkező felhasználók nem tudnak bejelentkezni a portálokra vagy nem tudnak eszközöket regisztrálni.


<strong>Megoldás:</strong> Az olyan Microsoft Office 365-ügyfeleknek, akik egyszeri bejelentkezést (SSO) használnak az AD FS 2.0-n keresztül, és a munkahelyükön több felső szintű tartomány szerepel az UPN-utótagban (például @contoso.com vagy @fabrikam.com), az AD FS 2.0 összevonási szolgáltatás külön példányát kell telepíteni minden utótag esetében. Már létezik egy [összegzés az AD FS 2.0-hoz](http://support.microsoft.com/kb/2607496), amelyhez használható a <strong>SupportMultipleDomain</strong> kapcsolóval, hogy az AD FS-kiszolgáló támogassa az ilyen helyzetet anélkül, hogy további AD FS 2.0 kiszolgálókra lenne szükség. További információkat [ebben a blogban](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) talál.


## <a name="android-issues"></a>Android-problémák

### <a name="android-enrollment-errors"></a>Android-eszközök regisztrálásának hibái

A következő táblázat azon hibákat tartalmazza, melyeket Android-eszközök az Intune-ban való regisztrálásakor tapasztalhatnak a végfelhasználók.

|Hibaüzenet|Probléma|Megoldás|
|---|---|---|
|**A rendszergazdának hozzáférési licencet kell hozzárendelnie**<br>A rendszergazda nem adott hozzáférést az alkalmazás használatához. Kérjen segítséget a rendszergazdától, vagy próbálkozzon újra később.|Az eszközt nem lehet regisztrálni, mert a felhasználó fiókja nem rendelkezik a szükséges licenccel.|Ahhoz, hogy a felhasználók regisztrálhassák az eszközeiket, hozzájuk kell rendelni a szükséges licencet. Ez az üzenet azt jelenti, hogy nem rendelkeznek a megfelelő licenctípussal a meghatározott mobileszköz-kezelő szolgáltatóhoz. Ha például az Intune lett mobileszköz-kezelő szolgáltatóként meghatározva, és System Center 2012 R2 Configuration Manager-licencet használnak, ezt a hibaüzenetet látják.<br><br>További információ: [Intune-licencek felhasználói fiókokhoz való hozzárendelése](/intune/licenses-assign).
|**A rendszergazdának be kell állítania a mobileszköz-felügyeleti szolgáltatót**<br>Úgy tűnik, hogy a rendszergazda még nem állította be a mobileszköz-felügyeleti szolgáltatót. Kérjen segítséget a rendszergazdától, vagy próbálkozzon újra később.|A mobileszköz-kezelő szolgáltató még nincs megadva.|A mobileszköz-kezelő szolgáltató nincs megadva az Intune-ban. További információ [a mobileszköz-felügyeleti szolgáltató beállításáról](/intune/mdm-authority-set).|


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

   ![A Smart Manager ikon kiválasztása az eszközön](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-icon.png)

2. Válassza a **Battery** (Akkumulátor) csempét.

   ![A Battery (Akkumulátor) csempe kiválasztása](./media/troubleshoot-device-enrollment-in-intune/smart-manager-battery-tile.png)

3. Válassza az **App power saving** (Alkalmazás energiatakarékossága) vagy **App optimization** (Alkalmazás optimalizálása) terület **Detail** (Részletek) elemét.

   ![Az App power saving (Alkalmazás energiatakarékossága) vagy App optimization (Alkalmazás optimalizálása) terület Detail (Részletek) elemének kiválasztása](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-power-saving-detail.png)

4. Koppintson a **Munkahelyi portál** elemre az alkalmazáslistában.

   ![A Munkahelyi portál kiválasztása az alkalmazáslistából](./media/troubleshoot-device-enrollment-in-intune/smart-manager-company-portal.png)

5. Válassza a **Turned off** (Kikapcsolva) beállítást.

   ![A Turned off (Kikapcsolva) beállítás kiválasztása az App optimization (Alkalmazás optimalizálása) párbeszédpanelen](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-optimization-turned-off.png)

6. Győződjön meg róla az **App power saving** (Alkalmazás energiatakarékossága) vagy az **App optimization** (Alkalmazás optimalizálása) területen, hogy a Munkahelyi portál ki van kapcsolva.

   ![Annak ellenőrzése, hogy a Munkahelyi portál ki van-e kapcsolva](./media/troubleshoot-device-enrollment-in-intune/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Profiltelepítési hiba
**Hiba:** **Profiltelepítési hiba** üzenet jelenik meg egy Android-eszközön.

**Megoldás:**

1.  Ellenőrizze, hogy az Ön által használt Intune szolgáltatás verziójának megfelelő licenc van-e hozzárendelve a felhasználóhoz.

2.  Győződjön meg arról, hogy az eszköz még nincs egy másik MDM szolgáltatóhoz regisztrálva, vagy még nincs hozzá felügyeleti profil telepítve.

3.  Ellenőrizze, hogy az Androidhoz készült Chrome az alapértelmezett böngésző-e, és a cookie-k engedélyezettek-e.

### <a name="android-certificate-issues"></a>Android-tanúsítványokkal kapcsolatos problémák

**Probléma:** A felhasználó eszköze a következő üzenetet mutatja: *Nem tud bejelentkezni, mert az eszközön hiányzik egy szükséges tanúsítvány.*

**1. megoldás**:

Előfordulhat, hogy a felhasználó [Az eszközhöz hiányzik egy szükséges tanúsítvány](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) című témakörben leírt útmutatás alapján be tudja szerezni a hiányzó tanúsítványt. Ha a hiba továbbra is fennáll, próbálkozzon a 2. megoldással.

**2. megoldás**:

Ha a felhasználók a vállalati hitelesítő adatok megadását, illetve az összevont bejelentkezési oldalra való átirányítást követően is a hiányzó tanúsítványra utaló hibát látják, elképzelhető, hogy az Active Directory összevonási szolgáltatások (AD FS) kiszolgálójáról hiányzik egy közbenső tanúsítvány.

A tanúsítványhiba azért fordul elő, mert az androidos eszközöknek közbenső tanúsítványokra van szükségük ahhoz, hogy szerepelhessenek az [SSL-kiszolgáló hello üzeneteiben](https://technet.microsoft.com/library/cc783349.aspx). Jelenleg az AD FS-kiszolgáló vagy a WAP és az AD FS közötti proxykiszolgáló alapértelmezett példányai csak az AD FS szolgáltatás SSL-tanúsítványát küldik el az SSL-kiszolgáló SSL-ügyfelek hello kérelmére adott hello válaszában.

A probléma megoldásához importálja a tanúsítványt az AD FS-kiszolgálón vagy a proxykon található személyes számítógép-tanúsítványok tárába a következő módon:

1.  Az ADFS és proxykiszolgálók szakaszban kattintson a jobb gombbal a **Start** > **Futtatás** > **certlm.msc** elemre a Helyi gép tanúsítványkezelő konzoljának indításához.
2.  Bontsa ki a **Személyes** elemet, majd válassza a **Tanúsítványok** lehetőséget.
3.  Keresse meg az AD FS szolgáltatással való kommunikációhoz szükséges tanúsítványt (ez egy nyilvános aláírású tanúsítvány), és kattintson rá duplán a tulajdonságok megjelenítéséhez.
4.  Válassza a **Tanúsítványlánc** lapot a tanúsítvány szülőtanúsítványának vagy -tanúsítványainak megjelenítéséhez.
5.  Az összes szülőtanúsítványnál válassza a **Tanúsítvány megtekintése** lehetőséget.
6.  Válassza a **Részletek** > **Másolás fájlba...**  lehetőséget.
7.  A varázsló utasításait követve exportálja vagy mentse a szülőtanúsítvány nyilvános kulcsát a fájl kívánt helyére.
8.  Kattintson a jobb gombbal a **Tanúsítványok** > **Minden feladat** > **Importálás** lehetőségre.
9.  A varázsló utasításait követve importálja a szülőtanúsítvány(oka)t a **Helyi számítógép\Személyes\Tanúsítványok** helyre.
10. Indítsa újra az AD FS-kiszolgálókat.
11. Ismételje meg a fenti lépéseket az összes AD FS- és proxykiszolgálón.

A [https://www.digicert.com/help/](https://www.digicert.com/help/) címen elérhető diagnosztikai eszközzel ellenőrizheti, hogy a tanúsítvány megfelelően lett-e telepítve. A **Kiszolgáló címe** mezőbe írja be az AD FS-kiszolgáló teljes tartománynevét (példa: sts.contso.com), majd kattintson a **Kiszolgáló vizsgálata** lehetőségre.

**A tanúsítványok megfelelő telepítésének ellenőrzése**:

A következő lépésekben csupán a tanúsítvány megfelelő telepítésének ellenőrzésére rendelkezésre álló számos módszer és eszköz egyikét mutatjuk be.

1. Nyissa meg az [ingyenes Digicert eszközt](ttps://www.digicert.com/help/).
2. Adja meg az AD FS-kiszolgáló teljes tartománynevét (például sts.contoso.com), majd válassza a **CHECK SERVER** (Kiszolgáló ellenőrzése) lehetőséget.

Ha a kiszolgálótanúsítványt megfelelően telepítette, az eredményeknél csak pipák jelennek meg. Ha a fenti probléma továbbra sem szűnt meg, piros X jelenik meg a jelentés „Certificate Name Matches” (Tanúsítványnév-egyezések) és „SSL Certificate is correctly Installed” (Az SSL-tanúsítvány megfelelő telepítése) részében.


## <a name="ios-issues"></a>iOS-problémák

### <a name="ios-enrollment-errors"></a>Az iOS beléptetési hibái
A következő táblázat azon hibákat tartalmazza, melyeket iOS-eszközök az Intune-ban való regisztrálásakor tapasztalhatnak a végfelhasználók.

|Hibaüzenet|Probléma|Megoldás|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Nem található eszközregisztrációs szabályzat|Ellenőrizze, hogy az összes regisztrációs előfeltétel, mint például az Apple Push Notification szolgáltatás (APNs) tanúsítványa konfigurálva van-e, illetve azt, hogy az „iOS mint platform” engedélyezve van-e. Útmutatásért tekintse meg a [Set up iOS and Mac device management](ios-enroll.md) (iOS- és Mac-eszközök kezelésének beállítása) című cikket.|
|DeviceCapReached|A már regisztrált mobileszközök száma túl magas.|A felhasználónak el kell távolítania az aktuálisan regisztrált mobileszközeit a Céges portálról, mielőtt másikat regisztrálhatna. Kövesse a megfelelő eszköz típusára vonatkozó utasításokat: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios), [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Probléma merült fel azzal a tanúsítvánnyal kapcsolatban, amely lehetővé teszi a mobileszköz és a céges hálózat közötti kommunikációt.<br /><br />|Az Apple Push Notification Service (APNs) révén elérhetők a beléptetett iOS-eszközök. Ha nem lettek végrehajtva az APN-tanúsítvány beszerzésének lépései, vagy ha az APN-tanúsítvány lejárt, a beléptetési kísérletek ezzel az üzenettel hiúsulnak meg.<br /><br />A felhasználók konfigurálásához olvassa el [Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz](users-add.md) című szakaszt, valamint a [felhasználók és eszközök rendszerezésével](groups-add.md) kapcsolatos tudnivalókat.|
|AccountNotOnboarded|Probléma merült fel azzal a tanúsítvánnyal kapcsolatban, amely lehetővé teszi a mobileszköz és a céges hálózat közötti kommunikációt.<br /><br />|Az Apple Push Notification Service (APNs) révén elérhetők a beléptetett iOS-eszközök. Ha nem lettek végrehajtva az APN-tanúsítvány beszerzésének lépései, vagy ha az APN-tanúsítvány lejárt, a beléptetési kísérletek ezzel az üzenettel hiúsulnak meg.<br /><br />További információ: [Az iOS kezelésének beállítása a Microsoft Intune-nal](ios-enroll.md).|
|DeviceTypeNotSupported|Lehet, hogy a felhasználó nem iOS-eszközzel próbált meg regisztrálni. A regisztrálni próbált mobileszköz nem támogatott.<br /><br />Győződjön meg róla, hogy az eszközön az iOS 8.0-ás vagy újabb verziója fut.<br /><br />|Győződjön meg róla, hogy a felhasználó eszközén 8.0-ás vagy újabb iOS-verziót fut.|
|UserLicenseTypeInvalid|A mobileszköz nem regisztrálható, mert a felhasználói fiók még nem tagja egy szükséges felhasználói csoportnak.<br /><br />|Ahhoz, hogy a felhasználók regisztrálhassák eszközeiket, a megfelelő felhasználói csoport tagjának kell lenniük. Ez az üzenet azt jelenti, hogy nem rendelkeznek a megfelelő licenctípussal a meghatározott mobileszköz-kezelő szolgáltatóhoz. Ha például az Intune lett mobileszköz-kezelő szolgáltatóként meghatározva, és System Center 2012 R2 Configuration Manager-licencet használnak, ezt a hibaüzenetet látják.<br /><br />További információért tekintse át az alábbi cikkeket:<br /><br />Olvassa el [Az iOS és Mac kezelésének beállítása a Microsoft Intune-nal](ios-enroll.md) című szakaszt, illetve a felhasználók konfigurálásával kapcsolatban [Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz](users-add.md) című szakaszt, valamint a [felhasználók és eszközök rendszerezésével](groups-add.md) kapcsolatos tudnivalókat.|
|MdmAuthorityNotDefined|A mobileszköz-kezelő szolgáltató még nincs megadva.<br /><br />|A mobileszköz-kezelő szolgáltató nincs megadva az Intune-ban.<br /><br />Tekintse meg az 1. elemet [Az első lépések a Microsoft Intune 30 napos próbaverziójában](free-trial-sign-up.md) „6. lépés: Mobileszközök regisztrálása és alkalmazások telepítése” szakaszában.|

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük
**Probléma:** Az iOS-eszközök nem jelentkeznek be az Intune szolgáltatásba. Az eszközök csak a szolgáltatásba való rendszeres bejelentkezéssel őrizhetik meg a vállalati erőforrásokhoz való hozzáférési jogosultságukat. Ha az eszközök rendszeres bejelentkezése nem történik meg:

- Nem kaphatják meg a szabályzatot, az alkalmazásokat és a távoli parancsokat az Intune szolgáltatástól.
- A felügyeleti konzolon **Nem megfelelő** felügyeleti állapotúnak látszanak.
- A feltételes hozzáférési szabályzattal védett felhasználók elveszíthetik a vállalati erőforrásokhoz való hozzáférésüket.

**Megoldás:** Az alábbi megoldások megosztásával segíthet a végfelhasználóknak visszaszerezni a vállalati erőforrásokhoz való hozzáférési jogosultságukat.

Amikor a felhasználók elindítják a Vállalati portál iOS-alkalmazást, megállapítható, hogy az eszköz kapcsolata megszakadt-e az Intune-nal. Ha az alkalmazás azt észleli, hogy nincs kapcsolat, automatikusan megpróbál szinkronizálni az Intune-nal az újrakapcsolódáshoz, és a felhasználók a következő értesítést fogják látni: **A szinkronizálási kísérlet folyamatban van...** beágyazott értesítés.

  ![A szinkronizálási kísérlet folyamatban van – értesítés](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_trying_to_sync_notification.png)

Ha a szinkronizálás sikeres, a **Sikeres szinkronizálás** beágyazott értesítés jelenik meg a Vállalati portál iOS-alkalmazásban, amely azt jelzi, hogy az eszköz kifogástalan állapotban van.

  ![Sikeres szinkronizálás – értesítés](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_sync_successful_notification.png)

Ha a szinkronizálás sikertelen, a felhasználók a **Nem lehet szinkronizálni** beágyazott értesítést fogják látni a Vállalati portál iOS-alkalmazásban.

  ![Nem lehet szinkronizálni – értesítés](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_unable_to_sync_notification.png)

A probléma elhárításához a felhasználóknak a **Nem lehet szinkronizálni** értesítés jobb oldalán lévő **Beállítás** gombot kell használniuk. A Beállítás gomb használatával a felhasználók a Vállalati hozzáférés beállítása folyamatképernyőre kerülnek, ahol a képernyőn megjelenő utasítások követésével regisztrálhatják az eszközüket.

  ![A Vállalati hozzáférés beállítása képernyő](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_company_access_setup.png)

Regisztráció után az eszközök ismét kifogástalan állapotba kerülnek, és visszakapják a vállalati erőforrásokhoz való hozzáférési jogosultságukat.

### <a name="verify-ws-trust-13-is-enabled"></a>Ellenőrizze, hogy a WS-Trust 1.3 engedélyezve van-e
**Probléma:** Az eszközregisztrációs programhoz (DEP) tartozó iOS-eszközöket nem lehet regisztrálni

A felhasználói affinitással rendelkező DEP-eszközök regisztrációjához engedélyezni kell a WS-Trust 1.3 Username/Mixed végpontot a felhasználói jogkivonat kérelmezése céljából. Az Active Directory alapértelmezés szerint engedélyezi ezt a végpontot. A Get-AdfsEndpoint PowerShell-parancsmagot futtatva, majd a trust/13/UsernameMixed végpontot megkeresve láthatja az engedélyezett végpontok listáját. Példa:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

További információt a [Get-AdfsEndpoint dokumentációjában](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) talál.

További információt az [Ajánlott eljárások az Active Directory összevonási szolgáltatások biztonságossá tételéhez](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs) című cikkben talál. Ha további segítségre van szüksége annak megállapításához, hogy a WS-Trust 1.3 Username/Mixed végpont engedélyezve van-e az ön identitás-összevonási szolgáltatójában, akkor az ADFS használata esetén forduljon a Microsoft ügyfélszolgálatához, külső identitásszolgáltató esetében pedig a szolgáltatóhoz.


### <a name="profile-installation-failed"></a>Profiltelepítési hiba
**Hiba:** **Profiltelepítési hiba** üzenet jelenik meg egy iOS-eszközön.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Sikertelen profiltelepítés hibaelhárításának lépései

1.  Ellenőrizze, hogy az Ön által használt Intune szolgáltatás verziójának megfelelő licenc van-e hozzárendelve a felhasználóhoz.

2.  Győződjön meg arról, hogy az eszköz még nincs egy másik MDM szolgáltatóhoz regisztrálva, vagy még nincs hozzá felügyeleti profil telepítve.

3.  Navigáljon a [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) oldalra, és telepítse a profilt a rendszer kérésekor.

4.  Ellenőrizze, hogy az iOS-hez készült Safari az alapértelmezett böngésző-e, és a cookie-k engedélyezettek-e.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>A regisztrált iOS-eszköz nem jelenik meg a konzolon a System Center Configuration Managerbe integrált Intune használata esetén
**Hiba:** A felhasználó regisztrálja az iOS-eszközt, de az nem jelenik meg a Configuration Manager felügyeleti konzolon. Az eszköz nem jelzi, hogy már regisztrálva van. Lehetséges okok:

- Az Ön Configuration Manager-helyén található Microsoft Intune-összekötő nem kommunikál az Intune szolgáltatással.
- Az állapotkezelő (statmgr) vagy az adatfelderítés-kezelő (ddm) összetevő nem dolgozza fel az Intune szolgáltatás üzeneteit.
- Előfordulhat, hogy az MDM-tanúsítványt az egyik fiókból töltötte le, és egy másik fiókban használta.


**Megoldás:** tekintse át a következő naplófájlokat a lehetséges hibák azonosítása érdekében:

- dmpdownloader.log
- ddm.log
- statmgr.log

Hamarosan közzétesszük az arra vonatkozó példákat, hogy mit kell keresni ezekben a naplófájlokban.


## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problémák a System Center Configuration Managerbe integrált Intune használatakor
### <a name="mobile-devices-disappear"></a>Mobileszközök tűnnek el
**Hiba:** Miután sikeresen regisztrált egy mobileszközt a Configuration Managerbe, eltűnik a mobileszköz-gyűjteményből, de továbbra is rendelkezik felügyeleti profillal, és szerepel a CSS-átjáróban.

**Megoldás:** Ez azért fordulhat elő, mert egyedi eljárással rendelkezik a tartományhoz nem csatlakozó eszközök eltávolításához, vagy a felhasználó kivonta az eszközt az előfizetésből. Ha meg szeretné állapítani, hogy melyik eljárás vagy felhasználói fiók távolította el az eszközt a Configuration Manager konzolból, hajtsa végre az alábbi lépéseket.

#### <a name="check-how-device-was-removed"></a>Az eszköz eltávolításának ellenőrzése

1.  A Configuration Manager felügyeleti konzolban válassza a **Figyelés** &gt; **Rendszer állapota** &gt; **Állapotüzenet-lekérdezések** elemet.

2.  Kattintson a jobb gombbal a **Manuálisan törölt gyűjtemény tagerőforrások** elemre, és válassza az **Üzenetek megjelenítése** parancsot.

3.  Válasszon ki egy megfelelő időpontot vagy dátumot, illetve az elmúlt 12 órát.

4.  Keresse meg a kérdéses eszközt, és ellenőrizze, hogy miként történt az eltávolítása. Az alábbi példában látható, hogy az SCCMInstall fiók törölte az eszközt egy ismeretlen alkalmazáson keresztül.

    ![Képernyőfelvétel az eszköztörlési diagnózisról](./media/troubleshoot-device-enrollment-in-intune/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Ellenőrizze, hogy a Configuration Manager nem rendelkezik-e ütemezett feladattal, parancsfájllal vagy egyéb folyamattal, amely automatikusan kiürítheti a tartományhoz nem csatlakozó, a mobil- vagy a kapcsolódó eszközöket.




### <a name="other-ios-enrollment-errors"></a>Egyéb iOS-beléptetési hibák
Az iOS-regisztrálási hibák listáját a dokumentációban, az [iOS-eszközregisztrációs problémák hibaelhárítása a Microsoft Intune-ban](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune) című cikkben találhatja.

## <a name="pc-issues"></a>PC-kkel kapcsolatos problémák


|Hibaüzenet|Probléma|Megoldás|
|---|---|---|
|**A rendszergazdának hozzáférési licencet kell hozzárendelnie**<br>A rendszergazda nem adott hozzáférést az alkalmazás használatához. Kérjen segítséget a rendszergazdától, vagy próbálkozzon újra később.|Az eszközt nem lehet regisztrálni, mert a felhasználó fiókja nem rendelkezik a szükséges licenccel.|Ahhoz, hogy a felhasználók regisztrálhassák az eszközeiket, hozzájuk kell rendelni a szükséges licencet. Ez az üzenet azt jelenti, hogy nem rendelkeznek a megfelelő licenctípussal a meghatározott mobileszköz-kezelő szolgáltatóhoz. Ha például az Intune lett mobileszköz-kezelő szolgáltatóként meghatározva, és System Center 2012 R2 Configuration Manager-licencet használnak, ezt a hibaüzenetet látják.<br>További információ [az Intune-licencek felhasználói fiókokhoz való hozzárendelésével](https://docs.microsoft.com/intune/licenses-assign) kapcsolatban.|



### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>A gép már regisztrálva van – hibakód: hr 0x8007064c
**Hiba:** A regisztrálás sikertelen **A gép már regisztrálva van** hibaüzenettel. A regisztrálási napló a **hr 0x8007064c** hibakódot tartalmazza.

Ennek az lehet az oka, hogy a számítógép korábban regisztrálva volt, vagy olyan számítógép klónozott lemezképét tartalmazza, amely már regisztrálva volt. Az előző fiók fióktanúsítványa továbbra is megtalálható a számítógépen.



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
    > Ha további tájékoztatásra van szüksége a beállításjegyzék biztonsági mentéséről és visszaállításáról, olvassa el a [How to back up and restore the registry in Windows](https://support.microsoft.com/kb/322756) (A beállításjegyzék biztonsági mentése és visszaállítása a Windows rendszerben) című témakört.

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
|0x80043008, 0x80CF3008|Nem sikerült elindítani a Microsoft Online Management Updates szolgáltatást.|Lépjen kapcsolatba a Microsoft ügyfélszolgálatával a [Hogyan kérhet támogatást az Intune-hoz](get-support.md) című szakaszban leírtak szerint.|
|0x80043009, 0x80CF3009|Az ügyfélszámítógép már be van léptetve a szolgáltatásba.|Az ügyfélszámítógépet el kell távolítania, mielőtt újból beléptetheti a szolgáltatásba.|
|0x8004300B, 0x80CF300B|Az ügyfélszoftver telepítési csomagja nem futtatható, mert az ügyfélen futó Windows-verzió nem támogatott.|Az Intune nem támogatja az ügyfélszámítógépen futó Windows-verziót.|
|0xAB2|A Windows Installer nem tud hozzáférni a VBScript futtatókörnyezethez egy egyéni művelet végrehajtásához.|A hibát egy egyéni művelet okozza, amely dinamikus kötésű kódtárakon (DLL-eken) alapul. Előfordulhat, hogy a DLL hibáinak elhárításához a következő témakörben ismertetett eszközöket kell használnia: [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Hasznos eszközök csomag- és telepítési problémák esetére).|
|0x80cf0440|Megszakadt a kapcsolat a szolgáltatásvégponttal.|A próbafiók vagy a díjköteles fiók fel van függesztve. Hozzon létre egy új próbafiókot vagy díjköteles fiókot, és végezze el újból a regisztrálást.|




### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](get-support.md) című témakörben leírtak szerint.