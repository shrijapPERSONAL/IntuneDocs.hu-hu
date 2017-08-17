---
title: "Egyéni beállítások az Intune-ban Android-eszközök esetén"
titleSuffix: Intune on Azure
description: "Az egyéni Android-profil beállításainak ismertetése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45a3a8fe4960cc1bb8c5f2150f57d34d59c08e0a
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Androidos eszközökre vonatkozó egyéni beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune Androidos **egyéni** profiljával OMA-URI-beállításokat léptethet érvénybe, amelyekkel felügyelheti az Android-eszközökön elérhető szolgáltatásokat. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat is érvénybe léptethet, amelyek nem konfigurálhatók Intune-szabályzatokkal.

## <a name="custom-profile-settings-for-android-devices"></a>Egyéni profilbeállítások Android rendszerű eszközökhöz

1. Az első lépésekhez használja az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakört.
2. OMA-URI beállítások hozzáadásához a **Profil létrehozása** panelen válassza a **Beállítások** lehetőséget.
3. A **Sor szerkesztése** panelen minden beállításhoz konfigurálja az alábbi értékeket:
    - **Név** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Leírás** – Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.
    - **Adattípus** – Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc**, **Karakterlánc (XML)**, **Dátum és idő**, **Egész szám**, **Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.
    - **OMA-URI** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.
4. Ha elkészült, kattintson az **OK** gombra, és folytassa, ha újabb beállításokat kíván megadni.

## <a name="next-steps"></a>További lépések

A beállítások befejezését követően létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen. Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

Használhatja az alábbi néhány példában látható egyéni beállításokat:

- [Előmegosztott kulccsal ellátott Wi-Fi-profil létrehozása egyéni Microsoft Intune-eszközprofillal](/intune/wi-fi-profile-shared-key)
- [Alkalmazásonkénti VPN-profil létrehozása androidos eszközökhöz egyéni Microsoft Intune-profillal](/intune/android-pulse-secure-per-app-vpn)
- [Alkalmazások engedélyezése és letiltása egyéni szabályzattal Samsung KNOX Standard-eszközökön a Microsoft Intune-ban](/intune/samsung-knox-apps-allow-block)
