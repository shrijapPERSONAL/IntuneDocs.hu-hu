---
title: E-mail-beállítások iOS-eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Olyan eszközkonfigurációs e-mail-profilt hozhat létre, amely az Exchange-kiszolgálót használja, és a tulajdonságokat az Azure Active Directoryból olvassa be. Engedélyezheti az SSL-t, tanúsítványok vagy felhasználónév és jelszó használatával hitelesítheti a felhasználókat, valamint szinkronizálhatja az e-maileket az iOS-eszközökön a Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6fd10ab6a1e9dd7249e2ae1d4bf558d190276ed
ms.sourcegitcommit: b0ee8626191961dc07f9f7f9d8e6a5fb09c63350
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51505878"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>iOS-eszközökre vonatkozó e-mail-profilbeállítások az Intune-ban

Az iOS-t futtató eszközök konfigurálásához használhatja az e-mail-profilbeállításokat.

> [!IMPORTANT]
> A jelen cikkben ismertetett S/MIME funkció jelenleg fejlesztés alatt áll. Emiatt az S/MIME funkciót ideiglenesen eltávolítottuk az Intune-ból. A funkció újbóli kibocsátását követően ez a megjegyzés törlésre kerül.

## <a name="email-settings"></a>E-mail beállítások

- **E-mail-kiszolgáló**: Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fiók neve**: Adja meg az e-mail-fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználói név attribútum az AAD-ből**: Ez a név az Intune által az Azure Active Directoryből (AAD) lekért attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:
  - **Egyszerű felhasználónév**: A nevet, például `user1` vagy `user1@contoso.com` kéri le.
  - **Elsődleges SMTP-cím**: E-mail-cím formátumban kéri le a nevet, például `user1@contoso.com`
  - **SAM-fiók neve**: Tartomány szükséges hozzá, például `domain\user1`.

    Ezt is adja meg:  
    - **Felhasználói tartománynév forrása**: Válassza az **AAD** (Azure Active Directory) vagy az **Egyéni** lehetőséget.

      Ha azt választja, hogy az attribútumokat az **AAD-ből** kéri le, adja meg ezt is:
      - **Felhasználói tartománynév attribútuma az AAD-ból**: Választhatja a felhasználóhoz tartozó **Teljes tartománynév** vagy a **NetBIOS-név** attribútum lehetőséget

      Ha az **Egyéni** attribútumot választja, adja meg a következőt:
      - **Használandó egyéni tartománynév**: Adja meg az Intune által a tartománynévhez használt értéket, például `contoso.com` vagy `contoso`

- **E-mail-cím attribútuma az AAD-ből**: Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím. Az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőség kiválasztásával az egyszerű felhasználónevet e-mail-címként használhatja. Az Exchange-kiszolgálóra való bejelentkezéshez válassza az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget.
- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget. Az Azure-alapú többtényezős hitelesítés nincs támogatva.
  - Ha a **Tanúsítvány** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.
- **SSL**: **Engedélyezheti** az SSL-kommunikáció használatát e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikáció során.
- **OAuth**: **Engedélyezheti** az Open Authorization (OAuth) használatát e-mailek küldésekor és fogadásakor, valamint az Exchange-dzsel való kommunikáció során. Ha az OAuth-kiszolgáló tanúsítványalapú hitelesítést használ, válassza a **Tanúsítvány** lehetőséget **hitelesítési módszernek**, és foglalja bele a tanúsítványt a profilba. Ellenkező esetben válassza a **Felhasználónév és jelszó** lehetőséget a **hitelesítési módszerhez**. OAuth használata esetén ügyeljen a következőkre:

  - A profil a felhasználóknak való elérhetővé tétele előtt ellenőrizze, hogy a levelezőszolgáltatása támogatja-e az OAuthot. Az Office 365 Exchange Online támogatja az OAuthot. A helyszíni Exchange és egyéb partneri vagy külső megoldások nem feltétlenül támogatják az OAuthot. A helyszíni Exchange konfigurálható modern hitelesítéshez (ehhez tekintse meg a [Hibrid modern hitelesítés bejelentése a helyszíni Exchange-hez](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) című blogbejegyzést).

    Ha az e-mail-profil OAuth-hitelesítést használ, amelyet a levelezőszolgáltató azonban nem támogat, a **Jelszó újbóli megadása** lehetőség nm lesz elérhető. Így például semmi nem történik, ha a felhasználó a **Jelszó újbóli megadása** lehetőséget választja az Apple eszközbeállításaiban.

  - Az OAuth engedélyezése esetén a végfelhasználók különböző „modern hitelesítési” bejelentkezési felületeket láthatnak, amelyek támogatják a többtényezős hitelesítést (MFA). 

  - Egyes szervezetek letilthatják a végfelhasználóknak az[önkiszolgáló alkalmazás-hozzáférést](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). Ebben a forgatókönyvben a modern hitelesítéses bejelentkezés sikertelen lehet mindaddig, amíg a rendszergazda létre nem hozza az „iOS Accounts” vállalati alkalmazást, és hozzáférést nem ad a felhasználóknak hozzá az Azure AD-ben.

    Az alapértelmezett művelet az alkalmazás hozzáadása az [alkalmazás-hozzáférési panel](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Alkalmazás hozzáadása** funkciójával, **üzleti jóváhagyás nélkül**. További információ: [felhasználók hozzárendelése alkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Az OAuth engedélyezésekor a következők történnek:  
  > 1. A már célzott eszközök új profilt kapnak.
  > 2. A rendszer újra kéri a végfelhasználók hitelesítő adatainak megadását.

- **S/MIME**: **Engedélyezheti az S/MIME** használatát a kimenő e-mailek S/MIME aláírással történő küldéséhez. Ha engedélyezve van, titkosíthatja az ilyen e-maileket fogadni képes címzettek e-mailjeit, és visszafejtheti a feladóktól kapott titkosított e-maileket.
  - Ha a **Tanúsítványok** lehetőséget választotta, válasszon ki egy meglévő PKCS-tanúsítványprofilt az Exchange-kapcsolat hitelesítéséhez, és/vagy az e-mail-forgalom titkosításához.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket. Vagy válassza a **Korlátlan** lehetőséget az összes elérhető e-mail szinkronizálása.
- **Üzenetek más e-mail-fiókba való áthelyezésének engedélyezése**: **Engedélyezés** után lehetővé teszi a felhasználóknak az e-mailek áthelyezését az eszközön konfigurált más fiókokba.
- **E-mailek küldésének engedélyezése külső gyártótól származó alkalmazásokból**: **Engedélyezés** után a felhasználók kiválaszthatják alapértelmezett e-mail-küldési fiókként ezt a profilt. Engedélyezi a külső alkalmazásoknak az e-mailek natív levelezőalkalmazásban történő megnyitását, például fájlok e-mailhez való csatolásakor.
- **Legutóbb használt e-mail-címek szinkronizálása**: **Engedélyezés** után a felhasználók szinkronizálni tudják az eszközön legutóbb használt e-mail-címek listáját a kiszolgálóval.

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
