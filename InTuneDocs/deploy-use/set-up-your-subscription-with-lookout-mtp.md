---
title: "Az előfizetés beállítása a Lookout használatára | Microsoft Intune"
description: "Ez a cikk a Lookout veszélyforrások elleni eszközvédelem konfigurálásának lépéseit ismerteti."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: bd22d4d19a8337194d331931995c0bd2321a90c5


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Az előfizetés beállítása a Lookout veszélyforrások elleni eszközvédelem használatára
A Lookout-ügyfélszolgálatának (enterprisesupport@lookout.com) a következői információkra lesz szüksége az Ön Azure Active Directory- (Azure AD-) előfizetéséről ahhoz, hogy előkészítse az előfizetést a Lookout veszélyforrások elleni eszközvédelmi szolgáltatás használatára. A Lookout Intune-nal való integrálásához a Lookout Mobility Endpoint Security-bérlő társítva lesz az Azure AD-előfizetéshez. 

* **Az Azure AD-bérlő azonosítója**
* **Az Azure AD-csoportobjektum azonosítója** a Lookout konzol **teljes körű** hozzáféréséhez
* Az **Azure AD-csoportobjektum azonosítója** a Lookout konzol **korlátozott** hozzáféréséhez (nem kötelező)

> [!IMPORTANT]
> Egy olyan létező Lookout Mobility Endpoint Security-bérlő, amely még nincs társítva az Azure AD-bérlőjéhez, nem használható fel az Azure AD-val és az Intune-nal való integrációhoz. Új Lookout Mobility Endpoint Security-bérlő létrehozásához lépjen kapcsolatba a Lookout támogatási csapatával. Azure AD-felhasználói számára használja az új bérlőt.

A következő szakasz segítségével gyűjtse össze a Lookout-támogatás számára szükséges információkat.  

