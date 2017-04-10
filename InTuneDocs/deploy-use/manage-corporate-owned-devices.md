---
title: "Vállalati tulajdonú eszközök felügyelete | Microsoft Docs"
description: "A vállalat által birtokolt eszközöket többféleképpen regisztrálhatja az eszköz típusa, megvásárlásának módja és a szervezet igényei alapján."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 521a37044d6721fe905db7740329688ba2c24b35
ms.openlocfilehash: ae077d80e05b33d625285d796917f4f6c153ca3f
ms.lasthandoff: 01/31/2017


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>A vállalati tulajdonú eszközök regisztrálása az Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune-nal felügyelendő szervezeti vagy vállalati tulajdonú eszközöket többféleképpen regisztrálhatja, az eszköz típusától, megvásárlásának módjától, illetve a szervezet igényeitől függően. Telepítheti a Munkahelyi portál alkalmazást is a vállalati tulajdonban lévő eszközök regisztrálásához és felügyeletéhez, például a „saját eszköz használata” (BYOD) forgatókönyvek esetében.

Alapértelmezés szerint platformtól függetlenül minden eszköz regisztrációja engedélyezett az Intune-ban. Az eszközök regisztrációjának letiltásához jelentkezzen be a [Microsoft Intune felügyeleti portálra](http://manage.microsoft.com) a rendszergazdai hitelesítő adataival. Válassza a **Felügyelet** > **Mobileszköz-kezelés** > **Regisztráció szabályai** elemet, és törölje a letiltandó platformokhoz tartozó megfelelő jelölőnégyzeteket.

## <a name="enroll-corporate-owned-ios-devices"></a>A vállalat által birtokolt iOS-eszközök regisztrálása

A vállalat által birtokolt eszközök regisztrálási módszerei a „saját eszköz választása” (CYOD) forgatókönyvekhez alkalmasak. A CYOD környezetben a szervezet fizeti ki a felhasználó által választott eszközt, és a szervezet felügyeli az eszközt.

Ha iOS-eszközöket kínál a felhasználóknak, a regisztrációt konfigurálhatja előzetesen úgy, hogy az eszközöket az Intune felügyelje az első bekapcsolásuktól kezdve. Az Intune támogatja az [Apple készülékregisztrációs programján (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) keresztüli, illetve a Mac számítógépen futó Apple Configurator eszköz segítségével történő [közvetlen](ios-direct-enrollment-in-microsoft-intune.md) vagy [Beállítási asszisztenssel](ios-setup-assistant-enrollment-in-microsoft-intune.md) végzett regisztrációt.

Ismerje meg, hogyan [regisztrálhatja a vállalati tulajdonban lévő iOS-eszközöket](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Eszközregisztráció-kezelői fiók létrehozása

Létrehozhat egy egyfelhasználós eszközregisztráció-kezelői (DEM) fiókot az Intune-ban a szervezet nagy számú mobileszközének felügyeletéhez. A DEM-fiók létrehozását követően a kijelölt fiókkezelők az általános jogú felhasználók által regisztrálható tizenöt eszköznél többet regisztrálhatnak.

A DEM-fiók használatával csak olyan eszközök regisztrálhatók, amelyeket nem egy meghatározott felhasználó használ. Az ilyen típusú eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz.

Tekintse át, hogyan [regisztrálhatja a vállalat által birtokolt eszközöket DEM-fiók használatával](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Vállalati tulajdonú Windows 10 Enterprise-eszközök regisztrálása

Ha az Azure Active Directory Premiumot vagy a Microsoft Nagyvállalati mobilitási csomagot használja a szervezetében, akkor [regisztrálhatja a Windows 10 Enterprise-eszközöket](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Amikor egy felhasználó felvesz egy munkahelyi vagy iskolai fiókot egy eszközön, az eszköz automatikusan megkapja a „Céges eszköz” címkét.

## <a name="import-imei-numbers"></a>IMEI-számok importálása

Számos mobileszközgyártó alkalmaz egy egyedi számot az eszközein, az úgynevezett nemzetközi mobileszköz-azonosítót (IMEI). Lehetősége van a szervezet tulajdonában lévő eszközök IMEI-számának importálására. Amikor az eszköz az Intune felügyelete alá kerül, céges eszközként lesz megjelölve.

Tekintse át, hogyan [jelölheti meg a vállalat által birtokolt eszközöket az IMEI-számok használatával](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Eszközök azonosítása vállalati tulajdonúként

Az Intune az alábbi feltételek bármelyikének teljesülése esetén „céges” eszközként ismeri fel az eszközt:

 - Az eszköz [regisztrálása DEM-fiókkal](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) történt (bármely platformon).
 - Az eszköz regisztrálása az [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) vagy az [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) használatával történt (csak iOS esetén).
 - Az eszköz gyártója [előzetesen deklarálta az eszközt IMEI-szám használatával](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (bármely, IMEI számokat használó platformon).
 - Az eszköz regisztrálva van az [Azure Active Directoryban vagy a Nagyvállalati mobilitási csomagban Windows 10 Enterprise-eszközként](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (csak Windows 10 esetén).

Ha egy eszköz vállalati tulajdonúként lett megjelölve, az eszköz bejegyzésénél a **Céges** szöveg jelenik meg a **Tulajdonos** oszlopban a felügyeleti konzolon. 

