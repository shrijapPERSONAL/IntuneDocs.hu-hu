---
title: "Operációsrendszer-verziók kezelése az Intune-nal"
description: "Megtudhatja, hogyan kezelhetők a különböző platformokon futó operációsrendszer-verziók a Microsoft Intune-nal."
keywords: 
author: dougeby
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 361ef17b-1ee0-4879-b7b1-d678b0787f5a
ms.openlocfilehash: ede4be83b995bbb415184275c34f0e1b4feb4091
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="manage-operating-system-versions-with-intune"></a>Operációsrendszer-verziók kezelése az Intune-nal
A korszerű mobil- és asztali platformokon gyors ütemben követik egymást az operációs rendszerek főbb részeit érintő frissítések, javítások és új kiadások. A Windows platform frissítéseinek és javításainak bevezetése teljes mértékben kezelhető központilag. Más platformok, például az iOS és a Android esetében azonban a végfelhasználóknak is részt kell vennie a folyamatban.  A Microsoft Intune-nal könnyedén kialakíthatja a különböző platformokon futó operációsrendszer-verziók felügyeleti rendszerét.

Az Intune segítséget nyújt az alábbi, gyakran előforduló feladatok kivitelezéséhez: 
- A végfelhasználók eszközein található operációsrendszer-verziók meghatározása
- Szervezeti adatokhoz történő hozzáférés szabályozása az operációs rendszer új kiadásának érvényesítése során
- A szervezet által jóváhagyott legújabb operációsrendszer-verzióra történő áttérés ösztönzése/kötelezővé tétele a végfelhasználók körében
- Egy új operációsrendszer-verzió szervezeti szintű bevezetésének kezelése
  
## <a name="operating-system-version-control-using-intune-mobile-device-management-mdm-enrollment-restrictions"></a>Operációsrendszer-verziók követésének szabályozása az Intune MDM- (mobileszköz-kezelés) regisztráció korlátozásával
Az Intune MDM-regisztráció kapcsán megadható, hogy egy ügyféleszköznek milyen követelményeknek kell megfelelnie ahhoz, hogy regisztrálni lehessen az Intune általi felügyelethez. Így biztosítható, hogy a felhasználók csak a szabályozásoknak megfelelő eszközöket tudjanak regisztrálni, mielőtt hozzáférnek a szervezeti erőforrásokhoz. Az eszközökkel kapcsolatos követelmények között, a legalacsonyabb és legmagasabb verziók számával megadható, hogy a támogatott platformok operációs rendszerének mely verziói engedélyezettek.
 
![Platformkonfigurációkra vonatkozó korlátozások panelje](./media/os-version-platform-configurations.png) 
 
### <a name="in-practice"></a>A gyakorlatban
A szervezetek az alábbi beállításokkal szabályozhatják, hogy a különböző típusú eszközöknek milyen követelményeknek kell megfelelnie ahhoz, hogy azokról hozzá lehessen férni a szervezeti erőforrásokhoz: 
1. A minimális verziószám megadásával biztosítható, hogy a végfelhasználók a támogatott platformok közül az aktuálisan érvényben lévő verziót használják a szervezeten belül. 
2. Dönthet úgy, hogy a legmagasabb verziószámot nem adja meg (nem korlátozza), vagy megadhatja a szervezetben utoljára érvényesített verzió számát maximumként, időt hagyva az új operációsrendszer-verziók belső tesztelésére.

