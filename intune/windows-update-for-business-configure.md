---
title: A Windows Update Vállalatoknak konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: A profilok szoftverfrissítési beállításainak frissítésével frissítési kört hozhat létre, áttekintheti a megfelelőséget, és szüneteltetheti a Windows Update Vállalatoknak frissítéseit a Microsoft Intune Windows 10-es eszközökön való használatával.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: 184f70aefbdc90c301ef2f97c5a3abb5ac49a4a8
ms.sourcegitcommit: 12f8b7f0bca1baa2c1f68dd6af4f16a4814daa11
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2019
ms.locfileid: "55737485"
---
# <a name="manage-software-updates-in-intune"></a>Szoftverfrissítések kezelése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Windows 10 rendszerű eszközök frissítésére a Windows szoftverszolgáltatás használható. A Windows 10-ben az új funkció- és minőségi frissítések magukban foglalják valamennyi korábbi frissítés tartalmát. Így a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 rendszerű eszközök naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.

A Windows Update Vállalatoknak használatával leegyszerűsítheti a frissítéskezelést. Nem kell jóváhagynia az eszközcsoportok egyes frissítéseit. A környezetek kockázatkezelését egy frissítéskibocsátási stratégia konfigurálásával intézheti. A Windows Update gondoskodik arról, hogy a frissítések a megfelelő időben települjenek. A Microsoft Intune lehetővé teszi a frissítési beállítások konfigurálását az eszközökön és a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A **Windows 10 frissítési körök** az Intune használatával konfigurálhatók és kezelhetők. A frissítési körök olyan beállításokat tartalmaznak, amelyek a Windows 10 frissítések telepítésének ütemezését és mikéntjét konfigurálják. Ha például a következő beállításokat lehet megadni:

- **Windows 10 karbantartási csatorna**: Válassza ki a karbantartási csatorna, ahonnan csoportok kapjanak frissítéseket. Az alábbi csatornák érhetők el: 
  - Féléves csatorna
  - Féléves csatorna (célzott)
  - Windows Insider &#8208; gyors
  - Windows Insider &#8208; lassú
  - A Windows Insider kiadása 
      
  További információ az elérhető karbantartási csatornákról: [A Windows mint szoftverszolgáltatás – áttekintés](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels).
- **Halasztási beállítások**: Frissítések telepítése az eszközcsoportokon frissítés halasztó beállítások konfigurálása. Ezzel a beállítással a lépésenkénti frissítési terv alapján a folyamat végig nyomon követhető.
- **Felfüggesztés**: Ha probléma van a frissítési terv, elhalaszthatja a frissítés telepítését. 
- **Karbantartási időszak**: Megadható egy időszak, amelyben a frissítések telepíthetők.
- **Frissítéstípus**: Válassza ki a típusú frissítések települjenek. Ezek lehetnek például a minőségi frissítések, funkciófrissítések vagy illesztőprogramok.
- **Telepítési viselkedésmód**: Úgy konfigurálja, hogyan telepíti a frissítést. Például meghatározható, hogy automatikusan újrainduljon-e az eszköz a frissítés után.
- **Megosztott letöltés**: Úgy dönt, hogy konfigurálható a letöltések megosztása. Ezzel a beállítással, miután egy eszköz végzett egy frissítés letöltésével, a többi eszköz már erről az eszközről tölti le a frissítést. A letöltés folyamata ezáltal felgyorsul.

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

    Ezt a beállítást konfigurálhatja manuálisan, vagy használhat Intune-profilt a Windows 10-es és újabb verziókhoz (**Eszközkorlátozások** > **Jelentéskészítés és telemetria** > adja meg a **Használati adatok megosztása** beállításaként a legalább **Alapszintű** lehetőséget). Az eszközprofilokról további információt nyújt az [Eszközkorlátozási beállítások konfigurálása](device-restrictions-configure.md) című témakör.

