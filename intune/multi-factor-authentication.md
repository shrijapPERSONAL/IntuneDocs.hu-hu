---
title: Többtényezős hitelesítés megkövetelése az Intune-os eszközregisztrációhoz
titlesuffix: Microsoft Intune
description: A többtényezős hitelesítés kötelezővé tétele az Azure AD-ben az Intune-os eszközregisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
ms.custom: intune-azure
ms.openlocfilehash: 270f19b6f0babb347b04731ca270a3c5bea18217
ms.sourcegitcommit: 5e5004a31207e75e54504d74548735c048676a03
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2018
ms.locfileid: "51225669"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Többtényezős hitelesítés megkövetelése az Intune-os eszközregisztrációhoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-nal növelheti vállalati erőforrásai biztonságát az Azure Active Directory (AD) többtényezős hitelesítést (MFA) eszközregisztrációkhoz való használatával.

Az MFA az alábbiak közül követeli meg legalább két ellenőrzési mód használatát:

- egy, a felhasználó által ismert információ (általában jelszó vagy PIN-kód)
- egy, a felhasználó birtokában lévő dolog (nehezen másolható, megbízható eszköz, például telefon)
- egy, a felhasználót azonosító dolog (biometrikus adatok, például ujjlenyomat).

Az MFA iOS, Android, Windows 8.1-es vagy újabb, Windows Phone 8.1-es vagy Windows 10 Mobile vagy újabb rendszerű eszközökön támogatott.

Az MFA engedélyezésekor a végfelhasználóknak kétféle hitelesítő adatot kell megadniuk az eszközök regisztrációjához.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Kötelező többtényezős hitelesítés beállítása az eszközök regisztrálásához az Intune-ban

Ha meg szeretné követelni a többtényezős hitelesítést a regisztráció során, tegye a következőket:

>[!Important]
>Ennek a szabályzatnak a használatához a felhasználókhoz rendelt legalább prémium P1 szintű Azure Active Directoryval kell rendelkeznie.

>[!Important]
>Ne konfiguráljon **eszközalapú hozzáférési szabályokat** a Microsoft Intune-regisztrációhoz.

1. Jelentkezzen be a [Microsoft Azure Portálra](https://portal.azure.com) a hitelesítő adataival.
2. A portálon lépjen az **[Azure Active Directoryra](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview)**.
3. Az **Azure Active Directory** Biztonság területén válassza a **[Feltételes hozzáférés](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)** lehetőséget.
4. Válassza az **Új szabályzat** lehetőséget.
5. Az **Új** szabályzat mezőbe írjon be egy beszédes nevet a szabályzathoz.
6. A **Hozzárendelések** szakaszban válassza a **Felhasználók és csoportok** lehetőséget.
7. A **Felhasználók és csoportok** területen válassza a **Felhasználók vagy csoportok kiválasztása** lehetőséget, majd jelölje be a **Felhasználók és csoportok** jelölőnégyzetet. Válassza ki azokat a felhasználókat és csoportokat, amelyek meg fogják kapni ezt a szabályzatot, majd válassza a **Kész** elemet.
8. A **Hozzárendelések** szakaszban válassza a **Felhőalkalmazások** lehetőséget.
9. A **Felhőalkalmazások** **Intune** lapján válassza az **Alkalmazások kiválasztása** elemet, majd a **Kijelölés** > **Microsoft Intune-regisztráció** lehetőséget, végül a **Kész** gombot.
10. A **Hozzárendelések** szakasz **Feltételek** területén nem kell semmilyen beállítást sem megadnia az MFA-hoz.
11. A **Hozzáférés-vezérlés** területen válassza az **Engedélyezés** elemet.
12. Az **Engedélyezés** szakaszban válassza a **Hozzáférés engedélyezése** lehetőséget, majd válassza a **Többtényezős hitelesítés megkövetelése** elemet. Ne válassza ki az **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, mert az eszközök megfelelőségét nem lehet ellenőrizni, amíg nincsenek regisztrálva. Válassza a **Kiválasztás** elemet.
13. Az **Új szabályzat** szakaszban válassza a **Szabályzat engedélyezése** > **Be** beállítást, majd a **Létrehozás** gombot.



## <a name="next-steps"></a>További lépések

Miután a végfelhasználók regisztrálták eszközeiket, egy második hitelesítési módot is használniuk kell, például PIN-kódot, telefont vagy biometrikát.