Ha a fentiekkel kapcsolatban további információkra van szüksége, olvassa át a [Típus szerinti korlátozás beállításának](https://docs.microsoft.com/en-us/intune/enrollment-restrictions-set#set-device-type-restrictions) leírását.
 
## <a name="operating-system-version-reporting-and-compliance-with-intune-mdm-device-compliance-policies"></a>Az operációsrendszer-verziók jelentése és megfelelőségük ellenőrzése Intune MDM eszközmegfelelőségi szabályzatokkal
Az Intune MDM eszközmegfelelőségi szabályzatai a következő feladatok végrehajtásához biztosítanak eszközöket: 
- Megfelelőségi szabályok meghatározása
- Megfelelőségi állapot megtekintése jelentéskészítéssel
- Megfelelőség hiányának kezelése az eszköz karanténba helyezésével és feltételes hozzáférés kikötésével

Hasonlóan ahhoz, ahogy a regisztrációs korlátozásoknál, a megfelelőségi szabályok között is megadható a legalacsonyabb és legmagasabb támogatott operációsrendszer-verzió. Az szabályzatokhoz ezenkívül határidők is definiálhatók, türelmi időt biztosítva a felhasználóknak arra, hogy gondoskodjanak eszközük megfelelőségéről. Az eszközmegfelelőségi szabályzatok segítenek elérni azt, hogy a végfelhasználók eszközei megfeleljenek a szervezeti szabályozásoknak.

![Eszközmegfelelőség – műveletek nem megfelelő eszközök észlelése esetén](./media/os-version-actions-noncompliance.png) 

### <a name="in-practice"></a>A gyakorlatban
Az eszközmegfelelési szabályzatok ugyanazokban az esetekben használhatók jól, mint a regisztrációs korlátozások. Ezek a szabályzatok segítenek elérni azt, hogy a szervezet felhasználói az operációs rendszerek aktuálisan érvényesített verzióit használják. Feltételes hozzáférés definiálásával megadható például, hogy ha egy adott végfelhasználói eszköz nem felel meg a szabályozásoknak, arról az eszközről ne lehessen elérni a szervezeti erőforrásokat, amíg felhasználója nem gondoskodik az operációs rendszer szervezeten belül támogatott verziójának telepítéséről. A felhasználókat a rendszer értesíti a megfelelőség hiányáról és arról, hogy milyen lépéseket kell tenniük annak érdekében, hogy ismét hozzáférjenek az erőforrásokhoz.   

Ha a fentiekkel kapcsolatban további információkra van szüksége, olvassa át az [Eszközmegfelelőségi szabályzatok – első lépések](https://docs.microsoft.com/en-us/intune/device-compliance-get-started) című témát.
 
## <a name="operating-system-version-controls-using-intune-app-protection-policies"></a>Operációsrendszer-verziók követése az Intune alkalmazásvédelmi szabályzataival    
Az Intune alkalmazásvédelmi szabályzataival és mobilalkalmazás-kezelési (MAM) beállításaival az alkalmazás szintjén adható meg, hogy minimálisan melyik operációrendszer-verzió szükséges. Így felhívhatja végfelhasználói figyelmét a megfelelőség hiányára, és ösztönözheti őket operációs rendszerük legalább ezen verzióra történő frissítésére.
 
Két lehetőség van: 

|Figyelmeztetés  |Letiltás  |
|---------|---------|
|Ha a végfelhasználó alkalmazásvédelmi szabályzattal vagy MAM hozzáférési beállítással védett alkalmazást nyit meg olyan eszközön, amelyen a megadottnál alacsonyabb számú operációsrendszer-verzió fut, a rendszer figyelmezteti, hogy frissítenie kell. Az alkalmazás adatait és a szervezeti adatokat ettől függetlenül el fogja tudni érni.|Letiltás esetén, ha a végfelhasználó alkalmazásvédelmi szabályzattal vagy MAM hozzáférési beállítással védett alkalmazást nyit meg olyan eszközön, amelyen a megadottnál alacsonyabb számú operációsrendszer-verzió fut, a rendszer figyelmezteti, hogy frissítenie kell. Az alkalmazásadatokat és a szervezeti adatokat nem fogja tudni elérni.|
|![Az Android frissítésére figyelmeztető párbeszédpanel](./media/os-version-update-warning.png)    |![Az alkalmazás használatának letiltásáról tájékoztató párbeszédpanel](./media/os-version-access-blocked.png)          |

 
### <a name="in-practice"></a>A gyakorlatban
Az alkalmazásvédelmi szabályzatokat legtöbbször akkor használják a különböző szervezetek, ha az alkalmazások nyitottak, vagy ha szeretnék elérni, hogy a végfelhasználók mindig az alkalmazások aktuális verzióját használják. Gyakran alkalmazott konfiguráció például, hogy a végfelhasználókat figyelmezteti a rendszer, ha az aktuálisnál eggyel korábbi verziót használnak, és letiltja, ha kettővel korábbi verziót.
 
Ha a fentiekkel kapcsolatban további információkra van szüksége, tekintse át az [Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése](https://docs.microsoft.com/intune/app-protection-policies) című cikket.

## <a name="managing-a-new-operating-system-version-rollout"></a>Új operációsrendszer-verzió bevezetésének kezelése
Az ebben a cikkben bemutatott Intune-funkciók segítséget nyújtanak ahhoz, hogy a szervezet áttérjen az operációs rendszer újabb verziójának használatára megadott időkereten belül. Az alábbi lépések a v1 operációs rendszerről a v2 operációs rendszerre 7 nap alatt történő áttérést modellezik.
- **1. lépés**: A regisztrációs korlátozások között adja meg az operációs rendszer v2 verzióját a regisztrációhoz szükséges minimális verzióként. Így gondoskodhat arról, hogy az újonnan regisztrált végfelhasználói eszközök megfeleljenek a szabályozásoknak.
- **2/a. lépés**: Az Intune alkalmazásvédelmi szabályzatait használva állítsa be, hogy az alkalmazás megnyitásakor illetve újraindításakor a rendszer figyelmeztesse a végfelhasználókat arra, hogy az operációs rendszer v2-es verzióját kell használniuk.
- **2/b. lépés**. Az eszközmegfelelőségi szabályzatoknál adja meg, hogy az eszközök megfelelőségéhez legalább az operációs rendszer v2-es verziója szükséges. A **Meg nem felelés esetén végrehajtandó műveletek** lehetőségnél adjon meg 7 napos türelmi időszakot és határozza meg olyan e-mail értesítés küldését, amely tartalmazza a határidőt és a követelményeket.
  -  Ezeknek a szabályzatoknak a megadása esetén a rendszer e-mailben, az Intune céges portálon keresztül, alkalmazásvédelmi szabályzattal védett alkalmazás esetén pedig az alkalmazás megnyitásakor tájékoztatja a végfelhasználókat arról, hogy frissíteniük kell az eszköz operációs rendszerét.
  - A nem megfelelő felhasználók azonosításához kérheti egy megfelelőségi jelentés készítését a rendszertől. 
- **3/a. lépés**: Intune alkalmazásvédelmi szabályzatait használva határozza meg a felhasználók letiltását arra az esetre, ha olyan eszközzel próbálnak megnyitni vagy újraindítani egy alkalmazást, amelyen nem az operációs rendszer v2 verziója fut.
- **3/b. lépés**: Eszközmegfelelőségi szabályzatokkal adja meg, hogy az eszközök megfelelőségéhez legalább az operációs rendszer v2-es verziója szükséges.
  - Ezeknek a szabályzatoknak a meghatározása esetén az eszközöket frissíteni kell ahhoz, hogy továbbra is el lehessen róluk érni a szervezeti adatokat. A védett szolgáltatások használatát a rendszer letiltja, ha az eszközök nem felelnek meg a megadott feltételeknek. Az alkalmazásvédelmi szabályzatokkal védett alkalmazások használatát a rendszer megnyitásukkor vagy akkor tiltja le, amikor azok megpróbálják elérni a szervezeti adatokat.

## <a name="next-steps"></a>További lépések
A szervezeten belül használt operációsrendszer-verziók felügyeletével kapcsolatban az alábbi témáknál talál további információkat: 

- [Típus szerinti korlátozás beállítása](https://docs.microsoft.com/en-us/intune/enrollment-restrictions-set#set-device-type-restrictions)
- [Eszközmegfelelőségi szabályzatok – első lépések](https://docs.microsoft.com/en-us/intune/device-compliance-get-started)
- [Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése](https://docs.microsoft.com/intune/app-protection-policies)
