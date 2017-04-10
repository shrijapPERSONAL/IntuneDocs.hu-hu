---
title: "E-mail-beállítások az Intune-ban Android-eszközök esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: További tudnivalók az e-mail-kapcsolatok androidos eszközökön való konfigurálásához használható Intune-beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 4a97af7fdf52e0e3055932f307223cb32e75c001
ms.lasthandoff: 02/18/2017


---

# <a name="email-profile-settings-for-android-devices-in-microsoft-intune"></a>Androidos eszközökre vonatkozó e-mail-profilbeállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-mail-kiszolgáló** – Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fióknév** – Adja meg az e-mail-fiók megjelenítendő nevét (ez lesz látható a felhasználók eszközén).
- **Felhasználónév attribútum az AAD-ből** – Ez az Active Directory (AD) vagy az Azure AD egy attribútuma, ennek alapján fogja generálni a rendszer ennek az e-mail-profilnak a felhasználónevét. Válassza az **elsődleges SMTP-címet** (például user1@contoso.com) vagy az **egyszerű felhasználónevet** (például user1 vagy user1@contoso.com).
- **E-mail-cím attribútuma az AAD-ből** – Válassza ki, hogyan jöjjön létre a felhasználói e-mail cím az egyes eszközökön. Ha az elsődleges SMTP-címmel kíván bejelentkezni az Exchange-be, válassza az **Elsődleges SMTP-cím** lehetőséget; ha a teljes egyszerű felhasználónevet kívánja használni e-mail-címként, válassza az **Egyszerű felhasználónév** lehetőséget.
- **Hitelesítési módszer** – Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
    - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.

## <a name="security-settings"></a>Biztonsági beállítások

- **SSL** – SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **S/MIME** – Kimenő e-mailek küldése S/MIME titkosítással.
    - Ha a **Tanúsítványok** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.

## <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége** – Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Szinkronizálás ütemezése** – Válassza ki azt az ütemezést, amely szerint az eszközök szinkronizálni fogják az adatokat az Exchange Serverrel. **Az üzenetek érkezésekor** lehetőség kiválasztásával a rendszer azonnal szinkronizálja az adatokat, amint megérkeznek, a **Manuális** beállítás esetén pedig a felhasználónak kell kezdeményeznie a szinkronizálást.

## <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus** – Válassza ki az eszközökre szinkronizálni kívánt tartalomtípusokat:
    - **Névjegyek**
    - **Naptár**
    - **Feladatok**

