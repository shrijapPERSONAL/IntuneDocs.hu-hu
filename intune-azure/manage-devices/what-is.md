---
title: "Eszközök kezelése az Intune-nal"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató az Intune-nal felügyelt eszközök megjelenítéséhez és az eszközökön végrehajtható különféle műveletekhez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 957192c744bf05cd835dfae60b6bb521b8f8b26b
ms.lasthandoff: 03/15/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az **Eszközök** munkafolyamat áttekintést nyújt a felügyelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.

Ezután válassza az alábbiak egyikét:

- **Áttekintés** – Tájékoztatást nyújt a regisztrált eszközökről és az egyes eszközökön futó operációs rendszerekről.
- **Kezelés** – A **Minden eszköz** lehetőséget választva megjelenítheti az összes kezelt eszköz listáját.
    Ha kijelöl egy eszközt a listán, megnyílik az <*eszköznév*> **Áttekintés** panel, amelyen az alábbiak közül választhat:
    - **Áttekintés** – Általános információkat nyújt az eszközről, köztük sok más mellett megadja az eszköz nevét, tulajdonosát, hogy BYOD-eszköz-e, és mikor jelentkezett be legutóbb. 
                
    - **Hardver** – Részletes információkat jelenít meg az eszközről, többek között a szabad tárhelyet, a modell és a gyártó nevét.
    ![Felügyelt eszköz hardverleltára](./media/hardware-inventory.png)
    - **Észlelt alkalmazások** – Felsorolja azokat a telepített alkalmazásokat, amelyeket az Intune az eszközön talált.
    ![Észlelt alkalmazások csomópont](./media/detected-applications.png)
- **Figyelés** – Az **Eszközműveletek** lehetőséget választva megjeleníthetők az eszközön végrehajtott műveletek és jelenlegi állapotuk.
![Eszközműveletek figyelése](./media/monitor-device-actions.png)
- **Súgó és támogatás** – a hibaelhárítási és a támogatási dokumentációra mutató hivatkozásokat jeleníti meg.

## <a name="available-device-actions"></a>Elérhető eszközműveletek

Ezenkívül a következő műveletek is végrehajthatók távolról az eszközön (nem minden eszközplatform támogatja az összes műveletet):

### <a name="remove-company-data"></a>**Céges adatok eltávolítása**
Csak az Intune által kezelt céges adatokat távolítja el. Személyes adatokat nem távolít el az eszközről. Az eszköz a továbbiakban nem áll az Intune felügyelete alatt, és nem fér hozzá a vállalati erőforrásokhoz (nem támogatott az Azure Active Directory szolgáltatáshoz csatlakoztatott Windows-eszközökön).

### <a name="factory-reset"></a>**Gyári beállítások visszaállítása**
Visszaállítja az eszköz alapbeállításait. Az eszközt a továbbiakban nem kezeli az Intune, és a vállalati és személyes adatok is törlődnek róla. Ez a művelet nem vonható vissza.

### <a name="remote-lock"></a>**Távoli zárolás**
Zárolja az eszközt. Az eszköz zárolását a PIN-kódjával vagy jelszavával kell feloldania a tulajdonosnak. Csak olyan eszköz zárolható távolról, amelyhez PIN-kód vagy jelszó van megadva.

### <a name="reset-passcode"></a>**Új PIN-kód**
Új PIN-kódot generál az eszközhöz. A kód az <*eszköznév*> **Áttekintés** panelen jelenik meg.

### <a name="bypass-activation-lock"></a>**Az aktiválási zár megkerülése**
A felhasználó Apple ID azonosítója és jelszava nélkül távolítja el az aktiválási zárat az iOS-eszközről. Az aktiválási zár megkerülése után az eszköz ismét bekapcsolja az aktiválási zárat a Find My iPhone alkalmazás elindulásakor. Csak akkor kerülje meg az aktiválási zárat, ha fizikailag is hozzáfér az eszközhöz.

### <a name="lost-mode"></a>**Elveszett eszköz mód**
Ha az iOS-eszköz elveszik vagy ellopják, lehetőség van az Elveszett eszköz mód aktiválására. Ilyenkor megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén. Tegye a következőt:
1.    Az iOS-eszköz tulajdonságainak panelén válassza az **Egyebek** > **Elveszett eszköz mód** elemet.
2.    Az **Elveszett eszköz mód** panelen engedélyezze a módot, majd írja be a megjelenítendő üzenetet, és szükség esetén adjon meg egy kapcsolattartói telefonszámot is.
3.    Kattintson az **OK**gombra.
Az Elveszett eszköz mód engedélyezésével teljesen letiltja az eszköz használatát. A végfelhasználó az Elveszett eszköz mód kikapcsolásáig nem tud hozzáférni az eszközhöz. Ha az Elveszett eszköz mód engedélyezve van, az **Eszköz megkeresése** művelet használatával derítheti ki, hogy merre található az eszköz.

### <a name="locate-device"></a>**Eszköz megkeresése**
Ennek a távoli műveletnek a használatával jelenítheti meg az elveszett vagy ellopott iOS-eszköz helyét a térképen. Az eszköz csak felügyelt módban lévő céges iOS-eszköz lehet. A művelet használata előtt az eszközt Elveszett eszköz módba kell állítani.
1.    Az iOS-eszköz tulajdonságainak panelén válassza az **Egyebek** > **Eszköz megkeresése** elemet.
2.    Miután a rendszer megtalálta az eszközt, megjeleníti annak helyét az **Eszköz megkeresése** panelen. 
    ![Eszköz megkeresése panel](./media/locate-device.png)

### <a name="restart"></a>**Újraindítás**
Kiváltja az eszköz újraindulását. Az eszköz tulajdonosa nem kap automatikus értesítést az újraindításról, ezért a munkája elveszhet.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Az Elveszett eszköz módhoz és az eszközkeresési műveletekhez tartozó biztonsági és adatvédelmi tudnivalók
- A művelet elindításáig a rendszer semmilyen információt nem küld az Intune-nak az eszköz helyéről.
- Az eszközkeresési művelet használatakor a rendszer az eszköz szélességi és hosszúsági koordinátáit küldi el az Intune-nak, és ezeket az adatokat jeleníti meg az Azure Portalon.
- A rendszer 24 óráig tárolja az adatokat, majd törli azokat. A helyadatokat manuálisan nem lehet eltávolítani.
- A helyadatok tároláskor és továbbításkor egyaránt titkosítva vannak.
- Az Elveszett eszköz mód konfigurálásakor ajánlott feltüntetni a zárolási képernyőn megjelenő üzenetben, hogy az eszköz helye meghatározható.

