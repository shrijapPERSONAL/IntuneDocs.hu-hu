---
title: "Az Intune e-mail-beállításai Windows 8.1-hez | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk az e-mail-kapcsolatoknak a Windows Phone 8.1 rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f16c9dfb41cb2cfe07ce473a131dac767dee9c74
ms.openlocfilehash: e8d8a7b7a7c752269e36e0e40f136f6fb002a19f


---

# <a name="email-profile-settings-for-windows-phone-81-devices-in-intune-azure-preview"></a>E-mail-profilbeállítások Windows Phone 8.1 rendszerű eszközökhöz az Azure-os Intune előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


- **Apply all settings to Windows Phone 8.1 only** (Az összes beállítás alkalmazása csak a Windows Phone 8.1-re) – Ezt a beállítást a hagyományos Intune-portálon lehet konfigurálni. Az Azure Portalon nem módosítható ez a beállítás. Ha ez a beállítás a **Konfigurálva** értékre van állítva, minden beállítást csak a Windows Phone 8.1-eszközökre alkalmaz a rendszer. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 Mobile rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **E-mail-kiszolgáló** – Itt adja meg az Exchange-kiszolgáló állomásnevét.
- **Fióknév** – Adja meg az e-mail-fiók megjelenítendő nevét (ez lesz látható a felhasználók eszközén).
- **Felhasználónév attribútum az AAD-ből** – Ez az Active Directory (AD) vagy az Azure AD egy attribútuma, ennek alapján fogja generálni a rendszer ennek az e-mail-profilnak a felhasználónevét. Válassza az **Elsődleges SMTP-cím** lehetőséget (például **user1@contoso.com**) lehetőséget, vagy az **Egyszerű felhasználónév** (például **user1** vagy **user1@contoso.com**) lehetőséget.
- **E-mail-cím attribútuma az AAD-ből** – Válassza ki, hogyan jöjjön létre a felhasználói e-mail cím az egyes eszközökön. Ha az elsődleges SMTP-címmel kíván bejelentkezni az Exchange-be, válassza az **Elsődleges SMTP-cím** lehetőséget; ha a teljes egyszerű felhasználónevet kívánja használni e-mail-címként, válassza az **Egyszerű felhasználónév** lehetőséget.


## <a name="security-settings"></a>Biztonsági beállítások

- **SSL** – SSL-kommunikáció használata az e-mailek küldésekor és fogadásakor, valamint az Exchange-kiszolgálóval való kommunikációhoz.



## <a name="synchronization-settings"></a>Szinkronizálási beállítások

- **Szinkronizálandó e-mailek mennyisége** – Válassza ki, hogy hány napra visszamenőleg szeretné szinkronizálni az e-maileket, vagy az összes e-mail szinkronizálásához válassza a **Korlátlan** lehetőséget.
- **Szinkronizálás ütemezése** – Válassza ki azt az ütemezést, amely szerint az eszközök adatai szinkronizálódni fognak az Exchange Serverrel. **Az üzenetek érkezésekor** lehetőség kiválasztásával a rendszer azonnal szinkronizálja az adatokat, amint megérkeznek, a **Manuális** beállítás esetén pedig a felhasználónak kell kezdeményeznie a szinkronizálást.

## <a name="content-sync-settings"></a>Tartalomszinkronizálási beállítások

- **Szinkronizálandó tartalomtípus** – Válassza ki az eszközökre szinkronizálni kívánt tartalomtípusokat:
    - **Névjegyek**
    - **Naptár**
    - **Feladatok**



<!--HONumber=Feb17_HO1-->


