---
title: "Az Intune oktatási beállításainak konfigurálása iOS-eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató az iOS-eszközök oktatási beállításainak kezeléséhez használható beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: e52fdf8c30a680d62071cd31e308dd0180e8b9dc


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Az Intune oktatási beállításainak konfigurálása iOS-eszközökhöz az Azure-os Intune előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>iOS-es oktatási beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok panelen válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be a kiadásfrissítési profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listájában válassza az **iOS** lehetőséget.
6. A **Profil típusa** legördülő listában válassza az **Oktatás** lehetőséget.
7. Az **Oktatás** panelen jelölje ki az alábbiakat:
    - **Tanári főtanúsítvány fájlja**
    - **Tanári PKCS12-/PFX-profil**
    - **Tanulói főtanúsítvány fájlja**
    - **Tanulói PKCS12-/PFX-profil**
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.



<!--HONumber=Feb17_HO1-->


