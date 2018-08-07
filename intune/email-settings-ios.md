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
ms.openlocfilehash: 2d2fc7f697d03c1ffcb952cd30e29f4959f2b7e9
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321169"
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
- **SSL**: **Engedélyezheti** az SSL-kommunikáció használatát e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikáció során.
- **S/MIME**: **Engedélyezheti az S/MIME** használatát a kimenő e-mailek S/MIME aláírással történő küldéséhez. Ha engedélyezve van, titkosíthatja az ilyen e-maileket fogadni képes címzettek e-mailjeit, és visszafejtheti a feladóktól kapott titkosított e-maileket.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez, és/vagy az e-mail-forgalom titkosításához.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket. Vagy válassza a **Korlátlan** lehetőséget az összes elérhető e-mail szinkronizálása.
- **Üzenetek más e-mail-fiókba való áthelyezésének engedélyezése**: **Engedélyezés** után lehetővé teszi a felhasználóknak az e-mailek áthelyezését az eszközön konfigurált más fiókokba.
- **E-mailek küldésének engedélyezése külső gyártótól származó alkalmazásokból**: **Engedélyezés** után a felhasználók kiválaszthatják alapértelmezett e-mail-küldési fiókként ezt a profilt, és engedélyezhetik a külső alkalmazásoknak az e-mailek natív levelezőalkalmazásban történő megnyitását, például fájlok e-mailhez való csatolásakor.
- **Legutóbb használt e-mail-címek szinkronizálása**: **Engedélyezés** után a felhasználók szinkronizálni tudják az eszközön legutóbb használt e-mail-címek listáját a kiszolgálóval.

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
