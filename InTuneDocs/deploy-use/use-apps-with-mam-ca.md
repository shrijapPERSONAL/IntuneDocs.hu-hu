---
title: "Alkalmazások használata MAM feltételes hozzáférés mellett | Microsoft Intune"
description: "Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 317d101c34854fdf4913adcf53bdef614599deb7


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>Mire számítson, ha egy alkalmazást a MAM feltételes hozzáféréssel használ?
A MAM feltételes hozzáférés közvetítésalkalmazással – amelynek az eszközön kell lennie – ellenőrzi az engedélyezett alkalmazás identitását:
*  **iOS** esetén a közvetítőalkalmazás a **Microsoft Authenticator alkalmazás**.
* **Android** esetén a közvetítőalkalmazás az **Intune Vállalati portál alkalmazás**. 

A MAM feltételes hozzáférés által támogatott alkalmazásba, például a OneDrive-ba vagy az Outlookba először bejelentkező végfelhasználónak le kell töltenie a közvetítőalkalmazást és regisztrálnia kell az eszközt Azure AD-ben. Az Azure AD-ba történő eszközregisztráció (korábban Munkahelyi csatlakoztatás) eszközrekordot és tanúsítványt hoz létre, amelyek ellenében jogkivonatokat állítanak ki.  Ez **nem** ugyanaz, mint az **MDM-regisztráció**. Nincsenek alkalmazott felügyelt profilok vagy szabályzatok, és nincs az eszközön található alkalmazásokról sem leltár.  A közvetítőalkalmazás telepítése és az eszköz regisztrálása csak a felügyelt alkalmazás első használatakor történik meg.

A következő listán azoknak a tulajdonságoknak a listája látható, amelyek magáról az eszközről származnak:

* alternativeSecurityIds (az Azure Active Directory-tanúsítvány ujjlenyomata és nyilvános kulcsának kivonata)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Eszköz Azure AD-regisztrációjának törlése.
Az eszközök regisztrációját az Azure AD felügyeleti konzoljával lehet törölni. Ezt általában a rendszergazda végzi el.  A végfelhasználó is törölheti a regisztrációt, magán az eszközön.

* **Azure AD felügyeleti konzol**: Törölje az Azure AD felügyeleti konzoljából** azt az eszközt, amelyet el szeretne távolítani.
* **iOS-eszköz**: Nyissa meg a Microsoft Authenticator alkalmazást, pöccintsen balra a fiókon, és válassza a Regisztráció törlése lehetőséget.  
* **Androidos eszköz**: Távolítsa el a Munkahelyi portál alkalmazást, vagy törölje a fiókot a **Rendszerbeállítások** területről.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>A MAM feltételes hozzáférés és az eszköz megfelelőségén alapuló feltételes hozzáférés  

Az [eszköz megfelelőségén alapuló feltételes hozzáférést](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Eszköz CA**) az [Intune felügyeleti konzolon](https://manage.microsoft.com) vagy az [Azure AD Premium felügyeleti konzolon (https://manage.windowsazure.com) konfigurálhatja. Az eszköz megfelelőségén alapuló feltételes hozzáférés előírja, hogy a felhasználók csak az Intune által felügyelt, az Intune eszközmegfelelőségi szabályzatának megfelelő eszközökkel vagy tartományhoz csatlakozó számítógéppel csatlakozzanak az Exchange Online-hoz.  Ha egy felhasználó egy vagy több biztonsági csoport tagja, amelyekre vonatkozik a MAM feltételes hozzáférés vagy eszköz megfelelőségén alapuló feltételes hozzáférés szabályzat, akkor az alábbi két előírás egyikének teljesülnie kell:
* A szolgáltatáshoz való hozzáférésre használt alkalmazás a MAM feltételes hozzáférés által támogatott mobilalkalmazás, és az eszközre, amelyen ez az alkalmazás fut, telepítve van az **iOS Authenticator (iOS-eszköz esetén)** vagy a **Vállalati portál alkalmazás (Android-eszköz esetén)**.
* A szolgáltatáshoz való hozzáférésre használt eszköz az **Intune által van felügyelve, és megfelel** az Intune eszközmegfelelőségi szabályzatának, vagy az eszköz egy **tartományhoz csatlakozó számítógép**.  Álljon itt néhány példa ennek illusztrálására:
  * Amennyiben a felhasználó **natív iOS levelezőalkalmazásról** szeretne kapcsolódni, **felügyelt és megfelelő eszközzel** kell tennie azt, ugyanis a natív levelezőalkalmazást nem támogatja a MAM feltételes hozzáférés.
  * Ha a felhasználó **Windowst futtató otthoni számítógépről** csatlakozik, az **eszköz megfelelőségén alapuló feltételes hozzáférés** alkalmazandó, amely előírja, a felhasználónak, hogy tartományhoz csatlakozó számítógépet kell használnia.




## <a name="next-steps"></a>További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>További információ

[Alkalmazásadatok védelme MAM-szabályzatok használatával](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


