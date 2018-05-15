---
title: A Windows Update Vállalatoknak konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: A profilok szoftverfrissítési beállításainak frissítésével frissítési kört hozhat létre, áttekintheti a megfelelőséget, és szüneteltetheti a Windows Update Vállalatoknak frissítéseit a Microsoft Intune Windows 10-es eszközökön való használatával.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 5/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: c8751572ec2c072504b2442cb7e76496e969e0a2
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="manage-software-updates-in-intune"></a>Szoftverfrissítések kezelése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Windows 10 rendszerű eszközök frissítésére a Windows szoftverszolgáltatás használható. A Windows 10-ben az új funkció- és minőségi frissítések magukban foglalják valamennyi korábbi frissítés tartalmát. Így a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 rendszerű eszközök naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.

A Windows Update Vállalatoknak használatával leegyszerűsítheti a frissítéskezelést. Nem kell jóváhagynia az eszközcsoportok egyes frissítéseit. A környezetek kockázatkezelését egy frissítéskibocsátási stratégia konfigurálásával intézheti. A Windows Update gondoskodik arról, hogy a frissítések a megfelelő időben települjenek. A Microsoft Intune lehetővé teszi a frissítési beállítások konfigurálását az eszközökön és a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A **Windows 10 frissítési körök** az Intune használatával konfigurálhatók és kezelhetők. A frissítési körök olyan beállításokat tartalmaznak, amelyek a Windows 10 frissítések telepítésének ütemezését és mikéntjét konfigurálják. Megadhatja például a következő beállításokat:

