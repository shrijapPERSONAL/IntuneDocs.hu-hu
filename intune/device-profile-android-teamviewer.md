---
title: "Eszközök távoli felügyelete a TeamViewer használatával"
titlesuffix: Azure portal
description: "Útmutató eszközök távoli felügyeletéhez a TeamViewer használatával.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a4e2b3493467f922b844130829db8e5ba14b246
ms.sourcegitcommit: 474a24ba67f6bf4f00268bf9e4eba52331a6b82d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Távsegítség nyújtása az Intune által felügyelt eszközökhöz

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel távsegítséget nyújthat a felügyelt eszközök felhasználóinak. Olvassa el a jelen témakört az első lépésekhez.

## <a name="before-you-start"></a>Előkészületek

### <a name="supported-devices"></a>Támogatott eszközök

Az Intune-nal felügyelt Android- és Windows-eszközök támogatják a távfelügyeletet.

>[!NOTE]
>A TeamViewer szoftver nem támogatja a Windows Holographic (HoloLens), a Windows Team (Surface Hub) és a Windows 10 S rendszereket. 



### <a name="required-permissions"></a>Szükséges engedélyek

Győződjön meg arról, hogy az Azure Portal felhasználójához a következő engedélyek vannak-e hozzárendelve [Intune-szerepkörként](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):
- Ahhoz, hogy a rendszergazda módosíthassa a TeamViewer-összekötő beállításait, adja meg a **Távsegítség frissítése** engedélyt.
- Ahhoz, hogy a rendszergazda egy új távsegítségre vonatkozó kérést kezdeményezhessen, adja meg a **Távsegítség kérése** engedélyt. A **Távsegítség kérése** engedéllyel rendelkező felhasználók kérhetik munkamenet indítását bármely felhasználó számára. Ez nem korlátozódik egyik Intune-szerepkör hozzárendelési hatókörére sem. Az Intune-szerepkörök hozzárendelési hatókörei nem korlátozzák azon felhasználók vagy eszközök körét, amelynek esetében távsegítségre vonatkozó kérések kezdeményezhetők.

>[!NOTE]
>Ha engedélyezi a TeamViewert, engedélyezi a TeamViewer for Intune összekötőjének TeamViewer-munkamenetek létrehozását, Active Directory-adatok olvasását és a TeamViewer-fiók hozzáférési jogkivonatának mentéset.

### <a name="configure-the-intune-teamviewer-connector"></a>Az Intune TeamViewer-összekötő konfigurálása

Mielőtt távsegítséget nyújtana eszközökre, az alábbi lépéseket követve konfigurálnia kell az Intune TeamViewer-összekötőt:


1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Beállítás** > **TeamViewer-összekötő** lehetőséget.
5. A **TeamViewer-összekötő** panelen kattintson az **Engedélyezés** elemre, majd tekintse át és fogadja el a TeamViewer szolgáltatás licencszerződését.
6. Válassza **Az engedélyezéshez jelentkezzen be a TeamViewer szolgáltatásba** lehetőséget.
7. Ekkor megnyílik a TeamViewer webhelyének egyik oldala. A TeamViewer-licenc hitelesítő adatainak megadását követően kattintson a **Bejelentkezés** gombra.


## <a name="how-to-remotely-administer-a-device"></a>Eszközök távoli felügyelete

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Felügyelet** > **Minden eszköz** lehetőséget.
5. Válassza ki az eszközt, amelyet szeretne távolról felügyelni, majd az eszköztulajdonságok paneljén válassza az **Egyéb** > **Új távsegítség-munkamenet** lehetőséget.
6. Miután az Intune kapcsolódott a TeamViewer szolgáltatáshoz, látni fog némi információt az eszközről. Válassza a **Csatlakozás** lehetőséget a távoli munkamenet elindításához.

![Androidos TeamViewer-példa](./media/android-teamviewer.png)

A TeamViewer ablakban számos távoli műveletet végezhet el az eszközön, beleértve az eszköz távvezérlését. A végrehajtható műveletek teljes ismertetéséért lásd: a [TeamViewer dokumentációját](https://www.teamviewer.com/support/documents/).

Ha végzett, zárja be a TeamViewer ablakot.

## <a name="next-steps"></a>További lépések

A végfelhasználó egy értesítésjelzőt lát az eszközén található céges portál alkalmazás ikonján, és megjelenik egy értesítés is, ha megnyitja az alkalmazást. Ekkor lehetőségük nyílik a távsegítségkérés elfogadására.

