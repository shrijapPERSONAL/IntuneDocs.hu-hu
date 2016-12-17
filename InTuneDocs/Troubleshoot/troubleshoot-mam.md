---
title: "Mobilalkalmazás-kezelési hibaelhárítás | Microsoft Docs"
description: "Ebben a témakörben a feltételes hozzáférést alkalmazó környezetekre vonatkozó hibaelhárítási információkat olvashat."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Mobilalkalmazás-kezelési hibaelhárítás

Ha az Intune mobilalkalmazás-kezeléssel kapcsolatos problémába ütközik, először ebben a cikkben próbálja meg megkeresni a megoldást. Ebben a témakörben számos gyakran előforduló problémát és kérdést megtárgyalunk, és ezekre kínálunk megoldásokat és válaszokat.

## <a name="common-it-administrator-issues"></a>A rendszergazdáknál gyakran előforduló problémák

1. **A probléma leírása:** Az Azure Portalon beállított, eszközregisztráció nélküli alkalmazásvédelmi szabályzat nem lép életbe az iOS- és Android-eszközökön futó Skype Vállalati verzió alkalmazásra vonatkozóan.

  **Megoldás**: A Skype Vállalati verziót a modern hitelesítésre kell beállítani.  Kövesse a [Bérlő engedélyezése modern hitelesítéshez](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) című részben található utasításokat a modern hitelesítés beállításához Skype-hoz.

2. **A probléma leírása:** Az alkalmazásvédelmi szabályzatok egyetlen felhasználónál sem lépnek életbe a [támogatott Office-alkalmazásokra](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) vonatkozóan.

  **Megoldás**: Ellenőrizze, hogy a felhasználók rendelkeznek-e Intune-licenccel, illetve, hogy a használt alkalmazásvédelmi szabályzat megcélozza-e az Office-alkalmazásokat. Az újonnan beállított alkalmazásvédelmi szabályzatok életbe lépéséhez esetenként 8 órának is el kell telnie.

