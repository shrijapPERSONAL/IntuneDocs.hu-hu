---
title: "A Windows 10 kiadásfrissítéseinek konfigurálása az Intune-ban"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt arról, hogyan frissíthetők a felügyelt Windows 10-es eszközök más verzióra az Intune-naI."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6bd4c4af168bc64acabc05fdaad93558ddd10a
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>A Windows 10 kiadásfrissítéseinek konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A témakörből megtudhatja, hogyan konfigurálhat Windows 10-es kiadásfrissítési profilt. Ez a profil lehetővé teszi az alábbi Windows 10-verziók valamelyikét futtató eszközök más verzióra történő automatikus frissítését:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 mobil verzió


Az alábbi verziófrissítési útvonalak támogatottak:

- Windows 10 Próról Windows 10 Enterprise-ra
- Windows 10 Home-ról Windows 10 Educationre
- Windows 10 Mobile-ról Windows 10 Mobile Enterprise-ra
- Windows 10 Holographic Próról Windows 10 Holographic Enterprise-ra


## <a name="before-you-start"></a>Előkészületek
Az eszközök legújabb verzióra történő frissítéséhez szüksége lesz a következők közül valamelyikre:

- Termékkulcsra, amely érvényes a Windows új verziójának – a házirend céljaként meghatározott összes eszközre történő – telepítéséhez (a Windows 10 asztali verziója esetén). A Többszörös aktiválási kulcsok (MAK), a Kulcskezelési kiszolgálói (KMS) kulcsok, vagy egy Microsoft által kiadott, a licencelési adatokat tartalmazó licencfájl segítségével telepítheti a Windows új verzióját minden eszközön, amelyet a szabályzat céljaként határozott meg (Windows 10 mobilverzió és Windows 10 Holographic esetén).
- A Windows 10 rendszerű eszközöket, amelyekhez hozzárendeli a szabályzatot, regisztrálni kell a Microsoft Intune-ban. A kiadásfrissítési szabályzat nem használható az Intune PC-ügyfélszoftvert futtató számítógépekkel.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be a kiadásfrissítési profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listából válassza az **Kiadásfrissítés** lehetőséget.
7. A **Kiadásfrissítés** panelen konfigurálja az alábbi beállításokat:
    - **Frissítendő kiadás** – A legördülő listából válassza ki azt a Windows 10-verziót, amelyet frissíteni szeretne az eszközökön.
    - **Frissítés erre a kiadásra** – A legördülő listából válassza ki a Windows 10 asztali verzió, a Windows 10 Holographic vagy a Windows 10 Mobile rendszernek azt a verzióját, amelyre a megcélzott eszközöket frissíteni szeretné.
    - **Termékkulcs** – Adja meg a Microsofttól beszerzett termékkulcsot, mely minden megcélzott, a Windows 10 asztali verzióját futtató eszköz frissítéséhez használható.<br>Miután létrehozta a termékkulcsot tartalmazó szabályzatot, a termékkulcsot már nem szerkesztheti. Ennek oka a kulcs biztonsági okokból történő elrejtése. Ha módosítani szeretné a termékkulcsot, a teljes kulcsot újra meg kell adnia.
    - **Licencfájl** – Válassza a **Tallózás** elemet, és jelölje ki a Microsofttól beszerzett, a Windows Holographic vagy a Windows 10 Mobile azon kiadásának licencadatait tartalmazó licencfájlt, amelyre a célzott eszközöket frissíteni szeretné.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="next-steps"></a>További lépések

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

>[!NOTE]
>Ha később eltávolítja a szabályzat-hozzárendelést, az eszközön futó Windows-verzió nem áll vissza, és továbbra is megfelelően működik.

