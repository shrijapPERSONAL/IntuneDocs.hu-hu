---
title: Regisztrálja vállalati Android munkahelyi profilos eszközök az Intune-ban
titlesuffix: Microsoft Intune
description: Ismerje meg, hogy miként regisztrálhatják az Android Enterprise munkahelyi profilos eszközök az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6522c3572db715e21b85050cd0c82b4cfb9b9deb
ms.sourcegitcommit: f1681554ad842c22ad3f82f0e6d44d5966e4aa3d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56458773"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Vállalati Android munkahelyi profilos eszközök regisztrálásának beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune segítséget nyújt a vállalati Android munkahelyi profilos eszközök munkahelyi és személyes adatokat meg külön üzembe alkalmazásait és beállításait. Android Enterprise kapcsolatos részleteket lásd: [Android Enterprise követelmények](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Android Enterprise munkahelyi profilok kezelése beállításához, kövesse az alábbi lépéseket:

1. [Az Intune-bérlői fiókkal csatlakozzon az Android Enterprise-fiókjához](connect-intune-android-enterprise.md).
2. Adja meg az Android Enterprise munkahelyi profil regisztrációs beállítások. Vállalati androidos munkahelyi profilok vannak [csak bizonyos Android-eszközökön támogatott](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Android Enterprise munkaprofilokat támogató Android hagyományos felügyeleti is támogatja. Intune-ban megadhatja, hogyan kell-e a Android Enterprise munkaprofilokat támogató eszközök felügyelete a [regisztrációs korlátozások](enrollment-restrictions-set.md).
    - **Blokkolás (alapértelmezett)**:  Minden Android-eszközök, beleértve az eszközöket, amelyek támogatják az Android Enterprise munkahelyi profilokat, hagyományos Android-eszközként lesz regisztrálhatók.
    - **Lehetővé teszi**: Munkahelyi profillal regisztrált Android Enterprise-, Android Enterprise támogató eszközök mindegyike munkahelyi profilos eszközök. Minden Android-eszköz, amely nem támogatja az Android Enterprise munkahelyi profilokkal mint egy hagyományos Android-eszköz regisztrálása akkor történik.
3. [A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket](/intune-user-help/enroll-your-device-in-intune-android).


Ha szeretne regisztrálni az Android Enterprise munkahelyi profilt használó eszközök, de ezeknek az eszközöknek már regisztráltak normál Android-eszközként, azokat az eszközöket kell először regisztrációjának törlése és majd újra kell regisztrálni.

Ha a vállalati Android munkahelyi profilos eszközök használatával regisztrál egy [Készülékregisztráció-kezelő](device-enrollment-manager-enroll.md) , akkor a fiókonként regisztrálható 10 eszközök legfeljebb.

További információ: [Az Intune által a Google-nek küldött adatok](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Hagyja jóvá a céges portál alkalmazást a felügyelt Google Play áruházban

Győződjön meg arról, hogy a felhasználók mindig rendelkeznek-e a hozzáférés a vállalati portál alkalmazás legfrissebb verziójára, jóvá kell hagynia a céges portál alkalmazás androidos a felügyelt Google Play áruházban. A jóváhagyással biztosítja, hogy minden felhasználó megkapja az automatikus frissítéseket. Ha nem hagyja jóvá a Céges portál alkalmazást, előfordulhat, hogy az nem fogja megkapni a Microsoft által kiadott fontos hibajavításokat és új funkciókat, és így idővel elavulttá válik.

Kövesse az alábbi lépéseket az Intune Céges portál alkalmazás jóváhagyásához:

1.  Keresse meg a céges portál alkalmazás a [felügyelt Google Play áruház](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Jelentkezzen be a felügyelt Google Play áruház Android Enterprise-kötés konfigurálásához használt azonos Google-fiókkal.
3.  Kattintson a **Jóváhagyás** lehetőségre. Ekkor megnyílik egy párbeszédpanel.
4.  Tekintse át a párbeszédpanelen látható engedélyeket, majd kattintson a **Jóváhagyás** lehetőségre. Ezeknek az engedélyeknek a jóváhagyására azért van szükség, hogy a Céges portál alkalmazás kezelni tudja az eszközön lévő munkahelyi profilt.
5.  Válassza a **Jóváhagyás fenntartása, amikor az alkalmazás új engedélyeket kér** lehetőséget, majd kattintson a **Mentés** gombra.

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Következő lépések az Android Enterprise munkahelyi profilok
- [Android Enterprise munkahelyi profil alkalmazások üzembe helyezése](apps-add-android-for-work.md)
- [Android Enterprise munkahelyi profil konfigurációs szabályzatok hozzáadása](device-profiles.md)
