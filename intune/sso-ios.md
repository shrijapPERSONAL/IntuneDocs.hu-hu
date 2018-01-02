---
title: "Az Intune konfigurálása egyszeri bejelentkezéshez iOS-es eszközökön"
titlesuffix: Azure portal
description: "Ismerje meg, hogyan konfigurálhatja az Intune-t egyszeri bejelentkezéshez iOS-eszközökön."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff71239a360b09ca831a6e99f5f7a759b08f5d56
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2017
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a>Az Intune konfigurálása egyszeri bejelentkezéshez iOS-es eszközökön

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A legtöbb üzletviteli alkalmazás biztonsági célokból megkövetel bizonyos szintű felhasználóhitelesítést. Sok esetben ez azt jelenti, hogy a felhasználóknak be kell írnia ugyanazokat a hitelesítő adatokat sorozatosan, mely frusztrációt okozhat. A felhasználói élmény javítása érdekében a fejlesztők létrehozhatnak egyszeri bejelentkezést támogató alkalmazásokat, melyek kevesebbszer kérik meg a felhasználót a hitelesítő adataik megadására.

Az iOS-eszköz egyszeri bejelentkezési képességeinek kihasználásához az alábbiak szükségesek:

- Egy alkalmazás, amely úgy lett megírva, hogy a felhasználói hitelesítő adatok tárát az iOS-eszköz egyszeri bejelentkezéses adatcsomagjában keresse.
- Az iOS-eszközön való egyszeri bejelentkezéshez konfigurált Intune.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Az Intune konfigurálása iOS-eszközökön való egyszeri bejelentkezéshez


1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Profilok** lehetőséget.
3. A Profilok panelen válassza a **Profil létrehozása** lehetőséget, adjon meg egy nevet és egy leírást, majd adja meg a következő beállításokat:
   - **Platform**: Válassza az **iOS** lehetőséget. 
   - **Profil típusa**: Válassza az **Eszközfunkciók** lehetőséget.
4. Az **Eszközfunkciók** panelen válassza az **Egyszeri bejelentkezés** lehetőséget.

   ![Egyszeri bejelentkezés panel](./media/sso-blade.png)

2. Az **Egyszeri bejelentkezés** panelen lévő mezők kitöltéséhez használja az alábbi összefoglaló táblázatot. A táblázatot követő szakaszokban további információt kaphat az egyes mezőkről.
   
   |Mező  |Megjegyzések|
   |---------|---------|
   |**Felhasználónév attribútum az AAD-ből**|Ezt a tulajdonságot az Intune minden egyes felhasználó esetén kikeresi az AAD-ból, és feltölti vele a vonatkozó mezőt (például egyszerű felhasználónév), mielőtt létrehozná az eszközön telepített XML-adatcsomagot.|
   |**Tartomány**|Az URL-cím tartományt jelölő része.|
   |**Az egyszeri bejelentkezést használó URL-előtagok**|A cég bármilyen olyan URL-címe, amely egyszeri bejelentkezéses felhasználóhitelesítést igényel.|
   |**Az egyszeri bejelentkezést használó alkalmazások**|A végfelhasználó eszközének azon alkalmazásai, amelyek az egyszeri bejelentkezéses adatcsomagot használják.|
   |**Hitelesítőadat-megújítási tanúsítvány**|Ha a hitelesítéshez tanúsítványokat használ, adja meg azt az SCEP- vagy PFX-tanúsítványt, amely el lesz juttatva a felhasználóhoz hitelesítési tanúsítványként.|

Az alábbi szakaszok további részleteket nyújtanak a fenti egyszeri bejelentkezéses mezőkről.

### <a name="username-attribute-from-aad-and-realm"></a>Felhasználónév attribútum az AAD-ből és Tartomány

- Ha az **egyszerű felhasználónév** lehetőséget választja ebben a mezőben, az a következőképp lesz elemezve:

   ![Felhasználónév attribútum](media/User-name-attribute.png)

   Szükség esetén felülírhatja a tartományt is, ha beírja a kívánt tartománynevet a **Tartomány** szövegmezőbe.

   Előfordulhat például, hogy a Contoso cégnek több régióban is van irodája, például Európában, Ázsiában és Észak-Amerikában. Tegyük fel, hogy az ázsiai felhasználóknak az egyszeri bejelentkezéses adatcsomagot kell használniuk, és az alkalmazás a következő formátumú egyszerű felhasználónevet (UPN-t) igényli: *username@asia.contoso.com*. Ilyen esetben, ha az **egyszerű felhasználónév** lehetőséget választja, akkor az egyes felhasználók tartományát a rendszer alapértelmezés szerint az AAD-ból keresi ki, mely így lehet mindössze *contoso.com*. Ezért az ázsiai felhasználóknak létrehozhatja külön ezt az adatcsomagot, és felülírhatja a tartományt az *asia.contoso.com* értékkel. Ezután a végfelhasználó UPN-je *username@asia.contoso.com* lesz, nem pedig *username@contoso.com*.

