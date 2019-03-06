---
title: iOS-es eszközfunkció-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg az Airprintet, az elrendezést, a kezdőképernyő, értesítések, közös használatú eszköz, egyszeri bejelentkezési és a Microsoft Intune webtartalomszűrő-beállításai iOS-eszközök konfigurálása a beállításokat. Az eszközkonfigurációs profil ezek a beállítások segítségével konfigurálhatja az iOS-eszközöket a szervezetben a másik Apple-funkciók használatához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/30/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e297c2c29c8f4c3b00aa88667adbddfce107fd7
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394534"
---
# <a name="ios-device-feature-settings-in-intune"></a>iOS-es eszközfunkció-beállítások az Intune-ban

Intune-ban a iOS felhasználók saját eszközeiken másik Apple-szolgáltatások használatához néhány beépített beállításokat tartalmaz. Például a rendszergazdák is vezérelheti, hogyan használja az iOS-felhasználók számára a AirPrint-nyomtatókra, alkalmazások és mappák hozzáadása a dockhoz és a kezdőképernyőn oldalak megjelenítése alkalmazásértesítések, eszköz címke részleteinek megjelenítése a zárolási képernyőn, egyszeri bejelentkezéses hitelesítéshez használja és hitelesítheti a felhasználókat a tanúsítványok.

Ez a cikk ezeket a beállításokat, és ismerteti az egyes beállítások funkciója.

## <a name="before-you-begin"></a>Előkészületek

