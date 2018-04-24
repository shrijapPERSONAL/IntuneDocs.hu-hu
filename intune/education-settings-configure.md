---
title: Az Intune oktatási beállításainak konfigurálása Windows 10 esetén
titleSuffix: Microsoft Intune
description: A cikk tájékoztatást nyújt arról, hogyan konfigurálhatók a felügyelt eszközökön a Windows 10-es oktatási beállítások az Intune-nal.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 413ad0bab32353fc6f5b401f9a7b910b6c5cb390
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Az oktatási beállítások konfigurálása a Microsoft Intune-ban Windows 10 esetén

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az oktatási profilokkal lehet megadni a Windows Vizsga alkalmazást konfiguráló részleteket, például a fiókadatokat és a vizsga URL-címét. Ennek konfigurálásakor megnyílik a Vizsga alkalmazás a megadott vizsgával, és annak befejezéséig az eszközön nem lehet másik alkalmazást futtatni.

A Vizsga alkalmazásról részletes információt a [Vizsgák a Windows 10-ben](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) című cikkben találhat.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Oktatási profilbeállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panel **Kezelés** területén válassza a **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adjon meg egy **Nevet** és **Leírást** az eszközkorlátozási profilra vonatkozóan.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listában válassza az **Oktatási profil** lehetőséget. 
7. Kattintson a **Beállítások > Konfigurálás** elemre, majd a **Vizsga** panelen konfigurálja a következőket:
    - **Fiók típusa** – Válassza ki a fiók típusát a legördülő mezőben.
    - **Fiók felhasználóneve** – Írja be a Vizsga alkalmazáshoz használni kívánt fiók felhasználónevét. Ez lehet tartományi fiók, Azure Active Directory- (AAD-) fiók vagy helyi számítógépfiók is.
    - **Felmérési URL-cím** – Adja meg annak a vizsgának az URL-jét, amelyet a felhasználóknak el kell végezniük. További információt a Vizsga dokumentációjában talál.
    - **Képernyőfigyelés** – Itt adhatja meg, hogy szeretné-e figyelni a felhasználók képernyőjét a vizsga során.
    - **Szövegjavaslat** – Engedélyezheti vagy letilthatja a szövegjavaslatokat a vizsga során.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="next-steps"></a>További lépések

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.



