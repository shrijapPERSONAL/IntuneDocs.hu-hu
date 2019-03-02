---
title: Android e-mail-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Egy konfigurációs e-mail profilok létrehozása, amelyek Exchange-kiszolgálók, és attribútumok lekérése az Azure Active Directoryból. Az SSL vagy s/MIME engedélyezése, hitelesítheti a felhasználókat a tanúsítványok vagy a felhasználónév/jelszó és szinkronizálni az e-mailek és az Androidra fejlesztett Samsung Knox-eszközökön a Microsoft Intune-nal ütemezések.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53f1c95fdbdd9d779fb339e4820a3e7000573e60
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236926"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>E-mailt, a hitelesítés és a szinkronizálás konfigurálása az Intune-ban Android-eszköz beállításai

Ez a cikk és az Androidra fejlesztett Samsung Knox-eszközökön az Intune-ban szabályozhatja a különböző e-mail-beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat állítson be egy e-mail-kiszolgálót, e-mailek és más titkosítása SSL használatával.

Intune-rendszergazdák hozzon létre, és rendelje hozzá az e-mail-beállítások Android Samsung Knox Standard-eszközökre.

Az Intune-ban e-mail profilokkal kapcsolatos további tudnivalókért lásd: [e-mail-beállítások konfigurálása](email-settings-configure.md).

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **Levelezési kiszolgáló**: Adja meg az Exchange-kiszolgáló állomásneve. Például írja be a következőt: `outlook.office365.com`.
- **Fiók neve**: Adja meg az e-mail fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználónév attribútum az aad-ből**: Ez a név az Intune-ban olvas be az Azure Active Directory (Azure AD) attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:
  - **Egyszerű felhasználónév**: A nevet, például lekérdezi `user1` vagy `user1@contoso.com`
  - **Felhasználónév**: Csak a nevét, például beolvasása `user1`
  - **sAM fióknév**: A tartományhoz, mint például szükséges `domain\user1`. sAM-fiók neve csak az Android-eszközökön használható.

    Ezt is adja meg:  
    - **Fióktartománynév forrása**: Válasszon **AAD** (az Azure Active Directory) vagy **egyéni**.

      Ha azt választja, hogy az attribútumokat az **AAD-ből** kéri le, adja meg ezt is:
      - **Attribútum az aad-ből**: Kérhet a **teljes tartománynév** vagy a **NetBIOS-név** a felhasználói attribútum

      Ha az **Egyéni** attribútumot választja, adja meg a következőt:
      - **Egyéni tartománynév használata**: Adjon meg egy értéket, amely a tartománynév például használja az Intune `contoso.com` vagy `contoso`

- **E-mail-cím attribútuma az aad-ből**: Ez a név az Azure AD-ből lekérdezi az Intune e-mailek attribútum. Intune-ban dinamikusan állít elő, az e-mail-cím, amelyet ehhez a profilhoz. A választható lehetőségek:
  - **Egyszerű felhasználónév**:  A teljes egyszerű nevet használja, mint például `user1@contoso.com` vagy `user1`, az e-mail-címként.
  - **Elsődleges SMTP-cím**: Például használja az elsődleges SMTP-cím `user1@contoso.com`, hogy jelentkezzen be az Exchange-hez.

- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.

### <a name="security-settings"></a>Biztonsági beállítások

- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **S/MIME**: Kimenő e-mailek küldése S/MIME titkosítással.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.

### <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége**: Válassza ki az e-mailt szeretne szinkronizálni, vagy válassza ki a kívánt napok száma **korlátlan** az összes elérhető e-mail szinkronizálása.
- **Szinkronizálás ütemezése**: Válassza ki az ütemezést, az eszközök az Exchange server adatainak szinkronizálása. **Az üzenetek érkezésekor** lehetőség kiválasztásával a rendszer azonnal szinkronizálja az adatokat, amint megérkeznek, a **Manuális** beállítás esetén pedig a felhasználónak kell kezdeményeznie a szinkronizálást.

### <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus**: Válassza ki az, hogy az eszközökre szinkronizálni kívánt tartalomtípusokat. **Nincs konfigurálva** letiltja ezt a beállítást. Ha a beállítása **nincs konfigurálva**, ha egy végfelhasználó lehetővé teszi, hogy szinkronizálás az eszközön, a szinkronizálás le van tiltva újra, amikor az eszköz szinkronizál az Intune-nal, a szabályzat erősíti. 

  Szinkronizálhatja az alábbi tartalommal:  
  - **Névjegyek**: Válasszon **engedélyezése** , hogy a végfelhasználók az eszközükkel névjegyek szinkronizálása.
  - **Naptár**: Válasszon **engedélyezése** , hogy a végfelhasználók szinkronizálni kell az eszközét a naptárban.
  - **Feladatok**: Válasszon **engedélyezése** , hogy a végfelhasználók a feladatokat, hogy az eszközök szinkronizálni.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Az e-mail-profilok is létrehozhat [Android Enterprise - munkahelyi profil](email-settings-android-enterprise.md), [iOS](email-settings-ios.md), [Windows 10 és újabb](email-settings-windows-10.md), és [Windows Phone 8.1-es](email-settings-windows-phone-8-1.md).
