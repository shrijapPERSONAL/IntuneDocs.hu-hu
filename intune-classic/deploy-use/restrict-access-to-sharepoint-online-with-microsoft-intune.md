---
title: A SharePoint Online védelme
description: Feltételes hozzáféréssel védheti és kezelheti a vállalati adatokhoz való hozzáférést a SharePoint Online-on.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b7285c272efac8eab406393b0b896795fa5d8ed
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31027976"
---
# <a name="protect-access-to-sharepoint-online-with-microsoft-intune"></a>A SharePoint Online-hoz való hozzáférés védelme a Microsoft Intune-nal

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A SharePoint Online-on lévő fájlok elérésének szabályozására a Microsoft Intune feltételes hozzáférés funkcióját használhatja.
A feltételes hozzáférés két összetevőből áll:
- Egy eszközmegfelelőségi szabályzatból, amelynek az eszköznek meg kell felelnie, hogy a rendszer megfelelőnek találja.
- Egy feltételes hozzáférési szabályzatból, amelyben meghatározhatja azokat a feltételeket, amelyeknek az eszköznek meg kell felelnie ahhoz, hogy hozzáférhessen a szolgáltatáshoz.
Ha szeretné jobban megismerni a feltételes hozzáférés működését, olvassa el [Az e-mailek, az O365- és egyéb szolgáltatások elérésének védelme](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című témakört.

A megfelelőségi és a feltételes hozzáférési szabályzatokat a felhasználók számára lépteti életbe. A rendszer minden olyan eszköz megfelelőségét ellenőrzi, amelyről a felhasználó használja a szolgáltatásokat.

Amikor egy felhasználó támogatott alkalmazással (például a OneDrive-val) próbál hozzáférni egy fájlhoz az eszközéről, a rendszer a következő kiértékelést hajtja végre:

![Azokat a döntési pontokat megjelenítő diagram, amelyek meghatározzák, hogy kapjon-e hozzáférést az adott eszköz a SharePoint Online-hoz](../media/ConditionalAccess8-6.png)


**Mielőtt** beállítaná a SharePoint Online-ra vonatkozó feltételes hozzáférési szabályzatot, a következőknek kell teljesülniük:
- Rendelkeznie kell **SharePoint Online-előfizetéssel**, a felhasználóknak pedig licenccel kell rendelkezniük a SharePoint Online-hoz.
- Rendelkeznie kell **Enterprise Mobility + Security (EMS) előfizetéssel** vagy **Azure Active Directory (Azure AD) Premium előfizetéssel**, és a felhasználóknak is licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/pricing/details/active-directory/) talál.


  Ha csatlakozni szeretne a kívánt fájlokhoz, az eszköznek az alábbi feltételeknek kell megfelelnie:
-   **Regisztrálva** kell lennie az Intune-ban, vagy tartományhoz csatlakoztatott számítógépnek kell lennie.

-   **Regisztrálva** kell lennie az Azure Active Directoryban (ez automatikusan megtörténik, amikor az eszközt regisztrálják az Intune-ban).


-   **Meg kell felelnie** az Intune összes telepített megfelelőségi szabályzatának.

Az eszköz állapotát a rendszer az Azure Active Directoryban tárolja, amely a megadott feltételek alapján engedélyezi vagy tiltja a fájlok elérését.

Ha egy feltétel nem teljesül, a felhasználó számára az alábbi üzenetek egyike jelenik meg a bejelentkezéskor:

-   Ha az eszköz még nincs regisztrálva az Intune-ban vagy az Azure Active Directoryban, egy üzenet jelenik meg, amely leírja, hogy hogyan kell telepíteni a Céges portál alkalmazást és regisztrálni az eszközt.

-   Ha az eszköz nem megfelelő, egy üzenet jelenik meg, amely a felhasználót az Intune Céges portál webhelyére irányítja, ahol további információkat talál a problémáról és annak megoldásáról.

**A feltételes hozzáférés a külső megosztásra nem vonatkozik**. Arról, hogy hogyan akadályozhatja meg a külső megosztást a bérlőjén vagy a webhelycsoportján belül, a [Külső megosztás kezelése SharePoint Online-környezetben](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) című cikk nyújt tájékoztatást.

>[!NOTE]
>Ha engedélyezi a SharePoint Online-on a feltételes hozzáférést, javasoljuk, hogy tiltsa le a tartományt a listán a [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) című témakörben ismertetett módon.  

