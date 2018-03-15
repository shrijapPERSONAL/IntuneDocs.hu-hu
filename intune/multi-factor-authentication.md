---
title: "Többtényezős hitelesítés megkövetelése az Intune-os eszközregisztrációhoz"
titlesuffix: Microsoft Intune
description: "A többtényezős hitelesítés kötelezővé tétele az Azure AD-ben az Intune-os eszközregisztrálásához."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/10/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 4dbb1b94fa7e2ebc5ce31ae00c3cb893f9e1470e
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Többtényezős hitelesítés megkövetelése az Intune-os eszközregisztrációhoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune-nal növelheti vállalati erőforrásai biztonságát az Azure Active Directory (AD) többtényezős hitelesítést (MFA) eszközregisztrációkhoz való használatával.

Az MFA az alábbiak közül követeli meg legalább két ellenőrzési mód használatát:

- egy, a felhasználó által ismert információ (általában jelszó vagy PIN-kód)
- egy, a felhasználó birtokában lévő dolog (nehezen másolható, megbízható eszköz, például telefon)
- egy, a felhasználót azonosító dolog (biometrikus adatok, például ujjlenyomat).

Az MFA iOS, Android, Windows 8.1-es vagy újabb, Windows Phone 8.1-es vagy Windows 10 Mobile vagy újabb rendszerű eszközökön támogatott.

Az MFA engedélyezésekor a végfelhasználóknak kétféle hitelesítő adatot kell megadniuk az eszközök regisztrációjához.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Kötelező többtényezős hitelesítés beállítása az eszközök regisztrálásához az Intune-ban

Ha meg szeretné követelni a többtényezős hitelesítést a regisztráció során, tegye a következőket:

[!Important]
>Ennek a szabályzatnak a használatához a felhasználókhoz rendelt legalább prémium P1 szintű Azure Active Directoryval kell rendelkeznie.

>[!Important]
>Ne konfiguráljon **eszközalapú hozzáférési szabályokat** a Microsoft Intune-regisztrációhoz.

1. Jelentkezzen be a [Microsoft Azure Portálra](https://portal.azure.com) a hitelesítő adataival.
2. A portálon válassza az **Azure Active Directory** lehetőséget.
2. Az **Azure Active Directoryban** válassza a **Kezelés** > **Vállalati alkalmazások** pontot.
3. A **Vállalati alkalmazások** lapon válassza a **Kezelés**  > **Minden alkalmazás** pontot. Megjelenik az Ön által kezel összes Azure-alkalmazást tartalmazó lista.
3. A listáról válassza a **Microsoft Intune-regisztráció** elemet.
4. A **Microsoft Intune-ban** válassza a **Biztonság** > **Feltételes hozzáférés** elemet.
5. Válassza az **Új szabályzat** lehetőséget.
6. Az **Új** szabályzat mezőbe írjon be egy beszédes nevet a szabályzathoz.
7. A **Hozzárendelések** szakaszban válassza a **Felhasználók és csoportok** lehetőséget.
8. A **Felhasználók és csoportok** lapon válassza ki azokat a felhasználókat és csoportokat, amelyek meg fogják kapni ezt a szabályzatot, majd válassza a **Kész** elemet.
9. A **Hozzárendelések** szakaszban válassza a **Felhőalkalmazások** lehetőséget.
10. A **Felhőalkalmazások** **Intune** lapján válassza az **Alkalmazások kiválasztása** elemet, majd a **Kijelölés** > **Microsoft Intune-regisztráció** lehetőséget, végül a **Kész** gombot.
11. A **Hozzárendelések** szakaszban válassza a **Feltételek** lehetőséget.
12. A **Feltételek** szakaszban nem kell semmilyen beállítást sem megadnia az MFA-hoz.
13. A **Hozzáférés-vezérlés** területen válassza az **Engedélyezés** elemet.
14. Az **Engedélyezés** szakaszban válassza a **Hozzáférés engedélyezése** lehetőséget, majd válassza a **Többtényezős hitelesítés megkövetelése** elemet.
    Ne válassza ki az **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, mert az eszközök megfelelőségét nem lehet ellenőrizni, amíg nincsenek regisztrálva.
15. Válassza a **Kijelölés** elemet.
16. Az **Új szabályzat** szakaszban válassza a **Szabályzat engedélyezése** > **Be** beállítást, majd a **Létrehozás** gombot.



## <a name="next-steps"></a>További lépések

Miután a végfelhasználók regisztrálták eszközeiket, egy második hitelesítési módot is használniuk kell, például PIN-kódot, telefont vagy biometrikát.
