---
title: "macOS-eszközök regisztrálása az Intune-ban |Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató macOS-eszközöknek az Azure-os Intune előzetes verziójában való regisztrálásához"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>macOS-eszközök regisztrálása az Azure-os Intune előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune rendszergazdák macOS-eszközöket is kezelhetnek. Az Azure Portal alapértelmezés szerint lehetővé teszi a felhasználók számára macOS-eszközeik regisztrálását. Elég tájékoztatni a felhasználókat arról, hogy a [Céges portál webhelyre](http://portal.manage.microsoft.com) belépve regisztrálhatják macOS-eszközeiket. 

## <a name="prerequisites"></a>Előfeltételek

macOS-eszközök regisztrációjának indítása előtt végezze el az alábbiakat:

- [Tartományok beállítása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Az MDM-szolgáltató beállítása](set-mdm-authority.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [A Céges portál konfigurálása](/intune-azure/manage-apps/company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS-regisztráció beállítása

Az Intune alapértelmezés szerint úgy van beállítva, hogy lehetővé teszi macOS-eszközök regisztrálását. 

A macOS-eszközök regisztrációját engedélyező vagy letiltó beállítást az Azure Portal Intune paneljéről, a **Beléptetés** > **Regisztrációs korlátozások** elem kiválasztásával jelenítheti meg. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A végfelhasználói regisztrációra vonatkozó útmutatást a [macOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos) című témakör tartalmaz. A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [iOS vagy macOS rendszerű eszköz használata az Intune-nal](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


