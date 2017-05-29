---
title: "A mobileszközök regisztrálásának módjai | Microsoft Docs"
description: "Néhány egyszerű kérdés megválaszolásával eldöntheti, hogyan végzi el a mobileszközök beléptetését az Intune-ban"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 64f8a051cfa873df034e3d260862181ce637948c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---
# <a name="choose-how-to-enroll-mobile-devices"></a>A mobileszközök regisztrálásának módjai

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A kérdésekre adott válaszai segítenek eldönteni, hogy mely regisztrációs módszer a legmegfelelőbb az Ön által felügyelt eszközök számára.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Hogyan kezelheti a megosztott iOS-eszközeit?**

> [!div class="button"]
[iOS-eszközök regisztrálása DEP keretében >]/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [!div class="button"]
> [iOS-eszközök közvetlen regisztrálása >]/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune) [!div class="button"]
[DEM-regisztráció >]/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók első alkalommal kapcsolják be az eszközt, az letölti a DEP-profilt és azzal regisztrálja az magát.

  - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt. Ha nem szeretné a gyári beállításokat visszaállítani az eszközökön, használja Közvetlen regisztrációt.

  - **Készülékregisztráció-kezelő** - Az Intune eszközregisztráció-kezelő funkciója lehetővé teszi, hogy a vezető vagy rendszergazda egyetlen felhasználói fiókkal több mobileszközt regisztráljon. Ezek az eszközök nem rendelkezhetnek felhasználói affinitással (azaz dedikált felhasználókkal), és regisztrálásuk a Vállalati portál alkalmazás telepítésével és az abba való bejelentkezéssel történik.

> [!div class="button"]
[< Vissza](choose-how-to-enroll-devices3.md)

