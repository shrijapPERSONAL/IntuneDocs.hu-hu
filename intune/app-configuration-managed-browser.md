---
title: Egy házirend által védett böngészőt vállalati webes hozzáférés felügyelete
titleSuffix: Microsoft Intune
description: Egy házirend által védett böngészőt, Intune által hozzárendelt segítségével kezelheti a vállalati webböngészést és a webes adatok átvitele.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f32cfbb5e05958ec9d8f303809d3ffa28c3a3ec
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898991"
---
# <a name="manage-web-access-using-a-microsoft-intune-policy-protected-browser"></a>Egy böngészővel a Microsoft Intune a házirend által védett webes hozzáférés felügyelete

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-szabályzattal védett (Microsoft Edge vagy Intune Managed Browser) böngésző használatával gondoskodhat róla, hogy a vállalati webhelyek hozzáférésére mindig megfelelő biztonsági előírások vonatkozzanak.  Az Intune-nal konfigurált védett böngészők kihasználják az alábbi megoldások előnyeit:

- Alkalmazásvédelmi szabályzatokat
- Feltételes hozzáférés
- Egyszeri bejelentkezés
- Alkalmazás-konfigurációs beállítások
- Az Azure application proxy-integráció

## <a name="microsoft-edge-support"></a>A Microsoft Edge-támogatás

A Microsoft Edge vállalati forgatókönyvek iOS és Android rendszerű eszközökön használható. A Microsoft Edge az azonos felügyeleti forgatókönyvek, igény szerinti hozzáadásával továbbfejlesztett végfelhasználói élmény az Intune Managed Browser támogatja. A következő Microsoft Edge az Intune szabályzatai által engedélyezett vállalati funkciók érhetők el. Ezek a vállalati szolgáltatások a következők:

1. **Kettős-Identity** -felhasználók hozzáadhatnak, mind a munkahelyi fiókot, valamint egy személyes fiók, történő tallózásának tartalombeállításait. Nincs teljes elválasztását, amely hasonló az architektúra és a felhasználói felület az Office 365 és az Outlook két identitások között. Intune-rendszergazdák a munkahelyi fiók belül védett böngészési élményt a kívánt házirendeket állíthat be lesz. 
2. **Az Intune app protection házirend-integráció** - rendszergazdák mostantól alkalmazásvédelmi szabályzatokat a Microsoft Edge, a vezérlő a kivágási, másolási és beillesztési műveleteket, köztük megakadályozza, hogy a képernyőképek rögzítését, célként, és annak biztosítása, hogy a felhasználó által kiválasztott hivatkozások csak nyissa meg más felügyelt az alkalmazások.
3. **Az Azure Application Proxy-integráció** - rendszergazdák szabályozhatja a hozzáférést az SaaS-alkalmazások és a web apps szolgáltatásban, így biztosítja, hogy csak a böngészőalapú alkalmazások futtatása a biztonságos Microsoft Edge böngészőben, hogy a végfelhasználók számára a vállalati hálózathoz való csatlakozás vagy csatlakozás a a Az Internet. 
4. **Kedvencek felügyelt és a kezdőlap parancsikonok** – a könnyű hozzáférést, a rendszergazdák beállíthatnak URL-címek a Kedvencek jelenik meg, amikor a végfelhasználók számára a vállalati környezetben vannak. A rendszergazdák beállíthatnak egy kezdőlap parancsikon jelenik meg az elsődleges helyi értékként, amikor a vállalati felhasználó megnyitja a Microsoft Edge-ben új vagy egy új lap.

A Microsoft Intune alkalmazásvédelmi szabályzatokat a Microsoft Edge segítenek a szervezet adatok és erőforrások védelmét. Az Intune által védett Microsoft Edge biztosítja, hogy a vállalati erőforrások védelme nem csak a natív módon telepített alkalmazások belül is a webböngészőn keresztül elérhető.

## <a name="getting-started"></a>Első lépések