- Az **Eszközazonosító** lehetőség választása esetén az Intune automatikusan kiválasztja az Intune-eszközazonosítót.

   Az alkalmazásoknak alapértelmezés szerint csak az eszközazonosítóra van szükségük. De ha az alkalmazása a tartományt is használja az eszközazonosító mellett, akkor megadhatja a tartományt a **Tartomány** szövegmezőben.

   > [!NOTE]
   > Alapértelmezett megoldásként hagyja a tartományt üresen, ha eszközazonosítót használ.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Az egyszeri bejelentkezést használó URL-előtagok

Ide beírhatja a cége bármely olyan URL-címét, amely felhasználóhitelesítést igényel.

Ha egy felhasználó csatlakozik ezen webhelyek bármelyikéhez, az iOS-eszköz az egyszeri bejelentkezéses hitelesítő adatokat használja, így a felhasználónak nem kell további hitelesítő adatokat megadnia. Ha azonban engedélyezte a többtényezős hitelesítést, a felhasználónak meg kell adnia a hitelesítés második tényezőjét.

> [!NOTE]
> Ezeknek az URL-címeknek érvényes formátumú teljes tartományneveknek kell lenniük. Az Apple a következő formátumot írja elő: `http://<yourURL.domain>`

Az URL-egyeztetési mintáknak `http://` vagy `https://` előtaggal kell kezdődniük. Az eszköz egyszerű, karakterlánc-alapú egyeztetést végez, ezért a `http://www.contoso.com/` URL-előtag nem felel meg a `http://www.contoso.com:80/` címnek. iOS 9.0-s vagy újabb rendszer esetén azonban használhat egyetlen * helyettesítő karaktert az összes egyező érték megadásához. Például a `http://*.contoso.com/` minta illeszkedik mind a `http://store.contoso.com/`, mind pedig a `http://www.contoso.com` címre.
A `http://.com` és a `https://.com` minta pedig illeszkedik az összes HTTP, illetve HTTPS előtagú URL-címre.

### <a name="apps-that-will-use-single-sign-on"></a>Az egyszeri bejelentkezést használó alkalmazások

Adja meg, hogy a végfelhasználó eszközének mely alkalmazásai használják az egyszeri bejelentkezéses adatcsomagot.

Az `AppIdentifierMatches` tömbnek olyan karakterláncokat kell tartalmaznia, amelyek illeszkednek az alkalmazásköteg azonosítóira. Ezek a karakterláncok lehetnek pontos egyezések (például: `com.contoso.myapp`), illetve meghatározhatnak előtag-egyeztetést is a kötegazonosítóhoz a * helyettesítő karakter segítségével. A helyettesítő karakternek egy pont karakter (.) után kell állnia, és csak egyszer szerepelhet az értékben, a karakterlánc végén (például: `com.contoso.*`). A helyettesítő karakter használatakor az összes olyan alkalmazás hozzáférést kap a fiókhoz, amelynek a kötegazonosítója a megadott előtaggal kezdődik.

Az **Alkalmazás neve** mezőben megadhat egy felhasználóbarát nevet, mely alapján könnyebben azonosíthatja a kötegazonosítót.

### <a name="credential-renewal-certificate"></a>Hitelesítőadat-megújítási tanúsítvány

Ha a végfelhasználóit tanúsítványokkal hitelesíti (nem pedig jelszavakkal), akkor ebben a mezőben megadhatja azt az SCEP- vagy PFX-tanúsítványt, amelyet a felhasználó megkap hitelesítési tanúsítványként. Ez jellemzően ugyanaz a tanúsítvány, amelyet más profilokhoz is kioszt a végfelhasználónak, ideértve például a VPN-t, a vezeték nélküli hálózatokat és a levelezést.

## <a name="next-steps"></a>További lépések

Az eszközfunkciók konfigurálásáról bővebben [Az eszközfunkció-beállítások konfigurálása a Microsoft Intune-ban](device-features-configure.md) című témakörben olvashat.