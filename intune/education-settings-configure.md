---
title: "Az Intune oktatási beállításainak konfigurálása Windows 10 esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt arról, hogyan konfigurálhatók a felügyelt eszközökön a Windows 10-es oktatási beállítások az Intune-nal."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39aa668794280adc612122e9b2c3c4e7737b65e9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Az oktatási beállítások konfigurálása a Microsoft Intune-ban Windows 10 esetén

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az oktatási profilokkal lehet megadni a Windows Vizsga alkalmazást konfiguráló részleteket, például a fiókadatokat és a vizsga URL-címét. Ennek konfigurálásakor megnyílik a Vizsga alkalmazás a megadott vizsgával, és annak befejezéséig az eszközön nem lehet másik alkalmazást futtatni.

A témakörben található információk alapján megismerheti az eszközkorlátozási profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Oktatási profilbeállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az eszközkorlátozási profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listában válassza az **Oktatási profil** lehetőséget. 
7. Kattintson a Beállítások > Konfigurálás elemre, majd a **Vizsga** panelen konfigurálja a következőket:
    - **Fiók felhasználóneve** – Írja be a Vizsga alkalmazáshoz használni kívánt fiók felhasználónevét. Ez lehet tartományi fiók, Azure Active Directory- (AAD-) fiók vagy helyi számítógépfiók is.
    - **Felmérési URL-cím** – Adja meg annak a vizsgának az URL-jét, amelyet a felhasználóknak el kell végezniük. További információt a Vizsga dokumentációjában talál.
    - **Képernyőfigyelés** – Itt adhatja meg, hogy szeretné-e figyelni a felhasználók képernyőjét a vizsga során.
    - **Szövegjavaslat** – Engedélyezheti vagy letilthatja a szövegjavaslatokat a vizsga során.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.



