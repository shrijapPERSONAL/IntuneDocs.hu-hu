---
title: Mi a Microsoft Intune mindent a cégem előnyére
titleSuffix: ''
description: A Microsoft Intune-nal gyakori üzleti problémák megoldásában.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/26/2019
ms.topic: overview
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0118087d5084830ac7b1761109a2bb542ec37421
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041813"
---
# <a name="what-can-intune-do-for-my-company"></a>Hogyan válhat az Intune a cégem előnyére?
A Microsoft Intune egy felhőalapú nagyvállalati mobileszköz-felügyeleti (EMM) szolgáltatás, amely segítséget nyújt a munkatársak hatékonyságának fenntartásához a vállalati adatok védelmének megőrzése mellett.

Az Intune-nal a következőkre nyílik lehetősége:

- Felügyelheti a munkatársak által a vállalati adatok elérésére használt mobileszközöket.
- Felügyelheti a munkatársak által használt alkalmazásokat.
- Megóvhatja vállalati adatokat, szabályozva azt, ahogyan a munkatársak elérik és megosztják őket.
- Gondoskodhat arról, hogy az eszközök és az alkalmazások megfeleljenek a vállalat biztonsági követelményeinek.

## <a name="common-business-problems-that-intune-helps-solve"></a>Az Intune segítségével megoldható gyakori üzleti problémák

* [A helyszíni e-mailek és adatok védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Az Office 365 e-mailjeinek és adatainak védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Vállalati tulajdonú telefonok kiadása az informatikai dolgozóknak](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [„Saját eszközök használata” (BYOD) vagy „személyes eszközök” program ajánlása az összes dolgozónak](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Az Office 365 nem felügyelt nyilvános kioszkból történő biztonságos elérésének engedélyezése a dolgozók számára](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Korlátozott használatú megosztott táblagépek kiadása adott feladattal foglalkozó dolgozóknak](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

## <a name="quickstarts"></a>Gyorsútmutatók

Tisztában vagyunk vele, hogy a kezdeti lépésekhez mobileszközök kezelését nehéz lehet. Győződjön meg arról, hogy a vállalat nevében szüksége számos különböző döntést kell meghoznia. A következő gyors útmutatók súgó, az első lépések az Intune-nal, és végezze el a néhány gyakori feladatok minimális időn belül.

Kövesse a megfelelő sorrendben a **útmutatóink** ezt oldal bal oldalán a tartalomjegyzékből használatával.

- [Próbálja ki ingyenesen az Intune alkalmazást](free-trial-sign-up.md) – Az Intune tesztkörnyezetben történő kipróbálásához hozzon létre egy ingyenes előfizetést.    
- [Felhasználó létrehozása](quickstart-create-user.md) – A felhasználók Intune-ba való felvételével engedélyezheti nekik, hogy mobileszközről is elérjék a céges erőforrásokat.
- [Hozzon létre egy csoportot](quickstart-create-group.md) –, hogy könnyebben kezelhesse a szabályzatokat és alkalmazásokat, hozzáférhet a csoportokba rendezheti a felhasználókat.
- [Automatikus regisztráció beállítása](quickstart-setup-auto-enrollment.md) – állítsa be az Intune-eszközök automatikus regisztrálása, amikor adott felhasználói bejelentkeznek a Windows 10 rendszerű eszközökön.
- [Az eszköz regisztrálása](quickstart-enroll-windows-device.md) – a szerepkört egy Intune-felhasználó és eszköz regisztrálása az Intune-ban. Ezután térjen vissza az Intune-ban, és győződjön meg arról, hogy az eszköz regisztrálása sikerült.
- [Eszközmegfelelőségi szabályzat létrehozása](quickstart-set-password-length-android.md) – Létrehozhat egy megfelelőségi szabályzatot egy eszközhöz, és hozzárendelhet egy csoportot a szabályzathoz.
- [Értesítések küldése nem megfelelő eszközök](quickstart-send-notification.md) – e-mail-értesítés küldése a munkatársak megfelelőségi szabályzatot hoz létre és nem megfelelő eszközökkel rendelkező tagjainak.
- [Alkalmazás hozzáadása és hozzárendelése](quickstart-add-assign-app.md) – Hozzáadhat és hozzárendelhet egy alkalmazást a cég alkalmazottaihoz.
- [Alkalmazásvédelmi szabályzat létrehozása és hozzárendelése](quickstart-create-assign-app-policy.md) – Létrehozhat és hozzárendelhet egy alkalmazásvédelmi szabályzatot egy ügyfélalkalmazáshoz a végfelhasználó eszközén.
- [Egyéni szerepkör létrehozása és hozzárendelése](quickstart-create-custom-role.md) – Létrehozhat és hozzárendelhet egy specifikus engedélyeket biztosító egyéni szerepkört a biztonsági műveleti részleg számára. 
- [E-mail-profil létrehozása iOS-eszközökhöz](quickstart-email-profile.md) – Létrehozhat egy e-mail-profilt iOS-eszközökhöz.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, egy aktivált Intune rendszergazdai és bérlői fiókkal kell rendelkeznie. [Az Intune ingyenes](free-trial-sign-up.md), tesztkörnyezetben történő kipróbálásához hozzon létre egy ingyenes előfizetést. A jelenlegi előfizetők ezeket a tevékenységeket, az élő bérlőben is elvégezhetik. Ezek az első lépéseket bemutató cikkekben azt feltételezik, hogy tesztelési célú eszközöket dolgozik.

Az Első lépések útmutató összes feladatának elvégzéséhez az is szükséges, hogy Ön a cég globális rendszergazdája legyen.

## <a name="intune-architecture"></a>Az Intune architektúrája

Az Intune az Enterprise Mobility + Security (EMS) megoldás mobileszköz- és mobilalkalmazás-felügyeletért felelős összetevője. Szorosan együttműködik más EMS-összetevőkkel, így az identitáskezelés és a hozzáférés-vezérlés terén az Azure Active Directoryval (Azure AD), valamint az adatvédelem terén az Azure Information Protectionnel. Az Office 365-öt használ, engedélyezheti a munkatársak hatékonyságának minden eszközükön a szervezet adatait védeni.

![A Microsoft Intune magas szintű architekturális diagramja](/intune/media/intunearchitecture.svg)

## <a name="next-steps"></a>További lépések

[Az Azure használatának első lépései](get-started-azure.md) – Ebből a gyakorlatból megismerkedhet az Azure Portal felépítésével, és megtudhatja, hogyan módosíthatja a megjelenő oldalt.

## <a name="learn-more"></a>További információ

* [Mi az az Intune?](introduction-intune.md)
* [Mi az az Azure Portal?](what-is-intune.md)
* [Eszközök és alkalmazások életciklusa](introduction-device-app-lifecycles.md)
