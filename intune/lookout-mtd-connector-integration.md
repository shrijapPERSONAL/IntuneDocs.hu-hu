---
title: "A Lookout-integráció beállítása az Intune-ban"
titlesuffix: Azure portal
description: "Lookout-előfizetés beállítása az Intune-ban"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a9925b91b009f43c08533222a5fdfc765ea51c2
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/19/2017
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a>A Lookout Mobile Threat Defense integrációjának beállítása az Intune-ban

A Lookout Mobile Threat Defense-előfizetés beállításához a következő lépések szükségesek:

| #        |Lépés  |
| ------------- |:-------------|
| 1 | [Azure AD-információk gyűjtése](#collect-azure-ad-information) |
| 2 | [Az előfizetés konfigurálása](#configure-your-subscription) |
| 3 | [Regisztrációs csoportok konfigurálása](#configure-enrollment-groups) |
| 4 | [Az állapotszinkronizálás konfigurálása](#configure-state-sync) |
| 5 | [E-mail-címzettek adatainak konfigurálása hibajelentésekhez](#configure-error-report-email-recipient-information) |
| 6 | [Regisztrációs beállítások konfigurálása](#configure-enrollment-settings) |
| 7 | [E-mailben történő értesítések konfigurálása](#configure-email-notifications) |
| 8 | [A veszélyforrások besorolásának konfigurálása](#configure-threat-classification) |
| 9 | [A regisztráció figyelése](#watching-enrollment) |

> [!IMPORTANT]
> Egy olyan létező Lookout Mobility Endpoint Security-bérlő, amely még nincs társítva az Azure AD-bérlőjéhez, nem használható fel az Azure AD-val és az Intune-nal való integrációhoz. Új Lookout Mobility Endpoint Security-bérlő létrehozásához lépjen kapcsolatba a Lookout támogatási csapatával. Azure AD-felhasználói számára használja az új bérlőt.

## <a name="collect-azure-ad-information"></a>Azure AD-információk gyűjtése
A Lookout Intune-nal való integrálásához a Lookout Mobility Endpoint Security-bérlő társítva lesz az Azure AD-előfizetéshez. A Lookout ügyfélszolgálatának (enterprisesupport@lookout.com) a következő információkra lesz szüksége ahhoz, hogy aktiválja a Lookout Mobile Threat Defense-előfizetést:

* **Az Azure AD-bérlő azonosítója**
* **Az Azure AD-csoportobjektum azonosítója** a Lookout konzol **teljes körű** hozzáféréséhez
* Az **Azure AD-csoportobjektum azonosítója** a Lookout konzol **korlátozott** hozzáféréséhez (nem kötelező)

A következő lépések segítségével gyűjtse össze a Lookout-támogatás számára szükséges információkat.

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com), és jelölje ki az előfizetését. 

2. Az előfizetés nevének kiválasztása után megjelenő URL-cím tartalmazza az előfizetés azonosítóját.  Ha probléma merül fel az előfizetési azonosító lékérdezésekor, további információt talál ebben a [Microsoft-támogatási cikkben](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b).

3. Kérdezze le az Azure AD-csoportazonosítót. A Lookout konzol két hozzáférési szintet támogat:  
  * **Teljes hozzáférés:** Az Azure AD-rendszergazda létrehozhat egy csoportot teljes hozzáférésű felhasználók számára, és választhatóan egy korlátozott hozzáférésű felhasználókból álló csoportot is.  Csak ennek a két csoportnak a tagjai jelentkezhetnek be a **Lookout konzolra**.
  * **Korlátozott hozzáférés:** a csoport felhasználóinak a Lookout konzol több konfigurációs és regisztrációval kapcsolatos moduljához nincs hozzáférésük, illetve csak olvasási hozzáférésük van a Lookout konzol **Security Policy** moduljához.  

    > [!TIP] 
    > Az engedélyekről további információt talál a Lookout-webhelyen, [ebben a cikkben](https://personal.support.lookout.com/hc/articles/114094105653).

    > [!NOTE] 
    > A **Csoportobjektum azonosítója** a **Tulajdonságok** lapon található az **Azure AD felügyeleti portálján**.

4. Miután kigyűjtötte ezeket az információkat, lépjen kapcsolatba a Lookout támogatási szolgálatával (e-mail: enterprisesupport@lookout.com). A Lookout ügyfélszolgálat a megadott információkat felhasználva, az elsődleges kapcsolattartóval együttműködve előkészíti az előfizetést, és elkészíti a vállalati Lookout-fiókot.

## <a name="configure-your-subscription"></a>Az előfizetés konfigurálása

1. Miután a Lookout ügyfélszolgálata elkészítette a vállalati Lookout-fiókot, a Lookout e-mailben küldi el a vállalat elsődleges kapcsolattartójának címére a bejelentkezési URL-címet: https://aad.lookout.com/les?action=consent.

2.  Az Azure AD-bérlő regisztrálásához a Lookout-konzolra való első bejelentkezésnél egy Azure AD-szerepkörű globális rendszergazdai felhasználói fiókkal kell bejelentkezni. A későbbiekben nem szükséges ezt a szintű Azure AD-jogosultságot használni. Egy hozzájárulást kérő lap jelenik meg. A regisztráció befejezéséhez válassza az **elfogad** lehetőséget. Miután elfogadta és hozzájárulását adta, át lesz irányítva a Lookout-konzolra.

    ![A Lookout-konzol első alkalommal megjelenő bejelentkezési lapjának képernyőképe](./media/lookout_mtp_initial_login.png)
    > [MEGJEGYZÉS] A bejelentkezési problémákkal kapcsolatos segítségért tekintse meg a [Lookout-integráció hibaelhárításával](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) foglakozó weblapot.

3.  Nyissa meg a [Lookout konzolon](https://aad.lookout.com) a **System** (Rendszer) modult, válassza a **Connectors** (Összekötők) lapot, majd az **Intune** lehetőséget.

    ![képernyőkép a Lookout konzolról, amelyen az összekötők lap meg van nyitva, az Intune lehetőség pedig ki van emelve](./media/lookout_mtp_setup-intune-connector.png)

4.  A **Connectors (Összekötők)** > **Connection Settings (Kapcsolat beállítása)** lapon adja meg a **Heartbeat Frequency (Szívverés gyakorisága)** értékét.

    ![képernyőkép a kapcsolat beállítása lapról, amin a szívverés gyakorisága már konfigurálva van](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Regisztrációs csoportok konfigurálása
1. Ajánlott eljárásként az [Azure AD felügyeleti portálon](https://manage.windowsazure.com) hozzon létre egy néhány tagból álló Azure AD-alapú biztonsági csoportot a Lookout-integráció teszteléséhez.

    > [MEGJEGYZÉS] Az Azure AD regisztrációs csoportjához tartozó felhasználók minden, a Lookout által támogatott és az Intune-ban regisztrált eszköze, amely támogatott, valamint azonosítva és regisztrálva van, jogosult aktiválásra a Lookout MTD-konzolon.

2. Nyissa meg a [Lookout-konzolon](https://aad.lookout.com) a **System (Rendszer)** modult, válassza a **Connectors (Összekötők)** lapot, majd az **Enrollment Management (Regisztrációkezelés)** lehetőséget választva adja meg azoknak a felhasználóknak a csoportját, akiknek az eszközei regisztrálva lesznek a Lookoutban. A regisztráláshoz adja meg az Azure AD biztonsági csoport **Megjelenített nevét**.

    ![képernyőkép az Intune-összekötő regisztrálási oldaláról](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > A **Megjelenített névben** különbséget kell tenni a kis- és nagybetűk között, ahogyan az az Azure portálon a biztonsági csoport **Tulajdonságok** lapján látható. Amint az alábbi képen látható, a biztonsági csoport **Megjelenített nevében** nagybetűs szavak, míg a címben csak kisbetűk szerepelnek. A Lookout-konzolon a biztonsági csoport **Megjelenített nevénél** használja a megfelelő írásmódot.
    >![képernyőkép az Azure portálról, az Azure Active Directory szolgáltatás tulajdonságok lapjáról](./media/aad-group-display-name.png)

    >[!NOTE] 
    >Az új eszközök keresésének gyakorisága értéknél javasolt megtartani az alapértelmezett (5 perces) beállítást. Jelenlegi korlátok: **A Lookout nem tudja ellenőrizni a csoportok megjelenített neveit:** Ügyeljen rá, hogy az Azure Portal **MEGJELENÍTETT NÉV** mezője pontosan megegyezzen az Azure AD biztonsági csoporttal. **A beágyazott csoportok létrehozása nem támogatott:** A Lookoutban használt Azure AD biztonsági csoportok csak felhasználókat tartalmazhatnak. Más csoportok nem lehetnek tagjai.

3.  Az eszköz akkor aktiválódik a Lookoutban, amikor a csoport hozzáadása után a felhasználó az első alkalommal megnyitja a Lookout for Work alkalmazást a támogatott eszközön.

4.  Ha az eredményekkel elégedett, a regisztrációt további felhasználói csoportokra is kiterjesztheti.

## <a name="configure-state-sync"></a>Az állapotszinkronizálás konfigurálása
Az **Állapotszinkronizálás** lehetőségnél adja meg az Intune-ba küldendő adattípusokat.  A Lookout Intune-integrációjának megfelelő működéséhez mind az eszközállapotra, mind a fenyegetések állapotára szükség van. Ezek a beállítások alapértelmezés szerint engedélyezve vannak.

## <a name="configure-error-report-email-recipient-information"></a>E-mail-címzettek adatainak konfigurálása hibajelentésekhez
A **Hibakezelés** lehetőségnél írja be azt az e-mail címet, amelyre a hibajelentéseket szeretné irányítani.

![képernyőkép az Intune-összekötő hibakezelési oldaláról](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Regisztrációs beállítások konfigurálása
A **System** modul **Connectors** lapján adja meg, hogy hány nap múltán tekintse a program leválasztottnak az adott eszközt.  A leválasztott eszközöket nem megfelelőnek tekinti a program, és az Intune-beli feltételes hozzáférésre vonatkozó szabályzatok alapján törli a munkahelyi alkalmazásokhoz való hozzáférésüket. 1 és 90 nap közötti időtartam adható meg.

![A Lookout regisztrációs beállításai](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>E-mailben történő értesítések konfigurálása
Ha e-mailben szeretne értesítéseket kapni a veszélyforrásokról, jelentkezzen be a [Lookout konzolra](https://aad.lookout.com) azzal a felhasználói fiókkal, amelybe az értesítéseket szeretné kapni. A **Rendszer** modulban, a **Beállítások** lapon válassza ki azt a fenyegetési szintet, amelyhez értesítést kíván beállítani, és a kapcsolójukat állítsa **BE** értékre. Mentse a változtatásokat.

![képernyőkép a beállítások lapról a felhasználói fiókkal](./media/lookout-mtp-email-notifications.png) Ha már nem szeretne email értesítéseket kapni, állítsa az értesítés típusa melletti kapcsolót **KI** értékre.

### <a name="configure-threat-classification"></a>A veszélyforrások besorolásának konfigurálása
A Lookout Mobile Threat Defense osztályokba sorolja a különféle fenyegetési típusokat. A [Lookout veszélyforrás-besorolásaiban](http://personal.support.lookout.com/hc/articles/114094130693) alapértelmezett kockázati szintek tartoznak a fenyegetésekhez. Ezek bármikor módosíthatók a vállalat igényeinek megfelelően.

![képernyőkép a szabályzat oldaláról a fenyegetések besorolásával](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> A kockázati szintek fontos elemét alkotják a Mobile Threat Defense-nek, mert az Intune-integráció az eszköz megfelelőségét a kockázati szintek alapján számítja ki futásidőben. Az Intune-rendszergazda állítja be a szabályzatban, hogy egy eszköz akkor nem megfelelő, ha egy olyan aktív fenyegetés található rajta, amelynek a szintje: **Magas**, **Közepes** vagy **Alacsony**. A Lookout Mobile Threat Defense veszélyforrás-besorolási szabályzata közvetlen alapja az Intune-ban lezajló eszközmegfelelőségi számításnak.

## <a name="watching-enrollment"></a>A regisztráció figyelése
A telepítés befejezése után a Lookout Mobile Threat Defense elkezdi lekérdezni az Azure AD-ből azokat az eszközöket, amelyek megfelelnek a megadott regisztrációs csoportoknak.  A regisztrált eszközök adatai az Eszközök modulban találhatók.  Az eszközök kezdeti állapota mindig „folyamatban” lesz.  Az eszközállapot akkor frissül, ha a Lookout for Work alkalmazás az illető eszközön telepítve lett, megnyitották és aktiválták azt.  Ha szeretne részletes információt arról, hogyan lehet leküldeni a Lookout for Work alkalmazást az eszközre, tekintse meg a [Lookout for Work alkalmazások hozzáadása az Intune-nal](mtd-apps-ios-app-configuration-policy-add-assign.md) témakört.

## <a name="next-steps"></a>További lépések

[Lookout-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
