---
title: Szűrési szabályzatok hatókörcímkékkel a Microsoft Intune-ban – Azure | Microsoft Docs
description: Hatókörcímkékkel a konfigurációs profilokat meghatározott szerepkörök szerint szűrheti.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2536a5978bc9af99053e4513f4ceea8c0a40e633
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742261"
---
# <a name="use-scope-tags-to-filter-policies"></a>Hatókörcímkék használata szabályzatok szűrésére

A hatókörcímkék lehetővé teszik a szabályzatok Ön által létrehozott egyéni címkékkel való szűrését. Hatókörcímkék szerepköröket és alkalmazásokat is alkalmazhat.

Amikor egy rendszergazda az Intune-ban létrehoz egy erőforrást, minden rendszergazdának rendelt hatókörcímkék automatikusan rendeli hozzá az új erőforrás.

Létrehozhat például egy „Műszaki részleg” nevű hatókörcímkét, és hozzárendelheti a műszaki részleggel kapcsolatos konfigurációs profilokhoz. Hozzárendelheti ugyanazt a címkét a „Mérnöki rendszergazdák” szerepkörhöz. Ekkor csak a „Műszaki részleg” címkével rendelkező szabályzatokat fogják látni.

## <a name="to-create-a-scope-tag"></a>Hatókörcímke létrehozása

Válassza a **Szerepkörök** > **Hatókör (címkék)** > **Létrehozás** lehetőséget.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Hatókörcímke hozzáadása egy konfigurációs profilhoz

Válassza az **Eszközkonfiguráció** > **Profilok** > válasszon egy profilt > **Tulajdonságok** > **Hatókör (Címkék)** lehetőséget.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Hatókörcímke hozzárendelése egy szerepkörhöz

Válassza a **Szerepkörök** > **Minden szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** >  **Hatókör (címkék)** lehetőséget.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Hatókörcímke hozzárendelése egy alkalmazáshoz

Válasszon **ügyfélalkalmazás** > **alkalmazások** > Válasszon egy alkalmazást > **tulajdonságok** > **hatókör (címkék)**  >  **Hozzáadás** > Válassza ki a címkék > **kiválasztása** > **OK** > **mentése**.


## <a name="next-steps"></a>További lépések

A [szerepkörök](role-based-access-control.md) és a [profilok](device-profile-assign.md) kezelése.

