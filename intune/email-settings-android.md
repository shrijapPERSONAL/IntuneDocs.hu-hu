---
title: E-mail-beállítások Android rendszerű és androidos munkahelyi profilos eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Olyan eszközkonfigurációs e-mail-profilt hozhat létre, amely az Exchange-kiszolgálót használja, és a tulajdonságokat az Azure Active Directoryból olvassa be. Engedélyezheti az SSL-t, tanúsítványok vagy felhasználónév és jelszó használatával hitelesítheti a felhasználókat, valamint szinkronizálhatja az e-maileket az androidos és androidos munkahelyi profilt használó eszközökön a Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 136ccb6079b16c13098c1dbd6ca49e8254c14f89
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905767"
---
# <a name="email-profile-settings-for-devices-running-android-and-android-enterprise---intune"></a>Android és vállalati Android rendszerű eszközök e-mail-profilokra vonatkozó beállításai - Intune

Az Androidot futtató eszközök konfigurálásához használhatja az e-mail-profilbeállításokat.

Intune-rendszergazdaként e-mail-beállításokat hozhat létre és rendelhet hozzá az alábbi Android-eszközökhöz:

- Android Samsung Knox Standard
- Vállalati Android

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mail-kiszolgáló**: Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fiók neve**: Adja meg az e-mail-fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználói név attribútum az AAD-ből**: Ez a név az Intune által az Azure Active Directoryből (AAD) lekért attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:
  - **Egyszerű felhasználónév**: A nevet, például `user1` vagy `user1@contoso.com` kéri le.
  - **Felhasználónév**: Csak a nevet olvassa be, például `user1`
  - **SAM-fiók neve**: Tartomány szükséges hozzá, például `domain\user1`. A SAM-fiók neve csak androidos eszközökkel használható. A vállalati Android nem támogatott.

    Ezt is adja meg:  
    - **Felhasználói tartománynév forrása**: Válassza az **AAD** (Azure Active Directory) vagy az **Egyéni** lehetőséget.

      Ha azt választja, hogy az attribútumokat az **AAD-ből** kéri le, adja meg ezt is:
      - **Felhasználói tartománynév attribútuma az AAD-ból**: Választhatja a felhasználóhoz tartozó **Teljes tartománynév** vagy a **NetBIOS-név** attribútum lehetőséget

      Ha az **Egyéni** attribútumot választja, adja meg a következőt:
      - **Használandó egyéni tartománynév**: Adja meg az Intune által a tartománynévhez használt értéket, például `contoso.com` vagy `contoso`

- **E-mail-cím attribútuma az AAD-ből**: Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím. Ha e-mail-címként a teljes egyszerű felhasználónevet szeretné használni, válassza az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőséget, vagy az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget, ha az elsődleges SMTP-címet szeretné használni az Exchange-be való bejelentkezéshez.

- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.

### <a name="security-settings"></a>Biztonsági beállítások

- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **S/MIME**: Kimenő e-mailek küldése S/MIME titkosítással.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.

### <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége**: Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Szinkronizálás ütemezése**: Válassza ki azt az ütemezést, amely alapján az eszközök szinkronizálni fogják az adatokat az Exchange-kiszolgálóval. **Az üzenetek érkezésekor** lehetőség kiválasztásával a rendszer azonnal szinkronizálja az adatokat, amint megérkeznek, a **Manuális** beállítás esetén pedig a felhasználónak kell kezdeményeznie a szinkronizálást.

### <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus**: Válassza ki az eszközökre szinkronizálni kívánt tartalomtípusokat:
  - **Névjegyek**
  - **Naptár**
  - **Feladatok**

## <a name="android-enterprise"></a>Vállalati Android

- **Levelezőalkalmazás**: Válassza a **Gmail** vagy a **Nine Work** lehetőséget
- **E-mail-kiszolgáló**: Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Felhasználónév attribútum az AAD-ből**: Ez a név az Active Directory (AD) vagy az Azure AD attribútuma, amely az e-mail-profilhoz tartozó felhasználónév létrehozására szolgál. Válassza az **elsődleges SMTP-címet** (például user1@contoso.com) vagy az **egyszerű felhasználónevet** (például user1 vagy user1@contoso.com).
- **E-mail-cím attribútuma az AAD-ből**: Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím az egyes eszközökön. Az **Egyszerű felhasználónév** lehetőség kiválasztásával az egyszerű felhasználónevet e-mail-címként vagy **felhasználónévként** használhatja.
- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.
- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Szinkronizálandó tartalomtípus** (csak Nine Work esetén): Válassza ki az eszközökre szinkronizálni kívánt tartalomtípusokat:
  - **Névjegyek**
  - **Naptár**
  - **Feladatok**

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
