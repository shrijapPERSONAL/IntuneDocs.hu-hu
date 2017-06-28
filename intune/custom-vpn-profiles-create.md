---
title: "Egyéni VPN-profilok létrehozása a Microsoft Intune-nal"
titleSuffix: Intune on Azure
description: "Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 11da0d31a9a00364a6105006c3e75b6bb6f2cb77
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Egyéni VPN-profilok létrehozása a Microsoft Intune-ban

## <a name="create-a-custom-configuration"></a>Egyéni konfiguráció létrehozása
Egyéni Intune-konfigurációs szabályzatokkal VPN-profilok hozhatók létre a következőkhöz:

* Android 4 vagy újabb rendszerű eszközök
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* A Windows Phone 8.1-es vagy újabb verzióját futtató eszközök
* A Windows 10 asztali verzióját futtató regisztrált eszközök 
* Windows 10 Mobile-t futtató eszközök

Az ilyen típusú szabályzat akkor lehet hasznos, ha a szabványos Intune VPN-szabályzatok nem tartalmazzák a használni kívánt beállításokat.

## <a name="to-create-a-custom-configuration-policy"></a>Egyéni konfigurációs szabályzat létrehozása:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
5. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
6. A **Profil létrehozása** panelen töltse ki az egyéni VPN-profil **Név** és **Leírás** mezőjét.
7. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a VPN-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet egyéni eszközbeállításokat megadni:
    - **Android**
    - **iOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **macOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **Windows Phone 8.1**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza az **Egyéni** lehetőséget.
7. Az **Egyéni OMA-URI beállítások** panelen minden egyes megadni kívánt URI-beállításhoz válassza a **Hozzáadás** elemet, adja meg a kért adatokat, majd kattintson az **OK** gombra. Például:

   ![VPN-profil egyéni konfigurációjának párbeszédpanelje](./media/Intune_Add_VPN_URI.png)

4.  Miután megadta az összes szükséges URI-beállítást, kattintson az **OK** gombra, majd a **Profil létrehozása** panelen válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.





