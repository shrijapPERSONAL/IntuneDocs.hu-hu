---
title: "A feltételes hozzáférés hibaelhárítása|Microsoft Docs"
description: "A teendők abban az esetben, ha a felhasználók nem tudnak hozzáférni az erőforrásokhoz az Intune feltételes hozzáférésével."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19635b4dda7f4f04690ad165bad6608cad7ac84f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-conditional-access"></a>A feltételes hozzáférés hibaelhárítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az e-mailek vagy a SharePoint megnyitásakor a felhasználóknak a rendszer általában egy regisztrálási kérelmet jelenít meg. A kérés a vállalati portálra irányítja a felhasználót.

Ez a témakör ismerteti a teendőket abban az esetben, ha a felhasználók nem tudnak hozzáférni az erőforrásokhoz az Intune feltételes hozzáférésével.


## <a name="the-basics-for-success-in-conditional-access"></a>A sikeres feltételes hozzáférés alapjai

A feltételes hozzáférés megfelelő működéséhez az alábbi feltételeknek kell teljesülnie:

-    Az eszközt az Intune-nak kell felügyelnie
-    Az eszköznek regisztrálva kell lennie az Azure Active Directoryban (AAD). A regisztrációra általában automatikusan kerül sor az Intune-ban történő regisztrálás során
-    Az eszköznek meg kell felelnie az Intune megfelelőségi szabályzatának mind az eszköz, mind a felhasználó tekintetében.  Ha nincsenek megfelelőségi szabályzatok, az Intune-regisztráció is elegendő.
-    Az eszközön aktiválni kell az Exchange ActiveSync protokollt, ha a felhasználó nem az Outlookon, hanem az eszköz natív levelezőprogramján keresztül fér hozzá e-mailjeihez.     iOS-, Windows Phone- és Android/KNOX Standard-eszközök esetében ez automatikusan történik.
-    Az Intune Exchange Connectort megfelelően konfigurálni kell. További információkért lásd az [Az Exchange Connector hibaelhárítása a Microsoft Intune-ban](troubleshoot-exchange-connector.md) című ismertetőt.

Az egyes eszközökre vonatkozó feltételek megtekinthetők az Azure felügyeleti portálon, valamint az eszköz könyvtárjelentésében.

## <a name="enrollment-issues"></a>Regisztrációs problémák

 -  Az eszköz nincs regisztrálva, így a regisztrálás megoldja a problémát.
 -  A felhasználó regisztrálta az eszközt, de a munkahelyi csatlakoztatás sikertelen volt. A felhasználónak frissítenie kell a regisztrációt a vállalati portálról.