3. **A probléma leírása:** Az informatikai rendszergazda nem tud alkalmazásvédelmi szabályzatokat konfigurálni az Azure Portalon.

  **Megoldás**:

  A következő felhasználói szerepkörök rendelkeznek hozzáféréssel az Azure Portalhoz:

  - Globális rendszergazda; ez a szerepkör az [Office-portálon](http://portal.office.com/) állítható be.
  - Tulajdonos; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.
  - Közreműködő; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.<br>

  A szerepkörök beállításával kapcsolatban a [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) című részben talál segítséget.

4. **A probléma leírása:** A felügyeleti konzol jelentéseiben nem szerepelnek azok a felhasználói fiókok, amelyekre a közelmúltban alkalmazták az alkalmazásvédelmi szabályzatot.

  **Megoldás**: Az alkalmazásvédelmi szabályzattal újonnan megcélzott felhasználók esetében előfordul, hogy 24 órának is el kell telnie, hogy a felhasználó megjelenjen a jelentésekben.

5. **A probléma leírása:** A szabályzatok módosításainak / frissítéseinek életbe lépése akár 8 órát is igénybe vehet.  

  **Megoldás**: A végfelhasználó jelentkezzen ki az alkalmazásból, majd jelentkezzen be újra, ezzel kikényszerítve a szinkronizálást a szolgáltatással.  

6. **A probléma leírása:** Az alkalmazásvédelmi szabályzat nem kezeli az Apple DEP-eszközöket.

  **Megoldás**: Győződjön meg róla, hogy használja-e a Felhasználói affinitás funkciót az Apple Eszközregisztrációs programmal (DEP). Felhasználói affinitásra minden olyan alkalmazás esetében szükség van, amely felhasználói hitelesítést igényel DEP alatt.
Az iOS DEP-regisztrációról bővebben lásd: [Az Eszközregisztrációs program vállalati tulajdonú iOS-eszközeinek regisztrálása](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="common-end-user-issues"></a>A végfelhasználóknál előforduló gyakori problémák

### <a name="issues-on-ios"></a>iOS-problémák

Párbeszédpanel/hibaüzenet | Ok | Kockázatcsökkentés |
-- | --- | --- |
**Nincs beállítva az alkalmazás**: Ez az alkalmazás nincs beállítva az Ön általi használatra. Segítségért forduljon a rendszergazdához. | Nem sikerült észlelni az alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. |Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**Üdvözli Önt az Intune Managed Browser**: Ez az alkalmazás akkor működik optimálisan, ha a Microsoft Intune felügyeli. Bármikor böngészheti vele az internetet. Ha az alkalmazást a Microsoft Intune felügyeli, további adatbiztonsági funkciókat is elérhet. | Nem sikerült észlelni az Intune Managed Browser alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. <br><br>A felhasználó ebben az esetben is internetezhet, de az alkalmazást nem az Intune fogja felügyelni. | Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az Intune Managed Browser alkalmazást.
**A bejelentkezés sikertelen**: Nem tudtuk bejelentkeztetni. Próbálkozzon újra később. | Nem sikerült regisztrálni a felhasználót a MAM-szolgáltatásban, miután a felhasználó megpróbált munkahelyi vagy iskolai fiókjával bejelentkezni. | Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**A fiók nincs beállítva**: A szervezete nem állította be a fiókját a munkahelyi vagy iskolai adatok elérésére. Kérjen segítséget a rendszergazdától. | A felhasználói fiókhoz nem tartozik Intune A Direct-licenc. | Rendeljen Intune-licencet a felhasználó fiókjához az [Office-portálon](http://portal.office.com).
**Nem felel meg az eszköz**: Nem használhatja az alkalmazást, mert ez egy feltört eszköz. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó feltört eszközt használ. | Állítsa vissza az eszköz gyári alapbeállításait. Kövesse az Apple támogatói webhelyén található [utasításokat](https://support.apple.com/en-us/HT201274).
**Internetkapcsolat szükséges**: Az alkalmazáshasználati jogosultsága ellenőrzéséhez internetkapcsolatra van szükség. | Az eszközön nincs internetkapcsolat. | Csatlakoztassa az eszközt egy Wi-Fi- vagy adathálózathoz.
**Ismeretlen hiba**: Próbálja meg újraindítani az alkalmazást. Ha nem szűnik meg a probléma, kérjen segítséget a rendszergazdától. | Ismeretlen hiba történt. | Próbálkozzon újra egy kis idő elteltével. Ha a probléma nem szűnik meg, hozzon létre egy Intune-beli támogatási jegyet [itt](/how-to-get-support-for-microsoft-intune.md).
**Hozzáférés a szervezet adataihoz**: A megadott munkahelyi vagy iskolai fióknak nincs hozzáférése ehhez az alkalmazáshoz. Lehetséges, hogy másik fiókkal kell bejelentkeznie. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó egy második, az eszközön a MAM-mal regisztrált fióktól eltérő munkahelyi vagy iskolai fiókkal próbál bejelentkezni. A MAM egyszerre csak egy munkahelyi vagy iskolai fiókot képes kezelni egy eszközön. | A felhasználó jelentkezzen be azzal a fiókkal, amelynek felhasználóneve megjelenik a bejelentkezési képernyőn. <br> <br> Vagy jelentkezzen be az új munkahelyi vagy iskolai fiókkal, és távolítsa el a MAM-mal jelenleg regisztrált fiókot.
**Csatlakozási probléma**: Váratlan csatlakozási probléma lépett fel. Ellenőrizze a kapcsolatot, majd próbálkozzon újra.  |  Váratlan hiba. | Próbálkozzon újra egy kis idő elteltével. Ha a probléma nem szűnik meg, hozzon létre egy Intune-beli támogatási jegyet [itt](/how-to-get-support-for-microsoft-intune.md).
**Riasztás**: Ez az alkalmazás már nem használható. További információért forduljon a rendszergazdához. | Nem sikerült ellenőrizni az alkalmazás tanúsítványának érvényességét. | Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Telepítse újra az alkalmazást.
**Hiba**: Az alkalmazás problémát észlelt, ezért leáll. Ha nem szűnik meg a probléma, forduljon a rendszergazdához. | Nem sikerült beolvasni a MAM-alkalmazás PIN kódját az Apple iOS kulcsláncából. | Indítsa újra az eszközt. Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Telepítse újra az alkalmazást.


### <a name="issues-on-android"></a>Android-problémák

Párbeszédpanel/hibaüzenet | Ok | Kockázatcsökkentés |
-- | --- | --- |
**Nincs beállítva az alkalmazás**: Ez az alkalmazás nincs beállítva az Ön általi használatra. Segítségért forduljon a rendszergazdához. | Nem sikerült észlelni az alkalmazáshoz használandó alkalmazásvédelmi szabályzatot. |Léptessen életbe egy iOS-es alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozza meg benne ezt az alkalmazást.
**Failed app launch** (Alkalmazás indítása sikertelen): Hiba történt az alkalmazás indításakor. Próbálja meg frissíteni az alkalmazást vagy az Intune Munkahelyi portál alkalmazást. Ha segítségre van szüksége, lépjen kapcsolatba a rendszergazdával. | Az Intune észleli az alkalmazásra vonatkozó érvényes alkalmazásvédelmi szabályzatot, de az alkalmazás összeomlik a MAM inicializálása során. | Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Ellenőrizze, hogy telepítve van-e az eszközön az Intune Munkahelyi portál alkalmazás, és hogy naprakész-e. <br><br> Ha a probléma nem szűnik meg, küldje el a naplókat az Intune-nak a Munkahelyi portál alkalmazással, vagy hozzon létre egy támogatási jegyet [itt](/how-to-get-support-for-microsoft-intune.md).
**Nem találhatók alkalmazások**: Ezen az eszközön nem található olyan alkalmazás, amellyel munkahelye engedélyezné a tartalom megnyitását. Segítségért forduljon a rendszergazdához. | A felhasználó munkahelyi vagy iskolai adatokat próbált meg megnyitni egy másik alkalmazásban, de az Intune nem talált olyan más felügyelt alkalmazást, amely jogosult az adatok megnyitására. | Állítson be egy androidos alkalmazásvédelmi szabályzatot a felhasználó biztonsági csoportjában, és célozzon meg vele legalább egy másik MAM-kompatibilis alkalmazást, amely alkalmas a kérdéses adatok megnyitására.
**A bejelentkezés sikertelen**: Próbáljon meg újra bejelentkezni. Ha nem szűnik meg a probléma, kérje a rendszergazda segítségét. | Nem sikerült hitelesíteni a fiókot, amellyel a felhasználó megpróbál bejelentkezni. | A felhasználó azzal a munkahelyi vagy iskolai fiókkal jelentkezzen be, amely már regisztrálva van az Intune MAM-szolgáltatásában (ez az első munkahelyi vagy iskolai fiók, amellyel sikeresen bejelentkezett ebbe az alkalmazásba). <br><br> Törölje az alkalmazásadatokat. <br><br> Ellenőrizze, hogy az alkalmazás naprakész verzióját használja-e. <br><br> Ellenőrizze, hogy a Munkahelyi portál alkalmazás naprakész verzióját használja-e.
**Internetkapcsolat szükséges**: Az alkalmazáshasználati jogosultsága ellenőrzéséhez internetkapcsolatra van szükség. | Az eszközön nincs internetkapcsolat. | Csatlakoztassa az eszközt egy Wi-Fi- vagy adathálózathoz.
**Nem felel meg az eszköz**: Nem használhatja az alkalmazást, mert ez egy feltört eszköz. Segítségért forduljon a rendszergazdához. | Az Intune észlelte, hogy a felhasználó feltört eszközt használ. | Állítsa vissza az eszköz gyári alapbeállításait.
**A fiók nincs beállítva**: Ezt az alkalmazást a Microsoft Intune-nak kell kezelnie, de az Ön fiókja még nincs beállítva. Segítségért forduljon a rendszergazdához. | A felhasználói fiókhoz nem tartozik Intune A Direct-licenc. | Rendeljen Intune-licencet a felhasználó fiókjához az [Office-portálon](http://portal.office.com).
**Unable to register the app** (Nem sikerült regisztrálni az alkalmazást): Ezt az alkalmazást a Microsoft Intune-nak kell kezelnie, de ezúttal nem sikerült azt regisztrálni. Segítségért forduljon a rendszergazdához. | Nem sikerült automatikusan regisztrálni az alkalmazást a MAM-szolgáltatásban, pedig alkalmazásvédelmi szabályzatra van szükség. | Törölje az alkalmazásadatokat. <br><br> Küldje el a naplókat az Intune-nak a Munkahelyi portál alkalmazás segítségével, vagy hozzon létre egy támogatási jegyet [itt](/how-to-get-support-for-microsoft-intune.md).





### <a name="see-also"></a>További információ
- [A mobilalkalmazás-kezelés beállításának ellenőrzése](../deploy-use/validate-mobile-application-management.md)
- [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


