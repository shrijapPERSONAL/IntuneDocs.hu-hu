---
title: Eszközök PIN-kódjának visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A PIN-kód eltávolítása művelettel eltávolíthatja vagy visszaállíthatja a PIN-kódot az Intune-nal kezelt vagy figyelt eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ha új PIN-kódot szeretne létrehozni egy eszközhöz, használja a  **PIN-kód eltávolítása** műveletet.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows Phone 8.1 (nincs az Azure Active Directoryhoz csatlakoztatva), beleértve a Windows 10 alkotói frissítésig terjedő kiadásokat
- Windows 10 alkotói frissítés és újabb
- iOS
- Az Android 7-nél régebbi verziói

Ez a funkció nem támogatott a következő rendszereken:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Új PIN-kód kérése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. Az Ön által kezel eszközök listájáról válasszon ki egy eszközt, majd válassza a **...További** lehetőséget. Majd válassza a **PIN-kód eltávolítása** távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.
