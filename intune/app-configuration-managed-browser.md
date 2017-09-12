---
title: "Webes hozzáférés felügyelete a Managed Browser alkalmazással"
titlesuffix: Azure portal
description: "Telepítheti a Managed Browser alkalmazást, amellyel korlátozhatja a webböngészést és a webes adatok egyéb alkalmazásokba történő átvitelét.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8534b51c89cd8dedc674468c5299b79a29f608
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Managed Browser egy webböngésző-alkalmazás, amely nyilvános alkalmazásáruházakból tölthető le, és a szervezeten belül használható. A Managed Browser az Intune-nal többféleképpen konfigurálható:
- Egyszeri bejelentkezéshez használható a MyApps szolgáltatással, és használatával a webes adatok védelme mellett érhetők el vállalati helyek és SaaS-alkalmazások.
- URL-címek és tartománynevek listájával is konfigurálható, és ezzel meghatározható, hogy a felhasználó milyen helyeket kereshet fel vállalati környezetben.
- Előre beállítható a kezdőlapja és a választott könyvjelzők.

Mivel az alkalmazás integrálva van az Intune SDK-val, alkalmazásvédelmi szabályzatok is alkalmazhatók rá, többek között a következők célokra:
- Kivágás, másolás és beillesztés műveletek korlátozása
- Képernyőmentés megakadályozása
- Annak biztosítása, hogy a felhasználók által kiválasztott tartalomra mutató hivatkozások csak más felügyelt alkalmazásokban nyíljanak meg.

További információt a [Mik azok az alkalmazásvédelmi szabályzatok?](/intune/app-protection-policy) című témakörben talál.

Ezeket a beállításokat azokra az eszközökre alkalmazhatja, amelyek regisztrálva vannak az Intune-ban vagy egy másik eszközkezelő termékben, de olyan eszközökre is, amelyek nem állnak felügyelet alatt.

Ha a felhasználók telepítik a Managed Browser alkalmazást az alkalmazásáruházból, és azt nem az Intune felügyeli, akkor az egyszerű webböngészőként használható, amely a Microsoft MyApps webhelyen keresztül támogatja az egyszeri bejelentkezést. A felhasználók közvetlenül a MyApps webhelyére vannak irányítva, ahol megjelenik az összes számukra kiosztott SaaS-alkalmazás.
Ha a Managed Browsert nem az Intune felügyeli, más Intune által kezelt alkalmazások adatait nem lehet elérni vele. 

A Managed Browser nem támogatja a Secure Sockets Layer 3-as verziójú (SSLv3) titkosítási protokollját.

Managed Browser-szabályzatokat a következő eszköztípusokhoz hozhat létre:

-   Android 4 vagy újabb rendszerű eszközök

-   iOS 8.0 vagy újabb rendszerű eszközök

>[!IMPORTANT]
>2017 októberétől az Intune Managed Browser alkalmazás Androidon kizárólag az Android 4.4-es vagy újabb rendszerű eszközöket fogja támogatni. Az Intune Managed Browser alkalmazás iOS-en kizárólag az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni.
>Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.


Az Intune Managed Browser támogatja a [Microsoft Intune alkalmazási partnerektől származó](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) webes tartalom megnyitását.

## <a name="create-a-managed-browser-app-configuration"></a>A Managed Browser alkalmazás konfigurációjának létrehozása

