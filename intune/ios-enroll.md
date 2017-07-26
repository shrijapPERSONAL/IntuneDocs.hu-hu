---
title: "A Windows-eszközök regisztrálási módjának kiválasztása az Intune-ban"
titleSuffix: Intune on Azure
description: "Útmutató Windows-eszközök Microsoft Intune-ban való regisztrációjának beállításához.”"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bdbc7ca68995e23295cf099ce73dfdcaeba37c
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/18/2017
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-eszközök regisztrálása az Intune-ban

Az Intune lehetőséget nyújt az iPadek és iPhone-ok mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz.

Intune-rendszergazdaként engedélyezheti az iOS-eszközök regisztrációját. Engedélyezheti a felhasználók számára a személyes tulajdonban lévő eszközök regisztrálását, azaz a BYOD-regisztrációt. Emellett vállalati tulajdonban lévő eszközök is regisztrálását is engedélyezheti.

## <a name="prerequisites-for-ios-enrollment"></a>Az iOS eszközök beléptetésének előfeltételei
iOS-eszközök engedélyezése előtt végezze el az alábbi lépéseket:
- [Az Intune beállítása](setup-steps.md) – Ezekkel a lépésekkel állíthatja be az Intune-infrastruktúrát. Különösen fontos, hogy az eszközregisztrációhoz szükség van [saját MDM-szolgáltató beállítására](mdm-authority-set.md).
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md) – Az Apple tanúsítványt igényel az iOS- és macOS eszközök felügyeletének lehetővé tételéhez.

Az előfeltételek teljesítését követően a felhasználók telepíthetik a Céges portál alkalmazást saját iOS-eszközeik regisztrálásához, vagy a rendszergazda beállíthatja a vállalati tulajdonú iOS-eszközök felügyeletét. A rendszergazdák hozzárendelhetnek [eszközregisztráció-kezelőket](device-enrollment-manager-enroll.md) is, akik számos eszközt regisztrálhatnak egyetlen felügyeleti fiókkal. Az Intune a következő módszereket támogatja a vállalati tulajdonban lévő iOS-eszközök regisztrálásához:

## <a name="device-enrollment-program"></a>Készülékregisztrációs program
A szervezetek az Apple Device Enrollment készülékregisztrációs programján keresztül vásárolhatnak iOS-eszközöket. A DEP vezeték nélkül képes telepíteni egy regisztrációs profilt, amely felügyelet alá helyezi az eszközöket. További tudnivalók a [Készülékregisztrációs programról](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Az Apple School Manager egy eszközvásárlási és -regisztrációs program iskolák részére. A DEP-hez hasonlóan lehetőséget nyújt egy profil üzembe helyezésére az eszközök felügyeletben történő regisztrálásához. További információ az [Apple School Manager](apple-school-manager-set-up-ios.md) programról.

## <a name="apple-configurator"></a>Apple Configurator
iOS-eszközök regisztrálhatók a Mac számítógépen futó Apple Configuratorral is. Az eszközök előkészítéséhez csatlakoztassa őket USB-kapcsolaton keresztül, és telepítsen regisztrációs profilt. Az Apple Configurator használatával kétféle módon lehet regisztrálni az eszközöket:
- Regisztrálás a Beállítási asszisztenssel – ez a folyamat visszaállítja az eszközt gyári alaphelyzetbe, felkészíti az eszközt a Beállítási asszisztens futtatására, és telepíti a cég szabályzatait az eszköz új felhasználójának.
- Közvetlen regisztrálás – ez a folyamat nem állítja vissza az eszközt gyári alaphelyzetbe, és előre definiált szabályzattal regisztrálja azt. A módszer felhasználói affinitás nélküli eszközökkel használható.

További információ az [Apple Configurator-regisztrációról](apple-configurator-setup-assistant-enroll-ios.md).
