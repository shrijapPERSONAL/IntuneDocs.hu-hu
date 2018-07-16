---
title: E-mail-beállítások iOS-eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Olyan eszközkonfigurációs e-mail-profilt hozhat létre, amely az Exchange-kiszolgálót használja, és a tulajdonságokat az Azure Active Directoryból olvassa be. Engedélyezheti az SSL-t, tanúsítványok vagy felhasználónév és jelszó használatával hitelesítheti a felhasználókat, valamint szinkronizálhatja az e-maileket az iOS-eszközökön a Microsoft Intune használatával.
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
ms.openlocfilehash: 3a231adf4e1f5687bc88c8c9b15241d3f89e711d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905338"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>iOS-eszközökre vonatkozó e-mail-profilbeállítások az Intune-ban

Az iOS-t futtató eszközök konfigurálásához használhatja az e-mail-profilbeállításokat.

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

- **E-mail-cím attribútuma az AAD-ből**: Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím. Ha e-mail-címként a teljes egyszerű felhasználónevet szeretné használni, válassza az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőséget, vagy az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget, ha az elsődleges SMTP-címet szeretné használni az Exchange-be való bejelentkezéshez.
- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget. Az Azure-alapú többtényezős hitelesítés nincs támogatva.
  - Ha a **Tanúsítvány** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.
- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **S/MIME**: Kimenő e-mailek küldése S/MIME aláírással.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket. Vagy válassza a **Korlátlan** lehetőséget az összes elérhető e-mail szinkronizálása.
- **Üzenetek más e-mail fiókba való áthelyezésének engedélyezése**: Lehetővé teszi a felhasználóknak az e-mailek áthelyezését az eszközön konfigurált más fiókokba.
- **E-mailek küldésének engedélyezése külső gyártótól származó alkalmazásokból**: A felhasználók kiválaszthatják alapértelmezett e-mail-küldési fiókként ezt a profilt, és engedélyezhetik a külső alkalmazások számára az e-maileknek a natív e-mail alkalmazásban történő megnyitását, például fájlok e-mailhez való csatolásához.
- **Utoljára használt e-mail címek szinkronizálása**: A felhasználók szinkronizálni tudják az eszközön utoljára használt e-mail címek listáját a kiszolgálóval.

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
