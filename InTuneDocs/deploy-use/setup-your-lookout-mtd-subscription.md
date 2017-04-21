---
title: "Az előfizetés beállítása a Lookout használatára | Microsoft Docs"
description: "Ez a cikk a Lookout veszélyforrások elleni eszközvédelem konfigurálásának lépéseit ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 66be6716df38d868e8247131b49ffb50fc48e60b
ms.openlocfilehash: 60dbfa644a53fec3823e1182f5dec7eb97d8b5df
ms.lasthandoff: 04/15/2017


---

# <a name="set-up-your-lookout-mobile-threat-defense-subscription"></a>A Lookout Mobile Threat Defense-előfizetés beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Lookout Mobile Threat Defense beállításához az alábbi lépések szükségesek:

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
| 1 | [A regisztráció figyelése](#watching-enrollment) |


> [!IMPORTANT]
> Egy olyan létező Lookout Mobility Endpoint Security-bérlő, amely még nincs társítva az Azure AD-bérlőjéhez, nem használható fel az Azure AD-val és az Intune-nal való integrációhoz. Új Lookout Mobility Endpoint Security-bérlő létrehozásához lépjen kapcsolatba a Lookout támogatási csapatával. Azure AD-felhasználói számára használja az új bérlőt.

## <a name="collect-azure-ad-information"></a>Azure AD-információk gyűjtése
A Lookout Intune-nal való integrálásához a Lookout Mobility Endpoint Security-bérlő társítva lesz az Azure AD-előfizetéshez. A Lookout ügyfélszolgálatának (enterprisesupport@lookout.com) a következő információkra lesz szüksége ahhoz, hogy aktiválja a Lookout Mobile Threat Defense-előfizetést:  

* **Az Azure AD-bérlő azonosítója**
* **Az Azure AD-csoportobjektum azonosítója** a Lookout konzol **teljes körű** hozzáféréséhez
* Az **Azure AD-csoportobjektum azonosítója** a Lookout konzol **korlátozott** hozzáféréséhez (nem kötelező)

A következő lépések segítségével gyűjtse össze a Lookout-támogatás számára szükséges információkat.

1. Jelentkezzen be az [Azure AD felügyeleti portálra](https://manage.windowsazure.com) és válassza ki előfizetését. 
  ![képernyőkép Azure AD-oldalról a bérlő nevével](../media/mtp/aad_tenant_name.png)
2. Az előfizetés nevének kiválasztása után megjelenő URL-cím tartalmazza az előfizetés azonosítóját.  Ha probléma merül fel az előfizetési azonosító lékérdezésekor, további információt talál ebben a [Microsoft-támogatási cikkben](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b). 
3. Kérdezze le az Azure AD-csoportazonosítót. A Lookout konzol két hozzáférési szintet támogat:  
  * **Teljes hozzáférés:** Az Azure AD-rendszergazda létrehozhat egy csoportot teljes hozzáférésű felhasználók számára, és választhatóan egy korlátozott hozzáférésű felhasználókból álló csoportot is.  Csak ennek a két csoportnak a tagjai jelentkezhetnek be a **Lookout konzolra**.
  * **Korlátozott hozzáférés:** a csoport felhasználóinak a Lookout konzol több konfigurációs és regisztrációval kapcsolatos moduljához nincs hozzáférésük, illetve csak olvasási hozzáférésük van a Lookout konzol **Security Policy** moduljához.  

  Az engedélyekről további információt talál a Lookout-webhelyen, [ebben a cikkben](https://personal.support.lookout.com/hc/articles/114094105653).

  A **Csoportobjektum azonosítója** az **Azure AD felügyeleti konzolján** , a csoport **Tulajdonságok** lapján található.

  ![a tulajdonságok lap képernyőképe a csoportazonosító mező kiemelésével](../media/mtp/aad_group_object_id.png)

4. Miután kigyűjtötte ezeket az információkat, lépjen kapcsolatba a Lookout támogatási szolgálatával (e-mail: enterprisesupport@lookout.com). A Lookout ügyfélszolgálat a megadott információkat felhasználva, az elsődleges kapcsolattartóval együttműködve előkészíti az előfizetést, és elkészíti a vállalati Lookout-fiókot.

## <a name="configure-your-subscription"></a>Az előfizetés konfigurálása
1. Miután a Lookout ügyfélszolgálata elkészítette a vállalati Lookout-fiókot, a Lookout e-mailben küldi el a vállalat elsődleges kapcsolattartójának címére a bejelentkezési URL-címet: https://aad.lookout.com/les?action=consent.

2.  Az Azure AD-bérlő regisztrálásához a Lookout-konzolra való első bejelentkezésnél egy Azure AD-szerepkörű globális rendszergazdai felhasználói fiókkal kell bejelentkezni. A későbbiekben nem szükséges ezt a szintű Azure AD-jogosultságot használni. Egy hozzájárulást kérő lap jelenik meg. A regisztráció befejezéséhez válassza az **elfogad** lehetőséget.

  ![képernyőkép a Lookout konzolra való első belépésről](../media/mtp/lookout_mtp_initial_login.png) A hozzájárulás és beleegyezés után a rendszer átirányítja a Lookout konzolra.

  Bejelentkezési problémákkal kapcsolatban lásd: [A Lookout-integráció hibaelhárítása](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration).

3.  Nyissa meg a [Lookout konzolon](https://aad.lookout.com) a **System** (Rendszer) modult, válassza a **Connectors** (Összekötők) lapot, majd az **Intune** lehetőséget.

  ![képernyőkép a Lookout konzolról, amelyen az összekötők lap meg van nyitva, az Intune lehetőség pedig ki van emelve](../media/mtp/lookout_mtp_setup-intune-connector.png)

4.  A **Connectors (Összekötők)** > **Connection Settings (Kapcsolat beállítása)** lapon adja meg a **Heartbeat Frequency (Szívverés gyakorisága)** értékét.

  ![képernyőkép a kapcsolat beállítása lapról, amin a szívverés gyakorisága már konfigurálva van](../media/mtp/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Regisztrációs csoportok konfigurálása
1. Ajánlott eljárásként az [Azure AD felügyeleti portálon](https://manage.windowsazure.com) hozzon létre egy néhány tagból álló Azure AD-alapú biztonsági csoportot a Lookout-integráció teszteléséhez.

  Az Azure AD regisztrációs csoportjához tartozó felhasználók Lookout által támogatott és az Intune-ban regisztrált minden azonosítható és támogatott eszköze regisztrálható és aktiválható a Lookout veszélyforrások elleni eszközvédelemben.

2. Nyissa meg a [Lookout-konzolon](https://aad.lookout.com) a **System (Rendszer)** modult, válassza a **Connectors (Összekötők)** lapot, majd az **Enrollment Management (Regisztrációkezelés)** lehetőséget választva adja meg azoknak a felhasználóknak a csoportját, akiknek az eszközei regisztrálva lesznek a Lookoutban. A regisztráláshoz adja meg az Azure AD biztonsági csoport **Megjelenített nevét**.

  ![képernyőkép az Intune-összekötő regisztrálási oldaláról](../media/mtp/lookout-mtp-enrollment.png)

  >[!IMPORTANT]
  > A **Megjelenített névben** különbséget kell tenni a kis- és nagybetűk között, ahogyan az az Azure portálon a biztonsági csoport **Tulajdonságok** lapján látható. Amint az alábbi képen látható, a biztonsági csoport **Megjelenített nevében** nagybetűs szavak, míg a címben csak kisbetűk szerepelnek. A Lookout-konzolon a biztonsági csoport **Megjelenített nevénél** használja a megfelelő írásmódot.
  >![képernyőkép az Azure portálról, az Azure Active Directory szolgáltatás tulajdonságok lapjáról](../media/mtp/aad-group-display-name.png)

  Az új eszközök keresésének gyakorisága értéknél javasolt megtartani az alapértelmezett (5 perces) beállítást.

  **Aktuális korlátozások:**
  * A Lookout nem tudja ellenőrizni a csoport megjelenítendő nevét.  Ellenőrizze, hogy az Azure AD biztonsági csoportjának neve pontosan ugyanaz-e, mint ami az Azure portálon a **MEGJELENÍTETT NÉV** mezőben található.
  * Beágyazott csoportok létrehozása nem támogatott.  A Lookoutban használt Azure AD biztonsági csoportok kizárólag felhasználókat tartalmazhatnak. Más csoportok nem lehetnek tagjai.

3.  Az eszköz akkor aktiválódik a Lookoutban, amikor a csoport hozzáadása után a felhasználó az első alkalommal megnyitja a Lookout for Work alkalmazást a támogatott eszközön.

4.  Ha az eredményekkel elégedett, a regisztrációt további felhasználói csoportokra is kiterjesztheti.

## <a name="configure-state-sync"></a>Az állapotszinkronizálás konfigurálása
Az **Állapotszinkronizálás** lehetőségnél adja meg az Intune-ba küldendő adattípusokat.  A Lookout Intune-integrációjának megfelelő működéséhez mind az eszközállapotra, mind a fenyegetések állapotára szükség van.  Alapértelmezés szerint ezek engedélyezve vannak.

## <a name="configure-error-report-email-recipient-information"></a>E-mail-címzettek adatainak konfigurálása hibajelentésekhez
A **Hibakezelés** lehetőségnél írja be azt az e-mail címet, amelyre a hibajelentéseket szeretné irányítani.

![képernyőkép az Intune-összekötő hibakezelési oldaláról](../media/mtp/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Regisztrációs beállítások konfigurálása
A **System** modul **Connectors** lapján adja meg, hogy hány nap múltán tekintse a program leválasztottnak az adott eszközt.  A leválasztott eszközöket nem megfelelőnek tekinti a program, és az Intune-beli feltételes hozzáférésre vonatkozó szabályzatok alapján törli a munkahelyi alkalmazásokhoz való hozzáférésüket. 1 és 90 nap közötti időtartam adható meg.

![](../media/mtp/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>E-mailben történő értesítések konfigurálása
Ha e-mailben szeretne értesítéseket kapni a veszélyforrásokról, jelentkezzen be a [Lookout konzolra](https://aad.lookout.com) azzal a felhasználói fiókkal, amelybe az értesítéseket szeretné kapni. A **Rendszer** modulban, a **Beállítások** lapon válassza ki azt a fenyegetési szintet, amelyhez értesítést kíván beállítani, és a kapcsolójukat állítsa **BE** értékre. Mentse a változtatásokat.

![képernyőkép a beállítások lapról a felhasználói fiókkal](../media/mtp/lookout-mtp-email-notifications.png) Ha már nem szeretne email értesítéseket kapni, állítsa az értesítés típusa melletti kapcsolót **KI** értékre.

### <a name="configure-threat-classification"></a>A veszélyforrások besorolásának konfigurálása
A Lookout Mobile Threat Defense osztályokba sorolja a különféle fenyegetési típusokat. A [Lookout veszélyforrás-besorolásaiban](http://personal.support.lookout.com/hc/articles/114094130693) alapértelmezett kockázati szintek tartoznak a fenyegetésekhez. Ezek bármikor módosíthatók a vállalat igényeinek megfelelően.

![képernyőkép a szabályzat oldaláról a fenyegetések besorolásával](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> A kockázati szintek fontos elemét alkotják a Mobile Threat Defense-nek, mert az Intune-integráció az eszköz megfelelőségét a kockázati szintek alapján számítja ki futásidőben. Az Intune-rendszergazda állítja be a szabályzatban, hogy egy eszköz akkor nem megfelelő, ha egy olyan aktív fenyegetés található rajta, amelynek a szintje: **Magas**, **Közepes** vagy **Alacsony**. A Lookout Mobile Threat Defense veszélyforrás-besorolási szabályzata közvetlen alapja az Intune-ban lezajló eszközmegfelelőségi számításnak.

## <a name="watching-enrollment"></a>A regisztráció figyelése
A telepítés befejezése után a Lookout Mobile Threat Defense elkezdi lekérdezni az Azure AD-ből azokat az eszközöket, amelyek megfelelnek a megadott regisztrációs csoportoknak.  A regisztrált eszközök adatai az Eszközök modulban találhatók.  Az eszközök kezdeti állapota mindig „folyamatban” lesz.  Az eszközállapot akkor frissül, ha a Lookout for Work alkalmazás az illető eszközön telepítve lett, megnyitották és aktiválták azt.  A Lookout for Work alkalmazás eszközökre való elküldéséről további információt talál a [Lookout for Work alkalmazások konfigurálása és telepítése](configure-and-deploy-lookout-for-work-apps.md) című témakörben.
## <a name="next-steps"></a>További lépések
[Lookout MTP-kapcsolat engedélyezése az Intune-ban](https://docs.microsoft.com/intune/deploy-use/enable-lookout-mtd-connection)

