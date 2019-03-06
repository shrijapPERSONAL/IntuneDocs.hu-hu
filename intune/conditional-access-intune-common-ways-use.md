---
title: Feltételes hozzáférési forgatókönyvek |} A Microsoft Intune-ban
description: A cikk azt ismerteti, hogyan használható az Intune feltételes hozzáférése az eszköz- és alkalmazásalapú feltételes hozzáféréshez.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 46b2dbf31d5813a646fc2ea1a97f7ba273c3c6e9
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394348"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Mik a feltételes hozzáférés használatának szokásos módjai az Intune-ban?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-ban kétféle feltételes hozzáférés létezik: eszközalapú és alkalmazásalapú feltételes hozzáférés. A feltételes hozzáférés megfelelőségének a szervezetben való engedélyezéséhez konfigurálnia kell a kapcsolódó megfelelőségi szabályzatokat. A feltételes hozzáférés gyakori használati formái a helyszíni Exchange-hozzáférés engedélyezése vagy letiltása, a hálózati hozzáférés vezérlése vagy egy Mobile Threat Defense-megoldással való integráció.

Az alábbi információ segítségével megismerheti az Intune *mobileszköz*-megfelelőségi és a *mobilalkalmazás*-kezelési funkcióit. 

> [!NOTE]
> A feltételes hozzáférés az Azure Active Directory egyik lehetősége, amelyet a prémium szintű Azure Active Directory-licencek biztosítanak. Az Intune ezt a lehetőséget mobileszköz-megfelelőségi és mobilalkalmazás-felügyeleti megoldások hozzáadásával bővíti tovább. Az *Intune-ból* elérhető feltételes hozzáférési csomópont ugyanaz a csomópont, amelyet az *Azure AD-ből* is el lehet érni.  

## <a name="device-based-conditional-access"></a>Eszközalapú feltételes hozzáférés

