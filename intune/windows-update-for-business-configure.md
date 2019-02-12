---
title: A Windows Update Vállalatoknak konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: A profilok szoftverfrissítési beállításainak frissítésével frissítési kört hozhat létre, áttekintheti a megfelelőséget, és szüneteltetheti a Windows Update Vállalatoknak frissítéseit a Microsoft Intune Windows 10-es eszközökön való használatával.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e89c1916c1096923b555bdf9c532d14b829f806
ms.sourcegitcommit: e262b0ad8df610e25eb9421b9ebc2673bcf1020e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2019
ms.locfileid: "55986858"
---
# <a name="manage-software-updates-in-intune"></a>Szoftverfrissítések kezelése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune adja meg, hogyan és mikor a Windows mint szoftverszolgáltatás frissíti a Windows 10 rendszerű eszközök frissítési körök meghatározásához. Frissítési körök szabályzatok, a hozzárendelt eszközök csoportjait. Frissítési körök használatával kialakítható az üzleti igényeknek leginkább megfelelő frissítési stratégia. További információ: [Frissítések kezelése a Vállalati Windows Update használatával](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

A Windows 10-ben az új funkció- és minőségi frissítések magukban foglalják valamennyi korábbi frissítés tartalmát. Így a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 rendszerű eszközök naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.


A Windows Update Vállalatoknak használatával leegyszerűsítheti a frissítéskezelést. Nem kell jóváhagynia az eszközcsoportok egyes frissítéseit. A környezetek kockázatkezelését egy frissítéskibocsátási stratégia konfigurálásával intézheti. Az Intune lehetővé teszi a [frissítési beállítások konfigurálását](windows-update-settings.md) eszközökön és a frissítések telepítésének késleltetését lehetővé teszi. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A beállítások gyűjteménye, amely konfigurálja a Windows 10-frissítések telepítésekor a get a neve egy *Windows 10 frissítési kör*.

A Windows 10 frissítési körének támogatási [címkék hatókör](scope-tags.md). Hatókörcímkék használhatja a frissítési körök szűrése, és kezelheti a konfigurációkat, amelyekkel részhalmazához.

## <a name="prerequisites"></a>Előfeltételek  

A következő előfeltételeknek teljesülniük kell a Windows-frissítések használata a Windows 10-es eszközökhöz az Intune-ban.  

- Windows 10 rendszerű számítógépek kell futtatnia, legalább Windows 10 Pro Windows Évfordulós frissítéssel vagy újabb (1607-es vagy újabb verzió)
- Windows Update támogatja az alábbi Windows 10-es verziója esetén:
  - Windows 10
  - Windows 10 Team (Surface Hub-eszközök esetén)
  - Windows Holographic for Business  

    Windows Holographic for Business támogatja a beállítások egy része a Windows-frissítések, például:
    - **Az automatikus frissítés viselkedése**
    - **Microsoft-termékek frissítései**
    - **Karbantartási csatorna**: Támogatja a **félévi csatorna** és **féléves csatorna (célzott)** beállításai  

    További információkért lásd: [Windows Holographic kezelése](windows-holographic-for-business.md)  
  
  A Windows 10 Mobile rendszert futtató eszközök nem támogatottak.

- Windows-eszközön **visszajelzés és diagnosztika** > **diagnosztikai és használati adatok** értékre kell állítani **alapszintű**, **bővített**, vagy **teljes**.  

  Konfigurálhatja ezt a beállítást manuálisan vagy egy Intune eszközkorlátozási profilt a Windows 10-es és újabb verziók használata. Az eszközkorlátozási profilra használatához beállítás konfigurálásával **általános** > **diagnosztikai adatok küldésének** való legalább **alapszintű**. Az eszközprofilokról további információt nyújt az [Eszközkorlátozási beállítások konfigurálása](device-restrictions-configure.md) című témakör.  

