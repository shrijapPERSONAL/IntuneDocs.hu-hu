---
title: "Az Intune eszközkonfigurálási profiljainak létrehozása| Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató az Intune eszközkonfigurálási profiljainak létrehozásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6c6ac8112a6b6413df635607a24d0d06466c0b88


---

# <a name="how-to-create-device-configuration-profiles"></a>Eszközkonfigurációs profilok létrehozása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Jelentkezzen be az Azure Portal webhelyre.
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
        -  [Eszközkorlátozási beállítások](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [E-mail-beállítások](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [VPN-beállítások](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Wi-Fi-beállítások](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [A Windows 10 kiadásfrissítési beállításai](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Tanúsítványbeállítások](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [A Windows Információvédelem beállításai](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Oktatási beállítások](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Egyéni beállítások](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Eszközprofil létrehozása](./media/create-device-profile.png)
4. Ha végzett a beállítások konfigurálásával, a **Profil létrehozása** panelen válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](how-to-assign-device-profiles.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.


### <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendelésével kapcsolatos további információkért lásd: [How to assign device profiles with Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles) (Eszközprofilok hozzárendelése a Microsoft Intune-nal).



<!--HONumber=Feb17_HO1-->