## <a name="compliance-issues"></a>Megfelelőségi problémák

 -  Az eszköz nem felel meg az Intune házirendjeinek. A leggyakoribb probléma ebben az esetben a titkosítás és a jelszókövetelmények. A rendszer átirányítja a felhasználót a vállalati portálra, ahol konfigurálhatja az eszköz megfelelőségét.
 -  A megfelelőségi adatok regisztrálása az eszközön időbe telhet. Várjon néhány percet, és próbálkozzon újra.
 -  iOS eszközök esetén:
     -   Ha már van a felhasználó által létrehozott e-mail-profil, ez meggátolja az Intune-rendszergazda által létrehozott profil telepítését. Ez gyakori probléma, mivel az iOS-felhasználók gyakran hoznak létre egy e-mail-profilt a regisztráció előtt. A vállalati portál tájékoztatja a felhasználót, hogy a manuálisan beállított e-mail-profil sérti a megfelelőségi házirendet, és megkéri, hogy távolítsa el a profilt. A felhasználónak ekkor törölnie kell az e-mail-profilt, hogy az Intune-profilt telepíthesse. A probléma elkerülése érdekében kérje meg a felhasználókat, hogy e-mail-profil telepítése nélkül regisztráljanak, és engedélyezzék az Intune-nak, hogy telepítse a profilt.
     -     Az iOS-eszközök esetében előfordulhat, hogy elakadnak a megfelelőség-ellenőrzési állapotban, és megakadályozzák, hogy a felhasználó újabb bejelentkezést kezdeményezzen. A vállalati portál újraindítása megoldhatja ezt a problémát; ilyenkor a megfelelőségi állapot az eszköz állapotát tükrözi az Intune-ban. Miután az összes információt összegyűjtötték az eszközről, a megfelelőségi ellenőrzés gyorsan történik; átlagosan kevesebb mint fél másodpercet vesz igénybe.

        Az eszközök jellemzően azért akadnak el ebben az állapotban, mert nem sikerül csatlakozniuk a szolgáltatáshoz, vagy mert a szinkronizálás túlságosan hosszú ideig tart.  Ha a probléma különböző hálózati konfigurációkban (mobil, Wi-Fi, VPN) az eszköz többszöri újraindítása ellenére is tartósan fennáll, és ellenőrizte, hogy az SSP naprakész állapotban van az eszközön, a [Hogyan kérhet támogatást az Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírt módon vegye fel a kapcsolatot a Microsoft ügyfélszolgálatával.

 - Androidos eszközök esetén:
     - Előfordulhat, hogy bizonyos androidos eszközök titkosítottnak tűnnek, de a Céges portál alkalmazás nem titkosítottként ismeri fel azokat. 
    
        -    Az ebben az állapotban lévő eszközökhöz a felhasználónak egy biztonságos indítási PIN-kódot kell megadnia. A felhasználó számára a Céges portál alkalmazás értesítést jelenít meg, kérve egy indítási PIN-kód beállítását az eszközhöz. Koppintson az eszközértesítésre, és a meglévő PIN-kód vagy a jelszó ellenőrzése után válassza a **Require PIN to start device** (PIN-kód kérése az eszköz indításához) beállítást a **Secure start-up** (Biztonságos indítás) képernyőn. Ezután koppintson az eszközhöz tartozó **Megfelelőség ellenőrzése** gombra a Céges portál alkalmazásban. Az eszközt ettől kezdve titkosítottként kell, hogy észlelje a program.
    
        -     Egyes eszközgyártók alapértelmezett PIN-kód használatával titkosítják eszközeiket a felhasználó által megadott PIN-kód helyett. Az Intune az alapértelmezett PIN-kódot használó titkosítást nem biztonságosnak ismeri fel, mert ez a titkosítási módszer az eszközön lévő adatokat az eszközhöz fizikai hozzáféréssel rendelkező rosszindulatú felhasználók általi kockázatnak teszi ki. Ha ez a probléma, vegye fontolóra az [alkalmazásvédelmi szabályzatok](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) használatát.

## <a name="policy-issues"></a>Szabályzattal kapcsolatos problémák

Ha a megfelelőségi házirend létrehozásakor hozzákapcsolja azt egy e-mail-házirendhez, mindkét házirendet ugyanannál a felhasználónál kell üzembe helyezni, így érdemes jól megfontolni, hogy melyik házirendet melyik csoport számára helyezi üzembe. A csak az egyik házirenddel rendelkező felhasználók eszközei valószínűleg nem fognak megfelelni.


## <a name="exchange-activesync-issues"></a>Exchange ActiveSync-problémák

### <a name="compliant-android-device-gets-quarantine-notice"></a>Egy megfelelő Android-eszköz karanténba helyezésről szóló értesítést kap
- A regisztrált és megfelelő Android-eszközök is kaphatnak karanténba helyezésről szóló értesítést a vállalati erőforrásokhoz való hozzáféréskor. A **Kezdés** nevű hivatkozásra kattintás előtt a felhasználónak meg kell győződnie arról, hogy a vállalati portál nem volt megnyitva az erőforrásokhoz való hozzáféréskor. A felhasználónak be kell zárnia a vállalati portált, újra meg kell próbálnia hozzáférni a vállalati erőforrásokhoz, majd ez után kell a **Kezdés** nevű hivatkozásra kattintania.

### <a name="retired-device-continues-to-have-access"></a>Egy kivont eszköz továbbra is rendelkezik hozzáféréssel.
- Az Exchange Online használata esetén a kivont eszközök a kivonást követően még több órán át rendelkezhetnek hozzáféréssel. Ennek az az oka, hogy az Exchange hat órán át gyorsítótárazza a hozzáférési jogosultságokat. Ebben az esetben érdemes más adatvédelmi megoldást keresnie a kivont eszközökre.

### <a name="device-is-compliant-and-registered-with-aad-but-still-blocked"></a>Az eszköz megfelelő és regisztrálva van az AAD-ben, de továbbra is letiltott
- Előfordul, hogy késik az Exchange ActiveSync-azonosító (EASID) átadása az AAD felé. Ennek a problémának az oka leggyakrabban a szabályozás. Várjon néhány percet, és próbálkozzon újra.

### <a name="device-blocked"></a>Eszköz zárolva

Előfordulhat, hogy egy eszköz feltételes hozzáférését a rendszer anélkül zárolja, hogy az eszköz aktiválási e-mailt kapna.

- Van olyan alapértelmezett Exchange-szabály, amely karanténba zár vagy blokkol eszközöket? Ha egy alapértelmezett szabály blokkolja vagy karanténba zárja az eszközt, az eszköz nem tudja fogadni az aktiválási e-mailt az Exchange Connectortól. Ez a rendszer kialakításából fakad.
- Az értesítési fiók konfigurációja megfelel az Alapkonfiguráció című részben leírtaknak?
- Az eszköz az Intune felügyeleti konzoljában Exchange ActiveSync-eszközként jelenik meg? Ha nem, akkor valószínű, hogy az eszköz felderítése sikertelen, feltehetően az Exchange Connector szinkronizálási problémája miatt. Lásd: Az Exchange ActiveSync-eszköz nem deríthető fel az Exchange-ből.
- Ellenőrizze az Exchange Connector naplófájljaiban a SendEmail műveletekkel kapcsolatos hibákat. A keresendő parancs lehet például egy SendEmail művelet az értesítési fiókból a felhasználói fiók felé.
- Mielőtt az Exchange Connector zárolná az eszközt, aktiválási e-mailt küld. Ha az eszköz offline állapotban van, előfordulhat, hogy nem kapja meg az aktiválási e-mailt. Ellenőrizze, hogy az eszköz e-mail-ügyfele ügyfélleküldéses módszerrel és nem lekérdezéssel fér hozzá az e-mailekhez, mert ez is okozhatja azt, hogy nem érkeznek meg. Váltson lekérdezési módra, és ellenőrizze, hogy az eszköz megkapja-e az e-mailt.

## <a name="non-compliant-device-not-blocked"></a>Nem megfelelő eszköz nincs letiltva

Ha olyan eszközzel találkozik, amely nem megfelelő, mégis rendelkezik hozzáféréssel, hajtsa végre a következőket.

- Tekintse át a cél- és kizárási csoportokat. Ha a felhasználó nem szerepel a megfelelő cél- vagy kizárási csoportban, akkor nem tiltható le. A rendszer csak a célcsoportban lévő felhasználók eszközeinek megfelelőségét ellenőrzi.
- Gondoskodjon az eszköz felderítéséről. Az Exchange Connector egy Exchange 2010-es CAS-kiszolgálóra mutat, a felhasználó pedig egy Exchange 2013-kiszolgálón van? Ebben az esetben, ha az alapértelmezett Exchange-szabály az Engedélyezés, az Intune nem észleli az eszköz kapcsolatát az Exchange szolgáltatással, még akkor sem, ha a felhasználó a célcsoportban van.
- Ellenőrizze az eszköz meglétét/hozzáférési állapotát az Exchange-ben:
    - A következő PowerShell-parancsmag segítségével kérheti le az adott postaládához tartozó valamennyi mobileszköz listáját: „Get-ActiveSyncDeviceStatistics -mailbox mbx”. Ha az eszköz nem szerepel a listán, akkor nem fér hozzá az Exchange-hez.
    - Ha az eszköz szerepel a listán, használja a Get-CASmailbox-identity:’upn’ | fl parancsmagot az eszköz hozzáférési állapota részletes információinak lekérdezéséhez, majd az információkat adja meg a Microsoft támogatási szolgálatának.

## <a name="before-you-open-a-support-ticket"></a>Támogatási jegy megnyitása előtt
Ha ezekkel a hibaelhárítási eljárásokkal nem sikerül megoldani a problémát, előfordulhat, hogy további információt kell megadnia a Microsoft támogatási szolgálata számára, például az OWA-postaláda vagy az Exchange Connector naplófájljait.

### <a name="collecting-owa-mailbox-logs"></a>Az OWA-postaláda naplófájljainak gyűjtése

1. Jelentkezzen be az OWA-n keresztül, és kattintson a jobb felső sarokban, a neve mellett található beállítások (fogaskerék) ikonra.
2. Kattintson a **Beállítások** lehetőségre
3. Válassza a **Telefon** (vagy **Mobileszközök**) lehetőséget a bal oldali oszlopban.
4. A felső menüben kattintson a **Mobileszközök** elemre.
5. Válassza ki az eszközét a listából, majd válassza a **Naplózás megkezdése** lehetőséget.
6. Ha a rendszer kéri, kattintson az **Igen** lehetőségre az előugró párbeszédpanelen.
7. Hajtsa végre újra a hibát okozó műveletet, hogy reprodukálja azt.
8. Várjon 1-2 percet, majd lépjen vissza a telefonlistához az OWA-ban. Győződjön meg arról, hogy a listában a telefonja ki van jelölve, majd a felső menüben válassza a **Napló beolvasása** lehetőséget.
9. Ekkor egy mellékletet tartalmazó e-mailt kell kapnia a saját címéről. A támogatási jegy megnyitásakor küldje el az e-mail tartalmát a Microsoft támogatásnak.

### <a name="exchange-connector-logs"></a>Az Exchange Connector naplófájljai

#### <a name="general-log-information"></a>Általános naplófájl-információk
Az Exchange Connector naplófájljainak megtekintéséhez használja a Server Trace Viewer eszközt (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx). Ennek az eszköznek a használatához le kell töltenie a Windows Server SDK-t.

>[!NOTE]
>A naplófájlok a C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs mappában találhatók. A naplók a *Connector0.log* fájltól a *Connector29.log* fájlig tartó 30 naplófájlban találhatók. Miután egy naplófájlban összegyűlt 10 MB adat, a rendszer megnyitja a következőt. Amikor betelik a Connector29 naplófájl, a folyamat a Connector0 naplófájllal újraindul, felülírva a korábbi naplófájlokat.

#### <a name="locating-sync-logs"></a>A szinkronizálási naplók keresése

-    A naplófájlokban a **full sync** keresőkifejezéssel kereshet teljes szinkronizálásra. A teljes szinkronizálás kezdetét a következő szöveg jelzi:

    „Handling command: Getting the mobile device list without a time filter (full sync) for <number> users”

    A teljes szinkronizálás naplófájljának a vége így néz ki:

    „Getting the mobile device list without a time filter (full sync) for 4 users completed successfully. Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','”

-    A naplófájlokban a **quick sync** keresőkifejezéssel kereshet gyors (különbözeti) szinkronizálásra.

##### <a name="exceptions-in-get-next-command"></a>A Get next parancs kivételei
Az Exchange Connector naplófájljaiban keresse meg a **Get next paranccsal** kapcsolatos kivételeket, és adja meg azokat a Microsoft támogatási szolgálata számára.

#### <a name="verbose-logging"></a>Részletes naplózás

Részletes naplózás engedélyezése:

1.    Nyissa meg az Exchange Connector nyomkövetés-konfigurációs fájlját. A fájl helye: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.    Keresse meg a TraceSourceLine-t a következő kulccsal: OnPremisesExchangeConnectorService
3.    Az alábbiak szerint módosítsa a **SourceLevel** csomópont értékét az alapértelmezett **Warning ActivityTracing**-ről **Verbose ActivityTracing**-re.

    <TraceSourceLine>
          <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
          <Value xsi:type="TraceSource">
            <SourceLevel>All</SourceLevel>
            <Listeners>
              <Listener>
                <ListenerType>CircularTraceListener</ListenerType>
                <SourceLevel>Verbose ActivityTracing</SourceLevel>
                <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
                <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
                <FileQuota>30</FileQuota>
              </Listener>
            </Listeners>
          </Value>
    </TraceSourceLine>



### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.