1.  Jelentkezzen be az Azure Portalra.
2.  Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3.  A felügyeleti lista **Mobilalkalmazások** paneljén válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget.
4.  Az **Alkalmazáskonfigurációs szabályzatok** panelen kattintson a **Hozzáadás** lehetőségre.
5.  Az **Alkalmazáskonfiguráció hozzáadása** panelen az alkalmazáskonfigurációs beállításokhoz írja be a **Nevet** és a **Leírást** (ez utóbbi nem kötelező).
6.  Az **Eszközregisztráció** típusaként válassza a **Nem az Intune-nal regisztrált** lehetőséget.
7.  Válassza a **Kötelező alkalmazások kiválasztása** elemet, majd a **Célalkalmazások** panelen válassza a **Managed Browser** lehetőséget iOS-hez, Androidhoz vagy igény szerint mindkettőhöz.
8.  Az **OK** kiválasztásával visszatérhet az **Alkalmazáskonfiguráció hozzáadása** panelre.
9.  Kattintson a **Konfigurációs beállítások** elemre. A **Konfigurálás** panelen kulcs-érték párok definiálásával adhatja meg a Managed Browserhez szükséges konfigurációkat. A jelen témakör későbbi részeiben további információt talál a definiálható kulcs-érték párokról.
10. Ha elkészült, válassza az **OK** elemet.
11. Az **Alkalmazáskonfiguráció hozzáadása** panelen válassza a **Létrehozás** elemet.
12. Ezzel létrejön az új konfiguráció, és megjelenik az **Alkalmazáskonfiguráció** panelen.

>[!IMPORTANT]
>A Managed Browser jelenleg automatikus regisztrációra hagyatkozik. Az alkalmazáskonfigurációk érvényre jutásához az szükséges, hogy az eszközön lévő alkalmazások egyikét már az Intune alkalmazásvédelmi szabályzatai felügyeljék.

## <a name="assign-the-configuration-settings-you-created"></a>A létrehozott konfigurációs beállítások hozzárendelése

A beállításokat Azure AD-beli felhasználói csoportokhoz lehet hozzárendelni. Ha az illető felhasználó rendelkezik telepített Managed Browser alkalmazással, akkor az alkalmazás felügyelete a megadott beállításokkal történik.

1. Az Intune mobilalkalmazás-kezelési irányítópult **Beállítások** paneljén válassza az **Alkalmazáskonfiguráció** lehetőséget.
2. A listából válassza ki a hozzárendelni kívánt alkalmazáskonfigurációt.
3. A következő panelen válassza a **Felhasználói csoportok** lehetőséget.
4. A **Felhasználói csoportok** panelen válassza ki azt az Azure AD-csoportot, amelyhez az alkalmazáskonfigurációt hozzá szeretné rendelni, majd válassza az **OK** elemet.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Alkalmazásproxy-beállítások konfigurálása a Managed Browser alkalmazáshoz

Az Intune Managed Browser és az [Azure AD Alkalmazásproxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) együtt használva támogathatja az iOS- és Android-eszközök felhasználóit a következő helyzetekben:

- Egy felhasználó letölti a Microsoft Outlook alkalmazást és bejelentkezik. Az Intune alkalmazásvédelmi szabályzatai automatikusan érvényre jutnak. Titkosítják az elmentett adatokat, és megakadályozzák, hogy a felhasználó vállalati fájlokat továbbítson az eszközön lévő nem felügyelt alkalmazások vagy helyek felé. Kiköthető, hogy amikor a felhasználó egy intranetes webhelyre mutató hivatkozásra kattint az Outlookban, akkor a hivatkozás más böngésző helyett a Managed Browser alkalmazásban nyíljon meg. A Managed Browser felismeri, hogy az adott intranetes webhely az Alkalmazásproxyn keresztül megnyílt a felhasználónak. A felhasználót automatikusan az Alkalmazásproxyn keresztül irányítja át, hogy csak minden lehetséges többtényezős hitelesítés és feltételes hozzáférés ellenőrzése után érhesse el az intranetes helyet. Ez a webhely, amely távoli felhasználók számára korábban nem volt megtalálható, most már elérhető, és az Outlook-beli hivatkozás is az elvárható módon működik.
- Egy távoli felhasználó megnyitja a Managed Browser alkalmazást, és a belső URL-cím segítségével megnyit egy intranetes webhelyet. A Managed Browser felismeri, hogy az adott intranetes webhely az Alkalmazásproxyn keresztül megnyílt a felhasználónak. A felhasználót automatikusan az Alkalmazásproxyn keresztül irányítja át, hogy csak minden lehetséges többtényezős hitelesítés és feltételes hozzáférés ellenőrzése után érhesse el az intranetes helyet. Ez a webhely, amely távoli felhasználók számára korábban nem volt megtalálható, most már elérhető.