[Hozzon létre egy IOS-es eszközkonfigurációs profil](device-features-configure.md#create-a-device-profile).

## <a name="airprint-settings"></a>AirPrint-beállítások

Ez a funkció lehetővé teszi, hogy iOS felhasználók számára ismert AirPrint-nyomtatókra történő nyomtatás.

1. A **beállítások**válassza **AirPrint**. Adja meg a következő tulajdonságokat az AirPrint-kiszolgáló:

    - **IP-cím**: Adja meg a nyomtató IPv4 vagy IPv6-címét. Ha állomásnevek nyomtatók azonosítására használ, a nyomtató billentyűparancsot a terminálon pingelésével beszerezheti az IP-címet. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
    - **Elérési út**: Az elérési út általában `ipp/print` nyomtatók a hálózaton. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
    - **Port**: Adja meg az AirPrint-célhely figyelőportja. Ha üresen hagyja ezt a tulajdonságot, az AirPrint az alapértelmezett portot használ. Az iOS 11.0-s vagy újabb érhető el.
    - **TLS**: Válasszon **engedélyezése** AirPrint-kapcsolatok a Transport Layer Security (TLS) biztonságos. Az iOS 11.0-s vagy újabb érhető el.

2. Válassza a **Hozzáadás** lehetőséget. Az AirPrint-kiszolgáló hozzáadásakor a listához. Számos AirPrint-kiszolgálókat is hozzáadhat.

    Emellett **importálás** ezeket az információkat egy vesszővel tagolt fájlt (.csv). Miután létrehozta a listában, akkor is **exportálása** az AirPrint-kiszolgálók listáját.

3. Amikor végzett, válassza ki a **OK** mentheti a listát.

Az IP-címét a nyomtatót, az erőforrás elérési útja és a portot kell AirPrinter-kiszolgálók hozzáadásához. A következő lépések bemutatják, hogyan beolvasni ezeket az információkat.

1. Az azonos helyi hálózatra (alhálózatra), az AirPrint-nyomtatókra csatlakoztatott Mac számítógépen nyissa meg a **terminálon** (a **/Applications/Utilities**).
2. A Terminalba írja be a `ippfind`, és válassza ki, adja meg.

    Megjegyzés: a nyomtató-információkat. Például előfordulhat, hogy vissza valami hasonló `ipp://myprinter.local.:631/ipp/port1`. Az első része a nyomtató neve. A második (`ipp/port1`) az erőforrás elérési útja.

3. A Terminalba írja be a `ping myprinter.local`, és válassza ki, adja meg.

   Megjegyzés: az IP-címet. Például előfordulhat, hogy vissza valami hasonló `PING myprinter.local (10.50.25.21)`.

4. IP-cím és az erőforrás elérési útja értéket használja. Ebben a példában az IP-cím van `10.50.25.21`, és az erőforrás-elérési út `/ipp/port1`.

## <a name="home-screen-layout-settings"></a>Kezdőképernyő-elrendezési beállítások

Ezek a beállítások konfigurálása az alkalmazások és mappák elrendezését az dock- és iOS-eszközök. Ez a funkció használatához az iOS-eszközök kell felügyelt módban kell és futtatása iOS 9.3 vagy újabb.

### <a name="dock"></a>Rögzítési hely

Használja a **Dock** beállítások legfeljebb 6 elemet vagy mappát ad hozzá az iOS-képernyőn elhelyezkedő dockhoz. Számos eszköz támogatja a kevesebb elemet. Például az iPhone-eszközök csak négy elem elhelyezését támogatják. Ebben az esetben csak az első négy elem hozzáadásakor látható az eszközön.

1. A **beállítások**válassza **kezdőképernyő-elrendezés (csak felügyelt)** > **Dock** > **Hozzáadás**. Akár is hozzáadhat **hat** (alkalmazások és mappák kombinált) elem a dock esetében.
2. A **típus**, felvehet egy **alkalmazás** vagy egy **mappa**.

    - **Alkalmazás felvétele**: Válassza ezt a lehetőséget, hogy alkalmazásokat adhasson a képernyőn elhelyezkedő dockhoz. Enter:

      - **Alkalmazásnév**: Adja meg az alkalmazás nevét. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
      - **Alkalmazásköteg-azonosító**: Adja meg az alkalmazás Csomagazonosítóját. Lásd: [Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások](#bundle-ids-for-built-in-ios-apps) (a jelen cikkben) vonatkozó példákat.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Mappa hozzáadása a**: Válassza ezt a beállítást, a mappa hozzáadása a képernyőn elhelyezkedő dockhoz. 

      Egy lap egy mappában hozzáadott alkalmazások balról vannak elrendezve, jobb oldalon, és ugyanabban a sorrendben, mint a listában. További alkalmazások, mint a lapon elfér is hozzáadhat, ha az alkalmazások áthelyezik egy másik lapot.

      1. Adjon meg egy **mappanevet**. Ez a név jelenik meg a felhasználók eszközén.
      2. Válasszon **Hozzáadás**, és adja meg a következő tulajdonságokat:

          - **Lap neve**: Adjon meg egy nevet a laphoz. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
          - **Alkalmazásnév**: Adja meg az alkalmazás nevét. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
          - **Alkalmazásköteg-azonosító**: Adja meg az alkalmazás Csomagazonosítóját. Lásd: [Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások](#bundle-ids-for-built-in-ios-apps) (a jelen cikkben) vonatkozó példákat.

      3. Válassza a **Hozzáadás** lehetőséget. Akár is hozzáadhat **20** dock oldalak az eszközhöz.
      4. Válassza ki **OK** a módosítások mentéséhez.

#### <a name="example"></a>Példa

A következő példában a dock képernyő csak a Safari, Mail és készletek alkalmazásokat jeleníti meg. A Mail alkalmazás ki van jelölve, a tulajdonságainak megjelenítéséhez:

![Példa iOS Dock beállításokra](./media/FfFiUcP.png)

A szabályzatot egy iPhone-eszközhöz társítja, az a tároló jelenik meg az alábbi képhez hasonló:

![Példa iOS Dock elrendezésére iPhone-eszközön](./media/bAgCe8F.png)

### <a name="pages"></a>Pages

Adja hozzá a kezdőképernyőn látható kívánt lapokat és az egyes lapokon megjelenő alkalmazásokat. Alkalmazások hozzáadása egy laphoz vannak elrendezve balról jobbra, ugyanabban a sorrendben, mint a listában. További alkalmazások, mint a lapon elfér is hozzáadhat, ha az alkalmazások áthelyezik egy másik lapot.

> [!TIP]
> Bármely kezdőlap kezdőképernyő és a lapok látható elemek átrendezéséhez húzza át, és el kell dobni ezeket.

1. A **beállítások**válassza **kezdőképernyő-elrendezés (csak felügyelt)** > **Oldalak** > **Hozzáadás**. Akár is hozzáadhat **40** oldalak az eszközön.
2. Adjon meg egy **lap neve**. Ezt a nevet használja, hogy az Azure Portalon, és *nem* jelenik meg az iOS-eszközön. 

    Válassza a **Hozzáadás** lehetőséget. Akár is hozzáadhat **60** elemek (alkalmazások és mappa együttes) az eszközön.

3. A **típus**, felvehet egy **alkalmazás** vagy egy **mappa**.

    - **Alkalmazás felvétele**: Ezt a lehetőséget az alkalmazások hozzáadása egy laphoz a képernyőn. Enter:

      - **Alkalmazásnév**: Adja meg az alkalmazás nevét. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
      - **Alkalmazásköteg-azonosító**: Adja meg az alkalmazás Csomagazonosítóját. Lásd: [Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások](#bundle-ids-for-built-in-ios-apps) (a jelen cikkben) vonatkozó példákat.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Mappa hozzáadása a**: Válassza ezt a beállítást, a mappa hozzáadása a képernyőn elhelyezkedő dockhoz. 

      Egy lap egy mappában hozzáadott alkalmazások balról vannak elrendezve, jobb oldalon, és ugyanabban a sorrendben, mint a listában. További alkalmazások, mint a lapon elfér is hozzáadhat, ha az alkalmazások áthelyezik egy másik lapot.

      1. Adjon meg egy **mappanevet**. Ez a név jelenik meg a felhasználók eszközén.
      2. Válasszon **Hozzáadás**, és adja meg a következő tulajdonságokat:

          - **Lap neve**: Adjon meg egy nevet a laphoz. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
          - **Alkalmazásnév**: Adja meg az alkalmazás nevét. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* jelenik meg az iOS-eszközön.
          - **Alkalmazásköteg-azonosító**: Adja meg az alkalmazás Csomagazonosítóját. Lásd: [Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások](#bundle-ids-for-built-in-ios-apps) (a jelen cikkben) vonatkozó példákat.

      3. Válassza a **Hozzáadás** lehetőséget.
      4. Válassza ki **OK** a módosítások mentéséhez.

#### <a name="example"></a>Példa

A következő példában egy új lap nevű **Contoso** kerül. Az oldal mutatja a barátok keresése és a beállítások alkalmazást. A beállítások alkalmazás ki van jelölve, a tulajdonságainak megjelenítéséhez:

![Példa iOS-kezdőképernyő beállítására](./media/Jc2OxyX.png)

A szabályzatot egy iPhone-eszközhöz társítja, az oldal jelenik meg az alábbi képhez hasonló:

![iOS-eszköz módosított kezdőképernyővel](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Alkalmazás-értesítések beállításai

Válassza ki az iOS-eszközök értesítések küldése hogyan telepített alkalmazások. Ezek a beállítások az iOS 9.3-at vagy újabb verziót futtató felügyelt eszközökön vannak támogatva.

1. A **beállítások**válassza **Alkalmazásértesítések (csak felügyelt)** > **Hozzáadás**:

    ![Alkalmazásértesítés hozzáadása iOS-profilt az Intune-ban](./media/ios-macos-app-notifications.png)

2. Adja meg a következő tulajdonságokat:

    - **Alkalmazás Csomagazonosítója**: Adja meg a **Alkalmazásköteg-azonosító** a hozzáadni kívánt alkalmazás. Lásd: [Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások](#bundle-ids-for-built-in-ios-apps) (a jelen cikkben) vonatkozó példákat.
    - **Alkalmazásnév**: Adja meg a hozzáadni kívánt alkalmazás nevét. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* látható az eszközön.
    - **Közzétevő**: Adja meg az alkalmazás kiadójának nevét adja hozzá. Ezt a nevet használja, hogy az Azure Portalon. Ez *nem* látható az eszközön.
    - **Értesítések**: **Engedélyezése** vagy **letiltása** az alkalmazás értesítéseket küldjön az eszközre.
       - **Megjelenítés az értesítési központban**: **Engedélyezése** lehetővé teszi az alkalmazás értesítéseket jeleníthet meg az értesítési központban. **Tiltsa le** megakadályozza, hogy az alkalmazás értesítések megjelenítése az értesítési központban.
       - **Megjelenítés a zárolási képernyőn**: Válassza ki **engedélyezése** megtekintéséhez jelenhetnek meg az eszköz zárolási képernyőjén. **Tiltsa le** megakadályozza, hogy az alkalmazás értesítések megjelenítése a zárolási képernyőn.
       - **Riasztás típusa**: Ha az eszköz zárolásának származó, válassza ki, hogyan az értesítés jelenik meg. A választható lehetőségek:
         - **Nincs**: Nincs értesítés jelenik meg.
         - **Banner**: Egy szalagcím rövid időre az értesítés mellett látható.
         - **Modális**: Az értesítés jelenik meg, és a felhasználó manuálisan kell bezárnia, az eszköz használatához a folytatás előtt.
       - **Jelvény az alkalmazásikonon**: Válassza ki **engedélyezése** egy jelvény hozzá az alkalmazás ikonjára. A jelvény azt jelenti, hogy az alkalmazás értesítést küld.
       - **A hangok**: Válassza ki **engedélyezése** , ha értesítés érkezik.

3. Válassza ki **OK** a módosítások mentéséhez. Folytassa a kívánt alkalmazásokat. Amikor végzett, válassza ki a **OK**.

## <a name="lock-screen-message-settings"></a>Zárolási képernyőjén üzenetek beállításai

Ezek a beállítások használatával egy egyéni üzenetet vagy szöveg megjelenítése a bejelentkezési ablakban és a zárolási képernyőn. Például megadhat egy "Ha megtalálja, térjen vissza..." üzenetet és eszközcímkeadatokat. 

Ez a funkció támogatja a rendszert futtató felügyelt eszközök:

- iOS 9.3 és újabb verziók

1. A **beállítások**válassza **(csak felügyelt) üzenet a zárolási képernyőn**.
2. Adja meg a következő beállításokat:

    - **Eszközcímke-információ**: Adja meg az eszköz az eszközcímke adatait. Például írja be a következőt: `Owned by Contoso Corp` vagy `Serial Number: {{serialnumber}}`. 

      A beírt szöveg jelenik meg a bejelentkezési ablakban és a zárolási képernyő, az eszközön.

    - **Lábjegyzet a zárolási képernyőn**: Ha az eszköz elveszett vagy ellopták, adjon meg egy, melyek segíthetnek az eszközt. Megadhatja a kívánt szöveget. Például: `If found, call Contoso at ...`.

    Eszközök tokenjeit is használható eszközre vonatkozó információk hozzáadása a mezőkhöz. Írja be például a sorozatszám megjeleníthető `Serial Number: {{serialnumber}}`. A zárolási képernyőn a szöveg látható hasonló `Serial Number 123456789ABC`. Változók megadásakor ügyeljen arra, hogy kapcsos zárójeleket `{{ }}`. [Alkalmazás-konfigurációs jogkivonatokról](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) használható változók listáját tartalmazza. Is `deviceName` vagy bármely más eszközspecifikus érték.

    > [!NOTE]
    > Változók nem érvényesíti a felhasználói felületen. Ennek eredményeképpen jelenhet meg helytelen adatbevitel a mentett profilokat. Ha például meg `{{Devicename}}` helyett `{{devicename}}`, akkor a szövegkonstanst látható az eszköz egyedi neve helyett.

3. Amikor végzett, válassza ki a **OK** a módosítások mentéséhez.

## <a name="single-sign-on-settings"></a>Egyszeri bejelentkezés beállításai

A legtöbb üzletviteli alkalmazás biztonsági célokból megkövetel bizonyos szintű felhasználóhitelesítést. Sok esetben a hitelesítést kell lennie a felhasználónak meg kell adnia a ugyanazokat a hitelesítő adatokat többször is, amely kellemetlen, a felhasználók számára. A felhasználói élmény javítása érdekében a fejlesztők hozhat létre alkalmazásokat, amelyek az egyszeri bejelentkezés (SSO) használatára. Egyszeri bejelentkezés használata csökkenti a felhasználónak meg kell adnia a hitelesítő adatok száma.

Egyszeri bejelentkezés használatára, hogy rendelkezik-e:

- Egy alkalmazást, amely a felhasználói hitelesítő adatok tárolójából az egyszeri bejelentkezés az eszközön a keresett vannak kódolva.
- Az iOS-eszközön való egyszeri bejelentkezéshez konfigurált Intune.

1. A **beállítások**válassza **egyszeri bejelentkezési**:

   ![Egyszeri bejelentkezés panel](./media/sso-blade.png)

2. Adja meg a következő beállításokat:

    - **Felhasználónév attribútum az aad-ből**: Intune az Azure ad-ben ez az attribútum az egyes felhasználók keres. Intune az eszközön telepített XML létrehozása előtt majd tölti fel a megfelelő mezőben (például egyszerű felhasználónév). A választható lehetőségek:

      - **Egyszerű felhasználónév**: Az UPN-jét a rendszer elemzi a következő módon:

        ![Felhasználónév attribútum](media/User-name-attribute.png)

        Szükség esetén felülírhatja a tartományt is, ha beírja a kívánt tartománynevet a **Tartomány** szövegmezőbe.

        Például a Contoso számos régióban, például Európában, Ázsiában és Észak-Amerika rendelkezik. A Contoso biztosítani szeretné az egyszeri bejelentkezés használatára ázsiai felhasználóknak, és az alkalmazás igényel az egyszerű felhasználónév az a `username@asia.contoso.com` formátumban. Ha bejelöli **egyszerű felhasználónév**, az Azure Active Directory, amely átveszi a tartomány minden felhasználó számára a rendszer `contoso.com`. Ezért az ázsiai felhasználóknak kattintson **egyszerű felhasználónév**, és adja meg `asia.contoso.com`. A végfelhasználó UPN válik `username@asia.contoso.com`, hanem `username@contoso.com`.

      - **Intune-Eszközazonosítót**: Az Intune automatikusan kiválasztja az Intune-eszközazonosító.

        Az alkalmazásoknak alapértelmezés szerint csak az eszközazonosítóra van szükségük. De ha az alkalmazás használ, a tartomány és az eszköz azonosítója, akkor a tartomány szövegmezőben megadhatja a tartományt.

        > [!NOTE]
        > Alapértelmezett esetben hagyja a tartományt üresen, ha eszközazonosítót használ.

      - **Az Azure AD-Eszközazonosító**

    - **A kezdőtartomány**: Adja meg az URL-címet a tartomány részét. Például írja be a következőt: `contoso.com`.
    - **Az egyszeri bejelentkezést használó URL-cím-előtagok**: **Adjon hozzá** bármely URL-címek a szervezet, amely egyszeri bejelentkezéses felhasználóhitelesítést igényel.

        Ha egy felhasználó csatlakozik ezen webhelyekhez, az iOS-eszköz az egyszeri bejelentkezés hitelesítő adatait használja, és a felhasználónak nem kell hitelesítő adatokat megadnia. Ha a multi-factor authentication szolgáltatás engedélyezve van, felhasználók szükségesek adja meg a második hitelesítésre.

        > [!NOTE]
        > Ezeknek az URL-címeknek érvényes formátumú teljes tartományneveknek kell lenniük. Apple következő igényel a `http://<yourURL.domain>` formátumban.

        Az URL-egyeztetési mintáknak `http://` vagy `https://` előtaggal kell kezdődniük. Egy egyszerű megkülönböztető egyeztetés fut, ezért a `http://www.contoso.com/` nem egyezik a URL-előtagot `http://www.contoso.com:80/`. IOS 10.0-s vagy újabb, egy helyettesítő karakter \* adja meg az összes egyező érték is használható. Ha például `http://*.contoso.com/` megegyezik, egyaránt `http://store.contoso.com/` és `http://www.contoso.com`.

        A `http://.com` és `https://.com` minták felel meg az összes HTTP és HTTPS URL-címek, jelölik.

    - **Az egyszeri bejelentkezést használó alkalmazások**: **Adjon hozzá** használó végfelhasználók számára az eszközökön telepített alkalmazások egyszeri bejelentkezés.

        A `AppIdentifierMatches` tömb kell tartalmaznia, amelyek illeszkednek az alkalmazásköteg-azonosítókat. Ezek a karakterláncok lehetnek pontos egyezések, mint például `com.contoso.myapp`, vagy adja meg az előtag-egyeztetést a csomag azonosítója használatával a \* helyettesítő karaktert. A helyettesítő karakter után egy pont karakter (.) kell megjelennie, és csak egyszer szerepelhet, a karakterlánc végén például `com.contoso.*`. A helyettesítő karakter használatakor az összes olyan alkalmazás hozzáférést kap a fiókhoz, amelynek a kötegazonosítója a megadott előtaggal kezdődik.

        Az **Alkalmazásnév** elemnél megadhat egy felhasználóbarát nevet, amely alapján könnyebben felismeri a kötegazonosítót.

    - **Hitelesítőadat-megújítási tanúsítvány**: Ha tanúsítványokat használ a hitelesítéshez (nem pedig jelszavakkal), válassza ki a meglévő SCEP- vagy PFX-tanúsítvány hitelesítési tanúsítványként. Ez a tanúsítvány általában ugyanazt a tanúsítványt, amelyet más profilokhoz, például a VPN-, Wi-Fi vagy e-mailt a felhasználónak.

3. Amikor végzett, válassza ki a **OK** a módosítások mentéséhez.

## <a name="web-content-filter-settings"></a>Webtartalomszűrő-beállításai

Ezek a beállítások hozzáféréseket a böngésző URL-CÍMÉT az iOS-eszközökön.

1. A **beállítások**válassza **webes tartalomszűrés (csak felügyelt)**.
2. Válassza ki a **szűrőtípust**. A választható lehetőségek:

    - **URL-címek konfigurálása**: Használja az Apple beépített átengedni felnőtt kifejezéseket, például TRÁGÁR és nyíltan nyelv. Ez a funkció minden lap értékeli ki, mert be töltve, és azonosítja és letiltja a nem megfelelő tartalmat. URL-címek, amelyek nem szeretné, hogy be van jelölve, a szűrő által is hozzáadhat. Másik lehetőségként letiltása adott URL-címek, z Apple webszűrőjének beállításaitól függetlenül.

      - **Engedélyezett URL-címek**: **Adjon hozzá** az engedélyezni kívánt URL-címeket. Az URL-címek az Apple átengedni kihagyása.

        > [!NOTE]
        > Az URL-címeket, akkor adja meg az Apple átengedni evauluated nem kívánt URL-címek. Az URL-címek nem engedélyezett webhelyek listája. Hozzon létre egy engedélyezett webhelyek listájában, állítsa be a **szűrőtípus** való **csak meghatározott webhelyek**.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Blokkolt URL-címek**: **Adjon hozzá** az URL-címeket meg szeretné szüntetni történő megnyitását, az Apple webszűrőjének beállításaitól függetlenül.

        Válassza ki **OK** a módosítások mentéséhez.

    - **Csak meghatározott webhelyek** (az a Safari webböngésző csak): Ezen URL-ek a Safari könyvjelzői közé kerülnek. A felhasználó **csak** ezeket a webhelyeket látogathatják meg más webhelyek nem lehet megnyitni. Akkor célszerű ezt a lehetőséget választani, ha a felhasználók által elérhető URL-ek listája pontosan ismert.

      - **URL-CÍM**: Adja meg az engedélyezni kívánt webhely URL-CÍMÉT. Például írja be a következőt: `https://www.contoso.com`.
      - **Lássa el könyvjelzővel elérési út**: Adja meg a könyvjelző tárolási helyét. Például írja be a következőt: `/Contoso/Business Apps`. Ha nem adja meg az elérési utat, a könyvjelző az eszköz alapértelmezett könyvjelzőmappájába kerül.
      - **Cím**: Adja meg egy leíró címet a könyvjelzőnek.

      Ha nem ad meg semmilyen URL, akkor a végfelhasználók az alábbiakat kivéve webhelyekhez férnek hozzá `microsoft.com`, `microsoft.net`, és `apple.com`. Az URL-címek az Intune által automatikusan engedélyezve van.

      Válassza ki **OK** a módosítások mentéséhez.

## <a name="wallpaper-settings"></a>Háttérkép beállításai

Adja hozzá a felügyelt iOS-eszközök egyéni .png, .jpg és .jpeg kép. Például használja a vállalati embléma a zárolási képernyőn.

Szokatlan viselkedés tapasztalható, amikor nincs kép profil hozzá van rendelve eszközökhöz egy meglévő képpel. Például hozzon létre egy lemezkép-profilhoz. Ez a profil hozzá van rendelve eszközökhöz, amelyeken már van egy képet. Ebben a forgatókönyvben a lemezképet, az eszköz alapértelmezett változhat, vagy az eredeti rendszerkép felfüggesztheti az eszközön. Ez a viselkedés szabályozza, amely korlátozza az Apple MDM-platformmal.

- **Háttérkép megjelenítési helyét**: Válasszon egy helyet, a kép megjelenítéséhez az eszközön. A választható lehetőségek:
  - **Nincs konfigurálva**: Egyéni rendszerkép nem hozzáad az eszközhöz. Az eszköz az operációs rendszer alapértelmezett használja.
  - **Zárolási képernyő**: A kép hozzáadása a zárolási képernyőn.
  - **Kezdőképernyő**: A kép ad hozzá a kezdőképernyőn.
  - **Zárolási képernyő és a kezdőképernyőn**: Használja ugyanazt a lemezképet a zárolási képernyő és kezdőképernyőjén.
- **Kép háttérkép**: Töltse fel egy meglévő .png, .jpg vagy .jpeg lemezkép létrehozásához használni szeretne. Győződjön meg arról, hogy a fájl mérete legfeljebb 750 KB. Emellett **eltávolítása** hozzáadott kép.

> [!TIP]
> A zárolási képernyőn látható kép-profil létrehozása a zárolási képernyő és a kezdőképernyő különböző képek megjelenítéséhez. Hozzon létre egy másik profilt a kezdőképernyő lemezképpel. Az iOS-felhasználói vagy eszközcsoportok mindkét profil hozzárendelésére.

## <a name="bundle-ids-for-built-in-ios-apps"></a>Alkalmazásköteg-azonosítókat beépített iOS-alkalmazások

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, lépjen kapcsolatba a szoftver gyártójával.

|||
|-|-|
|Alkalmazás neve|Csomagazonosító|
|Alkalmazásáruház|com.apple.AppStore|
|Számológép|com.apple.calculator|
|Naptár|com.apple.mobilecal|
|Fényképezőgép|com.apple.camera|
|Óra|com.apple.mobiletimer|
|Iránytű|com.apple.compass|
|Névjegyek|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Barátok keresése|com.apple.mobileme.fmf1|
|iPhone keresése|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Állapot|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Térképek|com.apple.Maps|
|Üzenetek|com.apple.MobileSMS|
|Zene|com.apple.Music|
|Hírek|com.apple.news|
|Megjegyzések|com.apple.mobilenotes|
|Számok|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotók|com.apple.mobileslideshow|
|Podcastok|com.apple.podcasts|
|Emlékeztetők|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Beállítások|com.apple.Preferences|
|Részvények|com.apple.stocks|
|Tippek|com.apple.tips|
|Videók|com.apple.videos|
|Hangjegyzetek|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Időjárás|com.apple.weather|

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Ezenkívül létrehozhat eszköz az eszközfunkció-profilok [macOS](macos-device-features-settings.md) eszközök.
