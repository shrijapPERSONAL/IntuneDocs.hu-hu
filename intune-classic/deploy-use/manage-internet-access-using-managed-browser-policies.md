---
title: Webes hozzáférés felügyelete a Managed Browser alkalmazással
description: Telepítheti a Managed Browser alkalmazást, amellyel korlátozhatja a webböngészést és a webes adatok egyéb alkalmazásokba történő átvitelét.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9781af943dbfb782cf367257127021473e35c168
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A felügyelt böngésző egy webböngésző-alkalmazás, amelyet a Microsoft Intune használatával helyezhet üzembe a szervezetében. A felügyeltböngésző-szabályzatban megadható egy engedélyezési vagy blokklista, amellyel korlátozhatók a felügyelt böngésző felhasználói által felkereshető webhelyek.

Mivel az alkalmazás integrálva van az Intune SDK-val, alkalmazásvédelmi szabályzatok is alkalmazhatók rá. Ezekkel többek között szabályozhatja a kivágási, másolási és beillesztési műveleteket, és ezzel megakadályozhatja képernyőfelvételek készítését, vagy szabályozhatja azt is, hogy azok a tartalmak, amelyek hivatkozásaira a felhasználók kattintanak, csak felügyelt alkalmazásokban nyílhassanak meg. További részletekért lásd: [Mobilalkalmazás-kezelési házirendek konfigurálása és telepítése a Microsoft Intune-konzolon](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

>[!IMPORTANT]
>A Managed Browser alkalmazás csak akkor fogadja és alkalmazza az Intune alkalmazásvédelmi szabályzatait, ha az eszközön egy másik alkalmazás alkalmazásvédelmi szabályzatot fogadott.<br><br> Ezen felül, ha a felhasználók a felügyelt böngészőt az App Store áruházból telepítik, és azt nem az Intune felügyeli, a következők történnek:<br /><br />
>**iOS** – A felügyelt böngészőalkalmazás egyszerű webböngészőként használható, de néhány szolgáltatás nem érhető el, és nem fér hozzá a többi, Intune által felügyelt alkalmazás adataihoz.<br />
**Android** – A felügyelt böngészőalkalmazás nem használható.<br /><br />
Ha a felhasználók a felügyelt böngészőt iOS 9-es verziónál régebbi verziójú iOS-eszközre telepítik, azt az Ön által létrehozott szabályzatok egyike sem fogja felügyelni. Ha a felhasználók biztosítani szeretnék, hogy az Intune felügyelje a böngészőt, el kell távolítaniuk az alkalmazást, mielőtt Ön felügyelt alkalmazásként telepítené a számukra. Ha a felhasználó iOS 9-es vagy újabb rendszeren telepíti a felügyelt böngészőt, a rendszer a felhasználót annak engedélyezésére kéri, hogy ez szabályzattal felügyelhető legyen.

Felügyeltböngésző-szabályzatokat a következő eszköztípusok esetében hozhat létre:

-   Android 4 vagy újabb rendszerű eszközök

-   iOS 8.0 vagy újabb rendszerű eszközök

Az Intune által felügyelt böngésző támogatja a [Microsoft Intune alkalmazási partnerektől származó](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) webes tartalom megnyitását.

## <a name="create-a-managed-browser-policy"></a>Felügyeltböngésző-szabályzat létrehozása.

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet.

2.  Konfigurálja a **Szoftverek** kategória alábbi házirend-típusainak egyikét:

    -   **Managed Browser (Android 4 és újabb verziók)**

    -   **Managed Browser (iOS 8.0 és újabb verziók)**

    Részletesebb tájékoztatás a szabályzatok használatáról és telepítéséről: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Az alábbi információk a felügyeltböngésző-szabályzat beállításainak konfigurálásához nyújtanak segítséget:

    - **Név**. Egyedi nevet adjon a felügyelt böngészőnek, hogy könnyen azonosíthassa az Intune konzolon.
    - **Leírás**. Adjon meg egy leírást, amely áttekintést nyújt a felügyeltböngésző-szabályzatról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a böngésző megkeresését.
    - **Engedélyezési vagy tiltólista beállítása azon URL-címek korlátozásához, amelyeket a Managed Browser (felügyelt böngésző) megnyithat**. Válasszon az alábbi lehetőségek közül:
        - **Csak az alábbiakban felsorolt URL-címek megnyitásának engedélyezése a felügyelt böngésző számára**. Azon URL-címek listájának megadása, amelyeket a felügyelt böngésző megnyithat.
        - **Az alábbiakban felsorolt URL-címek megnyitásának tiltása a felügyelt böngésző számára**. Azon URL-címek listájának megadása, amelyeket a felügyelt böngésző nem nyithat meg.
**Megjegyzés:** Ugyanabban a felügyeltböngésző-szabályzatban nem adhat meg egyszerre engedélyezett és tiltott URL-címeket is.
Az URL-címek megadható formátumáról további informácót a jelen témakör **Engedélyezett és blokkolt URL-címek URL-formátuma** című szakasza tartalmaz.

4.  Ha elkészült, válassza a **Házirend mentése** elemet.

Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg.

## <a name="create-a-deployment-for-the-managed-browser-app"></a>A felügyelt böngészőalkalmazás telepítésének létrehozása
Miután létrehozta a felügyeltböngésző-szabályzatot, létrehozhatja a felügyelt böngészőalkalmazás szoftvertelepítését, és hozzárendelheti a létrehozott felügyeltböngésző-szabályzathoz.

> [!IMPORTANT]
> A felügyeltböngésző-szabályzatokat az Intune egyéb szabályzataitól eltérő módon kell telepíteni. Ezt a szabályzattípust hozzá kell rendelni a felügyelt böngésző szoftvercsomagjához.

Telepítse az alkalmazást, és ügyeljen arra, hogy a **Mobilalkalmazások kezelései** lapon a felügyeltböngésző-szabályzat kiválasztásával hozzá kell rendelnie a szabályzatot az alkalmazáshoz.

Az alkalmazások telepítésével kapcsolatos részletekért lásd: [Alkalmazások telepítése Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Felügyelt böngésző – biztonság és adatvédelem

-   Az IOS-eszközökön nem nyithatók meg azok a felhasználók által felkeresett webhelyek, amelyek lejárt vagy nem megbízható tanúsítvánnyal rendelkeznek.

-   A felügyelt böngésző nem használja a felhasználók eszközein futó beépített böngésző beállításait. Ennek az az oka, hogy a felügyelt böngésző nem fér hozzá ezekhez a beállításokhoz.

-   Ha engedélyezi az **Egyszerű PIN-kód megkövetelése a hozzáféréshez** vagy a **Vállalati hitelesítő adatok megkövetelése a hozzáféréshez** beállítást a felügyelt böngészőhöz hozzárendelt mobilalkalmazás-felügyeleti szabályzatban, és a felhasználó a hitelesítési lapon a súgóhivatkozásra kattint, bármely internetes webhelyet elérhet, függetlenül attól, hogy azok hozzá lettek-e adva a felügyeltböngésző-szabályzat blokklistájához.

-   A felügyelt böngésző csak akkor képes blokkolni a hozzáférést a webhelyekhez, ha azokat közvetlenül érik el. Nem képes blokkolni a hozzáférést, ha a felhasználó köztes szolgáltatások (például egy fordítási szolgáltatás) használatával éri el a webhelyet.

-   A hitelesítés lehetővé tétele és az Intune-dokumentáció elérése érdekében a **&#42;.microsoft.com** mentesül az engedélyezési és blokkolási beállítások alól, és mindig engedélyezve van.

### <a name="turn-off-usage-data"></a>A használatra vonatkozó adatok kikapcsolása
A Microsoft termék- és szolgáltatásfejlesztési célból automatikus módszerekkel név nélküli adatokat gyűjt a felügyelt böngésző teljesítményéről és használatáról. A felhasználók kikapcsolhatják az adatgyűjtést az eszköz **Használati adatok** beállításával. Nem tudja befolyásolni ezen adatok gyűjtését.

## <a name="reference-information"></a>Kapcsolódó információk

### <a name="url-format-for-allowed-and-blocked-urls"></a>Az engedélyezett és a blokkolt URL-címek URL-formátuma
Az alábbi táblázat azokat az engedélyezett formátumokat és helyettesítő karaktereket ismerteti, amelyek az URL-címek engedélyezési és blokklistákban való megadásakor használhatók:

- A csillag (**&#42;**) helyettesítő karakter és szimbólum a megengedett minták alábbi listájának szabályai szerint használható.

- Az URL-címek listába történő bevitelekor ellenőrizze, hogy az URL-címet a **http** vagy a **https** előtaggal adta-e meg.

- A címben portszámokat is megadhat. Ha nem ad meg portszámot, a rendszer a következő értékeket használja:

  -   HTTP – 80-as port

  -   HTTPS – 443-as port

  A portszám helyettesítő karakterrel való megadása nem támogatott. Például a <strong>http&colon;//www&period;contoso&period;com:*;</strong> és a <strong>http&colon;//www&period;contoso&period;com: /*;</strong> nem támogatott.

- Az alábbi táblázat az URL-címek megadásakor használható mintákat ismerteti:

|                  URL-cím                  |                     Részletek                      |                                                Egyezik                                                |                                Nem egyezik                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        http://www.contoso.com         |              Egyetlen lapnak felel meg               |                                            www.contoso.com                                            |  host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/   |
|          http://contoso.com           |              Egyetlen lapnak felel meg               |                                             contoso.com/                                              | host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com |
|    <http://www.contoso.com/&#42>;     | Az összes www.contoso.com karakterlánccal kezdődő URL-cím |      www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows      |              host.contoso.com<br /><br />host.contoso.com/images              |
|    http://&#42;.contoso.com/&#42;     |     A contoso.com összes altartománya     | developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos |                               contoso.host.com                                |
|     http://www.contoso.com/images     |             Egyetlen mappa              |                                        www.contoso.com/images                                         |                          www.contoso.com/images/dogs                          |
|       http://www.contoso.com:80       |  Egyetlen lap, amely portszámot használ   |                                       http://www.contoso.com:80                                       |                                                                               |
|        https://www.contoso.com        |          Egyetlen biztonságos lap           |                                        https://www.contoso.com                                        |                            http://www.contoso.com                             |
| <http://www.contoso.com/images/&#42>; |    Egyetlen mappa és annak összes almappája    |                  www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats                   |                            www.contoso.com/videos                             |

- Az alábbi példák nem engedélyezett beviteleket szemléltetnek:

  - &#42;.com

  - &#42;.contoso/&#42;

  - www.contoso.com/&#42;images

  - www.contoso.com/&#42;images&#42;pigs

  - www.contoso.com/page&#42;

  - IP-címek

  - https://&#42;

  - http://&#42;

  - http://www.contoso.com:&#42;

  - http://www.contoso.com: /&#42;

### <a name="how-conflicts-between-the-allow-and-block-list-are-resolved"></a>Az engedélyezési lista és a blokklista közötti ütközések feloldása
Ha egy eszközön több felügyeltböngésző-szabályzatot léptet érvénybe, és ezek beállításai ütköznek, a rendszer mind a módot (engedélyezés vagy letiltás), mind az URL-listákat kiértékeli. Ütközés esetén a következőképpen viselkedik:

-   Ha a módok mindegyik szabályzatban azonosak, de az URL-listák eltérőek, az URL-címek használatát nem kényszeríti ki az eszközön.

-   Ha a módok mindegyik szabályzatban eltérőek, de az URL-listák azonosak, az URL-címek használatát nem kényszeríti ki az eszközön.

-   Ha az eszközön első alkalommal léptet érvénybe felügyeltböngésző-szabályzatot, és két szabályzat ütközik, a rendszer nem kényszeríti ki az URL-cím használatát az eszközön. A konfliktusokat a **Házirend** munkaterület **Házirendütközések** csomópontjában tekintheti meg.

-   Ha egy eszközön már érvénybe léptetett felügyeltböngésző-szabályzatot, és egy második érvénybe léptetett szabályzat ütköző beállításokat tartalmaz, az eredeti beállítások nem módosulnak az eszközön. A konfliktusokat a **Házirend** munkaterület **Házirendütközések** csomópontjában tekintheti meg.