A Microsoft Edge és az Intune Managed Browser olyan webböngésző-alkalmazások, amelyeket Ön és végfelhasználói nyilvános alkalmazás-áruházakból tölthetnek le a szervezeten belül használatra. 

Az operációs rendszerre vonatkozó követelmények a böngésző szabályzataival kapcsolatban:
- Android 4 és újabb verziók, vagy
- iOS 8.0 és újabb verziók.

Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.

>[!NOTE]
>A Managed Browser nem támogatja a Secure Sockets Layer 3-as verziójú (SSLv3) titkosítási protokollját.


## <a name="application-protection-policies-for-protected-browsers"></a>Alkalmazásvédelmi szabályzatok a védelemmel ellátott böngészőkhöz

Mivel a Microsoft Edge és a Managed Browser rendelkeznek Intune SDK-integrációval, így alkalmazásvédelmi szabályzatok is alkalmazhatók rájuk, például a következők:
- Kivágás, másolás és beillesztés műveletek korlátozása.
- Képernyőmentés megakadályozása.
- Annak biztosítása, hogy a vállalati hivatkozásokat csak a felügyelt alkalmazásokon és böngészőkön belül lehessen megnyitni.

További információt a [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md) című témakörben talál.

Ezek a beállítások az alábbiakra alkalmazhatók:

- Az Intune-ban regisztrált eszközök
- Más MDM-termékben regisztrált eszközök
- Nem felügyelt eszközök

>[!NOTE]
>Ha a felhasználók telepítik a Managed Browser alkalmazást az alkalmazásáruházból, és azt nem az Intune felügyeli, akkor az egyszerű webböngészőként használható, amely a Microsoft MyApps webhelyen keresztül támogatja az egyszeri bejelentkezést. A felhasználók közvetlenül a MyApps webhelyére vannak irányítva, ahol megjelenik az összes számukra kiosztott SaaS-alkalmazás.
Ha a Microsoft Edge vagy a Managed Browser böngészőt nem az Intune felügyeli, nem tudják elérni az Intune által kezelt más alkalmazások adatait. 


## <a name="conditional-access-for-protected-browsers"></a>Feltételes hozzáférés védett böngészőkhöz