- A klasszikus Azure-portál néhány egyéb Windows 10-frissítési beállítást is tartalmaz az eszközkonfigurációs profilban. Amennyiben ezen beállítások bármelyike már konfigurálva van az Azure Portalra való migráláskor, erősen ajánlott a következő lépések végrehajtása:

  1. Hozzon létre Windows 10 frissítési köröket az Azure Portalon a kívánt beállításokkal. Az **Előzetes funkciók engedélyezése** beállítást az Azure Portal nem támogatja, mert az már nem alkalmazható a legújabb Windows 10 buildekre. A frissítési körök létrehozásakor megadhatja a további beállításokat és más Windows 10-es frissítési beállításokat is.

   > [!NOTE]
   > A klasszikus portálon megadott Windows 10-frissítési beállítások nem jelennek meg az Azure Portalon az áttelepítés után. Ezek a beállítások azonban érvénybe lépnek. Ha a beállítások bármelyikét migrálja, majd módosítja az áttelepített szabályzatot az Azure Portalon, akkor ezek a beállítások törlődnek a szabályzatból.

  2. Törölje a frissítési beállításokat a klasszikus portálon. Az Azure Portalra történő migrálás és az azonos beállításoknak egy frissítési körben történő megadása után az esetleges szabályzatütközések elkerülése érdekében törölje a beállításokat a klasszikus portálon. Ha például ugyanazt a beállítást különböző értékekkel konfigurálja, ütközés alakul ki. Ezt nem könnyű megállapítani, mert a klasszikus portálon konfigurált beállítás nincs az Azure Portalon.

## <a name="create-and-assign-update-rings"></a>Frissítési körök létrehozása és hozzárendelése

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** elemre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
2. Válassza a **Szoftverfrissítések** > **Windows 10-es frissítési körök** > **Létrehozás** lehetőséget.
3. Adjon meg egy nevet, egy leírást (nem kötelező), majd válassza a **Konfigurálás** lehetőséget.
4. A **Beállítások** területen adja meg az alábbi adatokat:  

   **Beállítások frissítése**  
   - **Karbantartási csatorna**: Állítsa be, amelyen az eszköz megkaphatná a Windows-frissítéseket.
   - **Microsoft-termékfrissítések**: Válassza ki az alkalmazás-frissítéseket keresni a Microsoft Update webhelyről.
   - **Windows-illesztőprogramok**: Ki szeretne zárni a Windows Update-illesztőprogramokat frissítések során.
   - **Minőségi frissítések elhalasztása (nap)**: Adja meg a késleltetni a minőségi frissítések funkciófrissítéseket napok számát. Ezeknek a minőségi frissítéseknek a fogadása a kiadásuktól számítva legfeljebb 30 nappal késleltethető.

     A minőségi frissítések általában meglévő Windows-funkciók javításai és továbbfejlesztései, és rendszerint minden hónap második keddjén jelennek meg. A Windows Update Vállalatoknak szolgáltatáson keresztül érkező minőségi frissítések csak ezeket a frissítéseket tartalmazzák (a „B” kiadást), de a Microsoft bármikor adhat ki más frissítéseket is. Megadhatja, hogy késleltetni szeretné-e a minőségi frissítéseket a Windows Update-en való megjelenésük után, és ha igen, mennyi időre. További információ: [Frissítések telepítése a Vállalati Windows Update használatával](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).

   - **Szolgáltatásfrissítések elhalasztása (nap)**: Adja meg a késleltetni a Funkciófrissítések funkciófrissítéseket napok számát. Ezeknek a funkciófrissítéseknek a fogadása a kiadásuktól számítva legfeljebb 180 nappal késleltethető.

     A funkciófrissítések általában új Windows-funkciókat tartalmaznak. Miután konfigurálta a **Karbantartási csatorna** beállítást, megadhatja, hogy szeretné-e késleltetni a funkciófrissítéseket a Windows Update-en való megjelenésük után, és ha igen, mennyi időre.

     Példa: **Ha a karbantartási csatorna a féléves csatorna (célzott) értékre van beállítva, és a késleltetési idő pedig 30 nap**: Tegyük fel, hogy X funkciófrissítés először a Windows Update, a féléves csatorna (célzott) féléves. Az eszköz csak februárban, 30 nappal később fogadja a frissítést.

     **Ha a karbantartási csatorna a féléves csatorna értékre van beállítva, és a késleltetési idő pedig 30 nap**: Tegyük fel, az X funkciófrissítés először a Windows Update, a féléves csatorna (célzott) féléves. Négy hónappal később, áprilisban az X funkciófrissítés megjelenik a féléves csatornán. Az eszköz 30 nappal annak a féléves csatornán való megjelenése után fogadja a funkciófrissítést, és májusban frissül.  

   **A felhasználói élmény beállításainak**
   
   - **Automatikus frissítés viselkedése**: Válassza ki, hogyan automatikus frissítések települnek, ha az újraindítás vagy újraindítás. További információ:  [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).

     A beállításnak *visszaállítás alapértelmezettre* helyreállítja az eredeti automatikus frissítési beállítások futtató Windows 10-es gépen a *frissítése 2018. október* vagy újabb.  

     - **Automatikus frissítés gyakorisága**: Ha **automatikus telepítés és újraindítás ütemezett időpontban** a frissítési viselkedéshez, majd a beállítás akkor jelenik meg. Ezzel a beállítással ütemezheti a frissítésék telepítését, amelyet hét, nap és időpont szerint adhat meg.

   - **Újraindítási ellenőrzések**: Alapértelmezés szerint engedélyezett. Egy eszköz újraindításakor a rendszer bizonyos ellenőrzéseket végez, például ellenőrzi az aktív felhasználókat, az akkumulátor szintjét, a futó játékokat és más szempontokat. Ha át szeretné ugrani ezeket az ellenőrzéseket az eszközök újraindításakor, válassza a **Kihagyás** lehetőséget.

   - **A felhasználó felfüggesztése Windows-frissítések**: Alapértelmezés szerint engedélyezett. Ezzel a beállítással blokkolhatja vagy engedélyezheti a felhasználók számára történő telepítésének felfüggesztése használja a *beállítások* gépek. 
      
   - **Kézbesítésoptimalizálásos letöltési mód**: Kézbesítésoptimalizálás a Windows 10 frissítési kör szoftverfrissítések alatt részeként már nincs konfigurálva. Kézbesítésoptimalizálás most keresztül az eszköz konfigurációs van beállítva. Azonban a fenti konfiguráció marad a konzolban. Ezeket a korábbi konfigurációkat eltávolíthatja őket szerkesztésével *nincs konfigurálva*, de ezeket más módon nem módosíthatja. Tekintse meg a régi és új-csoportházirend közötti ütközések elkerülése érdekében [helyezheti át meglévő frissítési körök kézbesítésoptimalizálás az](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) és majd helyezze át a beállításokat egy kézbesítési optimalizálás profilhoz. 

