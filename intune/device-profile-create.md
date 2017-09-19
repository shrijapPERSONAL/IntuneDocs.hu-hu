---
title: "Intune-beli eszközkonfigurációs profilok létrehozása"
titlesuffix: Azure portal
description: "Ismerje meg, hogyan hozhat létre eszközkonfigurációs profilokat az Intune-ban.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab7a2f905a7eec33204516e07f0a5d2cda4e1d95
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Eszközkonfigurációs profilok létrehozása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
2. A profilok listáját megjelenítő panelen válassza a **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen adja meg a következőket:
    - **Név** – Adja meg az új profil leíró nevét.
    - **Leírás** – Megadhatja a profil leírását (nem kötelező).
    - **Platform** – Válassza ki a létrehozni kívánt profil platformtípusát.
    - **Profiltípus** – Válassza ki a létrehozni kívánt profil típusát. A rendelkezésre álló típusok listája a kiválasztott platformtól függően változik.
    - **Beállítások** – Az egyes profiltípusok beállításaival kapcsolatos további információkért tekintse meg az alábbi témaköröket:
        -  [Eszközfunkciók beállításai](device-features-configure.md)
        -  [Eszközkorlátozási beállítások](device-restrictions-configure.md)
        -  [E-mail-beállítások](email-settings-configure.md)
        -  [VPN-beállítások](vpn-settings-configure.md)
        -  [Wi-Fi-beállítások](wi-fi-settings-configure.md)
        -  [A Windows 10 kiadásfrissítési beállításai](edition-upgrade-configure-windows-10.md)
        -  [Tanúsítványbeállítások](certificates-configure.md)
        -  [A Windows Információvédelem beállításai](windows-information-protection-configure.md)
        -  [Oktatási beállítások](education-settings-configure.md)
        -  [Egyéni beállítások](custom-settings-configure.md)

    ![Eszközprofil létrehozása](./media/create-device-profile.png)
4. Ha végzett a beállítások konfigurálásával, a **Profil létrehozása** panelen válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profilt csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.


### <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendelésével kapcsolatos további információkért lásd: [How to assign device profiles with Microsoft Intune](device-profile-assign.md) (Eszközprofilok hozzárendelése a Microsoft Intune-nal).
