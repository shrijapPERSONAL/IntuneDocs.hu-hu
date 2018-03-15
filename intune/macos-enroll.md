---
title: "Regisztráció beállítása macOS-eszközökhöz"
titlesuffix: Microsoft Intune
description: "Útmutató macOS-eszközök Intune-ban való regisztrációjának beállításához."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 77a1551321079765f00f0e35d57211ae4c99e5a6
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Regisztráció beállítása macOS-eszközökhöz az Intune-ban

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

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Azt is engedélyezheti, hogy a felhasználók saját személyes eszközeiket regisztrálják az Intune-felügyelethez. Ezt „saját eszköz használata” vagy BYOD (Bring Your Own Device) néven ismerjük. Az előfeltételek teljesítése és a felhasználói licencek hozzárendelése után a felhasználók letölthetik az macOS-es Céges portál alkalmazást az App Store-ból, és az alkalmazástól kapott utasításokat követve elvégezhetik a regisztrációt.

## <a name="company-owned-ios-devices"></a>Vállalati tulajdonban lévő iOS-eszközök
A felhasználóknak eszközöket vásárló szervezetek számára az Intune [eszközregisztrációs-kezelő](device-enrollment-manager-enroll.md) fiókkal támogatja a vállalati tulajdonban lévő macOS-eszközök regisztrálását.

## <a name="set-up-macos-enrollment"></a>macOS-regisztráció beállítása

Az Intune alapértelmezés szerint lehetővé teszi macOS-eszközök regisztrálását.

A macOS-eszközök regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

Kérje a végfelhasználókat, hogy a [Céges portál webhelyen](http://portal.manage.microsoft.com) található útmutatás alapján regisztrálják eszközeiket. Hivatkozást is küldhet nekik az online regisztrációhoz: [macOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [macOS-eszköz használata az Intune-nal](/intune-user-help/using-your-macos-device-with-intune)
