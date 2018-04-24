---
title: Alkalmazások használata MAM feltételes hozzáféréssel
description: Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f313fcbfa26c8f82708f8f830404da97a3eca25
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a>A cikk ismerteti, mire lehet számítani olyan alkalmazás használata esetén, amelyre alkalmazásalapú feltételes hozzáférés érvényes.

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Az alkalmazásalapú feltételes hozzáférés egy közvetítőalkalmazással ellenőrzi a jóváhagyott alkalmazás azonosságát. A közvetítőalkalmazásnak jelen kell lennie az eszközön:
*  **iOS** esetén a közvetítőalkalmazás a **Microsoft Authenticator alkalmazás**.
* **Android** esetén a közvetítőalkalmazás az **Intune Vállalati portál alkalmazás**. 

Amikor a végfelhasználók először jelentkeznek be egy olyan alkalmazásba, amelyre alkalmazásalapú feltételes hozzáférés érvényes (például a OneDrive-ba vagy az Outlookba), a rendszer felkéri őket, hogy telepítsék a közvetítőalkalmazást, és regisztrálják az eszközt az Azure Active Directoryban. Az Azure AD-ba történő eszközregisztráció (korábban Munkahelyi csatlakoztatás) eszközrekordot és tanúsítványt hoz létre, amelyek ellenében jogkivonatokat állítanak ki.  Ez **nem** ugyanaz, mint az **MDM-regisztráció**. Nincsenek alkalmazott felügyelt profilok vagy szabályzatok, és nincs az eszközön található alkalmazásokról sem leltár.  A közvetítőalkalmazás telepítése és az eszköz regisztrálása csak a felügyelt alkalmazás első használatakor történik meg.

A következő listán azoknak a tulajdonságoknak a listája látható, amelyek magáról az eszközről származnak:

* alternativeSecurityIds (az Azure Active Directory-tanúsítvány ujjlenyomata és nyilvános kulcsának kivonata)
* deviceOSType
* deviceOSVersion
* displayName

> [!NOTE]
> Androidos eszközökön:
>   * A Céges portál alkalmazásnak telepítve kell lennie az eszközön, de a végfelhasználónak nem szükséges bejelentkeznie az alkalmazásba.
>   * Az eszközregisztrációt a OneDrive vagy az Outlook alkalmazáson keresztül kell elvégezni.

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Eszköz Azure AD-regisztrációjának törlése.
Az eszközök regisztrációját az Azure AD felügyeleti konzoljával lehet törölni. Ezt általában a rendszergazda végzi el.  A végfelhasználó is törölheti a regisztrációt, magán az eszközön.

* **Azure AD felügyeleti konzol**: Törölje az Azure AD felügyeleti konzoljából** azt az eszközt, amelyet el szeretne távolítani.
* **iOS-eszköz**: Nyissa meg a Microsoft Authenticator alkalmazást, pöccintsen balra a fiókon, és válassza a Regisztráció törlése lehetőséget.  
* **Androidos eszköz**: Távolítsa el a Munkahelyi portál alkalmazást, vagy törölje a fiókot a **Rendszerbeállítások** területről.

## <a name="app-based-ca-with-device-based-ca"></a>Alkalmazásalapú feltételes hozzáférés eszközalapú feltételes hozzáféréssel  

Az [eszköz megfelelőségén alapuló feltételes hozzáférést](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (<strong>Eszköz CA</strong>) az [Intune felügyeleti konzolon](https://manage.microsoft.com) vagy az [Azure AD Premium felügyeleti konzolon](https://manage.windowsazure.com) konfigurálhatja. Az eszköz megfelelőségén alapuló feltételes hozzáférés előírja, hogy a felhasználók csak az Intune által felügyelt, az Intune eszközmegfelelőségi szabályzatának megfelelő eszközökkel vagy tartományhoz csatlakozó számítógéppel csatlakozzanak az Exchange Online-hoz.  Ha egy felhasználó egy vagy több olyan biztonsági csoport tagja, amelyre vonatkozik az alkalmazásalapú feltételes hozzáférés vagy eszköz megfelelőségén alapuló feltételes hozzáférési szabályzat, akkor az alábbi két követelmény egyikének teljesülnie kell:
* A szolgáltatás elérésére használt alkalmazás olyan mobilalkalmazás, amelyet támogat a 
* , és az eszközre, amelyen ez az alkalmazás fut, telepítve van az **iOS Authenticator (iOS-eszköz esetén)** vagy a **Céges portál alkalmazás (Android-eszköz esetén)**.
* A szolgáltatáshoz való hozzáférésre használt eszköz az **Intune által van felügyelve, és megfelel** az Intune eszközmegfelelőségi szabályzatának, vagy az eszköz egy **tartományhoz csatlakozó számítógép**.  Álljon itt néhány példa ennek illusztrálására:
  * Amennyiben a felhasználó a **natív iOS-levelezőalkalmazásból** szeretne kapcsolódni, ezt **felügyelt és megfelelő eszközzel** kell tennie, ugyanis a natív levelezőalkalmazást nem támogatja az alkalmazásalapú feltételes hozzáférés.
  * Ha a felhasználó **Windowst futtató otthoni számítógépről** csatlakozik, az **eszköz megfelelőségén alapuló feltételes hozzáférés** alkalmazandó, amely előírja, a felhasználónak, hogy tartományhoz csatlakozó számítógépet kell használnia.

## <a name="next-steps"></a>További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Lásd még:

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