## <a name="support-for-mobile-devices"></a>A mobileszközök támogatása
A következők támogatottak:
- iOS 8.0 és újabb verziók
- Android 4.0-s és újabb verziók, Samsung KNOX szabvány 4.0-s vagy újabb verziók
- Windows Phone 8.1 és újabb verziók

Védheti a SharePoint Online-hoz való hozzáférést, ha a SharePoint Online-t **iOS-** és **Android-** eszközökön futó böngészővel érik el. A hozzáférés csak a szabályzatnak megfelelő eszközök támogatott böngészőiről engedélyezett:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS és Android 5.0 és újabb)

**A nem támogatott böngészőkből nem lehetséges hozzáférni a szolgáltatáshoz**.

## <a name="support-for-pcs"></a>Számítógépek támogatása
A következők támogatottak:
- Windows 8.1 és újabb (az Intune-nal regisztrált számítógépek esetében)
- Windows 7.0, Windows 8.1 vagy Windows 10 (ha a számítógépek tartományhoz csatlakoznak)
  > [!NOTE]
  >Ahhoz, hogy feltételes hozzáférést használhasson Windows 10-es számítógépeken, frissítenie kell a gépeket a Windows 10 évfordulós frissítéssel.

  - Tartományhoz csatlakozó számítógépek esetén be kell állítani az Azure Active Directoryban való [automatikus regisztrációt](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/). Az Azure AD eszközregisztrációs szolgáltatása automatikusan aktiválódik az Intune-t és az Office 365-öt használó ügyfelek számára. Azok az ügyfelek, akik már telepítették az ADFS eszközregisztrációs szolgáltatását, nem fogják látni a regisztrált eszközöket a helyszíni Active Directoryban.

  - Ha a szabályzat úgy van beállítva, hogy megkövetelje a tartományhoz való csatlakozást, és a számítógép nem csatlakozik tartományhoz, megjelenik egy üzenet, amely jelzi, hogy kapcsolatba kell lépni a rendszergazdával.

  - Ha a szabályzat úgy van beállítva, hogy tartományhoz való csatlakozást vagy megfelelőséget követeljen meg, és a számítógép egyik követelménynek sem felel meg, egy utasításokat tartalmazó üzenet jelenik meg, amely leírja, hogy hogyan telepítse a Munkahelyi portál alkalmazást, és hogyan regisztrálja az eszközt.
    >[!NOTE]
    >A feltételes hozzáférés nem támogatott az Intune-számítógépügyfelet futtató számítógépeken.

Az [Office 365 modern hitelesítésének engedélyezve kell lennie](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), és a számítógépre telepíteni kell az Office legújabb frissítéseit.

A modern hitelesítéssel Active Directory Authentication Library-alapú (ADAL-alapú) bejelentkezés biztosítható az Office 2013 Windows-ügyfelein, amely magasabb fokú biztonságot kínál, többek között a **többtényezős hitelesítéssel** és a **tanúsítványalapú hitelesítéssel**.


## <a name="configure-conditional-access-for-sharepoint-online"></a>A SharePoint Online feltételes hozzáférésének beállítása

### <a name="step-1-configure-active-directory-security-groups"></a>1. lépés: Az Active Directory-alapú biztonsági csoportok beállítása
Kezdés előtt állítsa be az Azure Active Directory-alapú biztonsági csoportokat a feltételes hozzáférési szabályzathoz. Ezeket a csoportokat az **Office 365 Felügyeleti központban** vagy az **Intune-fiókportálon** konfigurálhatja. Ezen csoportok alapján lehet megcélozni, illetve kivételként kezelni a felhasználókat. Ha egy felhasználóra szabályzat vonatkozik, az erőforrások eléréséhez az általa használt összes eszköznek meg kell felelnie a szabályzatnak.

Egy SharePoint Online-szabályzatban két csoporttípust adhat meg:

-   **Megcélzott csoportok**: Azokat a felhasználói csoportokat tartalmazza, amelyekre a szabályzat vonatkozik.

-   **Kivétel alá eső csoportok**: A szabályzat alól mentesülő felhasználók csoportjait tartalmazza.

Ha egy felhasználó mindkét csoportban szerepel, mentesül a szabályzat alól.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>2. lépés: Megfelelőségi szabályzat konfigurálása és telepítése
Ha eddig még nem tette meg, hozza létre és regisztrálja a megfelelőségi szabályzatot azoknak a felhasználóknak, akikre a SharePoint Online-szabályzat vonatkozni fog.