### <a name="before-you-start"></a>Előkészületek

- Állítsa be a belső alkalmazásokat az Azure AD alkalmazásproxyban.
    - Az Alkalmazásproxy konfigurálásáról és az alkalmazások közzétételéről a [telepítési dokumentációban]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started) olvashat. 
    - A Managed Browser alkalmazás 1.2.0-s vagy annál újabb verzióját kell használnia.
    - A Managed Browser felhasználói rendelkezzenek az alkalmazáshoz rendelt [Intune alkalmazásvédelmi szabályzattal]( app-protection-policy.md).

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>1. lépés: Automatikus átirányítás engedélyezése az Outlookból a Managed Browserhez
Az Outlookot olyan alkalmazásvédelmi szabályzattal kell konfigurálni, amelyben engedélyezett a **Webes tartalom megjelenítésének korlátozása a Managed Browser alkalmazásra** beállítás.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>2. lépés: Alkalmazáskonfigurációs szabályzat hozzárendelése a Managed Browser alkalmazáshoz.
Ez az eljárás az Alkalmazásproxy átirányítás használatára konfigurálja a Managed Browser alkalmazást. A Managed Browser alkalmazás konfigurációjának meghatározására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|||
|-|-|
|Kulcs|Érték|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>A Managed Browser kezdőlapjának beállítása

Ezzel a beállítással adható meg a kezdőlap, amelyet a felhasználók a Managed Browser elindításakor vagy új lap megnyitásakor látnak. A Managed Browser alkalmazás konfigurációjának meghatározására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|||
|-|-|
|Kulcs|Érték|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Adjon meg egy érvényes URL-címet. A helytelen URL-címek biztonsági intézkedésként le vannak tiltva.<br>Példa: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>A Managed Browser könyvjelzőinek beállítása

Ezzel a beállítással konfigurálhatók a Managed Browser felhasználói számára elérhető könyvjelzők.

- Ezeket a könyvjelzőket a felhasználók nem törölhetik és nem módosíthatják
- Ezek a könyvjelzők a lista tetején jelennek meg. A felhasználók által készített könyvjelzők ezek alá kerülnek.

A Managed Browser alkalmazás konfigurációjának meghatározására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|||
|-|-|
|Kulcs|Érték|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|Ennek a konfigurációnak egy könyvjelzőlista az értéke. Minden könyvjelző egy címből és egy URL-címből áll. A címet és az URL-címet a **&#124;** karakter választja el.<br><br>Példa: **Microsoft Bing&#124;https://www.bing.com**<br><br>Több könyvjelző megadásakor az egyes párokat a **&#124;&#124;** karakter választja el.<br><br>Példa: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Engedélyezett és letiltott URL-címek meghatározása a Managed Browser számára

A Managed Browser alkalmazás konfigurációjának meghatározására vonatkozó eljárással adja meg az alábbi kulcs-érték párt:

|||
|-|-|
|Kulcs|Érték|
|A következő lehetőségek közül választhat:<br><br>- Engedélyezett URL-címek megadásához (kizárólag ezek az URL-címek engedélyezettek, más webhelyek nem lesznek elérhetőek): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Tiltott URL-címek megadásához (minden más webhely elérhető lesz): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|A kulcs megfelelő értéke egy URL-címlista. Az engedélyezni vagy letiltani kívánt URL-címeket egyetlen értékként kell megadni, az egyes tételeket függőleges vonal **&#124;** karakterrel elválasztva egymástól.<br><br>Példák:<br><br>-**URL1&#124;URL2&#124;URL3**<br>-**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Mindkét kulcsot ne adja meg. Ha ugyanahhoz a felhasználóhoz mindkét kulcs meg van adva, akkor az engedélyezett kulcs érvényesül, mert az jelent nagyobb korlátozást.
>Ügyeljen továbbá arra, hogy ne tiltson le fontos webhelyeket, például a céges webhelyet.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Az engedélyezett és a blokkolt URL-címek URL-formátuma
Az alábbi táblázat azokat az engedélyezett formátumokat és helyettesítő karaktereket ismerteti, amelyek az URL-címek engedélyezési és blokklistákban való megadásakor használhatók:

