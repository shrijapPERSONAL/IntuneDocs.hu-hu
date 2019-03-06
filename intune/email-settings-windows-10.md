---
title: E-mail-beállítások Windows 10-es eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Olyan eszközkonfigurációs e-mail-profilt hozhat létre, amely az Exchange-kiszolgálót használja, és a tulajdonságokat az Azure Active Directoryból olvassa be. SSL-t is engedélyezhet, és a Microsoft Intune használatával szinkronizálhatja az e-maileket és az ütemezéseket Windows 10-es eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 911d16cfd729af1c55e3c06b9b30d94f281ed18a
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391353"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>E-mail-profilbeállítások Windows 10-et futtató eszközökön – Intune

Az e-mail-profilbeállítások segítségével a Mail alkalmazás konfigurálása a Windows 10 rendszerű eszközökön.

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

- **E-mail-cím attribútuma az aad-ből**: Válassza ki, hogyan generáljon a rendszer az e-mail címet a felhasználókhoz. Ha e-mail-címként a teljes egyszerű felhasználónevet szeretné használni, válassza az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőséget, vagy az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget, ha az elsődleges SMTP-címet szeretné használni az Exchange-be való bejelentkezéshez.

## <a name="security-settings"></a>Biztonsági beállítások

- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.

## <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége**: Válassza ki a szinkronizálni kívánt e-mailben napok száma. Vagy válassza a **Korlátlan** lehetőséget az összes elérhető e-mail szinkronizálása.
- **Szinkronizálás ütemezése**: Válassza ki az ütemezést, szinkronizálhatja az Exchange-kiszolgálón is megadhat az adatait eszközök **üzenetek érkezésekor**, szinkronizálja az adatokat, amint megérkeznek, vagy **manuális**, ahol a felhasználó az eszköz kell kezdeményeznie a szinkronizálást.

## <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus**: Válassza ki az, hogy az eszközökre szinkronizálni kívánt tartalomtípusokat:
  - **Névjegyek**
  - **Naptár**
  - **Feladatok**

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
