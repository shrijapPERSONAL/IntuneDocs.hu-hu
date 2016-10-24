---
title: "Többtényezős hitelesítés az Azure AD-vel | Microsoft Intune"
description: "Többtényezős hitelesítés kötelezővé tétele az Azure AD-ben az eszközök regisztrálásához."
keywords: 
author: nbigman
manager: angerobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: ccd55cc8637ebccfdbddd05c4f6b182c7923a2ab


---

# Többtényezős hitelesítés a Microsoft Intune-ban

Az Intune az Azure AD Multi-Factor Authentication (MFA) alkalmazásával segíti elő a vállalati erőforrások védelmét. Az MFA a felhasználónevek és jelszavak mellett olyan hitelesítési tényezőket is igényel, mint például a szöveges hitelesítés. Az MFA iOS, Windows 8.1 vagy újabb és Windows Phone 8.1 vagy újabb rendszerű eszközökön támogatott.

> [!NOTE]
>
> A Configuration Manager régebbi (az 1610-es kiadásnál korábbi) verzióiban az MFA-beállítás még megjelenik a Configuration Manager felügyeleti konzolján. Ne próbálkozzon az MFA konfigurálásával a Configuration Manager felügyeleti konzolján, mert az nem fog működni. Az MFA-t a jelen témakörben leírtak szerint konfigurálja.

### Kötelező többtényezős hitelesítés beállítása az eszközök regisztrálásához az Intune-ban
Az MFA eszközök regisztrálásakor való megköveteléséhez kövesse az alábbi lépéseket:

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



<!--HONumber=Sep16_HO4-->


