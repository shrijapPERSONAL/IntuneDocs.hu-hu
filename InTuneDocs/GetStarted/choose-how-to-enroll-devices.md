---
title: "A mobileszközök regisztrálásának módjai | Microsoft Intune"
description: "Néhány egyszerű kérdés megválaszolásával eldöntheti, hogyan végzi el a mobileszközök beléptetését az Intune-ban"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: f15c9748b1c55ec46ddd0056445bf434fa323c59


---

# <a name="choose-how-to-enroll-mobile-devices"></a>A mobileszközök regisztrálásának módjai

Az alábbi kérdésekre adott válaszaiból megtudhatja, hogy melyik regisztrációs módszer felel meg a legjobban az Ön által kezelt eszközöknek.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Az alkalmazottak saját eszközeiket használják, vagy a munkahely biztosítja nekik ezeket az eszközöket?**

  - **Felhasználói tulajdonban lévő eszközök** – „Saját eszközök használata” (Bring Your Own Device, BYOD) – regisztráció
  - **Vállalati tulajdonban lévő eszközök** – COD-regisztráció

> [!div class="button"]
[BYOD-regisztráció >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD-regisztráció >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Milyen BYOD-eszközöket regisztrálhatnak a felhasználói?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS és Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile & Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows rendszerű számítógépek](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**A vállalati tulajdonban lévő eszközök megosztott eszközök, vagy dedikált felhasználókkal rendelkeznek?**

> [!div class="button"]
[Megosztott >](#what-operating-system-are-your-shared-devices-running)   [Dedikált >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Milyen operációs rendszert futtatnak megosztott eszközei?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Hogyan felügyelheti a megosztott iOS-eszközeit?**

  > [!div class="button"]
  [iOS-eszközök regisztrálása a DEP segítségével >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-eszközök közvetlen regisztrálása >>  ](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)[DEM-regisztráció >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökhöz regisztrációs profil társítható. Amikor a felhasználók első alkalommal kapcsolják be az eszközt, az letölti a DEP-profilt és azzal regisztrálja magát.

  - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztráció lehetőséget. Ha nem szeretné a gyári beállításokat visszaállítani az eszközökön, használja Közvetlen regisztráció lehetőséget.

  - **Készülékregisztráció-kezelő (Intune)** - Az Intune eszközregisztráció-kezelő funkciója lehetővé teszi, hogy a vezető vagy rendszergazda egyetlen felhasználói fiókkal több mobileszközt regisztráljon. Ezek az eszközök nem rendelkezhetnek dedikált felhasználókkal (azaz felhasználói affinitással), és regisztrálásuk a Vállalati portál alkalmazás telepítésével és az abba való bejelentkezéssel történik.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Hogyan felügyelheti a dedikált iOS-eszközeit?**

  > [!div class="button"]
   [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-alapú Beállítási asszisztens](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Tag with IMEI (Címkézés IMEI azonosítóval)](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  A vállalati eszközök az alábbi módokon regisztrálhatók dedikált felhasználókkal:

  - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökhöz regisztrációs profil társítható. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrál az Intune-ban.

  - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztráció lehetőséget.

  - **Megjelölés IMEI-számmal** - A vállalati eszközök nemzetközi mobilkészülék-azonosító számainak (IMEI) importálásával azokat vállalati eszközökként jelölheti meg az Intune-ban. A felhasználók ezután személyes eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok.



<!--HONumber=Nov16_HO3-->