> [!NOTE]
> A megfelelőségi szabályzatok a Microsoft Intune csoportjaira vonatkoznak, a feltételes hozzáférési szabályzatok viszont az Azure Active Directory biztonsági csoportjait célozzák meg.

A megfelelőségi szabályzat konfigurálásának részletei a [Megfelelőségi szabályzat létrehozása](create-a-device-compliance-policy-in-microsoft-intune.md) című részben találhatók.

> [!IMPORTANT]
> Ha nem léptetett életbe megfelelőségi szabályzatot, a rendszer megfelelőnek tekinti az eszközöket.

Ha készen áll, folytassa a **3. lépéssel**.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>3. lépés: A SharePoint Online-szabályzat beállítása
Ezután állítsa be úgy a házirendet, hogy csak a felügyelt és a feltételeknek megfelelő eszközök érhessék el a SharePoint Online-t. A szabályzatot a rendszer ezek után az Azure Active Directoryban tárolja.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> Az Intune-eszközökre vonatkozó feltételes hozzáférési szabályzatot az Azure AD felügyeleti konzoljában is létrehozhatja (ezeket a szabályzatokat az Azure AD **eszközalapú feltételes hozzáférési szabályzatnak** nevezi). Ezenfelül más feltételes hozzáférési szabályzatokat (például többtényezős hitelesítést) is létrehozhat. Külső gyártók vállalati alkalmazásaihoz is beállíthat feltételes hozzáférési szabályzatokat, ha az Azure AD támogatja őket (ilyen például a Salesforce és a Box). További részleteket a [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/) (Hogyan állítható be eszközalapú feltételes hozzáférési szabályzat az Azure Active Directoryban az Azure Active Directoryhoz csatlakozó eszközök hozzáférés-vezérlésére) című cikkben olvashat.


1. A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Szabályzat** > **Feltételes hozzáférés** > **SharePoint Online-szabályzat** lehetőségre.
   ![A SharePoint Online-szabályzat oldalát bemutató képernyőkép](../media/mdm-ca-spo-policy-configuration.png)

2. Válassza a **Feltételes hozzáférési szabályzat engedélyezése SharePoint Online-hoz** lehetőséget.

3. Az **Alkalmazás hozzáférése** szakaszban kiválaszthatja, hogy mire szeretné alkalmazni a feltételes hozzáférési szabályzatot:

   - **Összes platform**

     Ha ezt a beállítást szeretné használni, a **SharePoint Online** elérésére használt összes eszközt regisztrálni kell az Intune-ban, és ezeknek meg kell felelniük a szabályzatoknak. Minden **modern hitelesítést** használó ügyfélalkalmazás a feltételes hozzáférési szabályzat hatálya alá tartozik. Ha a platformot az Intune jelenleg nem támogatja, akkor a **SharePoint Online**-hoz sem lehet róla hozzáférni.

     A **Minden platform** beállítás kiválasztása esetén az Azure Active Directory minden hitelesítési kérelemre alkalmazza a szabályzatot, az ügyfélalkalmazás által jelentett platformtól függetlenül. Az alábbiakat kivéve minden platform köteles regisztrálni, illetve megfelelni a szabályzatoknak:
     *   Azok a Windows-eszközök, amelyeket regisztrálni kell, illetve amelyeknek meg kell felelniük a szabályzatoknak, akár tartományhoz csatlakoznak, akár helyszíni Active Directoryt használnak, akár mindkettő igaz rájuk.
     * Nem támogatott platformok, például a Mac. Azonban az ezekről a platformokról származó, de modern hitelesítést használó alkalmazások továbbra is le lesznek tiltva.

   - **Megadott platformok**

      A megadott platformokon minden modern hitelesítést használó ügyfélalkalmazás a feltételes hozzáférési szabályzat hatálya alá tartozik.

     A Windows rendszerű számítógépek esetében a számítógépnek vagy tartományhoz csatlakoztatott számítógépnek kell lennie, vagy regisztrálva kell lennie az Intune-ban, és meg kell felelnie a szabályzatnak. A következő követelményeket állíthatja be:

     -   **Az eszközöknek tartományhoz kell csatlakozniuk vagy meg kell felelniük a házirendnek.** Ezzel a lehetőséggel előírhatja, hogy a számítógépeknek tartományhoz kell csatlakozniuk, vagy meg kell felelniük az Intune-ban beállított szabályzatoknak. Ha a számítógép egyik követelménynek sem felel meg, a rendszer kéri a felhasználótól, hogy regisztrálja az eszközt az Intune-ban.

     -   **Az eszközöknek meg kell felelniük a házirendnek.** Ha ezt a lehetőséget választja, előírhatja, hogy a számítógépeknek regisztrálva kell lenniük az Intune-ban, és meg kell felelniük a szabályzatnak. Ha a számítógép nincs regisztrálva, megjelenik egy, a regisztráció lépéseit bemutató üzenet.

