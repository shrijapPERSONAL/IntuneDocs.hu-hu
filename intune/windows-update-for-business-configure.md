---
title: "A Vállalati Windows Update beállításainak konfigurálása az Intune-ban"
titleSuffix: Azure portal
description: "Útmutató a Vállalati Windows Update Intune-beli konfigurálásához a Windows 10-es eszközök frissítéseinek kezeléséhez.”"
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: d6ccda2aba0b1383de6c38b7a2fdcfdc742d0e15
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="manage-software-updates"></a>Szoftverfrissítések kezelése

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Windows 10 rendszerű eszközök frissítésére a Windows szoftverszolgáltatás használható. A Windows 10-ben az új funkció- és minőségi frissítések magukban foglalják valamennyi korábbi frissítés tartalmát. Ennek köszönhetően a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 rendszerű eszközök naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.

A Vállalati Windows Update használatával egyszerűbbé válik a frissítések kezelése, így nem szükséges külön jóváhagyni az egyes frissítéseket az eszközcsoportokhoz. A különböző környezetekben továbbra is kezelhetők a kockázatok egy frissítéstelepítési stratégia konfigurálásával, és a Windows Update gondoskodik a frissítések megfelelő időpontban történő telepítéséről. A Microsoft Intune lehetővé teszi a frissítési beállítások konfigurálását az eszközökön és a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A **Windows 10 frissítési körök** az Intune használatával konfigurálhatók és kezelhetők. A frissítési kör olyan beállításokat tartalmaz, amelyek a Windows 10 frissítések telepítésének ütemezését és mikéntjét konfigurálják. Megadhatja például a következő beállításokat:

- **Windows 10 karbantartási csatorna**: Eldöntheti, hogy az eszközcsoportok a célzott féléves csatornán vagy a féléves csatornán kapjanak frissítéseket.  
- **Halasztó beállítások**: A frissítéseket halasztó beállítások megadásával késleltethető a frissítések telepítése az eszközcsoportokon. Ezzel a beállítással a lépésenkénti frissítési terv alapján a folyamat végig nyomon követhető.
- **Felfüggesztés**: A frissítések telepítésének felfüggesztése, ha a frissítési terv bármely pontján probléma merülne fel.
- **Karbantartási időszak**: Megadható egy időszak, amelyben a frissítések telepíthetők.
- **Frissítés típusa**: Megadható, hogy milyen típusú frissítések települjenek. Ezek lehetnek például a minőségi frissítések, funkciófrissítések vagy illesztőprogramok.
- **Műveletek a telepítéskor**: Itt konfigurálható a frissítések telepítési módja. Például meghatározható, hogy automatikusan újrainduljon-e az eszköz a frissítés után.
- **Megosztott letöltés**: Konfigurálható a letöltések megosztása. Ezzel a beállítással, miután egy eszköz végzett egy frissítés letöltésével, a többi eszköz már erről az eszközről tölti le a frissítést. A letöltés folyamata ezáltal felgyorsul.

