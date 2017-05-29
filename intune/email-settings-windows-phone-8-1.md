---
title: "E-mail-beállítások az Intune-ban Windows Phone 8.1-es eszközök esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk az e-mail-kapcsolatoknak a Windows Phone 8.1 rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 986d02721012ce356b18cf983087b5babd03bb23
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Windows Phone 8.1-es eszközökre vonatkozó e-mail-profilbeállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


- **Az összes beállítás alkalmazása csak Windows Phone 8.1 rendszeren** – Ezt a beállítást a hagyományos Intune-portálon lehet konfigurálni. Ez a beállítás az Azure Portal webhelyen nem módosítható. Ha ez a beállítás a **Konfigurálva** értékre van állítva, a rendszer minden beállítást csak a Windows Phone 8.1 rendszerű eszközökre alkalmaz. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 Mobile rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **E-mail-kiszolgáló** – Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fióknév** – Adja meg az e-mail-fiók megjelenítendő nevét (ez lesz látható a felhasználók eszközén).
- **Felhasználónév attribútum az AAD-ből** – Ez az Active Directory (AD) vagy az Azure AD egy attribútuma, ennek alapján fogja generálni a rendszer ennek az e-mail-profilnak a felhasználónevét. Válassza az **Elsődleges SMTP-cím** (például **user1@contoso.com**) lehetőséget, vagy az **Egyszerű felhasználónév** (például **user1** vagy **user1@contoso.com**) lehetőséget.
- **E-mail-cím attribútuma az AAD-ből** – Válassza ki, hogyan jöjjön létre a felhasználói e-mail-cím az egyes eszközökön. Ha az elsődleges SMTP-cím használatával kíván bejelentkezni az Exchange-be, válassza az **Elsődleges SMTP-cím** lehetőséget; ha e-mail-címként a teljes egyszerű felhasználónevet kívánja használni, válassza az **Egyszerű felhasználónév** lehetőséget.


## <a name="security-settings"></a>Biztonsági beállítások

- **SSL** – SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.



## <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége** – Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Szinkronizálás ütemezése** – Válassza ki azt az ütemezést, amely szerint az eszközök szinkronizálni fogják az adatokat az Exchange Serverrel. **Az üzenetek érkezésekor** lehetőség kiválasztásával a rendszer azonnal szinkronizálja az adatokat, amint megérkeznek, a **Manuális** beállítás esetén pedig a felhasználónak kell kezdeményeznie a szinkronizálást.

## <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus** – Válassza ki az eszközökre szinkronizálni kívánt tartalomtípusokat:
    - **Névjegyek**
    - **Naptár**
    - **Feladatok**

