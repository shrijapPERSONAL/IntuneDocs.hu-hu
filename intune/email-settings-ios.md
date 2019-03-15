---
title: E-mail-beállítások iOS-eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Tekintse meg az e-mail beállítások konfigurálása, és adja hozzá az iOS-eszközökhöz a Microsoft Intune, beleértve az Exchange-kiszolgálók használatával és az attribútumok lekérdezése az Azure Active Directoryból. SSL engedélyezése, hitelesítheti a felhasználókat a tanúsítványok vagy a felhasználónév/jelszó, és az eszköz konfigurációs profilokkal a Microsoft Intune-ban iOS-eszközök e-mail szinkronizálása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cf1daf42d1dfcd8dd25304040e868581a056943
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566410"
---
# <a name="email-profile-settings-for-ios-devices-in-intune"></a>E-mail-profilbeállítások iOS-eszközökhöz az Intune-ban

A Microsoft Intune, létrehozása és konfigurálása az e-mailt egy e-mail kiszolgálóhoz csatlakozni, válassza ki, hogy a felhasználók hitelesítése az S/MIME használata titkosításhoz, és több.

Ez a cikk és iOS rendszerű eszközökhöz elérhető összes e-mailek beállításainak ismerteti. Létrehozhat egy leküldéses vagy üzembe helyezése az alábbi e-mail-beállítások iOS-eszközök konfigurációs profil.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](email-settings-configure.md#create-a-device-profile).

## <a name="email-settings"></a>E-mail beállítások

- **Levelezési kiszolgáló**: Adja meg az Exchange-kiszolgáló állomásneve.
- **Fiók neve**: Adja meg az e-mail fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználónév attribútum az aad-ből**: Ez a név az Intune-ban lekérdezi az Azure Active Directory (AAD) attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:
  - **Egyszerű felhasználónév**: A nevet, például lekérdezi `user1` vagy `user1@contoso.com`
  - **Elsődleges SMTP-cím**: Nevét olvassa be az e-mail cím formátumú, például `user1@contoso.com`
  - **sAM fióknév**: A tartományhoz, mint például szükséges `domain\user1`.

    Ezt is adja meg:  
    - **Fióktartománynév forrása**: Válasszon **AAD** (az Azure Active Directory) vagy **egyéni**.

      Ha azt választja, hogy az attribútumokat az **AAD-ből** kéri le, adja meg ezt is:
      - **Attribútum az aad-ből**: Kérhet a **teljes tartománynév** vagy a **NetBIOS-név** a felhasználói attribútum

      Ha az **Egyéni** attribútumot választja, adja meg a következőt:
      - **Egyéni tartománynév használata**: Adjon meg egy értéket, amely a tartománynév például használja az Intune `contoso.com` vagy `contoso`

- **E-mail-cím attribútuma az aad-ből**: Válassza ki, hogyan generáljon a rendszer az e-mail címet a felhasználókhoz. Az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőség kiválasztásával az egyszerű felhasználónevet e-mail-címként használhatja. Az Exchange-kiszolgálóra való bejelentkezéshez válassza az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget.
- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget. Az Azure-alapú többtényezős hitelesítés nincs támogatva.
  - Ha a **Tanúsítvány** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.
- **SSL**: **Engedélyezése** használ Secure Sockets Layer (SSL) kommunikáció küldése e-mailt, fogadásakor és az Exchange-kiszolgálóval való kommunikáció során.
- **OAuth**: **Engedélyezése** nyílt engedélyezési (OAuth) kommunikáció használ, e-mailek, fogadásakor és az Exchange kiszolgálóval való kommunikációhoz küldésekor. Ha az OAuth-kiszolgáló tanúsítványalapú hitelesítést használ, válassza a **Tanúsítvány** lehetőséget **hitelesítési módszernek**, és foglalja bele a tanúsítványt a profilba. Ellenkező esetben válassza a **Felhasználónév és jelszó** lehetőséget a **hitelesítési módszerhez**. OAuth használata esetén ügyeljen a következőkre:

  - A profil a felhasználóknak való elérhetővé tétele előtt ellenőrizze, hogy a levelezőszolgáltatása támogatja-e az OAuthot. Az Office 365 Exchange Online támogatja az OAuthot. A helyszíni Exchange és egyéb partneri vagy külső megoldások nem feltétlenül támogatják az OAuthot. A helyszíni Exchange konfigurálható modern hitelesítéshez (ehhez tekintse meg a [Hibrid modern hitelesítés bejelentése a helyszíni Exchange-hez](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) című blogbejegyzést).

    Ha az e-mail-profil OAuth-hitelesítést használ, amelyet a levelezőszolgáltató azonban nem támogat, a **Jelszó újbóli megadása** lehetőség nm lesz elérhető. Így például semmi nem történik, ha a felhasználó a **Jelszó újbóli megadása** lehetőséget választja az Apple eszközbeállításaiban.

  - Az OAuth engedélyezése esetén a végfelhasználók különböző „modern hitelesítési” bejelentkezési felületeket láthatnak, amelyek támogatják a többtényezős hitelesítést (MFA). 

  - Egyes szervezetek letilthatják a végfelhasználóknak az[önkiszolgáló alkalmazás-hozzáférést](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). Ebben a forgatókönyvben a modern hitelesítéses bejelentkezés sikertelen lehet mindaddig, amíg a rendszergazda létre nem hozza az „iOS Accounts” vállalati alkalmazást, és hozzáférést nem ad a felhasználóknak hozzá az Azure AD-ben.

    Az alapértelmezett művelet az alkalmazás hozzáadása az [alkalmazás-hozzáférési panel](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Alkalmazás hozzáadása** funkciójával, **üzleti jóváhagyás nélkül**. További információ: [felhasználók hozzárendelése alkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Az OAuth engedélyezésekor a következők történnek:  
  > 1. A már célzott eszközök új profilt kapnak.
  > 2. A rendszer újra kéri a végfelhasználók hitelesítő adatainak megadását.

- **S/MIME**: **S/MIME engedélyezése** , hogy a felhasználók bejelentkezés és/vagy az IOS-es natív levelezőalkalmazást az e-mailek titkosításához. 

  S/MIME használata egy e-mail-üzenetet, ha meggyőződött a küldő és a kódintegritási hitelességének és az üzenetek titkosságát.

  - **S/MIME aláírással engedélyezve**: Válasszon **engedélyezése** , hogy a felhasználók digitális aláírására a kimenő e-mailt a megadott fiók. Aláírási segítséget a felhasználóknak, akik üzeneteket fogadni, gondolja át alaposan, hogy az üzenet érkezett, a megadott feladótól, nem pedig valaki a küldő kiállíthatna. **Tiltsa le** nem teszi lehetővé a felhasználók az üzenet digitális aláírással.
    - **Lehetővé teszi a felhasználó módosíthatja a beállítást**: Válasszon **engedélyezése** , hogy a felhasználók S/MIME aláírási viselkedés módosítása. **Tiltsa le** a felhasználók nem módosíthatják a konfigurált beállítás S/MIME aláírással. Elérhető az IOS-es 12 és újabb.

  - **S/MIME-tanúsítvány aláírási**: Válassza ki egy meglévő PKCS vagy SCEP-tanúsítványprofilt, amely e-mailek aláírására szolgál.
    - **Lehetővé teszi a felhasználó módosíthatja a beállítást**: Válasszon **engedélyezése** , hogy a felhasználók módosíthatják az aláíró tanúsítvány. **Tiltsa le** a felhasználók nem módosíthatják az aláíró tanúsítványnak, és kikényszeríti a felhasználók a konfigurált tanúsítványt használja. Elérhető az IOS-es 12 és újabb.

  - **Alapértelmezés szerint titkosítása**: **Engedélyezése** titkosítja az összes üzenet alapértelmezett viselkedésként. **Tiltsa le** nem titkosítja az összes üzenet alapértelmezett viselkedésként.
    - **Lehetővé teszi a felhasználó módosíthatja a beállítást**: Válasszon **engedélyezése** , hogy a felhasználók alapértelmezett titkosítás működésének módosításához. **Tiltsa le** a felhasználók nem módosíthatják a titkosítási alapértelmezett viselkedését, és kikényszeríti a felhasználók számára konfigurált beállítás használatát. Elérhető az IOS-es 12 és újabb.

  - **Üzenet titkosításnak**: Üzenet titkosítás lehetővé teszi, hogy a felhasználók eldönthetik, melyik e-mail elküldése előtt vannak titkosítva. Válasszon **engedélyezése** létrehozásakor egy új e-mailt az üzenet titkosítási beállítás megjeleníthető. Felhasználók választhat, hogy engedélyezve van a hibajelentések vagy üzenet titkosítást. **Tiltsa le** megakadályozza a bemutató üzenetenkénti titkosítási lehetőséget.

    Ha a **alapértelmezés szerint titkosítás** beállítás engedélyezve van, az üzenet titkosítás engedélyezése lehetővé teszi a felhasználóknak egy üzenet titkosítást. Ha a **alapértelmezés szerint titkosítás** beállítás le van tiltva, az üzenet titkosítás engedélyezése lehetővé teszi a felhasználóknak engedélyezve a titkosítás, egy üzenet.

  - **S/MIME titkosítás Cert**: Válassza ki egy meglévő PKCS vagy SCEP-tanúsítványprofilt, amely e-mailek titkosításához használt.
    - **Lehetővé teszi a felhasználó módosíthatja a beállítást**: Válasszon **engedélyezése** , hogy a felhasználók, módosítsa a titkosítási tanúsítványt. **Tiltsa le** a felhasználók nem módosíthatják a titkosítási tanúsítványt, és kikényszeríti a felhasználók a konfigurált tanúsítványt használja. Elérhető az IOS-es 12 és újabb.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki a szinkronizálni kívánt e-mailben napok száma. Vagy válassza a **Korlátlan** lehetőséget az összes elérhető e-mail szinkronizálása.
- **Üzenetek más e-mail fiókba történő áthelyezésének engedélyezése**: **Engedélyezése** lehetővé teszi a felhasználóknak az e-mail üzenetek más fiókokba a felhasználók saját eszközeiken konfigurált áthelyezését.
- **Lehetővé teszi az e-mail küldés harmadik féltől származó alkalmazásokból**: **Engedélyezése** lehetővé teszi a felhasználóknak, hogy ezt a profilt alapértelmezett e-mail-küldési fiókként. Engedélyezi a külső alkalmazásoknak az e-mailek natív levelezőalkalmazásban történő megnyitását, például fájlok e-mailhez való csatolásakor.
- **Legutóbb használt e-mail címek szinkronizálása**: **Engedélyezése** lehetővé teszi a felhasználóknak a kiszolgálóval az eszközön utoljára használt e-mail címek listájának szinkronizálásához.

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

E-mail-beállítások konfigurálása a [Android](email-settings-android.md), [Windows 10-es](email-settings-windows-10.md), és [Windows Phone 8.1-es](email-settings-windows-phone-8-1.md) eszközök.
