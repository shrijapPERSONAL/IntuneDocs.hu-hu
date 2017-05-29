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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 364064f3507c00f87b367c0aa4ff7b0f31cea4b7
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---
# <a name="choose-how-to-enroll-mobile-devices"></a>A mobileszközök regisztrálásának módjai

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A kérdésekre adott válaszai segítenek eldönteni, hogy mely regisztrációs módszer a legmegfelelőbb az Ön által felügyelt eszközök számára.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Hogyan kezelheti a dedikált, vállalati tulajdonú eszközöket?**

  > [!div class="button"]
[iOS DEP >]/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[iOS beállítási asszisztens >]/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"]
> [Megjelölés IMEI-számokkal >]/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  A vállalati eszközök az alábbi módokon regisztrálhatók dedikált felhasználókkal:

  - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrál az Intune-ban.

  - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt.

  - **Megjelölés IMEI-számmal** - A vállalati eszközök nemzetközi mobilkészülék-azonosító számainak (IMEI) importálásával azokat vállalati eszközökként jelölheti meg az Intune-ban. Ez az egyetlen módszer a dedikált („egyfelhasználós”) Windows és Android rendszerű eszközök vállalati tulajdonúként való azonosításához. Azok az iOS rendszerű eszközök, amelyeket nem regisztrálnak az Apple eszközregisztrációs programjában vagy az Apple Configurator eszközben, ugyancsak címkézhetők IMEI számmal. Az eszközök „vállalati tulajdonúként” való előzetes deklarálásukat követően terjeszthetők a felhasználóknak. A felhasználók ezután dedikált eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok.

> [!div class="button"]
[< Vissza](choose-how-to-enroll-devices3.md)

