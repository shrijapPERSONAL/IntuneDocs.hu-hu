---
title: Az Outlook beállításai iOS és Android rendszerű eszközökhöz a Microsoft Intune-ban
description: Létrehozhat egy konfigurációs szabályzatot az iOS- és Android-eszközökön futó Microsoft Outlook beállításainak megadásához.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ed1a895dd3e4cad6111b40913b43fa9c6a3cec
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903522"
---
# <a name="microsoft-outlook-configuration-settings"></a>A Microsoft Outlook konfigurációs beállításai 

Az iOS- és Android-eszközökön futó Microsoft Outlook beállításainak elvégzéséhez konfigurációs szabályzatot is használhat. 

Alkalmazáskonfigurációs szabályzat felügyelt iOS-eszközökhöz történő létrehozásával kapcsolatban lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt iOS-eszközökhöz](app-configuration-policies-use-ios.md). Alkalmazáskonfigurációs szabályzat felügyelt androidos eszközökhöz történő létrehozásával kapcsolatban lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt Android-eszközökhöz](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Konfigurációs beállítások

Amikor hozzáad egy konfigurációs szabályzatot az Intune-ban, speciális beállításokat is megadhat a Microsoft Outlook konfigurálásához. A **Konfigurációs beállítások** panelen például megadhatja az e-mail-fiók konfigurációját.

### <a name="basic-authentication-email-account-settings"></a>Alapszintű hitelesítéses e-mail-fiók beállításai
Az iOS és Android rendszerhez készült Outlook lehetőséget biztosít az Exchange-rendszergazdák számára, hogy a fiókkonfigurációkat leküldéssel továbbítsák olyan helyszíni felhasználóknak, akik az alapszintű hitelesítést használják az ActiveSync protokollal. További információért lásd a cikket, amely azzal foglalkozik, hogyan lehet [alapszintű hitelesítéssel beállítani Outlook-fiókokat iOS és Android rendszeren](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup). A fiókbeállítás konfigurációjának engedélyezéséhez az alábbi beállítások érhetők el:

- **E-mail-kiszolgáló**: Itt adhatja meg a helyszíni Exchange-kiszolgáló állomásnevét (például mail.contoso.com).
- **E-mail-fiók neve**: Adja meg az e-mail-fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználói név attribútum az AAD-ből**: Ez a név az Intune által az Azure Active Directoryból (Azure AD) lekért attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A lehetőségek a következők:
  - **Egyszerű felhasználónév**: A nevet, például `user1` vagy `user1@contoso.com` kéri le.
  - **Elsődleges SMTP-cím**: E-mail-cím formátumban kéri le a nevet, például `user1@contoso.com`
- **E-mail-cím attribútuma az AAD-ből**: Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím. Ha e-mail-címként a teljes egyszerű felhasználónevet szeretné használni, válassza az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőséget, vagy az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget, ha az elsődleges SMTP-címet szeretné használni az Exchange-be való bejelentkezéshez. Javasoljuk, hogy válassza az **Elsődleges SMTP-cím** lehetőséget.
- **Fióktartomány**: (opcionális) A fiók tartománya.

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)

