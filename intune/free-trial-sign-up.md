---
title: "Regisztráció a Microsoft Intune 30 napos próbaverziójára"
titleSuffix: Azure portal
description: "Regisztráció az Intune 30 napos próbaverziójára.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 03/04/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 08fa759515d437e40a751ce39b3ef617dd92e83f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Regisztráció a Microsoft Intune ingyenes próbaverziójára


Ez a cikk végigvezeti Önt az Azure Portalhoz tartozó önálló Intune-próbaverzióra történő regisztráció lépésein.

1. Látogasson el az [Intune regisztrációs](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) oldalára, és töltse ki az űrlapot a próbaverzióra való regisztrációhoz.
* Ha rendelkezik munkahelyi vagy iskolai fiókkal és azt szeretné használni az Intune próbaverziójához, akkor kövesse [ezeket a regisztrációs utasításokat](/intune/account-sign-up).

* Ha az informatikai operatív tevékenység és a felhasználók túlnyomó része nem az Ön földrajzi helyén van, érdemes lehet azt az adott földrajzi helyet kiválasztania a **Hol működik a cége?** legördülő listában.

2. A regisztrációs folyamat végén egy üzenet jelenik meg, amely az új fiók adatait tartalmazza. <br/> ![Fiókadatok képernyőképe](./media/2-end-of-sign-up-process.png) <br/>Ha ekkor a **Minden készen áll** gombra kattint, megnyílik az Office 365 felügyeleti központja, ahol felhasználókat adhat a tesztkörnyezethez. <br/><br/>Ha viszont közvetlenül az Intune Azure Portalra szeretne belépni, nyisson meg egy új böngészőablakot, és írja be a **https://portal.azure.com** címet a böngésző címsorába. Megnyílik az Azure bejelentkezési oldala, ahol a bejelentkezéshez megadhatja a kapott hitelesítő adatokat. Ezt a címet bármikor használhatja, amikor az Intune próbaverziójába szeretne belépni. <br/> ![Az Azure Portal bejelentkezési oldalának képernyőképe](./media/azure-portal-signin.png)

Amikor először jelentkezik be az Intune [Azure Portalba](https://portal.azure.com), akkor előfordulhat, hogy az Intune nem jelenik meg az Azure-irányítópulton. Az Intune szolgáltatás felvétele az Azure-irányítópultra:
1. Az irányítópult bal oldalán, az Azure-szolgáltatások listájában kattintson a **Minden szolgáltatás >** elemre, és a keresőmezőbe írja be az **Intune** kifejezést.
2. Válassza a listából az **Intune** elemet, és a csillagra kattintva vegye fel a szolgáltatáslistára.<br/> ![Kép: az Intune kiválasztása a szolgáltatáslistából](./media/azure-add-intune1.png)
3. Ezután a szolgáltatáslistában az **Intune** elemet kiválasztva megnyithatja az Intune-irányítópultot.

Amikor próbaverziót regisztrál, e-mailben elküldjük a fiókadatait is a regisztráció során megadott e-mail címre. Az e-mail megerősíti, hogy a próbaverzió aktív.

## <a name="keeping-the-admin-experiences-straight"></a>Átlátható felügyelet

Két portált használhat:
- Az Intune-irányítópultot az Azure-on ([portal.azure.com](https://portal.azure.com)), ahol megismerheti [mire képes az Intune](what-is-intune.md). Többnyire az Intune-irányítópulton fog dolgozni.
- Az Office 365 Felügyeleti központot ([portal.office.com](https://portal.office.com)), ahol a felhasználókat adhatja hozzá és kezelheti, ha nem az Azure Active Directoryt használja ezekre a feladatokra. Továbbá fiókjának számlázási- támogatási- és egyéb aspektusait is kezelheti itt.

## <a name="next-steps"></a>További lépések

### <a name="integration-with-other-products"></a>Integráció más termékekkel
Az Azure Active Directory felhasználói fiókok Intune-nal való használatával kapcsolatos további információk:
- [Identitáskövetelmények](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [A címtár-szinkronizálás követelményei](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Többtényezős hitelesítés követelményei](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

További információk [Az Intune és a System Center Configuration Manager együttes használatáról](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)