5. Ha elkészült, válassza az **OK** lehetőséget. A **Frissítési kör létrehozása** területen válassza a **Létrehozás** lehetőséget.

Az új frissítési kör megjelenik a frissítési körök listájában.

1. A kör hozzárendeléséhez jelölje ki a kört a frissítési körök listájában, majd a <*kör neve*> lapon válassza a **Hozzárendelések** lehetőséget.
2. A következő lapon válassza a **Válassza ki a befoglalandó csoportokat** lehetőséget, majd jelölje ki a csoportokat, amelyekhez hozzá kívánja rendelni ezt a kört.
3. Ha kész, válassza a **Kijelölés** lehetőséget a hozzárendelés befejezéséhez.

## <a name="update-compliance-reporting"></a>Frissítés-megfelelőségi jelentés
A frissítések megfelelőségét áttekintheti az Intune-ban vagy az ingyenesen használható Update Compliance megoldásban.

### <a name="review-update-compliance-in-intune"></a>Frissítés-megfelelőség ellenőrzése az Intune-ban 
<!-- 1352223 --> A szabályzatjelentésekben ellenőrizheti a konfigurált Windows 10-es frissítési körök üzembehelyezési állapotát.

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** elemre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
2. Válassza a **Szoftverfrissítések** > **Áttekintés** lehetőséget. Itt általános információkat találhat minden hozzárendelt frissítési kör állapotáról.
3. Nyissa meg az alábbi jelentések valamelyikét:

   **Minden frissítési körhöz**:  
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen
   2. A **Figyelés** szakaszban válassza a **Frissítési körönkénti telepítési állapot** lehetőséget.

   **Meghatározott frissítési körökhöz**:  
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen válassza ki az áttekinteni kívánt frissítési kört.
   2. Az adott frissítési kör adatainak megtekintéséhez a **Figyelés** szakaszban válasszon az alábbi jelentések közül:
      - **Eszközállapot**
      - **Felhasználó állapota**