- Ha a klasszikus Azure portálon [telepítse át a beállításait az Azure Portalra](#migrate-update-settings-to-the-azure-portal).  

## <a name="create-and-assign-update-rings"></a>Frissítési körök létrehozása és hozzárendelése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **Windows 10-es frissítési körök** > **Létrehozás** lehetőséget.
4. Adjon meg egy nevet, egy leírást (nem kötelező), majd válassza a **Konfigurálás** lehetőséget.
5. A **beállítások**, az üzleti igényeknek megfelelően konfigurálja. Az elérhető beállításokra vonatkozó további információkért lásd: [Windows-beállítások frissítése](windows-update-settings.md).  
6. Ha elkészült, válassza az **OK** lehetőséget. A **Frissítési kör létrehozása** területen válassza a **Létrehozás** lehetőséget. Az új frissítési kör megjelenik a frissítési körök listájában.
7. Rendelje hozzá a kört a frissítési körök listájában válassza ki a kört, majd a a \<kör neve > lapra, majd **hozzárendelések**.
8. Használja a **Belefoglalás** és **kizárása** lapra, adja meg, amely csoportosítja, hogy ezt a kört hozzárendelve, és adja meg **mentése** a hozzárendelés befejezéséhez.

## <a name="manage-your-windows-10-update-rings"></a>A Windows 10-es frissítési körök kezelése
A portálon, válassza ki a Windows 10 frissítési kör megnyitásához a **áttekintése** ablaktáblán. Erről az ablaktábláról a körök hozzárendelés állapota tekintheti meg és kezelheti a kör több műveletet. 
### <a name="to-view-an-updates-rings-overview-pane"></a>A frissítések körök áttekintő panel megjelenítése: 
1. Jelentkezzen be az Azure portálra.
2. Navigáljon a **Intune** > **szoftverfrissítések** > **Windows 10-es frissítési körök**.
3. Válassza ki a megtekinteni vagy kezelni kívánt frissítési kört.  

Hozzárendelés állapotának megtekintése, mellett válassza ki a következő műveletek kezelésére a frissítési körhöz az áttekintő panel tetején:  
- [Törlés](#delete)  
- [Felfüggesztés](#pause)  
- [Folytatása](#resume)  
- [Extend](#extend)  
- [Távolítsa el](#uninstall)  

![Rendelkezésre álló műveletek](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Törlés  
Válassza ki **törlése** leállítani a kiválasztott Windows 10 frissítési kör beállításainak kényszerítése. A konfiguráció egy kör törlése eltávolítja az Intune-ból, úgy, hogy az Intune már nem érvényes, és érvénybe lépteti ezeket a beállításokat.  

Egy kör törlése az Intune-ból nem módosítja a beállításokat a frissítési körhöz kiosztott eszközökön.  Ehelyett az eszköz megőrzi a jelenlegi beállításai. Ez az eszközök nem tartanak, milyen beállításokat korábban helyben korábbi rekord, és mivel az eszköz beállítások további frissítési körök, amelyek aktív marad, előfordulhat, hogy fogadjon.  

#### <a name="to-delete-a-ring"></a>A kör törlése  
1. Az Áttekintés lap megtekintésekor egy frissítési körhöz, válassza ki a **törlése**.  
2. Kattintson az **OK** gombra.  

### <a name="pause"></a>Szünet  
Válassza ki **szüneteltetése** , hogy a hozzárendelt eszközök kezdve akár 35 napig minőségi vagy Funkciófrissítéseket fogadjon a kör felfüggesztése. A megadott időtartam után a felfüggesztés automatikusan megszűnik, és az eszköz keresni kezdi az alkalmazható Windows-frissítéseket. A keresés után a frissítések ismét felfüggeszthetők. Ha folytatja a egy felfüggesztett frissítési kör, és ezután szüneteltetheti a kör újra, a szüneteltetés 35 napon belül időszak alaphelyzetbe.  

 #### <a name="to-pause-a-ring"></a>A kör felfüggesztése  
1. Az Áttekintés lap megtekintésekor egy frissítési körhöz, válassza ki a **szüneteltetése**.  
2. Válassza **funkció** vagy **minőségi** szüneteltetése, hogy a frissítés típusa, és válassza ki a **OK**.  
3. Felfüggesztés után egy frissítési típust, a felfüggesztés újra a frissítés típusa szüneteltetése kiválaszthatja.  

Ha frissítési típust szüneteltetve van, a kör áttekintő panelje jeleníti meg, hány nap van hátra a frissítési írja be a folytatja.

> [!IMPORTANT]  
> Felfüggesztési parancsot a kiadása után eszköz megkapja ezt a parancsot a következő alkalommal, amikor azok jelölje be a szolgáltatásba. Megtörténhet, hogy mielőtt bejelentkeznek, még telepítenek egy ütemezett frissítést. Ha az adott eszköz ki van kapcsolva a felfüggesztési parancs kiadásakor, akkor a bekapcsolása után esetleg letölthet és telepíthet ütemezett frissítéseket, mielőtt bejelentkezik az Intune-ba.

### <a name="resume"></a>Folytatás  
Amíg egy frissítési kör szüneteltetve van, választhatja **folytatása** állíthatja vissza a szolgáltatás- és minőségi frissítések adott körhöz aktív műveletet. Egy frissítési kör folytatása után újra szüneteltetheti a kört.  

#### <a name="to-resume-a-ring"></a>A kör folytatása  
1. Az Áttekintés lap megtekintésekor egy felfüggesztett frissítési körhöz, válassza ki a **folytatása**.  
2. Válasszon az elérhető lehetőségek közül, vagy folytathatja a **funkció** vagy **minőségi** frissítéseket, és válassza ki **OK**.  
3. Egy frissítés típusa folytatás után válassza ki újra a frissítés típusa visszaállítani folytatása.  

### <a name="extend"></a>Kiterjesztése  
Amíg egy frissítési kör szüneteltetve van, választhatja **kiterjesztése** alaphelyzetbe állítani a frissítési körhöz funkció- és minőségi frissítések szüneteltetése időszak 35 napon belül.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>A felfüggesztési időszak egy körhöz bővítése  
1. Az Áttekintés lap megtekintésekor egy felfüggesztett frissítési körhöz, válassza ki a **kiterjesztése**. 
2. Válasszon az elérhető lehetőségek közül, vagy folytathatja a **funkció** vagy **minőségi** frissítéseket, és válassza ki **OK**.  
3. Után egy frissítés típus szüneteltetésének meghosszabbítása, válassza ki újra a frissítés típusa kiterjeszteni kiterjesztése.  

### <a name="uninstall"></a>Eltávolítás  
Az Intune-rendszergazda használhat **Eltávolítás** eltávolítása (visszaállítása) a legújabb *funkció* update vagy a legújabb *minőségi* frissítés egy aktív vagy szüneteltetett frissítési körhöz. Egy típust az Eltávolítás után a második típus majd eltávolíthatja. Az Intune nem támogatja, és kezelheti a felhasználókat abban, frissítések eltávolítása.  

Az eltávolítás sikeres:  
- Egy eszköz futtatnia kell a Windows (verzió 1803) 2018 április 10. frissítés vagy újabb.  

Egy eszköz telepíteni kell a legújabb frissítést. Összegző frissítésekről szó, mert az eszközöket, amelyek a legújabb frissítés telepítésének lesz a legújabb funkció- és minőségi frissítés. Például előfordulhat, hogy használhatja ezt a beállítást, hogy állítsa vissza a legutóbbi frissítés kell tudomására jut a használhatatlanná tévő problémát a Windows 10 rendszerű gépeken.  

Eltávolítás használatakor, vegye figyelembe a következőket:  
- A funkciófrissítések és minőségi frissítések eltávolításának lehetősége csak ahhoz a karbantartási csatornához érhető el, amelyhez az eszköz tartozik.  

- Használatával távolítsa el a szolgáltatás, vagy a minőségi frissítések elindít egy szabályzatot, amely az előző frissítés a Windows 10-es gépekre visszaállítása.  

- A Windows 10-es eszközön után egy minőségi frissítés sikeresen vissza lesz vonva, végfelhasználók továbbra is szerepel a frissítés **Windows beállítások** > **frissíti**  >  **-Előzmények frissítéséhez**.  

- A szolgáltatás kifejezetten szoftverfrissítésekkel, az idő a funkciófrissítés eltávolítása csak 2-60 napos,-e a frissítési körök frissítési beállítás által konfigurált **Set funkciófrissítés-eltávolítási időszak (2 – 60 nap)**. Nem vonható vissza, amely már telepítve van egy eszközön a funkciófrissítés telepítése után a a beállított-eltávolítási időszak hosszabb a funkciófrissítés.  

  Vegyük példaként egy frissítési kör egyik funkciójával frissítési időszakot 20 napra, távolítsa el. 25 nap elteltével úgy dönt, hogy állítsa vissza a legújabb funkciófrissítést, és használja az Eltávolítás lehetőséget.  Eszközök, amelyek telepítették a funkciófrissítés több mint 20 napja nem távolíthatja el, mert azok szükségesek a bits eltávolította a karbantartási részeként. Eszközök, amelyek csak másolatot telepítették a funkciófrissítés 19 nappal ezelőtt azonban eltávolíthatja a frissítést, ha azok sikeresen be, hogy fogadni az eltávolítási parancs meghaladja az Eltávolítás 20 napos időszak előtt.  

További információ a Windows Update-szabályzatok: [frissítési CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) a Windows client management dokumentációjában.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>A legújabb Windows 10-es frissítés eltávolítása  
1. Az Áttekintés lap megtekintésekor egy felfüggesztett frissítési körhöz, válassza ki a **Eltávolítás**.  
2. Válasszon az elérhető lehetőségek közül, vagy távolítsa el a **funkció** vagy **minőségi** frissítéseket, és válassza ki **OK**.  
3. Után elindítása egy frissítés esetén az eltávolítás, kiválaszthatja az Eltávolítás újra, távolítsa el a fennmaradó frissítés típusa.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Frissítési beállítások áttelepítése az Azure Portalon  
A klasszikus Azure-portál néhány egyéb Windows 10-frissítési beállítást is tartalmaz az eszközkonfigurációs profilban. Amennyiben ezen beállítások bármelyike már konfigurálva van az Azure Portalra való migráláskor, erősen ajánlott a következő lépések végrehajtása:  

1. Hozzon létre Windows 10 frissítési köröket az Azure Portalon a kívánt beállításokkal. Az **Előzetes funkciók engedélyezése** beállítást az Azure Portal nem támogatja, mert az már nem alkalmazható a legújabb Windows 10 buildekre. A frissítési körök létrehozásakor megadhatja a másik három beállítást és a további Windows 10 frissítési beállításokat is.  

   > [!NOTE]  
   > A klasszikus portálon megadott Windows 10-frissítési beállítások nem jelennek meg az Azure Portalon az áttelepítés után. Ezek a beállítások azonban érvénybe lépnek. Ha a beállítások bármelyikét migrálja, majd módosítja az áttelepített szabályzatot az Azure Portalon, akkor ezek a beállítások törlődnek a szabályzatból.  

2. Törölje a frissítési beállításokat a klasszikus portálon. Az Azure Portalra történő migrálás és az azonos beállításoknak egy frissítési körben történő megadása után az esetleges szabályzat-ütközések elkerülése érdekében a beállításokat a klasszikus portálon törölni kell. Ha például ugyanazt a beállítást különböző értékekkel konfigurálja, ütközés alakul ki. Egy egyszerű módja annak, hiszen a klasszikus portálon megadott beállítások nem jelennek meg az Azure Portalon nem áll rendelkezésre.  

## <a name="next-steps"></a>További lépések
[Windows Intune által támogatott beállítások frissítése](windows-update-settings.md)  

[Frissítések az Intune megfelelőségi jelentések](windows-update-compliance-reports.md)

