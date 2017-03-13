---
title: "Eszközök kezelése az Intune-nal"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikkből elsajátíthatja az Intune-nal kezelt eszközök megjelenítését és rajtuk különféle műveletek végrehajtását."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d5d7b87f58604b93ba3b65d5d264a0a5e3743d45
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az **Eszközök és csoportok** munkafolyamat áttekintést nyújt a kezelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + Felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök és csoportok** lehetőséget.

    ![Eszközök és csoportok munkafolyamat](./media/devices-and-groups-workload.png)

Ezután válassza az alábbiak egyikét:

- **Áttekintés** – Tájékoztatást nyújt a regisztrált eszközökről és az egyes eszközökön futó operációs rendszerekről.
- **Kezelés** – A **Minden eszköz** lehetőséget választva megjelenítheti az összes kezelt eszköz listáját.
    Ha kijelöl egy eszközt a listán, megnyílik az <*eszköznév*> **Áttekintés** panel, amelyen az alábbiak közül választhat:
    - **Áttekintés** – Általános információkat nyújt az eszközről, köztük sok más mellett megadja az eszköz nevét, tulajdonosát, hogy BYOD-eszköz-e, és mikor jelentkezett be legutóbb. Ezenkívül a következő műveletek is végrehajthatók távolról az eszközön (nem minden eszközplatform támogatja az összes műveletet):
        - **Vállalati adatok eltávolítása** – Csak az Intune által kezelt vállalati adatokat távolítja el. Személyes adatokat nem távolít el az eszközről. Az eszköz a továbbiakban nem áll az Intune felügyelete alatt, és nem fér hozzá a vállalati erőforrásokhoz (nem támogatott az Azure Active Directory szolgáltatáshoz csatlakoztatott Windows-eszközökön).
        - **Gyári beállítások visszaállítása** – Visszaállítja az eszköz alapbeállításait. Az eszközt a továbbiakban nem kezeli az Intune, és a vállalati és személyes adatok is törlődnek róla. Ez a művelet nem vonható vissza.
        - **Távoli zárolás** – Zárolja az eszközt. Az eszköz zárolását a PIN-kódjával vagy jelszavával kell feloldania a tulajdonosnak. Csak olyan eszköz zárolható távolról, amelyhez PIN-kód vagy jelszó van megadva.
        - **Új PIN-kód** – új PIN-kódot generál az eszközhöz. A kód az <*eszköznév*> **Áttekintés** panelen jelenik meg.
        - **Aktiválási zár megkerülése** – A felhasználó Apple azonosítója és jelszava nélkül távolítja el az aktiválási zárat az iOS-eszközről. Az aktiválási zár megkerülése után az eszköz ismét bekapcsolja az aktiválási zárat a Find My iPhone alkalmazás elindulásakor. Csak akkor kerülje meg az aktiválási zárat, ha fizikailag is hozzáfér az eszközhöz.
        - **Elveszett eszköz mód** – Ha az eszközt ellopják, aktiválható az elveszett eszköz üzemmód. Ilyenkor megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén.
        - **Újraindítás** – Kiváltja az eszköz újraindulását. Az eszköz tulajdonosa nem kap automatikus értesítést az újraindításról, ezért a munkája elveszhet.
        ![Az eszköz áttekintése](http://i.imgur.com/4Rx4VXm.png)
        
    - **Hardver** – Részletes információkat jelenít meg az eszközről, többek között a szabad tárhelyet, a modell és a gyártó nevét.
    ![Felügyelt eszköz hardverleltára](./media/hardware-inventory.png)
    - **Észlelt alkalmazások** – Felsorolja azokat a telepített alkalmazásokat, amelyeket az Intune az eszközön talált.
    ![Észlelt alkalmazások csomópont](./media/detected-applications.png)
- **Figyelés** – Az **Eszközműveletek** lehetőséget választva megjeleníthetők az eszközön végrehajtott műveletek és jelenlegi állapotuk.
![Eszközműveletek figyelése](./media/monitor-device-actions.png)