A Managed Browser már egy feltételes hozzáféréshez jóváhagyott ügyfélalkalmazás. Ez azt jelenti, hogy úgy korlátozhatja a mobilböngészők hozzáférését az Azure AD-hez csatlakozó webalkalmazásokhoz, hogy a felhasználók csak a Managed Browsert használhassák, valamint letilthat minden más nem védett böngészőt, például a Safarit vagy a Chrome-ot. Ez a védelem is alkalmazható az Azure erőforrásokhoz, mint az Exchange online-hoz és a SharePoint online-hoz, a Microsoft 365 felügyeleti központot és még akkor is, amelyekhez külső felhasználók számára keresztül a helyszíni helyek a [Azure AD-alkalmazásproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Ha az Azure AD-hez csatlakozó webalkalmazásokat az Intune Managed Browser használatára korlátozza mobilplatformokon, hozzon létre egy feltételes hozzáférési szabályzatot, amelyhez jóváhagyott ügyfélalkalmazások szükségesek. 

> [!TIP]  
> A feltételes hozzáférés az Azure Active Directory (Azure AD) technológiája. Az *Intune-ból* elérhető feltételes hozzáférési csomópont ugyanaz a csomópont, amelyet az *Azure AD-ből* is el lehet érni.  


1. Az Intune-portálon válassza a **Feltételes hozzáférés** > **Új szabályzat** lehetőséget. 
2. Ezután válassza a panel **Hozzáférés-szabályozási** szakaszában a **Hozzáférés** lehetőséget. 
3. Kattintson a **Jóváhagyott ügyfélalkalmazás megkövetelése** lehetőségre. 
4. A **Hozzáférés** panelen kattintson a **Kiválasztás** elemre. Ezt a szabályzatot hozzá kell rendelni azokhoz a felhőalkalmazásokhoz, amelyek esetében azt szeretné, hogy csak az Intune Managed Browser alkalmazásból legyenek elérhetők.

    ![Azure AD – Managed Browser feltételes hozzáférési szabályzat](./media/managed-browser-conditional-access-01.png)

5. A **Hozzárendelések** szakaszban válassza a **Feltételek** > **Ügyfélalkalmazások** lehetőséget. Megjelenik az **Ügyfélalkalmazások** panel.
6. A **Konfigurálás** területen kattintson az **Igen** lehetőségre a szabályzat adott ügyfélalkalmazásokra való érvényesítéséhez.
7. Ellenőrizze, hogy a **Browser** van-e kiválasztva ügyfélalkalmazásként.

    ![Azure AD – Managed Browser – Ügyfélalkalmazások kiválasztása](./media/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Ha korlátozni szeretné, hogy mely natív (nem böngészőbeli) alkalmazások férhetnek hozzá ezekhez a felhőalkalmazásokhoz, válassza a **Mobilalkalmazások és asztali ügyfelek** lehetőséget.

8. A **Hozzárendelések** szakaszban válassza a **Felhasználók és csoportok** lehetőséget, majd válassza ki azokat a felhasználókat és csoportokat, akikhez hozzá szeretné rendelni ezt a szabályzatot. 

    > [!NOTE]
    > Az alkalmazáskonfigurációs szabályzatok fogadása érdekében a felhasználókat Intune App Protection-szabályzattal kell megcélozni. További információ az Intune App Protection szabályzatainak létrehozásáról: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

9. A szabályzat védelme alá tartozó alkalmazások megadásához a **Hozzárendelések** szakaszban válassza a **Felhőalkalmazások** lehetőséget.

Miután konfigurálta a fenti szabályzatot, a felhasználók csak az Intune Managed Browserrel férhetnek hozzá az Azure AD-hez kapcsolódó, a szabályzat védelme alá tartozó webalkalmazásokhoz. Ha a felhasználók egy nem kezelt böngészőt próbálnak meg használni ehhez, egy értesítés jelenik meg az eszközükön, amely tudatja velük, hogy csak az Intune Managed Browsert használhatják.

A Managed Browser nem támogatja a klasszikus feltételes hozzáférési szabályzatokat. További információért lásd: [Klasszikus szabályzatok áttelepítése az Azure Portalon](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration).

##  <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Egyszeri bejelentkezés az Azure AD-hez kapcsolódó webalkalmazásokba a szabályzat által védett böngészőkben

A Microsoft Edge és az Intune Managed Browser mostantól SSO-t is használhat iOS-en és Androidon minden olyan webalkalmazáshoz (SaaS-hez és helyszíni alkalmazásokhoz), amely az Azure AD-hez csatlakozik. Ha a Microsoft Authenticator telepítve van iOS-en vagy az Intune Céges portál Androidon, a szabályzat által védett böngészők felhasználói hozzáférhetnek az Azure AD-hez kapcsolódó webalkalmazásokhoz anélkül, hogy újra meg kellene adniuk a hitelesítő adataikat.

Az SSO megköveteli az eszközöktől, hogy regisztrálva legyenek a Microsoft Authenticator (iOS-en) vagy az Intune Céges portál alkalmazásban (Androidon). Az Authenticator vagy az Intune Céges portál alkalmazással rendelkező felhasználóknak regisztrálniuk kell az eszközüket, amikor megnyitnak egy Azure AD-hez csatlakozó webalkalmazást egy szabályzat által védett böngészőben, amennyiben az eszközüket még nem regisztrálta egy másik alkalmazás. Miután az eszközt regisztrálták az Intune által kezelt fiókkal, a fiók az Azure AD-hez csatlakozó webalkalmazások esetében SSO-val fog rendelkezni. 

> [!NOTE]
> Az eszközregisztráció egy egyszerű bejelentkezés az Azure AD szolgáltatással. Nem igényel teljes eszközregisztrációt, és nem ad az eszközre vonatkozó további jogosultságokat az informatikai részlegnek.

## <a name="create-a-protected-browser-app-configuration"></a>Egy védett böngésző alkalmazáskonfigurációjának létrehozása

>[!IMPORTANT]
>Az alkalmazáskonfigurációk érvényre jutásához az szükséges, hogy a felhasználó védelemmel ellátott böngészőjét vagy az eszközön lévő alkalmazások egyikét már az [Intune alkalmazásvédelmi szabályzata]( app-protection-policy.md) felügyelje.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3.  A felügyeleti lista **Ügyfélalkalmazások** paneljén válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget.
4.  Az **Alkalmazáskonfiguráció** panelen válassza a **Hozzáadás** lehetőséget.
5.  A **Konfigurációs szabályzat hozzáadása** panelen az alkalmazáskonfigurációs beállításokhoz írja be a **Nevet** és a **Leírást** (ez utóbbi nem kötelező).
6.  Az **Eszközregisztráció** típusaként válassza a **Felügyelt alkalmazások** lehetőséget.
7.  Válassza a **Kötelező alkalmazás kiválasztása** elemet, majd a **Célalkalmazások** panelen válassza a **Managed Browser** vagy a **Microsoft Edge** lehetőséget iOS-hez, Androidhoz vagy igény szerint mindkettőhöz.
8.  Az **OK** kiválasztásával visszatérhet a **Konfigurációs szabályzat hozzáadása** panelre.
9.  Kattintson a **Konfigurációs beállítások** elemre. A **Konfigurálás** panelen kulcs-érték párok definiálásával adhatja meg a Managed Browserhez szükséges konfigurációkat. A jelen cikk későbbi részeiben további információt talál a definiálható kulcs-érték párokról.
10. Ha elkészült, válassza az **OK** elemet.
11. A **Konfigurációs szabályzat hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.
12. Ezzel létrejön az új konfiguráció, és megjelenik az **Alkalmazáskonfiguráció** panelen.


## <a name="assign-the-configuration-settings-you-created"></a>A létrehozott konfigurációs beállítások hozzárendelése

A beállításokat Azure AD-beli felhasználói csoportokhoz lehet hozzárendelni. Ha az illető felhasználó rendelkezik a célzott védett böngésző telepített példányával, akkor az alkalmazás felügyelete a megadott beállításokkal történik.

1. Az Intune mobilalkalmazás-kezelési irányítópult **Ügyfélalkalmazások** paneljén válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget.
2. A listából válassza ki a hozzárendelni kívánt alkalmazáskonfigurációt.
3. Válassza ki a következő panelen a **Hozzárendelések** elemet.
4. A **Hozzárendelések** panelen válassza ki azt az Azure AD-csoportot, amelyhez az alkalmazáskonfigurációt hozzá szeretné rendelni, majd válassza az **OK** elemet.


## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Alkalmazásproxy-beállítások konfigurálása a védett böngészőkhöz

A Microsoft Edge vagy az Intune Managed Browser [Azure AD Alkalmazásproxyval]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) való együttes használata támogatja az iOS- és Android-eszközök felhasználóit a következő helyzetekben:

- Egy felhasználó letölti a Microsoft Outlook alkalmazást és bejelentkezik. Az Intune alkalmazásvédelmi szabályzatai automatikusan érvényre jutnak. Titkosítják az elmentett adatokat, és megakadályozzák, hogy a felhasználó vállalati fájlokat továbbítson az eszközön lévő nem felügyelt alkalmazások vagy helyek felé. Megadható, hogy amikor a felhasználó egy intranetes webhelyre mutató hivatkozásra kattint az Outlookban, akkor a hivatkozás egy másik böngésző helyett a védett böngészőalkalmazásban nyíljon meg. A védett böngésző felismeri, hogy az adott intranetes webhely az Alkalmazásproxyn keresztül megnyílt a felhasználónak. A felhasználót automatikusan az Alkalmazásproxyn keresztül irányítja át, hogy csak minden lehetséges többtényezős hitelesítés és feltételes hozzáférés ellenőrzése után érhesse el az intranetes helyet. Ez a webhely, amely távoli felhasználók számára korábban nem volt megtalálható, most már elérhető, és az Outlook-beli hivatkozás is az elvárható módon működik.
- Egy távoli felhasználó megnyitja a védett böngészőalkalmazást, és a belső URL-cím segítségével megnyit egy intranetes webhelyet. A védett böngésző felismeri, hogy az adott intranetes webhely az Alkalmazásproxyn keresztül megnyílt a felhasználónak. A felhasználót automatikusan az Alkalmazásproxyn keresztül irányítja át, hogy csak minden lehetséges többtényezős hitelesítés és feltételes hozzáférés ellenőrzése után érhesse el az intranetes helyet. Ez a webhely, amely távoli felhasználók számára korábban nem volt megtalálható, most már elérhető.

### <a name="before-you-start"></a>Előkészületek

- Állítsa be a belső alkalmazásokat az Azure AD alkalmazásproxyban.
    - Az Alkalmazásproxy konfigurálásáról és az alkalmazások közzétételéről a [telepítési dokumentációban](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) olvashat. 
- A Managed Browser alkalmazás 1.2.0-s vagy annál újabb verzióját kell használnia.
- A Managed Browser és a Microsoft Edge alkalmazások felhasználói rendelkezzenek az alkalmazáshoz rendelt [Intune alkalmazásvédelmi szabályzattal](app-protection-policy.md).

    > [!NOTE]
    > Az Alkalmazásproxy frissített átirányítási adatainak érvénybe lépése a Managed Browserben és a Microsoft Edge-ben akár 24 órát is igénybe vehet.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>1. lépés: Automatikus átirányítás engedélyezése az Outlookból egy védett böngészőhöz
Az Outlookot olyan alkalmazásvédelmi szabályzattal kell konfigurálni, amelyben engedélyezett a **Webes tartalom megjelenítésének korlátozása a Managed Browser alkalmazásra** beállítás.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>2. lépés: Alkalmazáskonfigurációs szabályzat hozzárendelése a védett böngészőhöz.
Ez az eljárás az Alkalmazásproxy átirányítás használatára konfigurálja a Managed Browser vagy a Microsoft Edge alkalmazást. A Microsoft Edge vagy a Managed Browser alkalmazás konfigurációjának létrehozására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

| Kulcs                                                             | Érték    |
|-----------------------------------------------------------------|----------|
| **com.microsoft.intune.mam.managedbrowser.AppProxyRedirection** | **true** |

További információt a Managed Browser, a Microsoft Edge és az Azure AD Alkalmazásproxy a helyszíni webalkalmazásokhoz való zökkenőmentes (és védett) hozzáféréséhez szükséges együttes használatáról az Enterprise Mobility + Security blog [Együtt jobb: Az Intune és az Azure Active Directory együtt teszi jobbá a felhasználói hozzáférést](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access) című blogbejegyzésében találhat.

> [!NOTE]
> A Microsoft Edge ugyanazokat a kulcs-érték párokat használja, mint a Managed Browser. 

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Védett böngésző kezdőlapjának beállítása

Ezzel a beállítással adható meg a kezdőlap, amelyet a felhasználók egy védett böngésző elindításakor vagy egy új lap létrehozásakor látnak. 
- Ezzel a beállítással megjeleníti a weblapot a Managed Browserben.  A Microsoft Edge ehelyett a kezdőlapra mutató parancsikont jelenít meg.
- A kezdőlap parancsikonja a keresési vezérlőelem alatt ikonként jelenik meg.  Nem lehet szerkeszteni vagy törölni.
- A kezdőlap parancsikonja megjeleníti a szervezet nevét a megkülönböztethetőség érdekében.  Mindig az első ikonként fog megjelenni.

A Microsoft Edge vagy a Managed Browser alkalmazás konfigurációjának létrehozására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|                                Kulcs                                |                                                           Value                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Adjon meg egy érvényes URL-címet. A helytelen URL-címek biztonsági intézkedésként le vannak tiltva.<br>Például: `<https://www.bing.com>` |

## <a name="how-to-configure-bookmarks-for-a-protected-browser"></a>Védett böngésző könyvjelzőinek konfigurálása

Ezzel a beállítással konfigurálhatók a Microsoft Edge vagy a Managed Browser felhasználói számára elérhető könyvjelzők.

- Ezeket a könyvjelzőket a felhasználók nem törölhetik és nem módosíthatják
- Ezek a könyvjelzők a lista tetején jelennek meg. A felhasználók által készített könyvjelzők ezek alá kerülnek.
- Ha engedélyezte az alkalmazásproxy-átirányítást, akkor alkalmazásproxyval rendelkező webalkalmazásokat akár belső, akár külső URL-cím használatával is hozzáadhat.

A Microsoft Edge vagy a Managed Browser alkalmazás konfigurációjának létrehozására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|                                Kulcs                                 |                                                                                                                                                                                                                                                         Érték                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | Ennek a konfigurációnak egy könyvjelzőlista az értéke. Minden könyvjelző egy címből és egy URL-címből áll. A címet és az URL-címet a <strong>&#124;</strong> karakter választja el.<br><br>Példa:<br> <code>Microsoft Bing&#124;https://www.bing.com</code><br><br>Több könyvjelző megadásakor az egyes párokat a <strong>&#124;&#124;</strong> karakter választja el.<br><br>Példa:<br> <code>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com</code> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-a-protected-browser"></a>Engedélyezett és letiltott URL-címek meghatározása egy védett böngésző számára

A Microsoft Edge vagy a Managed Browser alkalmazás konfigurációjának létrehozására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|Kulcs|Value|
|-|-|
|A következő lehetőségek közül választhat:<br><ul><li>Engedélyezett URL-címek megadása (csak ezek az URL-címek engedélyezettek, más webhelyek nem érhetők el):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Tiltott URL-címek megadása (minden más webhely elérhető lesz):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|A kulcs megfelelő értéke egy URL-címlista. Az engedélyezni vagy letiltani kívánt URL-címeket egyetlen értékként kell megadni, az egyes tételeket függőleges vonal **&#124;** karakterrel elválasztva egymástól.<br><br>Példák:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Mindkét kulcsot ne adja meg. Ha ugyanahhoz a felhasználóhoz mindkét kulcs meg van adva, akkor az engedélyezett kulcs érvényesül, mert az jelent nagyobb korlátozást.
>Ügyeljen továbbá arra, hogy ne tiltson le fontos webhelyeket, például a céges webhelyet.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Az engedélyezett és a blokkolt URL-címek URL-formátuma
Az alábbi táblázat azokat az engedélyezett formátumokat és helyettesítő karaktereket ismerteti, amelyek az URL-címek engedélyezési és blokklistákban való megadásakor használhatók:

- A csillag (**&#42;**) helyettesítő karakter és szimbólum a megengedett minták alábbi listájának szabályai szerint használható:

- Az URL-címek listába történő bevitelekor ellenőrizze, hogy az URL-címet a **http** vagy a **https** előtaggal adta-e meg.

- A címben portszámokat is megadhat. Ha nem ad meg portszámot, a rendszer a következő értékeket használja:

  -   HTTP – 80-as port

  -   HTTPS – 443-as port

  A portszám helyettesítő karakterrel való megadása nem támogatott. Például a `http://www.contoso.com:;` és a `http://www.contoso.com: /;` nem támogatottak.

- Az alábbi táblázat az URL-címek megadásakor használható mintákat ismerteti:

|                  URL-cím                  |                     Részletek                      |                                                Egyezik                                                |                                Nem egyezik                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        `http://www.contoso.com`         |              Egyetlen lapnak felel meg               |                                            `www.contoso.com`                                            |  `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`contoso.com`/   |
|          `http://contoso.com`           |              Egyetlen lapnak felel meg               |                                             `contoso.com/`                                              | `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com` |
|    `http://www.contoso.com/&#42;`     | Az összes `www.contoso.com` karakterlánccal kezdődő URL-cím |      `www.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com/videos/tvshows`      |              `host.contoso.com`<br /><br />`host.contoso.com/images`              |
|    `http://*.contoso.com/*`     |     A contoso.com összes altartománya     | `developer.contoso.com/resources`<br /><br />`news.contoso.com/images`<br /><br />`news.contoso.com/videos` |                               `contoso.host.com`                                |
|     `http://www.contoso.com/images`     |             Egyetlen mappa              |                                        `www.contoso.com/images`                                         |                          `www.contoso.com/images/dogs`                          |
|       `http://www.contoso.com:80`       |  Egyetlen lap, amely portszámot használ   |                                       `http://www.contoso.com:80`                                       |                                                                               |
|        `https://www.contoso.com`        |          Egyetlen biztonságos lap           |                                        `https://www.contoso.com`                                        |                            `http://www.contoso.com`                             |
| `http://www.contoso.com/images/&#42;` |    Egyetlen mappa és annak összes almappája    |                  `www.contoso.com/images/dogs`<br /><br />`www.contoso.com/images/cats`                   |                            `www.contoso.com/videos`                             |

- Az alábbi példák nem engedélyezett beviteleket szemléltetnek:

  - `*.com`

  - `*.contoso/*`

  - `www.contoso.com/*images`

  - `www.contoso.com/*images*pigs`

  - `www.contoso.com/page*`

  - IP-címek

  - `https://*`

  - `http://*`

  - `http://www.contoso.com:*`

  - `http://www.contoso.com: /*`
## <a name="opening-links-within-the-intune-managed-browser-vs-microsoft-edge"></a>A hivatkozások Intune Managed Browser böngészőben való megnyitása, összevetve a következőben való megnyitással: Microsoft Edge 

Az Intune Managed Browser és a Microsoft Edge most szabályzat által felügyelt böngészők vagy védett böngészők minősülnek. Jelenleg a meglévő alkalmazásvédelmi szabályzatok szerint a forgatókönyvtől és platformtól függően az Intune felügyelt alkalmazásainak webes hivatkozásai egy meghatározott böngészőben nyílnak meg. 

Androidon: 
* Ha a felhasználó rendelkezik mindkét Managed Browser és az eszköz letöltése a Microsoft Edge a felügyelt böngészőben nyílik meg. Annak érdekében, hogy a Microsoft Edge helyett a Managed Browser nyitotta, állítsa be az alkalmazás konfigurációs beállítás "com.microsoft.intune.useEdge" "true" az összes Intune által felügyelt alkalmazások egy házirend által felügyelt böngésző szükséges.  
* A Microsoft Edge megnyílik, ha csak a Microsoft Edge az eszközön, és a szabályzat vonatkozik.
* Felügyelt böngésző megnyílik, ha csak a Managed Browser az eszközön, és a szabályzat vonatkozik. 

Az iOS rendszeren, ha az alkalmazásokban integrálva van az Intune SDK for iOS 9.0.9+ verziója: 
* A Managed Browser Ha MB-ot és az Edge is az eszközön, kivéve, ha az alkalmazás konfigurációs beállítás "com.microsoft.intune.useEdge" értéke "true" az összes Intune által felügyelt alkalmazások egy házirend által felügyelt böngésző szükséges **vagy** Microsoft él, ha a Microsoft Edge telepítve van, és megkapta a szabályzatot. 
* A Microsoft Edge Ha csak a Microsoft Edge van az eszközön, a célja, és megkapta a szabályzatot. 
* Felügyelt böngésző Ha csak a Managed Browser az eszközön, a célja, és megkapta a szabályzatot.

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>A felügyelt alkalmazások naplóinak elérése a Managed Browser használatával iOS rendszeren

A végfelhasználók, akiknek az iOS-eszközén telepítve van a Managed Browser, a Microsoft által közzétett összes alkalmazás felügyeleti állapotát megtekinthetik. Elküldhetik a naplófájlokat a felügyelt iOS-eszköz hibaelhárítása céljából.

1. Nyissa meg az iOS **beállításait**.
2. Válassza ki a **Managed Browser** alkalmazás beállításait.
3. Az **Intune-diagnosztika engedélyezése** kapcsolóval állítsa át a böngészőt hibaelhárítási módba.
4. Nyissa meg a **Managed Browsert**. Kattintson az **Intune-alkalmazás állapotának megtekintése** lehetőségre az egyéni alkalmazásszabályzat-beállítások áttekintéséhez.
5. Az **Első lépések**, majd a **Naplók megosztása** vagy a **Naplók küldése a Microsoftnak** lehetőséget választva küldje el a hibaelhárítási naplófájlokat a rendszergazdának vagy a Microsoftnak.

A böngésző az alkalmazásban is megnyitható hibaelhárítási módban.

1. Nyissa meg a Managed Browsert.
2. A címsorba gépelje be a következőt: `about:intunehelp`
A böngésző hibaelhárítási módban indul el.

Az alkalmazásnaplókban tárolt beállítások listáját az [Alkalmazásvédelmi naplók áttekintése a Managed Browserben](app-protection-policy-settings-log.md) című témakörben találja.

## <a name="security-and-privacy-for-the-managed-browser"></a>Biztonság és adatvédelem a Managed Browser használatánál

-   A Managed Browser nem használja a felhasználók eszközein futó beépített böngésző egyedi beállításait. Ezekhez a beállításokhoz a Managed Browser nem fér hozzá.

-   Ha engedélyezi az **Egyszerű PIN-kód megkövetelése a hozzáféréshez** vagy a **Vállalati hitelesítő adatok megkövetelése a hozzáféréshez** beállítást a Managed Browser böngészőhöz hozzárendelt alkalmazásvédelmi szabályzatban, és a felhasználó a hitelesítési lapon a súgóhivatkozásra kattint, bármely internetes webhelyet elérhet, függetlenül attól, hogy azok hozzá lettek-e adva a felügyeltböngésző-szabályzat blokklistájához.

-   A Managed Browser csak akkor képes blokkolni a hozzáférést a webhelyekhez, ha azokat közvetlenül érik el. Nem blokkolja a hozzáférést, ha a felhasználó köztes szolgáltatások (például egy fordítási szolgáltatás) használatával éri el a webhelyet.

-   A hitelesítés lehetővé tétele és az Intune-dokumentáció elérése érdekében a **&#42;.microsoft.com** mentesül az engedélyezési és blokkolási beállítások alól, és mindig engedélyezve van.

### <a name="turn-off-usage-data"></a>A használatra vonatkozó adatok kikapcsolása
A Microsoft termék- és szolgáltatásfejlesztési célból automatikus módszerekkel név nélküli adatokat gyűjt a Managed Browser teljesítményéről és használatáról. A felhasználók kikapcsolhatják az adatgyűjtést az eszköz **Használati adatok** beállításával. Nem tudja befolyásolni ezen adatok gyűjtését.

-   Az iOS-eszközökön nem nyithatók meg azok a felhasználók által felkeresett webhelyek, amelyek lejárt vagy nem megbízható tanúsítvánnyal rendelkeznek.

## <a name="next-steps"></a>További lépések

- [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md) 
