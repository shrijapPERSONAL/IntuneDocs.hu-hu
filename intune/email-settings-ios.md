---
title: "A Microsoft Intune iOS-eszközökre vonatkozó e-mail-beállításai"
titleSuffix: 
description: "Útmutató az e-mail-beállítások iOS rendszerű eszközökön való konfigurálásához használható Intune-beállításokhoz."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1634512c85c156046d0324953463d745be06d649
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>Az iOS rendszerű eszközökre vonatkozó e-mail-profilbeállítások a Microsoft Intune-ban 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A cikk az iOS rendszerű eszközökhöz konfigurálható e-mail-profilbeállításokat mutatja be.

## <a name="email-settings"></a>E-mail beállítások

- **E-mail-kiszolgáló** – Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fióknév** – Adja meg az e-mail-fiók megjelenítendő nevét (ez a név lesz látható a felhasználók eszközén).
- **Felhasználónév attribútum az AAD-ből** – Ez az Active Directory (AD) vagy az Azure AD egy attribútuma, ennek alapján generálja a rendszer az e-mail-profil felhasználónevét. Válassza az **Elsődleges SMTP-cím** (például **user1@contoso.com**) lehetőséget, vagy az **Egyszerű felhasználónév** (például **user1** vagy **user1@contoso.com**) lehetőséget.
- **E-mail-cím attribútuma az AAD-ből** – Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím az egyes eszközökön. Ha az elsődleges SMTP-címmel kíván bejelentkezni az Exchange-be, válassza az **Elsődleges SMTP-cím** lehetőséget; ha a teljes egyszerű felhasználónevet kívánja használni e-mail-címként, válassza az **Egyszerű felhasználónév** lehetőséget.
- **Hitelesítési módszer** – Az e-mail-profil által használandó hitelesítési módszernek válassza a **Felhasználónév és jelszó** vagy a **Tanúsítványok** lehetőséget.
    - Ha a **Tanúsítvány** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.
- **SSL** – SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.
- **S/MIME** – Kimenő e-mailek küldése S/MIME aláírással.
    - Ha a **Tanúsítvány** lehetőséget választotta, válassza ki az ügyfél korábban létrehozott SCEP- vagy PKCS-tanúsítványát, amelyet az Exchange-kapcsolat hitelesítésére kíván használni.
- **Szinkronizálandó e-mailek mennyisége** – Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Üzenetek más e-mail fiókba való áthelyezésének engedélyezése** – Lehetővé teszi a felhasználóknak az e-mailek áthelyezését az eszközön konfigurált más fiókokba.
- **E-mailek küldésének engedélyezése külső gyártótól származó alkalmazásokból** – A felhasználók kiválaszthatják alapértelmezett e-mail-küldési fiókként ezt a profilt, és engedélyezhetik a külső alkalmazások számára az e-maileknek a natív e-mail alkalmazásban történő megnyitását, például fájlok e-mailhez való csatolásához.
- **Utoljára használt e-mail címek szinkronizálása** – Ezzel a funkcióval a felhasználók szinkronizálni tudják az eszközön utoljára használt e-mail címek listáját a kiszolgálóval.
