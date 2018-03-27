---
title: Többtényezős hitelesítés az Intune-os eszközregisztrációhoz
description: Többtényezős hitelesítés kötelezővé tétele az Azure AD-ben az eszközök regisztrálásához.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: ''
ms.service: ''
ms.technology: ''
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: e8572834aed14ee08b3ba3c74bc7504193397ef5
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Többtényezős hitelesítés az Intune-os eszközregisztrációhoz

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune az Azure AD Multi-Factor Authentication (MFA) alkalmazásával segíti elő a vállalati erőforrások védelmét.

Az MFA az alábbiak közül követeli meg legalább két ellenőrzési mód használatát: 

- egy, a felhasználó által ismert információ (általában jelszó vagy PIN-kód)
- egy, a felhasználó birtokában lévő dolog (nehezen másolható, megbízható eszköz, például telefon)
- egy, a felhasználóhoz kötődő jellegzetesség (biometrikus azonosítójegy).

Az MFA iOS, Windows 8.1-es vagy újabb, illetve Windows Phone 8.1-es vagy újabb rendszerű eszközökön támogatott.

> [!NOTE]
> A Configuration Manager régebbi (az 1610-es kiadásnál korábbi) verzióiban az MFA-beállítás még megjelenik a Configuration Manager felügyeleti konzolján. Ne próbálkozzon az MFA konfigurálásával a Configuration Manager felügyeleti konzolján, mert az nem fog működni. Az MFA-t a jelen témakörben leírtak szerint konfigurálja.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Kötelező többtényezős hitelesítés beállítása az eszközök regisztrálásához az Intune-ban
Ha meg szeretné követelni a többtényezős hitelesítést a regisztráció során, tegye a következőket:

1. Jelentkezzen be a [Microsoft Azure Portalra](https://manage.windowsazure.com) a rendszergazdai hitelesítő adataival.
2. Válassza ki a kívánt bérlőt.
2. Kattintson az **alkalmazások** fülre. Megjelenik azon szolgáltatások listája, amelyekhez konfigurálhatja az Azure AD biztonsági szolgáltatásait.
3. Válassza a **Microsoft Intune-regisztráció** elemet.
4. Válassza a **Konfigurálás** elemet. 
5. A **többtényezős hitelesítés és helyalapú hozzáférési szabályok** elemcsoportjában:
    
    -  Engedélyezheti a hozzáférési szabályokat
    -  Megadhatja, hogy a szabályokat az összes felhasználóra vagy meghatározott Azure AD-alapú biztonsági csoportokra kívánja-e alkalmazni.
    -  Kötelezővé teheti a többtényezős hitelesítést valamennyi eszköz regisztrálásához.
    -  Kötelezővé teheti a többtényezős hitelesítést akkor, ha az eszköz nem a munkahelyen van.
    -  Válassza a **Block access to corporate resources** (Vállalati erőforrásokhoz való hozzáférés tiltása) lehetőséget, hogy megakadályozza a vállalati hálózathoz nem csatlakoztatott eszközök regisztrálását. 
4. A **munkahelyi hálózati hely megadására/szerkesztésére** szolgáló hivatkozásra kattintva konfigurálhatja az eszközök regisztrálásához szükséges hálózati kapcsolatokra vonatkozó követelményeket.

> [!IMPORTANT]
> 
> Ne konfiguráljon **eszközalapú hozzáférési szabályokat** a Microsoft Intune-regisztrációhoz.