-   A csillag (**&#42;**) helyettesítő karakter és szimbólum a megengedett minták alábbi listájának szabályai szerint használható:

-   Az URL-címek listába történő bevitelekor ellenőrizze, hogy az URL-címet a **http** vagy a **https** előtaggal adta-e meg.

-   A címben portszámokat is megadhat. Ha nem ad meg portszámot, a rendszer a következő értékeket használja:

    -   HTTP – 80-as port

    -   HTTPS – 443-as port

    A portszám helyettesítő karakterrel való megadása nem támogatott. Például a **http&colon;//www&period;contoso&period;com:*;** és a *&colon;http&period;//www&period;contoso*com: /*;* nem támogatott.

-   Az alábbi táblázat az URL-címek megadásakor használható mintákat ismerteti:

|URL-cím|Részletek|Egyezik|Nem egyezik|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Egyetlen lapnak felel meg|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Egyetlen lapnak felel meg|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Az összes www.contoso.com karakterlánccal kezdődő URL-cím|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|A contoso.com összes altartománya|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Egyetlen mappa|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Egyetlen lap, amely portszámot használ|http://www.contoso.com:80|
    |https://www.contoso.com|Egyetlen biztonságos lap|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Egyetlen mappa és annak összes almappája|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Az alábbi példák nem engedélyezett beviteleket szemléltetnek:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP-címek

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

## <a name="security-and-privacy-for-the-managed-browser"></a>Biztonság és adatvédelem a Managed Browser használatánál

-   Az IOS-eszközökön nem nyithatók meg azok a felhasználók által felkeresett webhelyek, amelyek lejárt vagy nem megbízható tanúsítvánnyal rendelkeznek.

-   A Managed Browser nem használja a felhasználók eszközein futó beépített böngésző egyedi beállításait. Ezekhez a beállításokhoz a Managed Browser nem fér hozzá.

-   Ha engedélyezi az **Egyszerű PIN-kód megkövetelése a hozzáféréshez** vagy a **Vállalati hitelesítő adatok megkövetelése a hozzáféréshez** beállítást a Managed Browser böngészőhöz hozzárendelt alkalmazásvédelmi szabályzatban, és a felhasználó a hitelesítési lapon a súgóhivatkozásra kattint, bármely internetes webhelyet elérhet, függetlenül attól, hogy azok hozzá lettek-e adva a felügyeltböngésző-szabályzat blokklistájához.

-   A Managed Browser csak akkor képes blokkolni a hozzáférést a webhelyekhez, ha azokat közvetlenül érik el. Nem blokkolja a hozzáférést, ha a felhasználó köztes szolgáltatások (például egy fordítási szolgáltatás) használatával éri el a webhelyet.

-   A hitelesítés lehetővé tétele és az Intune-dokumentáció elérése érdekében a **&#42;.microsoft.com** mentesül az engedélyezési és blokkolási beállítások alól, és mindig engedélyezve van.

### <a name="turn-off-usage-data"></a>A használatra vonatkozó adatok kikapcsolása
A Microsoft termék- és szolgáltatásfejlesztési célból automatikus módszerekkel név nélküli adatokat gyűjt a Managed Browser teljesítményéről és használatáról. A felhasználók kikapcsolhatják az adatgyűjtést az eszköz **Használati adatok** beállításával. Nem tudja befolyásolni ezen adatok gyűjtését.