- **Windows 10 karbantartási csatorna**: Válassza ki azt a karbantartási csatornát, amelytől frissítéseket szeretne kérni az eszközcsoportoknak. Az alábbi csatornák érhetők el: 
  - Féléves csatorna
  - Féléves csatorna (célzott)
  - Windows Insider &#8208; gyors
  - Windows Insider &#8208; lassú
  - A Windows Insider kiadása 
      
  További információ az elérhető karbantartási csatornákról: [A Windows mint szoftverszolgáltatás – áttekintés](https://docs.microsoft.com/en-us/windows/deployment/update/waas-overview#servicing-channels).
- **Halasztó beállítások**: A frissítéseket halasztó beállítások megadásával késleltethető a frissítések telepítése az eszközcsoportokon. Ezzel a beállítással a lépésenkénti frissítési terv alapján a folyamat végig nyomon követhető.
- **Felfüggesztés**: A frissítések telepítésének felfüggesztése, ha a frissítési terv bármely pontján probléma merülne fel.
- **Karbantartási időszak**: Megadható egy időszak, amelyben a frissítések telepíthetők.
- **Frissítés típusa**: Megadható, hogy milyen típusú frissítések települjenek. Ezek lehetnek például a minőségi frissítések, funkciófrissítések vagy illesztőprogramok.
- **Műveletek a telepítéskor**: A frissítések telepítési módját konfigurálja. Például meghatározható, hogy automatikusan újrainduljon-e az eszköz a frissítés után.
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

  A klasszikus Azure-portál néhány egyéb Windows 10-frissítési beállítást is tartalmaz az eszközkonfigurációs profilban. Amennyiben ezen beállítások bármelyike már konfigurálva van az Azure Portalra való migráláskor, erősen ajánlott a következő lépések végrehajtása:

1. Hozzon létre Windows 10 frissítési köröket az Azure Portalon a kívánt beállításokkal. Az **Előzetes funkciók engedélyezése** beállítást az Azure Portal nem támogatja, mert az már nem alkalmazható a legújabb Windows 10 buildekre. A frissítési körök létrehozásakor megadhatja a másik három beállítást és a további Windows 10 frissítési beállításokat is.

   > [!NOTE]
   > A klasszikus portálon megadott Windows 10-frissítési beállítások nem jelennek meg az Azure Portalon az áttelepítés után. Ezek a beállítások azonban érvénybe lépnek. Ha a beállítások bármelyikét migrálja, majd módosítja az áttelepített szabályzatot az Azure Portalon, akkor ezek a beállítások törlődnek a szabályzatból.

2. Törölje a frissítési beállításokat a klasszikus portálon. Az Azure Portalra történő migrálás és az azonos beállításoknak egy frissítési körben történő megadása után az esetleges szabályzat-ütközések elkerülése érdekében a beállításokat a klasszikus portálon törölni kell. Ha például ugyanazt a beállítást különböző értékekkel konfigurálja, ütközés alakul ki. Ezt nem könnyű megállapítani, mert a klasszikus portálon konfigurált beállítás nem jelenik meg az Azure Portalon.

## <a name="create-and-assign-update-rings"></a>Frissítési körök létrehozása és hozzárendelése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **Windows 10-es frissítési körök** > **Létrehozás** lehetőséget.
4. Adjon meg egy nevet, egy leírást (nem kötelező), majd válassza a **Konfigurálás** lehetőséget.
5. A **Beállítások** területen adja meg az alábbi adatokat:

   - **Karbantartási csatorna**: Adja meg azt a csatornát, amelytől az eszköz a Windows-frissítéseket kapja.
   - **Microsoft-termékfrissítések**: Válassza az alkalmazás-frissítések keresését a Microsoft Update webhelyen.
   - **Windows-illesztőprogramok**: Válassza a Windows Update-illesztőprogramok mellőzését a frissítések során.
   - **Az automatikus frissítés viselkedése**: Adja meg, hogy hogyan települjenek az automatikus frissítések, illetve mikor indítsák újra az eszközt. További információ:  [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).
     - **Az automatikus viselkedés gyakorisága**: Ez a beállítás akkor jelenik meg, ha az **Automatikus telepítés és újraindítás az ütemezett időpontban** lehetőséget választja a frissítési viselkedéshez. Ezzel a beállítással ütemezheti a frissítésék telepítését, amelyet hét, nap és időpont szerint adhat meg.

   - **Újraindítási ellenőrzések**: Alapértelmezés szerint be van kapcsolva. Egy eszköz újraindításakor a rendszer bizonyos ellenőrzéseket végez, például ellenőrzi az aktív felhasználókat, az akkumulátor szintjét, a futó játékokat és más szempontokat. Ha át szeretné ugrani ezeket az ellenőrzéseket az eszközök újraindításakor, válassza a **Kihagyás** lehetőséget.

   - **Minőségi frissítések késleltetésének időtartama (nap)** – Adja meg, hány nappal kívánja késleltetni a minőségi frissítéseket. Ezeknek a minőségi frissítéseknek a fogadása a kiadásuktól számítva legfeljebb 30 nappal késleltethető.

     A minőségi frissítések általában meglévő Windows-funkciók javításai és továbbfejlesztései, és rendszerint minden hónap első keddjén jelennek meg, bár a Microsoft bármikor kibocsáthatja őket. Megadhatja, hogy szeretné-e késleltetni a minőségi frissítéseket a Windows Update-en való megjelenésük után, és ha igen, mennyi időre.

   - **Funkciófrissítések késleltetésének időtartama (nap)** – Adja meg, hány nappal kívánja késleltetni a funkciófrissítéseket. Ezeknek a funkciófrissítéseknek a fogadása a kiadásuktól számítva legfeljebb 180 nappal késleltethető.

     A funkciófrissítések általában új Windows-funkciókat tartalmaznak. Miután konfigurálta a **Karbantartási csatorna** beállítást, megadhatja, hogy szeretné-e késleltetni a funkciófrissítéseket a Windows Update-en való megjelenésük után, és ha igen, mennyi időre.

     Például: **Ha a karbantartási csatorna a Féléves csatorna (célzott) értékre van beállítva, a késleltetési idő pedig 30 nap**: Tegyük fel, hogy az X funkciófrissítés januárban jelenik meg először a Windows Update szolgáltatásban a (célzott) féléves csatornán. Az eszköz csak februárban, 30 nappal később fogadja a frissítést.

     **Ha a karbantartási csatorna a Féléves csatorna értékre van beállítva, a késleltetési idő pedig 30 nap**: Tegyük fel, hogy az X funkciófrissítés januárban jelenik meg először a Windows Update szolgáltatásban a (célzott) féléves csatornán. Négy hónappal később, áprilisban az X funkciófrissítés megjelenik a féléves csatornán. Az eszköz 30 nappal annak a féléves csatornán való megjelenése után fogadja a funkciófrissítést, és májusban frissül.

   - **Kézbesítésoptimalizálásos letöltési mód** – Válassza ki azt a módszert, amellyel az eszközök letöltik a Windows-frissítéseket. További információ: [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

6. Ha elkészült, válassza az **OK** lehetőséget. A **Frissítési kör létrehozása** területen válassza a **Létrehozás** lehetőséget.

Az új frissítési kör megjelenik a frissítési körök listájában.

1. A kör hozzárendeléséhez jelölje ki a kört a frissítési körök listájában, majd a <*kör neve*> lapon válassza a **Hozzárendelések** lehetőséget.
2. A következő lapon válassza a **Válassza ki a befoglalandó csoportokat** lehetőséget, majd jelölje ki a csoportokat, amelyekhez hozzá kívánja rendelni ezt a kört.
3. Ha kész, válassza a **Kijelölés** lehetőséget a hozzárendelés befejezéséhez.

## <a name="update-compliance-reporting"></a>Frissítés-megfelelőségi jelentés
A frissítés-megfelelőség nyomon követhető az Intune-ban vagy az Operations Management Suite (OMS) ingyenes megoldása, az Update Compliance segítségével.

### <a name="review-update-compliance-in-intune"></a>Frissítés-megfelelőség ellenőrzése az Intune-ban 
<!-- 1352223 -->
A szabályzatjelentésben ellenőrizheti a konfigurált Windows 10-es frissítési körök telepítési állapotát.

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson a **Minden szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **Áttekintés** lehetőséget. Itt általános információkat találhat minden hozzárendelt frissítési kör állapotáról.
4. Nyissa meg az alábbi jelentések valamelyikét:

   **Minden frissítési körhöz**:  
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen
   2. A **Figyelés** szakaszban válassza a **Frissítési körönkénti telepítési állapot** lehetőséget.

   **Meghatározott frissítési körökhöz**:  
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen válassza ki az áttekinteni kívánt frissítési kört.
   2. Az adott frissítési kör adatainak megtekintéséhez a **Figyelés** szakaszban válasszon az alábbi jelentések közül:
      - **Eszközállapot**
      - **Felhasználó állapota**

### <a name="review-update-compliance-using-oms"></a>Frissítés-megfelelőség ellenőrzése az OMS használatával
A Windows 10 frissítések alkalmazása nyomon követhető az Operations Management Suite (OMS) ingyenes megoldása, az Update Compliance segítségével. További információ: [Windows frissítések figyelése az Update Compliance használatával](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Ennek a megoldásnak a használatával kereskedelmi azonosító telepíthető azokra az Intune-nal felügyelt Windows 10 eszközökre, amelyekről frissítés-megfelelőségi jelentést kíván készíteni.

A kereskedelmi azonosítót az Intune-konzolon egy egyéni szabályzat OMA-URI beállításaival konfigurálhatja. További információ: [A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-szabályzatbeállítások](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

A kereskedelmi azonosító konfigurálásához szükséges (kis- és nagybetűket megkülönböztető) OMA-URI elérési út: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Az **OMA-URI beállítások hozzáadása vagy módosítása** alatt például a következő beállítások használhatók:

- **Beállítás neve**: Windows Analytics kereskedelmi azonosító
- **Beállítás leírása**: Kereskedelmi azonosító konfigurálása Windows Analytics megoldásokhoz
- **OMA-URI** (megkülönbözteti a kis- és nagybetűket): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Adattípus:** Karakterlánc
- **Érték**: <*Használja az OMS munkaterület Windows-telemetria lapján látható GUID értéket*>

![OMA-URI beállítás – Sor szerkesztése](./media/commID-edit.png)

> [!NOTE]
> További információ az MS DM-kiszolgálóról: [DMClient konfigurációs szolgáltató (CSP)](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Frissítések felfüggesztése
A frissítések felfüggesztésétől számítva legfeljebb 35 napig megakadályozható, hogy az eszköz minőségi vagy funkciófrissítéseket fogadjon. A megadott időtartam után a felfüggesztés automatikusan megszűnik, és az eszköz keresni kezdi az alkalmazható Windows-frissítéseket. A keresés után a frissítések ismét felfüggeszthetők.

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **Windows 10-es frissítési körök** lehetőséget.
4. A frissítési körök listájában válassza ki a felfüggeszteni kívánt kört, majd a **...** > **Minőségi frissítések felfüggesztése** > vagy **Funkciófrissítések felfüggesztése** lehetőséget a felfüggeszteni kívánt frissítéstípustól függetlenül.

> [!IMPORTANT]
> A felfüggesztési parancsot a kiadása után az eszközök akkor kapják meg, amikor legközelebb bejelentkeznek a szolgáltatásba. Megtörténhet, hogy mielőtt bejelentkeznek, még telepítenek egy ütemezett frissítést.
> Ha az adott eszköz ki van kapcsolva a felfüggesztési parancs kiadásakor, akkor a bekapcsolása után esetleg letölthet és telepíthet ütemezett frissítéseket, mielőtt bejelentkezik az Intune-ba.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business-támogatás

A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Az automatikus frissítés viselkedése**
- **Microsoft-termékek frissítései**
- **Karbantartás csatorna**: a **féléves csatorna** és **féléves csatorna (célzott)** beállításokat támogatja
