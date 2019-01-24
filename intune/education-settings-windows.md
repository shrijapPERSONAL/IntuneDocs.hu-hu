---
title: Windows 10-es oktatási beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: A Windows 10-eszközök oktatási beállítások listájának megtekintéséhez. Ezek a beállítások az eszközkonfigurációs profil használata a végezze el a vizsga alkalmazás, válassza ki, hogyan jelentkezzen a felhasználók vagy diákjai számára, hogy a figyelő a képernyő a teszt során, és az Intune-ban több.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1756ab89d63a2b9e928c7edfdb2056614be11e9a
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831673"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>A végezze el a vizsga alkalmazás konfigurálása a Windows 10 rendszerű eszközökön az Intune-nal

Ez a cikk bemutatja, mind a Microsoft Intune oktatási vizsga alkalmazás beállításait a Windows 10 és újabb verzióit futtató eszközökön konfigurálhatja. Az alkalmazás használatával tanulók is jelentkezzen be egy eszközt, és vizsga.

Ezek a beállítások hozzá eszközkonfigurációs profil, és ezután hozzárendelt vagy az eszközöket a Microsoft Intune segítségével telepítve.

[Vizsga alkalmazás az Intune-ban](education-settings-configure.md) Ez a szolgáltatás további információkkal szolgál.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Vizsga beállításai

- **Fiók típusa**: Válassza ki, hogyan jelentkeznek be a teszt. A választható lehetőségek:
  - Azure AD-fiók
  - Tartományi fiók
  - Helyi fiók
- **Fiók felhasználóneve**: Adja meg a felhasználókat a a vizsga alkalmazáshoz használni kívánt fiók nevére vizsga alkalmazás. Fiókok a következő formátumban adhatja meg:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Értékelési URL-cím**: Adja meg a teszt azt szeretné, hogy felhasználók URL-CÍMÉT. Az URL-cím beszerzésével kapcsolatban további információkért lásd: a [igénybe vehet a vizsga dokumentációjában talál](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Képernyőfigyelés**: Válasszon **engedélyezése** figyelni a felhasználók képernyőjét a vizsga során. **Nincs konfigurálva** megakadályozza, hogy a képernyő figyelése a vizsgálat során.
- **Szövegjavaslat**: Válasszon **engedélyezése** így teszt részt vevő szövegjavaslatokat is láthatják. **Nincs konfigurálva** szövegjavaslatokat blokkol, amikor a felhasználók képernyőjét a vizsga.

## <a name="next-steps"></a>További lépések

A profil létrehozása, de előfordulhat, hogy nem lehet sikeres bármit még. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md), és [állapotát nyomon](device-profile-monitor.md).