4. A **Böngészőalapú hozzáférés** SharePoint Online-hoz és a OneDrive Vállalati verzióhoz beállítás alatt engedélyezheti, hogy az Exchange Online-hoz csak a támogatott böngészőkkel lehessen hozzáférni: ezek a Safari (iOS) és a Chrome (Android). Más böngészőkkel nem lehetséges a hozzáférés. A OneDrive beállított alkalmazás-hozzáférési platformkorlátozásai itt is érvényesek lesznek.

   Az **Android** rendszerű eszközök felhasználóinak engedélyezniük kell a böngészőalapú hozzáférést. A felhasználónak ehhez a regisztrált eszközön be kell kapcsolnia a **Böngészőalapú hozzáférés engedélyezése** lehetőséget az alábbi módon:
   1.    Nyissa meg a **Munkahelyi portál** alkalmazást.
   2.    A három pontra (...) koppintva vagy a hardveres menü gombbal nyissa meg a **Beállítások** lapot.
   3.    Kattintson a **Böngészőalapú hozzáférés engedélyezése** gombra.
   4.    A Chrome böngészőben jelentkezzen ki az Office 365-ből, majd indítsa újra a Chrome-ot.

   Az **iOS** és az **Android** platformokon a szolgáltatás eléréséhez használt eszköz azonosításához az Azure Active Directory egy TLS-tanúsítványt (Transport Layer Security) rendel az eszközhöz. Az eszköz az alábbi képernyőfelvételnek megfelelően megjeleníti a tanúsítványt, és felkéri a felhasználót, hogy válassza ki a tanúsítványt. A felhasználónak a böngésző használatához ki kell választania ezt a tanúsítványt.

   **iOS**

   ![Képernyőfelvétel a tanúsítvány kiválasztásának kéréséről egy iPad készüléken](../media/mdm-browser-ca-ios-cert-prompt.png)

   **Android**

   ![Képernyőfelvétel a tanúsítvány kiválasztásának kéréséről egy Android készüléken](../media/mdm-browser-ca-android-cert-prompt.png)
5. A **Megcélzott csoportok** területen kattintson a **Módosítás** lehetőségre azoknak az Active Directorybeli biztonsági csoportoknak a kiválasztásához, amelyekre érvényes a szabályzat. Kiválaszthatja, hogy a szabályzat minden felhasználóra, vagy csak felhasználók bizonyos csoportjaira vonatkozzon.

6. A **Kivétel alá eső csoportok**területen kattintson a **Módosítás** lehetőségre azon Active Directory-alapú biztonsági csoportok kiválasztásához, amelyekre nem érvényes a szabályzat.

7. Ha elkészült, válassza a **Mentés** elemet.

Nem kell telepítenie a feltételes hozzáférési szabályzatot, az azonnal érvénybe lép.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>4. lépés: A megfelelőség és a feltételes hozzáférési szabályzatok figyelése
A **Csoportok** munkaterületen megtekintheti eszközei állapotát.

Válassza ki a kívánt mobileszközök csoportját. Ezután az **Eszközök** lapon válasszon az alábbi **Szűrők** közül:

-   **Az AAD-ben nem regisztrált eszközök**. Ezeknek az eszközöknek nem engedélyezett a SharePoint Online elérése.

-   **Nem megfelelő eszközök**. Ezeknek az eszközöknek nem engedélyezett a SharePoint Online elérése.

-   **Az AAD-ben regisztrált és megfelelő eszközök**. Ezeknek az eszközöknek engedélyezett a SharePoint Online elérése.

### <a name="see-also"></a>Lásd még:
[Az e-mailek és az O365-szolgáltatások elérésének védelme a Microsoft Intune-ban](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
