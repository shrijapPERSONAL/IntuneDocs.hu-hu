---
title: Android és Android vállalati e-mail-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Egy konfigurációs e-mail profilok létrehozása, amelyek Exchange-kiszolgálók, és attribútumok lekérése az Azure Active Directoryból. Az SSL vagy s/MIME engedélyezése, hitelesítheti a felhasználókat a tanúsítványok vagy a felhasználónév/jelszó és szinkronizálni az e-mailek és az ütemezések, Android és Android munkahelyi profilos eszközök Microsoft Intune-nal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: b96363d679a6f09327bf9a1b46421e786d1956a8
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316882"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android- és e-mailt, a hitelesítés és a szinkronizálás konfigurálása az Intune-ban Android Enterprise-eszközbeállítások

Ez a cikk és az Android- és Android Enterprise eszközökön szabályozhatja a különböző e-mail-beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat állítson be egy e-mail-kiszolgálót, e-mailek és más titkosítása SSL használatával.

Intune-rendszergazdaként e-mail-beállításokat hozhat létre és rendelhet hozzá az alábbi Android-eszközökhöz:

- Android Samsung Knox Standard
- Vállalati Android

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **Levelezési kiszolgáló**: Adja meg az Exchange-kiszolgáló állomásneve.
- **Fiók neve**: Adja meg az e-mail fiók megjelenítendő nevét. Ez a név jelenik meg az eszközön a felhasználók számára.
- **Felhasználónév attribútum az aad-ből**: Ez a név az Intune-ban lekérdezi az Azure Active Directory (AAD) attribútum. A profil által használt felhasználónevet az Intune dinamikusan generálja. A választható lehetőségek:
  - **Egyszerű felhasználónév**: A nevet, például lekérdezi `user1` vagy `user1@contoso.com`
  - **Felhasználónév**: Csak a nevét, például beolvasása `user1`
  - **sAM fióknév**: A tartományhoz, mint például szükséges `domain\user1`. A SAM-fiók neve csak androidos eszközökkel használható. A vállalati Android nem támogatott.

    Ezt is adja meg:  
    - **Fióktartománynév forrása**: Válasszon **AAD** (az Azure Active Directory) vagy **egyéni**.

      Ha azt választja, hogy az attribútumokat az **AAD-ből** kéri le, adja meg ezt is:
      - **Attribútum az aad-ből**: Kérhet a **teljes tartománynév** vagy a **NetBIOS-név** a felhasználói attribútum

      Ha az **Egyéni** attribútumot választja, adja meg a következőt:
      - **Egyéni tartománynév használata**: Adjon meg egy értéket, amely a tartománynév például használja az Intune `contoso.com` vagy `contoso`

- **E-mail-cím attribútuma az aad-ből**: Válassza ki, hogyan generáljon a rendszer az e-mail címet a felhasználókhoz. Ha e-mail-címként a teljes egyszerű felhasználónevet szeretné használni, válassza az **Egyszerű felhasználónév** (`user1@contoso.com` vagy `user1`) lehetőséget, vagy az **Elsődleges SMTP-cím** (`user1@contoso.com`) lehetőséget, ha az elsődleges SMTP-címet szeretné használni az Exchange-be való bejelentkezéshez.

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
  - **Névjegyek**
  - **Naptár**
  - **Feladatok**

## <a name="android-enterprise"></a>Vállalati Android

- **Levelezőalkalmazás**: Ezek közül bármelyikre **Gmail** vagy **Nine Work**
- **Levelezési kiszolgáló**: Az Exchange-kiszolgáló állomásneve.
- **Felhasználónév attribútum az aad-ből**: Ez a név az Active Directory (AD) vagy az Azure AD-ben, amely az e-mail-profilhoz tartozó felhasználónév létrehozására szolgál. Válassza az **elsődleges SMTP-címet** (például user1@contoso.com) vagy az **egyszerű felhasználónevet** (például user1 vagy user1@contoso.com).
- **E-mail-cím attribútuma az aad-ből**: A felhasználóhoz tartozó e-mail-cím előállításának módja az egyes eszközökön. Az **Egyszerű felhasználónév** lehetőség kiválasztásával az egyszerű felhasználónevet e-mail-címként vagy **felhasználónévként** használhatja.
- **Hitelesítési módszer**: Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
  - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát az Exchange-kapcsolat hitelesítéséhez.
- **SSL**: SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **Szinkronizálandó e-mailek mennyisége**: Válassza ki az e-mailt szeretne szinkronizálni, vagy válassza ki a kívánt napok száma **korlátlan** az összes elérhető e-mail szinkronizálása.
- **Szinkronizálandó tartalomtípus** (csak Nine Work): Válassza ki az, hogy az eszközökre szinkronizálni kívánt tartalomtípusokat. **Nincs konfigurálva** letiltja ezt a beállítást. Ha a beállítása **nincs konfigurálva**, ha egy végfelhasználó lehetővé teszi, hogy szinkronizálás az eszközön, a szinkronizálás le van tiltva újra, amikor az eszköz szinkronizál az Intune-nal, a szabályzat erősíti. 

  Szinkronizálhatja az alábbi tartalommal: 
  - **Névjegyek**
  - **Naptár**
  - **Feladatok**

## <a name="next-steps"></a>További lépések
[E-mail-beállítások konfigurálása az Intune-ban](email-settings-configure.md)
