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
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329427"
---
# <a name="use-scope-tags-to-filter-policies"></a>Hatókörcímkék használata szabályzatok szűrésére

A hatókörcímkék lehetővé teszik a szabályzatok Ön által létrehozott egyéni címkékkel való szűrését.

Létrehozhat például egy „Műszaki részleg” nevű hatókörcímkét, és hozzárendelheti a műszaki részleggel kapcsolatos konfigurációs profilokhoz. Hozzárendelheti ugyanazt a címkét a „Mérnöki rendszergazdák” szerepkörhöz. Ekkor csak a „Műszaki részleg” címkével rendelkező szabályzatokat fogják látni.

## <a name="to-create-a-scope-tag"></a>Hatókörcímke létrehozása

Válassza a **Szerepkörök** > **Hatókör (címkék)** > **Létrehozás** lehetőséget.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Hatókörcímke hozzáadása egy konfigurációs profilhoz

Válassza az **Eszközkonfiguráció** > **Profilok** > válasszon egy profilt > **Tulajdonságok** > **Hatókör (Címkék)** lehetőséget.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Hatókörcímke hozzárendelése egy szerepkörhöz

Válassza a **Szerepkörök** > **Minden szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** >  **Hatókör (címkék)** lehetőséget.

## <a name="next-steps"></a>További lépések

A [szerepkörök](role-based-access-control.md) és a [profilok](device-profile-assign.md) kezelése.

