---
title: "A Windows-eszközök regisztrálási módjának kiválasztása az Intune-ban"
titlesuffix: Azure portal
description: "Útmutató Windows-eszközök Microsoft Intune-ban való regisztrációjának beállításához.”"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 72b30ceed928ed2d3768441a5b5c2fbd8ffdeea4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-eszközök regisztrálása az Intune-ban

Az Intune lehetőséget nyújt az iPadek és iPhone-ok mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz.

Intune-rendszergazdaként engedélyezheti az iOS-eszközök regisztrációját. Engedélyezheti a felhasználók számára a személyes tulajdonban lévő eszközök regisztrálását, azaz a BYOD-regisztrációt. Emellett vállalati tulajdonban lévő eszközök is regisztrálását is engedélyezheti.

## <a name="prerequisites-for-ios-enrollment"></a>Az iOS eszközök beléptetésének előfeltételei
iOS-eszközök engedélyezése előtt végezze el az alábbi lépéseket:
- [Az Intune beállítása](setup-steps.md) – Ezekkel a lépésekkel állíthatja be az Intune-infrastruktúrát. Különösen fontos, hogy az eszközregisztrációhoz szükség van [saját MDM-szolgáltató beállítására](mdm-authority-set.md).
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md) – Az Apple tanúsítványt igényel az iOS- és macOS eszközök felügyeletének lehetővé tételéhez.

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Azt is engedélyezheti, hogy a felhasználók saját személyes eszközeiket regisztrálják az Intune-felügyelethez. Ezt „saját eszköz használata” vagy BYOD (Bring Your Own Device) néven ismerjük. Az előfeltételek teljesítése és a felhasználói licencek hozzárendelése után a felhasználók letölthetik az iOS-es Céges portál alkalmazást az App Store-ból, és az alkalmazástól kapott utasításokat követve elvégezhetik a regisztrációt.

## <a name="company-owned-ios-devices"></a>Vállalati tulajdonban lévő iOS-eszközök
A felhasználóknak eszközöket vásárló szervezetek számára az Intune a következő módszereket támogatja a vállalati tulajdonban lévő iOS-eszközök regisztrálásához:

- Az Apple készülékregisztrációs programja (DEP)
- Apple School Manager
- Regisztrálás az Apple Configurator és a Beállítási asszisztens segítségével
- Apple Configurator – közvetlen regisztráció

A vállalati tulajdonban lévő iOS-eszközök [készülékregisztráció-kezelő](device-enrollment-manager-enroll.md) fiók használatával is regisztrálhatók.

## <a name="device-enrollment-program"></a>Készülékregisztrációs program
A szervezetek az Apple Device Enrollment készülékregisztrációs programján keresztül vásárolhatnak iOS-eszközöket. A DEP vezeték nélkül képes telepíteni egy regisztrációs profilt, amely felügyelet alá helyezi az eszközöket. További tudnivalók a [Készülékregisztrációs programról](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Az Apple School Manager egy eszközvásárlási és -regisztrációs program iskolák részére. A DEP-hez hasonlóan lehetőséget nyújt egy profil üzembe helyezésére az eszközök felügyeletben történő regisztrálásához. További információ az [Apple School Manager](apple-school-manager-set-up-ios.md) programról.

## <a name="apple-configurator"></a>Apple Configurator
iOS-eszközök regisztrálhatók a Mac számítógépen futó Apple Configuratorral is. Az eszközök előkészítéséhez csatlakoztassa őket USB-kapcsolaton keresztül, és telepítsen regisztrációs profilt. Az Apple Configurator használatával kétféle módon lehet regisztrálni az eszközöket:
- Regisztrálás a Beállítási asszisztenssel – ez a folyamat visszaállítja az eszközt gyári alaphelyzetbe, felkészíti az eszközt a Beállítási asszisztens futtatására, és telepíti a cég szabályzatait az eszköz új felhasználójának.
- Közvetlen regisztrálás – ez a folyamat nem állítja vissza az eszközt gyári alaphelyzetbe, és előre definiált szabályzattal regisztrálja azt. A módszer felhasználói affinitás nélküli eszközökkel használható.

További információ az [Apple Configurator-regisztrációról](apple-configurator-setup-assistant-enroll-ios.md).