Az Intune és az Azure Active Directory együtt gondoskodik róla, hogy csak felügyelt és megfelelő eszközök férhessenek hozzá az e-mailekhez, az Office 365-szolgáltatásokhoz, a szolgáltatott szoftverként (SaaS) használt alkalmazásokhoz és a [helyszíni alkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Ezenkívül olyan szabályzatot is beállíthat az Azure Active Directoryban, amely az Office 365-szolgáltatásokhoz való hozzáférést csak tartományhoz csatlakozó számítógépek vagy az Intune-ban regisztrált mobileszközök számára engedélyezi.

Az Intune biztosítja az eszközök megfelelőségi állapotát értékelő eszközmegfelelőségi szabályzatokat. A rendszer jelenti a megfelelőségi állapotot az Azure Active Directorynak, amely azon szabályzat érvényre juttatásához fogja azt használni, amely akkor jön létre az Azure Active Directoryban, amikor a felhasználó kísérletet tesz a céges erőforrások elérésére.

Az Exchange Online és más Office 365-termékek eszközalapú feltételes hozzáférési szabályzatainak konfigurálása az [Azure Portalon](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) keresztül történik.
-   Tudjon meg többet [szükséges felügyelt eszközök feltételes hozzáféréssel az Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/require-managed-devices).

-   További információ az [Intune eszközmegfelelőségéről](device-compliance.md).

-   Tudjon meg többet [támogatott böngészők a feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/technical-reference#supported-browsers).

> [!NOTE]
> Az Android-eszközökön, amikor az eszköz alapú hozzáférés engedélyezi a Sharepoint online-hoz vagy a böngésző alapú hozzáférés Exchange Online-felhasználók engedélyeznie kell a **böngészőalapú hozzáférés engedélyezése** lehetőség a regisztrált eszköz a következőképpen:
> 1. Nyissa meg a **Vállalati portál alkalmazást**.
> 2. Nyissa meg a **Beállítások** lapot a három ponttal (...) vagy a hardveres menügombbal.
> 3. Kattintson a **Böngészőalapú hozzáférés engedélyezése** gombra. 
> 4. A Chrome böngészőben jelentkezzen ki az Office 365-ből, majd indítsa újra a Chrome-ot.

### <a name="conditional-access-for-exchange-on-premises"></a>Feltételes hozzáférés a helyszíni Exchange-hez

A feltételes hozzáférés használatával az eszközfelügyeleti szabályzatok és az eszközregisztráció állapota alapján engedélyezhető, illetve tiltható a hozzáférés a **helyszíni Exchange-hez**. A feltételes hozzáférés és az eszközmegfelelőségi szabályzat együttes alkalmazásával elérheti, hogy csak megfelelő eszközök férhessenek hozzá a helyszíni Exchange-hez.

A részletesebb vezérléshez speciális feltételes hozzáférési beállításokat is megadhat, például:

-   Egyes platformok engedélyezése vagy letiltása.

-   Az Intune által nem felügyelt eszközök azonnali letiltása.

Az eszközmegfelelőségi és feltételes hozzáférési szabályzatok alkalmazása esetén a rendszer ellenőrzi a helyszíni Exchange elérésére használt összes eszköz megfelelőségét.

Ha egy eszköz nem tesz eleget az adott feltételeknek, a rendszer végigvezeti a felhasználót az eszközregisztráció lépésein, hogy megszűnjön az eszköz megfelelőségét akadályozó probléma.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>A feltételes hozzáférés működése helyszíni Exchange esetén

Az Intune Exchange Connector lekéri az Exchange-kiszolgálón lévő összes Exchange Active Sync- (EAS-) rekordot, amelyeket az Intune átvesz, és megfeleltet az Intune-eszközrekordoknak. Ezek a rekordok az Intune által regisztrált és felismert eszközöknek felelnek meg. A folyamat engedélyezi vagy tiltja a hozzáférést az e-mailekhez.

Ha az EAS-rekord olyan friss, hogy az Intune még nem ismeri fel, az Intune kiad egy olyan parancsmagot, amely letiltja az e-mailekhez való hozzáférést. Az alábbi ábrán részletesen látható a folyamat:

![Folyamatábra: Feltételes hozzáférés helyszíni Exchange esetén](./media/ca-intune-common-ways-1.png)

1.  A felhasználó megkísérel hozzáférni a helyszíni Exchange 2010 SP1-es vagy későbbi verziójában tárolt céges e-mailekhez.

2.  Ha az Intune által nem felügyelt eszközt használ, a rendszer letiltja az eszköz e-mail-hozzáférését. Az Intune letiltási értesítést küld az EAS-ügyfélnek.

3.  Az EAS megkapja a letiltási értesítést, karanténba helyezi az eszközt, majd karanténüzenetet küld a korrekciós lépésekkel és azon hivatkozásokkal, amelyekkel a felhasználó regisztrálhatja az eszközt.

4.  A munkahelyi csatlakozás létrejöttével megtörténik az első lépés ahhoz, hogy az eszköz az Intune felügyelete alá kerüljön.

5.  A rendszer regisztrálja az eszközt az Intune-ban.

6.  Az Intune egy eszközrekordba képezi le az EAS-rekordot, és menti az eszközmegfelelőségi állapotot.

7.  Az eszközök Azure AD-beli regisztrációjának folyamata során a rendszer regisztrálja az EAS-es ügyfél-azonosítót, ami kapcsolatot létesít az Intune-eszközrekord és az EAS-es ügyfél-azonosító között.

8.  Az eszközök Azure AD-beli regisztrációja menti az eszköz állapotadatait.

9.  Ha a felhasználó teljesíti a feltételes hozzáférési szabályzatok feltételeit, az Intune parancsmagot ad ki az Intune Exchange Connectoron keresztül, amely lehetővé teszi a postaláda szinkronizálását.

10. Az Exchange-kiszolgáló elküldi az értesítést az EAS-ügyfélhez, hogy a felhasználó hozzáférhessen az e-mailjeihez.

#### <a name="whats-the-intune-role"></a>Mi az Intune szerepe?

Az Intune kiértékeli és felügyeli az eszköz állapotát.

#### <a name="whats-the-exchange-server-role"></a>Mi az Exchange-kiszolgáló szerepe?

Az Exchange-kiszolgáló biztosítja az API-t és az infrastruktúrát az eszközök karanténba helyezéséhez.

> [!IMPORTANT]
> Ne feledje, hogy az eszközmegfelelőség értékeléséhez az eszköz felhasználójának rendelkeznie kell egy hozzárendelt megfelelőségi profillal. Amennyiben a felhasználóra nem vonatkozik megfelelőségi szabályzat, a rendszer megfelelőként kezeli az eszközt, és egyáltalán nem korlátozza a hozzáférést.

### <a name="conditional-access-based-on-network-access-control"></a>Hálózati hozzáférés-vezérlésen alapuló feltételes hozzáférés

Az Intune-nak számos integrált partnere van (köztük a Cisco ISE, az Aruba Clear Pass és a Citrix NetScaler), amelyek segítségével biztosítja az Intune-regisztráción és az eszközmegfelelőségi állapoton alapuló hozzáférés-vezérlést.

A rendszer attól függően engedélyezheti vagy tilthatja a felhasználók hozzáférését a céges Wi-Fi-hez vagy VPN-erőforrásokhoz, hogy az eszközüket felügyelik-e az Intune eszközmegfelelőségi szabályzatai, illetve az eszköz megfelel-e azoknak.

-   További tudnivalókért lásd: [Hálózati hozzáférés-vezérlés (NAC) integrációja az Intune-nal](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Eszközkockázaton alapuló feltételes hozzáférés

Az Intune partneri megállapodást kötött a Mobile Threat Defense forgalmazóival. Ez a szolgáltatás biztonsági megoldást nyújt a mobileszközöket veszélyeztető kártevők, trójai vírusok és egyéb fenyegetések észleléséhez.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Hogyan működik az Intune és a Mobile Threat Defense integrációja?

Ha a mobileszközökön telepítve van a Mobile Threat Defense ügynöke, az ügynök megfelelőségiállapot-üzenetekben jelentheti az Intune-nak, hogy fenyegetés jelent meg az eszközön.

Az Intune és a Mobile Threat Defense integrációja fontos szerepet játszik az eszközkockázat alapján hozott feltételes hozzáférési döntésekben.

-   További tudnivalók: [Intune Mobile Threat Defense](mobile-threat-defense.md).

### <a name="conditional-access-for-windows-pcs"></a>Feltételes hozzáférés Windows rendszerű számítógépeken

Az asztali számítógépeken ken beállítható feltételes hozzáférés a mobileszközökhöz hasonló lehetőségeket biztosít. Ez a szakasz a feltételes hozzáférés Intune által felügyelt Windows rendszerű gépeken alkalmazható módjait tekinti át.

#### <a name="corporate-owned"></a>Céges tulajdonú eszközök

-   **A helyszíni AD-tartományhoz csatlakoztatott:** Ezt a beállítást gyakran használják szervezetek számára, akik ésszerűen magabiztosan hogyan azok már kezelése számítógépükön keresztül AD-csoportházirendekkel és/vagy a System Center Configuration Manager használ.

-   **Az Azure AD tartományhoz csatlakoztatott és Intune-felügyelet:** Ebben a forgatókönyvben általában szoftverfejlesztőknek válassza ki a saját eszköz (CYOD), és ahol ezek az eszközök csak ritkán csatlakoznak a vállalati hálózathoz laptophordozásos forgatókönyvekhez. Az eszköz az Azure AD-hoz csatlakozik, és az Intune-ban regisztrálják, ami eltávolít minden, a helyszíni AD-tól és tartományvezérlőktől való függőséget. A céges erőforrások kezelésekor ez lehet a feltételes hozzáférés feltétele.

-   **AD tartományhoz csatlakoztatott és a System Center Configuration Managerben:** Kezdődően az aktuális fejlesztési ágban, System Center Configuration Manager feltételes hozzáférési képességeket biztosít, amelyek adott megfelelőségi feltételek egy tartományhoz csatlakoztatott Számítógépről is képes kiértékelni:

    -   Titkosították-e a számítógépet?

    -   Telepítve van-e rajta kártevő szoftver? Frissítették az eszközt?

    -   Jailbreakelték vagy rootolták az eszközt?

#### <a name="bring-your-own-device-byod"></a>Saját eszközök használata (BYOD)

-   **Munkahelyi csatlakozás és Intune-felügyelet:** Itt a felhasználó csatlakozhat személyes eszközeik vállalati erőforrások és szolgáltatások eléréséhez. A munkahelyi csatlakozás használatával, és az eszközök regisztrálása az Intune MDM-ben fogadásához eszközszintű szabályzatokat, amelyek egyben egy másik lehetőség a feltételes hozzáférés feltételeinek értékeléséhez.

Tudjon meg többet [az Eszközfelügyelet az Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/devices/overview).

## <a name="app-based-conditional-access"></a>Alkalmazásalapú feltételes hozzáférés

Az Intune és az Azure Active Directory együtt biztosítja, hogy csak felügyelt alkalmazások férhessenek hozzá a céges e-mailekhez vagy más Office 365-szolgáltatásokhoz.

-   További tudnivalók: [Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md).

## <a name="next-steps"></a>További lépések

[Feltételes hozzáférés konfigurálása az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Helyszíni Exchange Connector telepítése az Intune-nal](https://docs.microsoft.com/intune/exchange-connector-install).

[Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez](conditional-access-exchange-create.md)
