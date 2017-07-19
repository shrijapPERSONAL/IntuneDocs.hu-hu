---
title: "Regisztrálás a 30 napos ingyenes próbaverzióhoz"
titleSuffix: Intune on Azure
description: "Regisztráció az Intune-ra az Azure-ban."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7dafdb974dd975eaa7f3268119de6c047c50f858
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal"></a>Regisztráció a Microsoft Intune ingyenes, az Azure Portalon elérhető próbaverziójára


Ez a cikk végigvezeti Önt az Azure Portalhoz tartozó önálló Intune-próbaverzióra történő regisztráció lépésein.

1. Látogasson el az [Intune regisztrációs](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) oldalára, és töltse ki az űrlapot a próbaverzióra való regisztrációhoz.
account-sign-up.md

  Ha az informatikai operatív tevékenység és a felhasználók túlnyomó része nem az Ön földrajzi helyén van, érdemes lehet azt az adott földrajzi helyet kiválasztania a **Hol működik a cége?** legördülő listában.

2. A regisztrációs folyamat végén egy üzenet jelenik meg, amely az új fiók adatait tartalmazza. <br/> ![Fiókadatok képernyőképe](./media/2-end-of-sign-up-process.png) <br/>Ha ekkor a **Minden készen áll** gombra kattint, megnyílik az Office 365 felügyeleti központja, ahol felhasználókat adhat a tesztkörnyezethez. <br/><br/>Ha viszont közvetlenül az Intune Azure Portalra szeretne belépni, nyisson meg egy új böngészőablakot, és írja be a **https://portal.azure.com** címet a böngésző címsorába. Megnyílik az Azure bejelentkezési oldala, ahol a bejelentkezéshez megadhatja a kapott hitelesítő adatokat. Ezt a címet bármikor használhatja, amikor az Intune próbaverziójába szeretne belépni. <br/> ![Az Azure Portal bejelentkezési oldalának képernyőképe](./media/azure-portal-signin.png)

Amikor először jelentkezik be az azure-os Intune-ba, akkor előfordulhat, hogy az Intune nem jelenik meg az Azure-irányítópulton. Az Intune szolgáltatás felvétele az Azure-irányítópultra:
1. Az irányítópult bal oldalán, az Azure-szolgáltatások listájában kattintson a **További szolgáltatások >** elemre, és a keresőmezőbe írja be az **Intune** kifejezést.
2. Válassza a listából az **Intune** elemet, és a csillagra kattintva vegye fel a szolgáltatáslistára.<br/> ![Kép: az Intune kiválasztása a szolgáltatáslistából](./media/azure-add-intune1.png)
3. Ezután a szolgáltatáslistában az **Intune** elemet kiválasztva megnyithatja az Intune-irányítópultot.

Amikor próbaverziót regisztrál, e-mailben elküldjük a fiókadatait is a regisztráció során megadott e-mail címre. Az e-mail megerősíti, hogy a próbaverzió aktív.



## <a name="keeping-the-admin-experiences-straight"></a>Átlátható felügyelet


Az Intune Azure Portalhoz három portált használhat:
- Az Intune-irányítópultját az Azure-on ([portal.azure.com](https://portal.azure.com)), ahol megismerheti [mire képes az Intune az Azure Portalon](what-is-intune.md).
- Az Office 365 Felügyeleti központot ([portal.office.com](https://portal.office.com)), ahol a felhasználókat adhatja hozzá és kezelheti, ha nem az Azure Active Directory-t használja ezekre a feladatokra. Továbbá fiókjának számlázási- támogatási- és egyéb aspektusait is kezelheti itt.
- A klasszikus Intune felügyeleti konzolt ([manage.microsoft.com](https://manage.microsoft.com)), ahol megismerheti azokat a funkciókat is, amelyek még nem elérhetőek az Azure-on.

Többnyire az alább látható Intune-irányítópulton fog dolgozni. Ezen az oldalon állíthatja be és kezelheti a csoportjait, szabályzatait, eszközeit és alkalmazásait.

Az irányítópultról elérheti a klasszikus Intune felügyeleti portált, ha a **Klasszikus portál** elemre kattint az irányítópult tetején.

Ha vissza szeretne térni az Intune Azure Portalhoz, nyissa meg a https://portal.azure.com webhelyet a böngészőben, és válassza újból az **Intune** elemet a szolgáltatáslistából.

 ![Az Intune-irányítópult képe](./media/intune-azure-dashboard.png)


Az alábbi képen az Office 365 felügyeleti központ látható, ahol hozzáadhatja és kezelheti a felhasználókat, valamint a fiók olyan egyéb aspektusait, mint a számlázás és a támogatás.

![Az Office 365 felügyeleti központját bemutató kép](./media/office-admin-center.png)

Ha az Office 365 felügyeleti központból szeretné elérni az Intune irányítópultot, nyissa meg a https://portal.azure.com webhelyet a böngészőben. Válassza a szolgáltatáslistából az **Intune** elemet.

Ha az Intune-ból szeretné elérni az Office 365 felügyeleti központot, nyissa meg a https://portal.office.com webhelyet a böngészőben. Ha már bejelentkezett az Intune-ba, akkor közvetlenül az Office 365 felügyeleti központba fog jutni.

## <a name="next-steps"></a>További lépések

### <a name="intune-on-azure"></a>Az Azure-on elérhető Intune szolgáltatás
További tudnivalók az [Azure Portálon elérhető Intune-ról](what-is-intune.md)
### <a name="classic-intune"></a>Klasszikus Intune
Kipróbálási forgatókönyv: [Mobileszköz-kezelés kipróbálása a Microsoft Intune-ban](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integráció más termékekkel
Az Azure Active Directory felhasználói fiókok Intune-nal való használatával kapcsolatos további információk:
- [Identitáskövetelmények](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [A címtár-szinkronizálás követelményei](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Többtényezős hitelesítés követelményei](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

További információk [Az Intune és a System Center Configuration Manager együttes használatáról](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)
