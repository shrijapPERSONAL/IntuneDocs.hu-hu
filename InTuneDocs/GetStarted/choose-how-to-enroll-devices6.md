---
title: "A mobileszközök regisztrálásának módjai | Microsoft Intune"
description: "Néhány egyszerű kérdés megválaszolásával eldöntheti, hogyan végzi el a mobileszközök beléptetését az Intune-ban"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f65bdbc7aa708b37a766275494e080436d9a5485
ms.openlocfilehash: 3e5c9ed2ba374172ea27b61a34f0746f582f0ebc


---
# A mobileszközök regisztrálásának módjai

A kérdésekre adott válaszai segítenek eldönteni, hogy mely regisztrációs módszer a legmegfelelőbb az Ön által felügyelt eszközök számára.

## **Hogyan kezelheti a dedikált iOS-eszközeit?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)   [iOS-alapú Beállítási asszisztens >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Tag with IMEI (Címkézés IMEI azonosítóval) >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  A vállalati eszközök az alábbi módokon regisztrálhatók dedikált felhasználókkal:

  - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrál az Intune-ban.

  - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt.

  - **Megjelölés IMEI-számmal** - A vállalati eszközök nemzetközi mobilkészülék-azonosító számainak (IMEI) importálásával azokat vállalati eszközökként jelölheti meg az Intune-ban. A felhasználók ezután személyes eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok.

  > [!div class="button"]
  [< Vissza](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO3-->


