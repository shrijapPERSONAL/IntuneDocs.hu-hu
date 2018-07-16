---
title: Egyéni Intune-profilbeállítások androidos munkahelyi profilokhoz
titlesuffix: Microsoft Intune
description: Információk az androidos munkahelyi profilos eszközök egyéni Microsoft Intune-profilbeállításainak létrehozásáról.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905291"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Egyéni Intune-profilbeállítások Androidos munkahelyi profilos eszközökhöz

Az Intune androidos munkahelyi profilok egyéni konfigurációs szabályzatával olyan OMA-URI-beállításokat rendelhet hozzá, amelyekkel vezérelhetők az androidos munkahelyi profilos eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat is érvénybe léptethet, amelyek nem konfigurálhatók Intune-szabályzatokkal. Az Intune jelenleg csak korlátozott számú egyéni Android-szabályzatot támogat. E cikk példái alapján megtudhatja, mely szabályzatokat lehet konfigurálni.

## <a name="create-a-custom-profile"></a>Egyéni profil létrehozása

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása](custom-settings-configure.md) című témakör utasításait. A **Platform** területen válassza a **Vállalati Android** lehetőséget, a **Profil típusa** beállításnál pedig az **Egyéni** lehetőséget.
2. Az **Egyéni OMA-URI beállítások** panelen a **Hozzáadás** elemet választva adhat meg új beállítást.
3. A **Sor hozzáadása** panelen adja meg a következőket:
    - **Név** – Adjon egyedi nevet az androidos munkahelyi profil egyéni beállításainak, hogy azok azonosíthatók legyenek az Azure Portal webhelyen.
    - **Leírás** – Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.
    - **OMA-URI** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Adattípus** – Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Sztring**, **Sztring (XML)**, **Dátum és idő**, **Egész szám**, **Lebegőpontos szám**, **Logikai** vagy **Base64 (fájl)** lehetőségek közül választhat.
    - **Érték** – Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket. Az érték megadásának módszere a választott adattípusnak megfelelően változhat. **Dátum és idő** típus esetén például a naptárból választhat értéket.
4. Ha végzett, az OK választásával térhet vissza az **Egyéni OMA-URI beállítások** panelre, hogy további beállításokat adjon meg vagy a **Létrehozás** választásával létrehozza az egyéni profilt.


## <a name="example"></a>Példa

Ebben a példában egyéni profilt fogunk létrehozni, amellyel megszabható, hogy engedélyezi-e a munkahelyi és személyes alkalmazások közötti másolást és beillesztést a felügyelt androidos munkahelyi profilt használó eszközökön.

1. Az ebben a cikkben leírt eljárással hozzon létre egyedi profilt androidos munkahelyi profilos eszközökhöz az alábbi értékek használatával:
    - **Név** – Írja be a „Másolás és beillesztés tiltása” szöveget, vagy más tetszőleges megnevezést.
    - **Leírás** – Írja be a „Letiltja a másolást és beillesztést munkahelyi és személyes alkalmazások között” szöveget, vagy más tetszőleges leírást.
    - **OMA-URI** – Írja be a **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** értéket.
    - **Adattípus** – Válassza a **Logikai** értéket jelezve, hogy ez az OMA-URI vagy **Igaz** vagy **Hamis**.
    - **Érték** – Válassza az **Igaz** értéket.
2. A kész beállításnak az ábrán láthatóhoz hasonlónak kell lennie.
![Másolás és beillesztés tiltása androidos munkahelyi profilhoz.](./media/custom-policy-afw-copy-paste.png)
3. Ezután ha ezt az egyéni profilt egy Ön által kezelt androidos munkahelyi profilt használó eszközhöz társítja, tiltva lesz a másolás és beillesztés a munkahelyi és személyes profilokban futó alkalmazások között.