A kialakított frissítési körök hozzárendelhetők az eszközcsoportokhoz. Frissítési körök használatával kialakítható az üzleti igényeknek leginkább megfelelő frissítési stratégia. További információ: [Frissítések kezelése a Vállalati Windows Update használatával](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Előkészületek

- A frissítéshez a Windows 10 rendszerű számítógépeken legalább Windows 10 Pro verziónak kell futnia az évfordulós frissítéssel.

- A Windows Update a Windows 10 alábbi verzióit támogatja:
    - Windows 10
    - Windows 10 Team (Surface Hub-eszközök esetén)
    - [Windows Holographic for Business](#windows-holographic-for-business-support)

 A Windows 10 Mobile rendszert futtató eszközök nem támogatottak.

- Windows eszközökön a **Visszajelzés és diagnosztika** > **Diagnosztikai és használati adatok** beállításnál legalább az **Alapszintű** értéknek kell szerepelnie.

    ![A Windows beállítása diagnosztikai és használati adatok küldéséhez](./media/telemetry-basic.png)

    Ezt a beállítást elvégezheti manuálisan, vagy a Windows 10 és újabb verziók esetén használhat egy Intune eszközkorlátozási profilt. Ehhez az **Általános** > **Diagnosztikai adatok küldése** beállításnál legalább az **Alapszintű** értéknek kell szerepelnie. Az eszközprofilokról további információt nyújt az [Eszközkorlátozási beállítások konfigurálása](device-restrictions-configure.md) című témakör.

- Az Intune felügyeleti konzolon négy beállítás szabályozza a szoftverfrissítések viselkedését. Ezek a beállítások az általános konfigurációs szabályzat részei a Windows 10 rendszerű számítógépeken és mobileszközökön:
    - **Automatikus frissítések engedélyezése**
    - **Előzetes funkciók engedélyezése**
    - **Telepítés ütemezett napja**
    - **Telepítés ütemezett időpontja**

  A klasszikus portál néhány egyéb Windows 10-frissítési beállítást is tartalmaz az eszközkonfigurációs profilban. Amennyiben ezen beállítások bármelyike már konfigurálva van az Intune felügyeleti konzolon az Azure Portalra való átálláskor, erősen ajánlott a következő lépések végrehajtása:

1. Hozzon létre Windows 10 frissítési köröket az Azure Portalon a kívánt beállításokkal. Az **Előzetes funkciók engedélyezése** beállítást az Azure Portal nem támogatja, mert az már nem alkalmazható a legújabb Windows 10 buildekre. A frissítési körök létrehozásakor megadhatja a másik három beállítást és a további Windows 10 frissítési beállításokat is.

  > [!NOTE]
  > A klasszikus portálon megadott Windows 10-frissítési beállítások nem jelennek meg az Azure Portalon az áttelepítés után. Ugyanakkor ezek a beállítások továbbra is érvényben maradnak. Ha a beállítások bármelyikét áttelepítette, majd módosítja az áttelepített szabályzatot az Azure Portalon, akkor ezek a beállítások törlődnek a szabályzatból.

2. Törölje a frissítési beállításokat a klasszikus portálon. Az Azure Portalra történő áttelepítés és az azonos beállításoknak egy frissítési körben történő megadása után az esetleges szabályzat-ütközések elkerülése érdekében a beállításokat a klasszikus portálon törölni kell. Ha például ugyanazon beállítás két különböző értékkel van megadva, az olyan ellentmondáshoz vezet, amely nehezen felderíthető, hiszen a klasszikus portálon megadott beállítások az Azure Portalon nem jelennek meg.

## <a name="how-to-create-and-assign-update-rings"></a>Frissítési körök létrehozása és hozzárendelése

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Szoftverfrissítések** lehetőséget.
4. A **Szoftverfrissítések** panelen válassza a **Kezelés** > **Windows 10-es frissítési körök** lehetőséget.
5. A frissítési körök listáját megjelenítő panelen válassza a **Létrehozás** lehetőséget.
6. A **Frissítési kör létrehozása** panelen adjon meg egy nevet és igény szerint leírást a frissítési körhöz, majd válassza a **Beállítások – Konfigurálás** lehetőséget.
7. A **Beállítások** panelen konfigurálja az alábbi adatokat:
    - **Karbantartási csatorna**: Állítsa be, hogy az eszköz a célzott féléves csatornán vagy a féléves csatornán kapjon frissítéseket.
    - **Microsoft-termékfrissítések**: Döntse el, hogy kíván-e alkalmazás-frissítéseket keresni a Microsoft Update webhelyen.
    - **Windows-illesztőprogramok**: Döntse el, hogy mellőzni kívánja-e a Windows Update-illesztőprogramokat a frissítések során.
    - **Automatikus frissítés módja**: Válassza ki, hogy milyen módon keressen, töltsön le és telepítsen frissítéseket az automatikus frissítés. További információ:  [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Minőségi frissítések késleltetésének időtartama (nap)** – Adja meg, hány nappal kívánja késleltetni a minőségi frissítéseket. Ezeknek a minőségi frissítéseknek a fogadása a kiadásuktól számítva legfeljebb 30 nappal késleltethető.  

    A minőségi frissítések általában meglévő Windows-funkciók javításai és továbbfejlesztései, és rendszerint minden hónap első keddjén jelennek meg, bár a Microsoft bármikor kibocsáthatja őket. Meghatározhatja, hogy az elérhetővé válásuk után kívánja-e késleltetni a minőségi frissítések fogadását, és ha igen, akkor mennyi ideig.

    - **Funkciófrissítések késleltetésének időtartama (nap)** – Adja meg, hány nappal kívánja késleltetni a funkciófrissítéseket. Ezeknek a funkciófrissítéseknek a fogadása a kiadásuktól számítva legfeljebb 180 nappal késleltethető.

    A funkciófrissítések általában új Windows-funkciók. A **Karbantartási csatorna** beállítás a célzott féléves csatornára vagy a féléves csatornára való konfigurálása után megadhatja, hogy szeretné-e késleltetni a Microsoft által a Windows Update szolgáltatásban közzétett funkciófrissítések fogadását, és ha igen, akkor mennyivel.

    Például: **Ha a karbantartási csatorna a Féléves csatorna (célzott) értékre van beállítva, a késleltetési idő pedig 30 nap**: Tegyük fel, hogy az X funkciófrissítés januárban jelenik meg először a Windows Update szolgáltatásban a (célzott) féléves csatornán. Az eszköz csak februárban, 30 nappal később fogadja a frissítést.

    **Ha a karbantartási csatorna a Féléves csatorna értékre van beállítva, a késleltetési idő pedig 30 nap**: Tegyük fel, hogy az X funkciófrissítés januárban jelenik meg először a Windows Update szolgáltatásban a (célzott) féléves csatornán. Négy hónappal később, áprilisban az X funkciófrissítés megjelenik a féléves csatornán. Az eszköz 30 nappal annak a féléves csatornán való megjelenése után fogadja a funkciófrissítést, és májusban frissül.

    - **Kézbesítésoptimalizálásos letöltési mód** – Válassza ki azt a módszert, amellyel az eszközök letöltik a Windows-frissítéseket. További információ: [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).
1. Ha minden kész, kattintson az **OK** gombra, majd a **Frissítési kör létrehozása** panelen a **Létrehozás** lehetőségre.

Az új frissítési kör megjelenik a frissítési körök listájában.

1. A kör hozzárendeléséhez jelölje ki a kört a frissítési körök listájában, majd a <*kör neve*> lapon válassza a **Hozzárendelések** lehetőséget.
2. A következő lapon válassza a **Válassza ki a befoglalandó csoportokat** lehetőséget, majd jelölje ki a csoportokat, amelyekhez hozzá kívánja rendelni ezt a kört.
3. Ha kész, válassza a **Kijelölés** lehetőséget a hozzárendelés befejezéséhez.

## <a name="update-compliance-reporting"></a>Frissítés-megfelelőségi jelentés
A frissítés-megfelelőség nyomon követhető az Intune-ban vagy az Operations Management Suite (OMS) ingyenes megoldása, az Update Compliance segítségével.

### <a name="review-update-compliance-in-intune"></a>Frissítés-megfelelőség ellenőrzése az Intune-ban 
<!-- 1352223 -->
A szabályzatjelentésben ellenőrizheti a konfigurált Windows 10-es frissítési körök telepítési állapotát. 
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Szoftverfrissítések** lehetőséget.
4. A **Szoftverfrissítések** panelen válassza az **Áttekintés** elemet. Itt általános információkat találhat minden hozzárendelt frissítési kör állapotáról.
5. Nyissa meg az alábbi jelentések valamelyikét: 
     
   **Minden frissítési körhöz:**
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** panelen. 
   2. A **Figyelés** szakaszban válassza a **Frissítési körönkénti telepítési állapot** lehetőséget.
                   
   **Meghatározott frissítési körökhöz:** 
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** panelen válassza ki a megtekinteni kívánt frissítési kört.
   2. Az adott frissítési kör adatainak megtekintéséhez a **Figyelés** szakaszban válasszon az alábbi jelentések közül:
      - **Eszközállapot**
      - **Felhasználó állapota**

### <a name="review-update-compliance-using-oms"></a>Frissítés-megfelelőség ellenőrzése az OMS használatával
A Windows 10 frissítések alkalmazása nyomon követhető az Operations Management Suite (OMS) ingyenes megoldása, az Update Compliance segítségével. További információ: [Windows frissítések figyelése az Update Compliance használatával](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Ennek a megoldásnak a használatával kereskedelmi azonosító telepíthető azokra az Intune-nal felügyelt Windows 10 eszközökre, amelyekről frissítés-megfelelőségi jelentést kíván készíteni.

A kereskedelmi azonosítót az Intune-konzolon egy egyéni szabályzat OMA-URI beállításaival konfigurálhatja. További információ: [A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-szabályzatbeállítások](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

A kereskedelmi azonosító konfigurálásához szükséges (kis- és nagybetűket megkülönböztető) OMA-URI elérési út: ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

Az **OMA-URI beállítások hozzáadása vagy módosítása** alatt például a következő beállítások használhatók:

- **Beállítás neve**: Windows Analytics kereskedelmi azonosító
- **Beállítás leírása**: Kereskedelmi azonosító konfigurálása Windows Analytics megoldásokhoz
- **OMA-URI** (megkülönbözteti a kis- és nagybetűket): ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID
- **Adattípus:** Karakterlánc
- **Érték**: <*Használja az OMS munkaterület Windows-telemetria lapján látható GUID értéket*>

![A Windows beállítása diagnosztikai és használati adatok küldéséhez](./media/commID.png)

## <a name="how-to-pause-updates"></a>Frissítések felfüggesztése
A frissítések felfüggesztésétől számítva legfeljebb 35 napig megakadályozható, hogy az eszköz minőségi vagy funkciófrissítéseket fogadjon. A megadott időtartam után a felfüggesztés automatikusan megszűnik, és az eszköz keresni kezdi az alkalmazható Windows-frissítéseket. A keresés után a frissítések ismét felfüggeszthetők.
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Szoftverfrissítések** lehetőséget.
4. A **Szoftverfrissítések** panelen válassza a **Kezelés** > **Windows 10-es frissítési körök** lehetőséget.
5. A frissítési körök listáját megjelenítő panelen válassza ki a felfüggeszteni kívánt kört, majd attól függően, hogy a frissítések melyik típusát kívánja felfüggeszteni, válassza a **...** > **Minőségi frissítések felfüggesztése** > vagy a **Funkciófrissítések felfüggesztése** lehetőséget.

> [!IMPORTANT]
> A felfüggesztési parancsot a kiadása után az eszközök akkor kapják meg, amikor legközelebb bejelentkeznek a szolgáltatásba. Megtörténhet, hogy mielőtt bejelentkeznek, még telepítenek egy ütemezett frissítést.
> Ha az adott eszköz ki van kapcsolva a felfüggesztési parancs kiadásakor, akkor a bekapcsolása után esetleg letölthet és telepíthet ütemezett frissítéseket, mielőtt bejelentkezik az Intune-ba.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business-támogatás

A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Az automatikus frissítés viselkedése**
- **Microsoft-termékek frissítései**
- **Karbantartási csatorna**