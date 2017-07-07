---
title: "Mobilalkalmazás-kezelési hibaelhárítás"
description: "Ebben a témakörben a feltételes hozzáférést alkalmazó környezetekre vonatkozó hibaelhárítási információkat olvashat."
keywords: 
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.custom: intune-classic
ms.openlocfilehash: dd4b216f04c909321bbf57f4dec5998e48cb490c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="troubleshoot-mobile-application-management"></a>Mobilalkalmazás-kezelési hibaelhárítás

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ha az Intune mobilalkalmazás-kezeléssel kapcsolatos problémába ütközik, először ebben a cikkben próbálja meg megkeresni a megoldást. Ebben a témakörben számos gyakran előforduló problémát és kérdést megtárgyalunk, és ezekre kínálunk megoldásokat és válaszokat.

Ha ezekkel az információkkal nem tudja megoldani a problémát, a [Hogyan kérhet támogatást az Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben talál további részleteket a segítségkéréshez.


## <a name="common-it-administrator-issues"></a>A rendszergazdáknál gyakran előforduló problémák

Ezek olyan gyakori problémák, amelyeket a rendszergazdák tapasztalhatnak az Intune-beli alkalmazásvédelmi szabályzatok használatakor.

| Probléma | Leírás | Megoldás |
| -- | -- | -- |
| A Skype Vállalati verzióra nem vonatkozó szabályzat | Az Azure Portalon beállított, eszközregisztráció nélküli alkalmazásvédelmi szabályzat nem lép életbe az iOS- és Android-eszközökön futó Skype Vállalati verzió alkalmazásra vonatkozóan. | A Skype Vállalati verziót a modern hitelesítésre kell beállítani.  Kövesse a [Bérlő engedélyezése modern hitelesítéshez](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) című részben található utasításokat a modern hitelesítés beállításához Skype-hoz. |
| Nem alkalmazott Office-alkalmazás-szabályzat | Az alkalmazásvédelmi szabályzatok egyetlen felhasználónál sem lépnek életbe a [támogatott Office-alkalmazásokra](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) vonatkozóan. | Ellenőrizze, hogy a felhasználók rendelkeznek-e Intune-licenccel, illetve, hogy a használt alkalmazásvédelmi szabályzat megcélozza-e az Office-alkalmazásokat. Az újonnan beállított alkalmazásvédelmi szabályzatok életbe lépéséhez esetenként 8 órának is el kell telnie. |
| A rendszergazda nem tudja beállítani az alkalmazásvédelmi szabályzatot az Azure Portalon | Az informatikai rendszergazda nem tud alkalmazásvédelmi szabályzatokat konfigurálni az Azure Portalon. | A következő felhasználói szerepkörök rendelkeznek hozzáféréssel az Azure Portalhoz: <ul><li>Globális rendszergazda; ez a szerepkör az [Office-portálon](http://portal.office.com/) állítható be.</li><li>Tulajdonos; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.</li><li>Közreműködő; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.</li></ul>  A szerepkörök beállításával kapcsolatban a [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) című részben talál segítséget.|
|Az alkalmazásvédelmi szabályzat jelentéseiből hiányzó felhasználói fiókok | A felügyeleti konzol jelentéseiben nem szerepelnek azok a felhasználói fiókok, amelyekre a közelmúltban alkalmazták az alkalmazásvédelmi szabályzatot. | Az alkalmazásvédelmi szabályzattal újonnan megcélzott felhasználók esetében előfordul, hogy 24 órának is el kell telnie, hogy a felhasználó megjelenjen a jelentésekben. |
| Nem működő szabályzatváltozások | Az alkalmazásvédelmi szabályzatokat érintő változások és frissítések életbe lépéséhez akár 8 órára is szükség lehet. | Ha alkalmazandó, a végfelhasználó jelentkezzen ki az alkalmazásból, majd jelentkezzen be újra, ezzel kényszerítve a szinkronizálást a szolgáltatással. |
| Az alkalmazásvédelmi szabályzat nem működik a DEP-pel | Az alkalmazásvédelmi szabályzat nem lép érvénybe az Apple DEP-eszközökön. | Győződjön meg róla, hogy használja-e a Felhasználói affinitás funkciót az Apple Eszközregisztrációs programmal (DEP). Felhasználói affinitásra minden olyan alkalmazás esetében szükség van, amely felhasználói hitelesítést igényel DEP alatt. <br><br>Az iOS DEP-regisztrációról bővebben lásd: [Az Eszközregisztrációs program vállalati tulajdonú iOS-eszközeinek regisztrálása](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).|
| Az adatátviteli szabályzat nem működik iOS-szel | A **Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak** és a **Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak** szabályzatok nem tudják kezelni az adatátvitelt az iOS-ben. | Lásd: [iOS-alkalmazások közti adatátvitel felügyelete a Microsoft Intune-nal](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>A végfelhasználóknál előforduló gyakori problémák

A végfelhasználóknál előforduló gyakori problémák a következő kategóriákba sorolhatók:

* **Normál használati forgatókönyvek**: A végfelhasználó ezen forgatókönyvek szerinti problémákat olyan alkalmazásoknál tapasztalhat, amelyek alkalmazásvédelmi szabályzattal rendelkeznek az Intune-ban. Ezek nem tényleges problémákat, de problémának vagy hibáknak tűnhetnek.

* **Normál használati párbeszédpanelek**: Ezeket a használati párbeszédpaneleket a végfelhasználók olyan alkalmazásokban láthatják, amelyek alkalmazásvédelmi szabályzattal rendelkeznek az Intune-ban. Ezeket az üzeneteket és párbeszédpanelek **nem** hibát jeleznek.

* **Hibaüzenetek és párbeszédpanelek**: Ezeket a hibaüzenetek és párbeszédpaneleket a végfelhasználók olyan alkalmazásokban láthatják, amelyek alkalmazásvédelmi szabályzattal rendelkeznek az Intune-ban. Ezek gyakran a rendszergazda által elkövetett hibát jeleznek, vagy az Intune-alkalmazásvédelem hibáját.



### <a name="normal-usage-scenarios"></a>Normál használati forgatókönyvek

Platform | Forgatókönyv | Magyarázat |
---| --- | --- |
iOS | A végfelhasználó az iOS megosztási bővítménnyel megnyithatja a munkahelyi vagy az iskolai adatokat a nem felügyelt alkalmazásokban, még akkor is, ha az adatátviteli szabályzat beállítása **Csak felügyelt alkalmazások** vagy **Nincs alkalmazás**. Nem jár ez adatszivárgással? | Az Intune alkalmazásvédelmi szabályzata nem tudja kezelni az iOS megosztási bővítményt az eszköz felügyelete nélkül. Ezért az **Intune titkosítja a „céges” adatokat, mielőtt az alkalmazáson kívül megosztaná**. Ezt úgy ellenőrizheti, hogy megpróbálja megnyitni a „céges” fájlt a felügyelt alkalmazáson kívüli más alkalmazással. A fájlnak titkosítottnak kell lennie, így nem nyitható meg a felügyelt alkalmazáson kívül mással.
Android | Miért kell a végfelhasználónak akkor is **telepítenie a Céges portál alkalmazást**, ha MAM-alkalmazásvédelmet használok eszközregisztráció nélkül?  | Androidon a legtöbb alkalmazásvédelmi funkció be van építve a Céges portál alkalmazásba. **Annak ellenére, hogy a Céges portál alkalmazás mindig szükséges, eszközregisztrációra nincs szükség**. A regisztráció nélküli alkalmazásvédelemhez a végfelhasználónak telepítenie kell a Céges portál alkalmazást az eszközre.

### <a name="normal-usage-dialogs"></a>Normál használati párbeszédpanelek

Platform | Üzenet vagy párbeszédpanel | Magyarázat |
--- | --- | --- |
iOS, Android | **Bejelentkezés**: Az adatok védelme érdekében a munkahelyének felügyelnie kell ezt az alkalmazást. A művelet befejezéséhez jelentkezzen be a munkahelyi vagy az iskolai fiókjába. | A végfelhasználónak be kell jelentkeznie a munkahelyi vagy az iskolai fiókjába ennek az alkalmazásvédelmi szabályzatot igénylő alkalmazásnak a használatához. Ahhoz, hogy a szabályzat érvénybe lépjen a felhasználónak hitelesítést kell végeznie az Azure Active Directoryban.
iOS, Android |**Újraindítás szükséges**: A munkahelye most már védi az adatait ebben az alkalmazásban. A folytatáshoz újra kell indítania az alkalmazást. | Az alkalmazás épp megkapta az Intune alkalmazásvédelmi szabályzatát, és újra kell indulnia a szabályzat érvénybe léptetéséhez.
iOS, Android |**Nem engedélyezett művelet**: A szervezete csak munkahelyi vagy iskolai adatok megnyitását engedélyezi ebben az alkalmazásban. | A rendszergazda a **Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak** beállításaként a **Csak felügyelt alkalmazások** lehetőséget adta meg. Ezért a végfelhasználó ebbe az alkalmazásba csak alkalmazásvédelmi szabályzattal rendelkező más alkalmazásokból viheti át az adatokat.
iOS, Android |**Nem engedélyezett művelet**: A munkahelye adatait csak felügyelt alkalmazásokba viheti át. | A rendszergazda **Az alkalmazás átadhat adatokat más alkalmazásoknak** beállításaként a **Csak felügyelt alkalmazások** lehetőséget adta meg. Ezért a végfelhasználó ebből az alkalmazásból csak alkalmazásvédelmi szabályzattal rendelkező más alkalmazásokba viheti át az adatokat.
iOS, Android |**Törlési riasztás**: A munkahelye törölte az alkalmazáshoz hozzárendelt adatokat. A folytatáshoz indítsa újra az alkalmazást. | A rendszergazda az Intune alkalmazásvédelmi funkciójával kezdeményezte az alkalmazástörlés.
Android | **Céges portál szükséges**: Csak akkor használhatja a munkahelyi vagy iskolai fiókját ebben az alkalmazásban, ha telepíti az Intune Céges portál alkalmazást. A folytatáshoz koppintson a „Ugrás az Áruházba” gombra. | Androidon a legtöbb alkalmazásvédelmi funkció be van építve a Céges portál alkalmazásba. **Annak ellenére, hogy a Céges portál alkalmazás mindig szükséges, eszközregisztrációra nincs szükség**. A regisztráció nélküli alkalmazásvédelemhez a végfelhasználónak telepítenie kell a Céges portál alkalmazást az eszközre.


### <a name="error-messages-and-dialogs-on-ios"></a>Hibaüzenetek és párbeszédpanelek az iOS-ben


Hibaüzenet vagy párbeszédpanel | Ok | Kockázatcsökkentés |
-- | --- | --- |
**Nincs beállítva az alkalmazás**: Ez az alkalmazás nincs beállítva az Ön általi használatra. Segítségért forduljon a rendszergazdához. | Nem sikerült észlelni az alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. |Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**Üdvözli Önt az Intune Managed Browser**: Ez az alkalmazás akkor működik optimálisan, ha a Microsoft Intune felügyeli. Bármikor böngészheti vele az internetet. Ha az alkalmazást a Microsoft Intune felügyeli, további adatbiztonsági funkciókat is elérhet. | Nem sikerült észlelni az Intune Managed Browser alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. <br><br>A felhasználó ebben az esetben is internetezhet, de az alkalmazást nem az Intune fogja felügyelni. | Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az Intune Managed Browser alkalmazást.
**A bejelentkezés sikertelen**: Nem tudtuk bejelentkeztetni. Próbálkozzon újra később. | Nem sikerült regisztrálni a felhasználót a MAM-szolgáltatásban, miután a felhasználó megpróbált munkahelyi vagy iskolai fiókjával bejelentkezni. | Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**A fiók nincs beállítva**: A szervezete nem állította be a fiókját a munkahelyi vagy iskolai adatok elérésére. Kérjen segítséget a rendszergazdától. | A felhasználói fiókhoz nem tartozik Intune A Direct-licenc. | Rendeljen Intune-licencet a felhasználó fiókjához az [Office-portálon](http://portal.office.com).
**Nem felel meg az eszköz**: Nem használhatja az alkalmazást, mert ez egy feltört eszköz. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó feltört eszközt használ. | Állítsa vissza az eszköz gyári alapbeállításait. Kövesse az Apple támogatói webhelyén található [utasításokat](https://support.apple.com/HT201274).
**Internetkapcsolat szükséges**: Az alkalmazáshasználati jogosultsága ellenőrzéséhez internetkapcsolatra van szükség. | Az eszközön nincs internetkapcsolat. | Csatlakoztassa az eszközt egy Wi-Fi- vagy adathálózathoz.
**Ismeretlen hiba**: Próbálja meg újraindítani az alkalmazást. Ha nem szűnik meg a probléma, kérjen segítséget a rendszergazdától. | Ismeretlen hiba történt. | Próbálkozzon újra egy kis idő elteltével. Ha a probléma nem szűnik meg, hozzon létre egy Intune-beli támogatási jegyet [itt](how-to-get-support-for-microsoft-intune.md).
**Hozzáférés a szervezet adataihoz**: A megadott munkahelyi vagy iskolai fióknak nincs hozzáférése ehhez az alkalmazáshoz. Lehetséges, hogy másik fiókkal kell bejelentkeznie. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó egy második, az eszközön a MAM-mal regisztrált fióktól eltérő munkahelyi vagy iskolai fiókkal próbál bejelentkezni. A MAM egyszerre csak egy munkahelyi vagy iskolai fiókot képes kezelni egy eszközön. | A felhasználó jelentkezzen be azzal a fiókkal, amelynek felhasználóneve megjelenik a bejelentkezési képernyőn. <br> <br> Vagy jelentkezzen be az új munkahelyi vagy iskolai fiókkal, és távolítsa el a MAM-mal jelenleg regisztrált fiókot.
**Csatlakozási probléma**: Váratlan csatlakozási probléma lépett fel. Ellenőrizze a kapcsolatot, majd próbálkozzon újra.  |  Váratlan hiba. | Próbálkozzon újra egy kis idő elteltével. Ha a probléma nem szűnik meg, hozzon létre egy Intune-beli támogatási jegyet [itt](how-to-get-support-for-microsoft-intune.md).
**Riasztás**: Ez az alkalmazás már nem használható. További információért forduljon a rendszergazdához. | Nem sikerült ellenőrizni az alkalmazás tanúsítványának érvényességét. | Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Telepítse újra az alkalmazást.
**Hiba**: Az alkalmazás problémát észlelt, ezért leáll. Ha nem szűnik meg a probléma, forduljon a rendszergazdához. | Nem sikerült beolvasni a MAM-alkalmazás PIN kódját az Apple iOS kulcsláncából. | Indítsa újra az eszközt. Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Telepítse újra az alkalmazást.


### <a name="error-messages-and-dialogs-on-android"></a>Hibaüzenetek és párbeszédpanelek az Androidban

Párbeszédpanel/hibaüzenet | Ok | Kockázatcsökkentés |
-- | --- | --- |
**Nincs beállítva az alkalmazás**: Ez az alkalmazás nincs beállítva az Ön általi használatra. Segítségért forduljon a rendszergazdához. | Nem sikerült észlelni az alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. |Léptessen életbe egy Andoridos alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**Failed app launch** (Alkalmazás indítása sikertelen): Hiba történt az alkalmazás indításakor. Próbálja meg frissíteni az alkalmazást vagy az Intune Munkahelyi portál alkalmazást. Ha segítségre van szüksége, lépjen kapcsolatba a rendszergazdával. | Az Intune észleli az alkalmazásra vonatkozó érvényes alkalmazásvédelmi szabályzatot, de az alkalmazás összeomlik a MAM inicializálása során. | Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Ellenőrizze, hogy telepítve van-e az eszközön az Intune Munkahelyi portál alkalmazás, és hogy naprakész-e. <br><br> Ha a probléma nem szűnik meg, küldje el a naplókat az Intune-nak a Munkahelyi portál alkalmazással, vagy hozzon létre egy támogatási jegyet [itt](how-to-get-support-for-microsoft-intune.md).
**Nem találhatók alkalmazások**: Ezen az eszközön nem található olyan alkalmazás, amellyel munkahelye engedélyezné a tartalom megnyitását. Segítségért forduljon a rendszergazdához. | A felhasználó munkahelyi vagy iskolai adatokat próbált meg megnyitni egy másik alkalmazásban, de az Intune nem talált olyan más felügyelt alkalmazást, amely jogosult az adatok megnyitására. | Állítson be egy androidos alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozzon meg vele legalább egy másik MAM-kompatibilis alkalmazást, amely alkalmas a kérdéses adatok megnyitására.
**A bejelentkezés sikertelen**: Próbáljon meg újra bejelentkezni. Ha nem szűnik meg a probléma, kérje a rendszergazda segítségét. | Nem sikerült hitelesíteni a fiókot, amellyel a felhasználó megpróbál bejelentkezni. | A felhasználó azzal a munkahelyi vagy iskolai fiókkal jelentkezzen be, amely már regisztrálva van az Intune MAM-szolgáltatásában (ez az első munkahelyi vagy iskolai fiók, amellyel sikeresen bejelentkezett ebbe az alkalmazásba). <br><br> Törölje az alkalmazásadatokat. <br><br> Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Ellenőrizze, hogy a Munkahelyi portál alkalmazás naprakész verzióját használja-e.
**Internetkapcsolat szükséges**: Az alkalmazáshasználati jogosultsága ellenőrzéséhez internetkapcsolatra van szükség. | Az eszközön nincs internetkapcsolat. | Csatlakoztassa az eszközt egy Wi-Fi- vagy adathálózathoz.
**Nem felel meg az eszköz**: Nem használhatja az alkalmazást, mert ez egy feltört eszköz. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó feltört eszközt használ. | Állítsa vissza az eszköz gyári alapbeállításait.
**A fiók nincs beállítva**: Ezt az alkalmazást a Microsoft Intune-nak kell kezelnie, de az Ön fiókja még nincs beállítva. Segítségért forduljon a rendszergazdához. | A felhasználói fiókhoz nem tartozik Intune A Direct-licenc. | Rendeljen Intune-licencet a felhasználó fiókjához az [Office-portálon](http://portal.office.com).
**Unable to register the app** (Nem sikerült regisztrálni az alkalmazást): Ezt az alkalmazást a Microsoft Intune-nak kell kezelnie, de ezúttal nem sikerült azt regisztrálni. Segítségért forduljon a rendszergazdához. | Nem sikerült automatikusan regisztrálni az alkalmazást a MAM-szolgáltatásban, pedig alkalmazásvédelmi szabályzatra van szükség. | Törölje az alkalmazásadatokat. <br><br> Küldje el a naplókat az Intune-nak a Munkahelyi portál alkalmazás segítségével, vagy hozzon létre egy támogatási jegyet [itt](how-to-get-support-for-microsoft-intune.md).




### <a name="see-also"></a>További információ
- [A mobilalkalmazás-kezelés beállításának ellenőrzése](../deploy-use/validate-mobile-application-management.md)
- [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Microsoft Intune-támogatás kérése](how-to-get-support-for-microsoft-intune.md)
