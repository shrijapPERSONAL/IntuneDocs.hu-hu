---
title: "Androidos eszközök távoli felügyelete a TeamViewer használatával"
titleSuffix: Intune on Azure
description: "Útmutató androidos eszközök távoli felügyeletéhez a TeamViewer használatával.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15a005ae2b84c7bd4f913f892089965c10f3b23e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Távsegítség nyújtása az Intune által felügyelt Android-eszközökhöz

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani az androidos eszközök felhasználóinak. Olvassa el a jelen témakört a beállítások megadásához és az első lépésekhez.

## <a name="before-you-start"></a>Előkészületek

### <a name="required-permissions"></a>Szükséges engedélyek

Győződjön meg arról, hogy az Azure Portal felhasználójához a következő engedélyek vannak-e hozzárendelve [Intune-szerepkörként](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):
- Ahhoz, hogy a rendszergazda módosíthassa a TeamViewer-összekötő beállításait, adja meg a **Távsegítség frissítése** engedélyt.
- Ahhoz, hogy a rendszergazda egy új távsegítségre vonatkozó beállítások megadását kezdeményezhesse, adja meg a **Távsegítség kérése** engedélyt. Az ezzel az engedéllyel rendelkező felhasználók kérhetik munkamenet indítását bármely felhasználó számára. Ez nem korlátozódik bármely Intune-szerepkör hozzárendelési hatókörére. Az Intune-szerepkörök hozzárendelési hatókörei nem korlátozzák azon felhasználók vagy eszközök körét, amelynek esetében távsegítségre vonatkozó kérések kezdeményezhetők.

>[!NOTE]
>Ha engedélyezi a TeamViewert, engedélyezi a TeamViewer for Intune összekötőjének TeamViewer-munkamenetek létrehozását, Active Directory-adatok olvasását és a TeamViewer-fiók hozzáférési jogkivonatának mentéset.

### <a name="configure-the-intune-teamviewer-connector"></a>Az Intune TeamViewer-összekötő konfigurálása

Mielőtt távsegítséget nyújtana androidos eszközökre, az alábbi lépéseket követve konfigurálnia kell az Intune TeamViewer-összekötőt:


1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Beállítás** > **TeamViewer-összekötő** lehetőséget.
5. A **TeamViewer-összekötő** panelen kattintson az **Engedélyezés** elemre, majd tekintse át és fogadja el a TeamViewer szolgáltatás licencszerződését.
6. Válassza **Az engedélyezéshez jelentkezzen be a TeamViewer szolgáltatásba** lehetőséget.
7. Ekkor megnyílik a TeamViewer webhelyének egyik oldala. A TeamViewer-licenc hitelesítő adatainak megadását követően kattintson a **Bejelentkezés** gombra.


## <a name="how-to-remotely-administer-an-android-device"></a>Androidos eszközök távoli felügyelete

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Felügyelet** > **Minden eszköz** lehetőséget.
5. Válassza ki az eszközt, amelyet szeretne távolról felügyelni, majd az eszköztulajdonságok paneljén válassza az **Egyéb** > **Új távsegítség-munkamenet** lehetőséget.
6. Miután az Intune kapcsolódott a TeamViewer szolgáltatáshoz, látni fog némi információt az androidos eszközről. Válassza a **Csatlakozás** lehetőséget a távoli munkamenet elindításához.

![Androidos TeamViewer-ablakok](./media/android-teamviewer.png)

A TeamViewer ablakban számos távoli műveletet végezhet el az androidos eszközön, beleértve az eszköz távvezérlését. A végrehajtható műveletek teljes ismertetéséért lásd: a [TeamViewer dokumentációját](https://www.teamviewer.com/support/documents/).

Ha elkészült. zárja be a TeamViewer ablakát.

## <a name="end-user-notifications"></a>Végfelhasználói értesítések

A végfelhasználó egy értesítésjelzőt fog látni a Céges portál alkalmazás ikonján az eszközén, és megjelenik egy értesítés is, ha megnyitja az alkalmazást. Ekkor lehetőségük nyílik a távsegítségkérés elfogadására.