### <a name="review-update-compliance-using-oms"></a>Frissítés-megfelelőség ellenőrzése az OMS használatával
A Windows 10-frissítések telepítését egy ingyenes megoldás, az Update Compliance segítségével ellenőrizheti. További információ: [Windows frissítések figyelése az Update Compliance használatával](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Ennek a megoldásnak a használatával kereskedelmi azonosító telepíthető azokra az Intune-nal felügyelt Windows 10 eszközökre, amelyekről frissítés-megfelelőségi jelentést kíván készíteni.

A kereskedelmi azonosítót az Intune-ban egy egyéni szabályzat OMA-URI-beállításaival konfigurálhatja. További információ: [A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-szabályzatbeállítások](custom-settings-windows-10.md).   

A kereskedelmi azonosító konfigurálásához szükséges (kis- és nagybetűket megkülönböztető) OMA-URI elérési út: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Az **OMA-URI beállítások hozzáadása vagy módosítása** alatt például a következő beállítások használhatók:

- **Beállítás neve**: Windows Analytics kereskedelmi azonosító
- **Beállítás leírása**: Kereskedelmi azonosító a Windows Analytics-megoldások konfigurálása
- **OMA-URI** (megkülönbözteti a kis- és nagybetűket): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Adattípus**: Sztring
- **Érték**: <*Használja az OMS munkaterület Windows-telemetria lapján látható GUID értéket*>

![OMA-URI beállítás – Sor szerkesztése](./media/commID-edit.png)

> [!NOTE]
> További információ az MS DM-kiszolgálóról: [DMClient konfigurációs szolgáltató (CSP)](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Frissítések felfüggesztése
A frissítések felfüggesztésétől számítva legfeljebb 35 napig megakadályozható, hogy az eszköz minőségi vagy funkciófrissítéseket fogadjon. A megadott időtartam után a felfüggesztés automatikusan megszűnik, és az eszköz keresni kezdi az alkalmazható Windows-frissítéseket. A keresés után a frissítések ismét felfüggeszthetők.

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** elemre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
2. Válassza a **Szoftverfrissítések** > **Windows 10-es frissítési körök** lehetőséget.
3. A frissítési körök listájában válassza ki a felfüggeszteni kívánt kört, majd a **...** > **Minőségi frissítések felfüggesztése** > vagy **Funkciófrissítések felfüggesztése** lehetőséget a felfüggeszteni kívánt frissítéstípustól függetlenül.

> [!IMPORTANT]
> A felfüggesztési parancsot a kiadása után az eszközök akkor kapják meg, amikor legközelebb bejelentkeznek a szolgáltatásba. Megtörténhet, hogy mielőtt bejelentkeznek, még telepítenek egy ütemezett frissítést.
> Ha az adott eszköz ki van kapcsolva a felfüggesztési parancs kiadásakor, akkor a bekapcsolása után esetleg letölthet és telepíthet ütemezett frissítéseket, mielőtt bejelentkezik az Intune-ba.

## <a name="uninstall-the-latest-from-windows-10-software-updates"></a>A Windows 10 legújabb szoftverfrissítéseinek eltávolítása 
Ha kritikus problémát tapasztal a Windows 10 rendszerű gépein, akkor választhatja az utolsó funkciófrissítés vagy az utolsó minőségi frissítés eltávolítását (vagyis a korábbi verzió visszaállítását). A funkciófrissítések és minőségi frissítések eltávolításának lehetősége csak ahhoz a karbantartási csatornához érhető el, amelyhez az eszköz tartozik. Az eltávolítás aktivál egy szabályzatot, mely visszaállítja az előző frissítést a Windows 10 rendszerű gépein. A funkciófrissítések esetében korlátozhatja 2–60 napra a legújabb verzió eltávolításának lehetőségét. A szoftverfrissítés eltávolítási lehetőségeinek beállításához:

1. Az Intune-ban válassza a **Szoftverfrissítések** lehetőséget.
2. Válassza a **Windows 10-es frissítés körök** lehetőséget, majd válasszon egy meglévő frissítés kört, és végül az **Eltávolítás** elemet.

> [!NOTE]
> Windows 10-es gépeken a minőségi frissítések sikeres visszaállítása után a végfelhasználók számára továbbra is megjelenik a frissítés a **Windows-beállítások** > **Frissítések** > **Frissítési előzmények** területen.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business-támogatás

A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Az automatikus frissítés viselkedése**
- **Microsoft-termékek frissítései**
- **Karbantartási csatorna**: Támogatja a **félévi csatorna** és **féléves csatorna (célzott)** beállításai
