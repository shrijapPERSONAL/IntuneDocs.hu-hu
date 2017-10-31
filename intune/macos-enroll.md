---
title: "macOS-eszközök regisztrálása az Intune-ban"
titlesuffix: Azure portal
description: "Útmutató macOS-eszközök Intune-regisztrációjához"
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a18aa5091c8be2095e2ac95717c2b8294b845cd5
ms.sourcegitcommit: 623c52116bc3fdd12680b9686dcd0e1eeb6ea5ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2017
---
# <a name="enroll-macos-devices-in-intune"></a>macOS-eszközök regisztrálása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune-nal macOS-eszközöket is lehet felügyelni. Az eszközfelügyelethez a felhasználóknak a [Céges portál webhely](http://portal.manage.microsoft.com) útmutatása alapján regisztrálniuk kell eszközeiket. Ha bekerültek a felügyelet alá, [egyéni beállításokat hozhat létre a macOS-eszközökhöz](custom-settings-macos.md). Hamarosan további képességek lesznek elérhetők.

## <a name="prerequisites"></a>Előfeltételek

macOS-eszközök regisztrációjának indítása előtt végezze el az alábbiakat:

- [Tartományok beállítása](custom-domain-name-configure.md)
- [Az MDM-szolgáltató beállítása](mdm-authority-set.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [A Céges portál konfigurálása](company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>macOS-regisztráció beállítása

Az Intune alapértelmezés szerint lehetővé teszi macOS-eszközök regisztrálását.

A macOS-eszközök regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A felhasználókat meg kell kérnie, hogy a [Céges portál webhelyen](http://portal.manage.microsoft.com) található útmutatás alapján regisztrálják macOS-eszközeiket. Hivatkozást is küldhet nekik az online regisztrációhoz: [macOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [iOS vagy macOS rendszerű eszköz használata az Intune-nal](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
