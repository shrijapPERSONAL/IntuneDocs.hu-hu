---
title: Egyéni VPN-profilok létrehozása a Microsoft Intune-nal
titleSuffix: ''
description: Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Egyéni VPN-profilok létrehozása a Microsoft Intune-ban

Egyéni Intune-konfigurációs szabályzatokkal VPN-profilok hozhatók létre a következő platformokon:

* Android 4 és újabb verziók
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* Windows Phone 8.1 és újabb verziók
* A Windows 10 asztali verzióját futtató regisztrált eszközök 
* Windows 10 mobil verzió

Az ilyen típusú szabályzat akkor lehet hasznos, ha a szabványos Intune VPN-szabályzatok nem tartalmazzák a használni kívánt beállításokat.

## <a name="to-create-a-custom-configuration-policy"></a>Egyéni konfigurációs szabályzat létrehozása:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panel **Kezelés** területén válassza a **Profilok** lehetőséget.
5. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
6. A **Profil létrehozása** panelen töltse ki az egyéni VPN-profil **Név** és **Leírás** mezőjét.
7. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a VPN-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet egyéni eszközbeállításokat megadni:
    - **Android**
    - **Android for Work**
    - **iOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **macOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil** típusa legördülő listában válassza az **Egyéni** lehetőséget.
7. Az **Egyéni OMA-URI beállítások** panelen minden egyes megadni kívánt URI-beállításhoz válassza a **Hozzáadás** elemet, adja meg a kért adatokat, majd kattintson az **OK** gombra. Például:

   ![VPN-profil egyéni konfigurációjának párbeszédpanelje](./media/Intune_Add_VPN_URI.png)

4.  Miután megadta az összes szükséges URI-beállítást, kattintson az **OK** gombra, majd a **Profil létrehozása** panelen válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.