## <a name="get-your-azure-ad-information"></a>Az Azure AD-adatok lekérdezése
### <a name="azure-ad-tenant-id"></a>Az Azure AD-bérlő azonosítója
Jelentkezzen be az [Azure AD felügyeleti portálra](https://manage.windowsazure.com) és válassza ki előfizetését. 

![képernyőkép az Azure AD-oldalról a bérlő nevével](../media/mtp/aad_tenant_name.png) Az előfizetés nevének kiválasztása után megjelenő URL-cím tartalmazza az előfizetés azonosítóját.  Ha probléma merül fel az előfizetési azonosító lékérdezésekor, további információt talál ebben a [Microsoft-támogatási cikkben](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US).   
### <a name="azure-ad-group-id"></a>Azure AD-csoportazonosító
A Lookout konzol két hozzáférési szintet támogat:  
* **Teljes hozzáférés:** Az Azure AD-rendszergazda létrehozhat egy csoportot teljes hozzáférésű felhasználók számára, és választhatóan egy korlátozott hozzáférésű felhasználókból álló csoportot is.  Csak ennek a két csoportnak a tagjai jelentkezhetnek be a **Lookout konzolra**.
* **Korlátozott hozzáférés:** a csoport felhasználóinak a Lookout konzol több konfigurációs és regisztrációval kapcsolatos moduljához nincs hozzáférésük, illetve csak olvasási hozzáférésük van a Lookout konzol **Security Policy** moduljához.  

Az engedélyekről további információt talál a Lookout-webhelyen, [ebben a cikkben](https://personal.support.lookout.com/hc/en-us/articles/114094105653).

A **Csoportobjektum azonosítója** az **Azure AD felügyeleti konzolján** , a csoport **Tulajdonságok** lapján található.

![a tulajdonságok lap képernyőképe a csoportazonosító mező kiemelésével](../media/mtp/aad_group_object_id.png)

Miután kigyűjtötte ezeket az információkat, lépjen kapcsolatba a Lookout támogatási szolgálatával (e-mail: enterprisesupport@lookout.com).

A Lookout ügyfélszolgálat a megadott információkat felhasználva, az elsődleges kapcsolattartóval együttműködve előkészíti az előfizetést, és elkészíti a vállalati Lookout-fiókot.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Az előfizetés beállítása a Lookout fenyegetések elleni eszközvédelem használatára
### <a name="step-1-set-up-your-device-threat-protection"></a>1. lépés: A veszélyforrások elleni védelem konfigurálása
Miután a Lookout ügyfélszolgálata létrehozta a vállalati Lookout-fiókot, bejelentkezhet a Lookout konzolra.   A Lookout e-mailben küldi el a bejelentkezési URL-címet a vállalat elsődleges kapcsolattartójának címére: https://aad.lookout.com/les?action=consent

A Lookout konzolra való első bejelentkezésnél egy Azure AD-szerepkörű globális rendszergazdai felhasználói fiókkal kell bejelentkezni, mert a Lookout ezt az információt követeli meg az Azure AD-bérlő regisztrálásához.   A későbbi bejelentkezéseknél nem szükséges ezt a szintű Azure AD-jogosultságot használni.  Az első bejelentkezésnél egy hozzájárulást kérő lap jelenik meg. A regisztráció befejezéséhez válassza az **elfogad** lehetőséget.

![képernyőkép a Lookout konzolra való első belépésről](../media/mtp/lookout_mtp_initial_login.png) A hozzájárulás és beleegyezés után a rendszer átirányítja a Lookout konzolra. A regisztráció elvégzése után a későbbiekben ezen az URL-címen jelentkezhet be: https://aad.lookout.com

Bejelentkezési problémák esetén olvassa el a [hibaelhárításról szóló cikket](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

A következőkben azokat a lépéseket mutatjuk be, amelyeket a Lookout beállításához el kell végezni a [Lookout konzolon](https://aad.lookout.com).

### <a name="step-2-configure-the-intune-connector"></a>2. lépés: Az Intune-összekötő konfigurálása

1.  Nyissa meg a Lookout konzolon a **System** (Rendszer) modult, válassza a **Connectors** (Összekötők) lapot, majd az **Intune** lehetőséget.

  ![képernyőkép a Lookout konzolról, amelyen az összekötők lap meg van nyitva, az Intune lehetőség pedig ki van emelve](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  A kapcsolat beállítása lehetőségnél állítsa be a szívverés percenkénti gyakoriságát.  Az Intune-összekötője immár készen áll.  

  ![képernyőkép a kapcsolat beállítása lapról, amin a szívverés gyakorisága már konfigurálva van](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>3. lépés: Regisztrációs csoportok konfigurálása
A **Regisztrációkezelés** lehetőséget választva adja meg azoknak a felhasználóknak a csoportját, akiknek az eszközei regisztrálva lesznek a Lookout-ban. Tesztelési célok miatt ajánlatos először egy kisebb csoportot definiálni, így könnyebben megismerkedhet az integráció működésével.  Ha a tesztelés után mindent rendben talál, a regisztrációt kiterjesztheti újabb felhasználói csoportokra is.

A regisztrációs csoportok kezeléséhez első lépésként adjon meg egy olyan Azure AD biztonsági csoportot, amely jó lesz a Lookout veszélyforrások elleni eszközvédelemben regisztráló első csoportnak. Miután létrehozta a csoportot az Azure AD-ben, a Lookout konzolon válassza az **Enrollment Management** (Regisztrációkezelés) lehetőséget, és adja meg az Azure AD biztonsági csoport megjelenített nevét a **Display Name** mezőben a regisztrációhoz.

Ha egy felhasználó tagja egy regisztrációs csoportnak, akkor az Azure AD által támogatott és azonosított minden eszköze regisztrálható és aktiválható a Lookout veszélyforrások elleni eszközvédelemben.  Az eszköz akkor aktiválódik a Lookoutban, amikor a felhasználó először nyitja meg a Lookout for Work alkalmazást a támogatott eszközön.

![képernyőkép az Intune-összekötő regisztrálási oldaláról](../media/mtp/lookout-mtp-enrollment.png)

Az új eszközök keresésének gyakorisága értéknél javasolt megtartani az alapértelmezett (5 perces) beállítást.

>[!IMPORTANT]
> A megjelenítendő névben különbséget kell tenni a kis- és nagybetűk között.  A **Megjelenített névnél** használja azt a formát, amely az Azure portálon a biztonsági csoport **Tulajdonságok** lapján látható. Amint az alábbi képen látható, a biztonsági csoport **Tulajdonságok** lapján a megjelenített névben nagybetűs szavak szerepelnek.  A címsorban azonban csupa kisbetű szerepel – ezt a formát ne használja a Lookout konzolon.
>![képernyőkép az Azure portálról, az Azure Active Directory szolgáltatás tulajdonságok lapjáról](../media/mtp/aad-group-display-name.png)

A jelenlegi verzió az alábbi korlátozásokat tartalmazza:  
* A csoport megjelenítendő nevénél nem történik ellenőrzés.  Fontos, hogy azt az értéket használja, amely az Azure Portalon az Azure AD biztonsági csoportjának **MEGJELENÍTETT NÉV** mezőjében látható.
* Csoporton belüli csoport létrehozása jelenleg nem támogatott.  A megadott Azure AD biztonsági csoportok csak felhasználókat tartalmazhatnak, beágyazott csoportokat nem.


### <a name="step-4-configure-state-sync"></a>4. lépés: Az állapotszinkronizálás konfigurálása
Az **Állapotszinkronizálás** lehetőségnél adja meg az Intune-ba küldendő adattípusokat.  A Lookout és az Intune integrációjának megfelelő működéséhez jelenleg az eszközállapotot és a fenyegetések állapotát egyaránt engedélyeznie kell.  Alapértelmezés szerint ezek engedélyezve vannak.
### <a name="step-5-configure-error-report-email-recipient-information"></a>5. lépés: E-mail-címzettek adatainak konfigurálása hibajelentésekhez
A **Hibakezelés** lehetőségnél írja be azt az e-mail címet, amelyre a hibajelentéseket szeretné irányítani.

![képernyőkép az Intune-összekötő hibakezelési oldaláról](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>6. lépés Regisztrációs beállítások konfigurálása
A **System** modul **Connectors** lapján adja meg, hogy hány nap múltán tekintse a program leválasztottnak az adott eszközt.  A leválasztott eszközöket nem megfelelőnek tekinti a program, és az Intune-beli feltételes hozzáférésre vonatkozó szabályzatok alapján törli a munkahelyi alkalmazásokhoz való hozzáférésüket. 1 és 90 nap közötti időtartam adható meg.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>7. lépés: E-mailben történő értesítések konfigurálása
Ha e-mailben szeretne értesítéseket kapni a veszélyforrásokról, jelentkezzen be a [Lookout konzolra](https://aad.lookout.com) azzal a felhasználói fiókkal, amelybe az értesítéseket szeretné kapni. A **Rendszer** modulban, a **Beállítások** lapon a kívánt értesítések melletti kapcsolót állítsa **BE** értékre. Mentse a változtatásokat.

![képernyőkép a beállítások lapról a felhasználói fiókkal](../media/mtp/lookout-mtp-email-notifications.png) Ha már nem szeretne email értesítéseket kapni, állítsa az értesítés típusa melletti kapcsolót **KI** értékre.
### <a name="step-8-configure-threat-classification"></a>8. lépés: A veszélyforrások besorolásának konfigurálása
A Lookout osztályokba sorolja a különféle fenyegetési típusokat. A [Lookout veszélyforrás-besorolásaiban](http://personal.support.lookout.com/hc/en-us/articles/114094130693) alapértelmezett kockázati szintek tartoznak a fenyegetésekhez. Ezek bármikor módosíthatók a vállalat igényeinek megfelelően.

![képernyőkép a szabályzat oldaláról a fenyegetések besorolásával](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Az itt meghatározott kockázati szintek fontos elemét alkotják a veszélyforrások elleni eszközvédelemnek, mert az Intune-integráció az eszköz megfelelőségét az itt meghatározott kockázati szintek alapján számítja ki futásidőben. Vagyis az Intune-rendszergazda állítja be a szabályzatban, hogy egy eszköz akkor nem megfelelő, ha egy olyan aktív fenyegetés található rajta, amelynek a szintje: magas, közepes vagy alacsony. A Lookout veszélyforrások elleni eszközvédelem veszélyforrás-besorolási szabályzata közvetlen alapja az Intune-ban lezajló eszközmegfelelőségi számításnak.

## <a name="watching-enrollment"></a>A regisztráció figyelése
A telepítés befejezése után a Lookout veszélyforrások elleni eszközvédelem elkezdi lekérdezni az Azure AD-ből azokat az eszközöket, amelyek megfelelnek a megadott regisztrációs csoportoknak.  A regisztrált eszközök adatai az Eszközök modulban találhatók.  Az eszközök kezdeti állapota mindig „folyamatban” lesz.  Az eszközállapot akkor frissül, ha a Lookout for Work alkalmazás az illető eszközön telepítve lett, megnyitották és aktiválták azt.  A Lookout for Work alkalmazás eszközökre való elküldéséről további információt talál a [Lookout for Work alkalmazások konfigurálása és telepítése](configure-and-deploy-lookout-for-work-apps.md) című témakörben.
## <a name="next-steps"></a>További lépések
[Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Dec16_HO2-->

