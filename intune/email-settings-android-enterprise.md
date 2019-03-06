---
title: Androidos vállalati e-mail-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Exchange-kiszolgálók használó konfigurációs e-mail profilok létrehozása és attribútumok lekérése az Azure Active Directoryból. Az SSL vagy s/MIME engedélyezése, hitelesítheti a felhasználókat a tanúsítványok vagy a felhasználónév/jelszó és szinkronizálni az e-mailek és az Android munkahelyi profilos eszközök Microsoft Intune-nal ütemezések.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 611199e521688b6dd83f6fe1aaeeb280522de095
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391247"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>E-mailt, a hitelesítés és a szinkronizálás konfigurálása az Intune-ban Android Enterprise eszközbeállítások

Ez a cikk és az Android Enterprise eszközökön szabályozhatja a különböző e-mail-beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat állítson be egy e-mail-kiszolgálót, e-mailek és más titkosítása SSL használatával.

Intune rendszergazdaként létrehozhat és vállalati Android-eszköz a munkahelyi profilban szereplő e-mail-beállításokat rendelhet.

Az Intune-ban e-mail profilokkal kapcsolatos további tudnivalókért lásd: [e-mail-beállítások konfigurálása](email-settings-configure.md).

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](email-settings-configure.md#create-a-device-profile), és válassza ki a munkahelyi profilt.

## <a name="android-enterprise"></a>Vállalati Android

- **Levelezőalkalmazás**: Ezek közül bármelyikre **Gmail** vagy **Nine Work**
- **Levelezési kiszolgáló**: Az Exchange-kiszolgáló állomásneve. Például írja be a következőt: `outlook.office365.com`.
- **Felhasználónév attribútum az aad-ből**: Ez a név az Intune-ban olvas be az Azure Active Directory (Azure AD) attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:

  - **Egyszerű felhasználónév**: A nevet, például lekérdezi `user1` vagy `user1@contoso.com`
  - **Felhasználónév**: Csak a nevét, például beolvasása `user1`

- **E-mail-cím attribútuma az aad-ből**: Ez a név az Azure AD-ből lekérdezi az Intune e-mailek attribútum. Intune-ban dinamikusan állít elő, az e-mail-cím, amelyet ehhez a profilhoz. A választható lehetőségek:
  - **Egyszerű felhasználónév**:  A teljes egyszerű nevet használja, mint például `user1@contoso.com` vagy `user1`, az e-mail-címként.
  - **Elsődleges SMTP-cím**: Például használja az elsődleges SMTP-cím `user1@contoso.com`, hogy jelentkezzen be az Exchange-hez.

- **Hitelesítési módszer**: Válassza ki **felhasználónév és jelszó** vagy **tanúsítványok** az e-mail profil által használandó hitelesítési módszert.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.
- **SSL**: Válasszon **engedélyezése** a Secure Sockets Layer (SSL) kommunikáció használata az e-mailek, fogadásakor és az Exchange-kiszolgálóval való kommunikációhoz küldésekor.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki a szinkronizálni kívánt e-mailek idő. Vagy válassza **korlátlan** az összes elérhető e-mail szinkronizálása.
- **Szinkronizálandó tartalomtípus** (csak Nine Work): Válassza ki az eszközökre szinkronizálni kívánt adatok. A választható lehetőségek:
  - **Névjegyek**: Válasszon **engedélyezése** , hogy a végfelhasználók az eszközükkel névjegyek szinkronizálása.
  - **Naptár**: Válasszon **engedélyezése** , hogy a végfelhasználók szinkronizálni kell az eszközét a naptárban.
  - **Feladatok**: Válasszon **engedélyezése** , hogy a végfelhasználók a feladatokat, hogy az eszközök szinkronizálni.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Az e-mail-profilok is létrehozhat [Androidra fejlesztett Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 és újabb](email-settings-windows-10.md), és [Windows Phone 8.1-es](email-settings-windows-phone-8-1.md) eszközök.
