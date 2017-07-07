---
title: "Egyéni Intune profilbeállítások Android for Work rendszerhez"
titleSuffix: Intune on Azure
description: "Információk az Android for Work-eszközök egyéni Intune-profilbeállításainak létrehozásáról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b48fc7bd784b5d6d531ef5bf28fe835e394b106
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Android for Work-eszközök egyéni Intune profilbeállításainak létrehozása

Az Intune Android for Work egyéni konfigurációs szabályzatával olyan OMA-URI-beállításokat rendelhet hozzá, amelyekkel vezérelhetők az Android for Work-eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat is érvénybe léptethet, amelyek nem konfigurálhatók Intune-szabályzatokkal. Az Intune jelenleg csak korlátozott számú egyéni Android-szabályzatot támogat. E témakör példái alapján megtudhatja, mely szabályzatokat lehet konfigurálni.

## <a name="create-a-custom-profile"></a>Egyéni profil létrehozása

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása](custom-settings-configure.md) című témakör utasításait.
2. Az **Egyéni OMA-URI beállítások** panelen a **Hozzáadás** elemet választva adhat meg új beállítást.
3. A **Sor hozzáadása** panelen adja meg a következőket:
    - **Név** – Adjon meg egyedi nevet az Android for Work egyéni beállításainak, hogy azok azonosíthatók legyenek az Intune-portálon.
    - **Leírás** – Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.
    - **OMA-URI** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Adattípus** – Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc**, **Karakterlánc (XML)**, **Dátum és idő**, **Egész szám**, **Lebegőpontos szám**, **Logikai** vagy **Base64 (fájl)** lehetőségek közül választhat.
    - **Érték** – Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket. Az érték megadásának módszere a választott adattípusnak megfelelően változhat. **Dátum és idő** típus esetén például a naptárból választhat értéket.
4. Ha végzett, az OK választásával térhet vissza az **Egyéni OMA-URI beállítások** panelre, hogy további beállításokat adjon meg vagy a **Létrehozás** választásával létrehozza az egyéni profilt.


## <a name="example"></a>Példa

Ebben a példában egyéni profilt fogunk létrehozni, amellyel megszabható, hogy engedélyezi-e a munkahelyi és személyes alkalmazások közötti másolást és beillesztést a felügyelt Android for Work-eszközökön.

1. Az ebben a témakörben leírt eljárással hozzon létre egyedi profilt Android for Work-eszközökhöz az alábbi értékek használatával:
    - **Név** – Írja be a „Másolás és beillesztés tiltása” szöveget, vagy más tetszőleges megnevezést.
    - **Leírás** – Írja be a „Letiltja a másolást és beillesztést munkahelyi és személyes alkalmazások között” szöveget, vagy más tetszőleges leírást.
    - **OMA-URI** – Írja be a **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** értéket.
    - **Adattípus** – Válassza a **Logikai** értéket jelezve, hogy ez az OMA-URI vagy **Igaz** vagy **Hamis**.
    - **Érték** – Válassza az **Igaz** értéket.
2. A kész beállításnak az ábrán láthatóhoz hasonlónak kell lennie.
![Másolás és beillesztés tiltása Android for Work rendszerben.](./media/custom-policy-afw-copy-paste.png)
3. Ezután ha ezt az egyéni profilt egy Ön által kezelt Android for Work-eszközhöz társítja, tiltva lesz a másolás és beillesztés a munkahelyi és személyes profilokban futó alkalmazások között.