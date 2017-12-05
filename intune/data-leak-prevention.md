---
title: "Adatszivárgás megakadályozása nem felügyelt eszközökön"
description: "Hozzáférés engedélyezése eszközökön a vállalati adatokhoz adatszivárgás elleni védelem mellett."
keywords: "adatvédelem, adatszivárgás elleni védelem, O365 eszköz, Office 365"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ae8702c51df1c3c2b8e6dd2a79bf4599e6b7677
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2017
---
# <a name="prevent-data-leaks-on-non-managed-devices"></a>Adatszivárgás megakadályozása nem felügyelt eszközökön

Ha az Office 365 által üzemeltetett vállalati adatokhoz engedélyez hozzáférést, ellenőrizheti, hogy a felhasználók hogyan osztják meg és mentik az adatokat, és megelőzheti a szándékos vagy véletlen adatszivárgást. A Microsoft Intune-nal olyan adatvédelmi szabályzatokat állíthat be, amelyekkel gondoskodhat a felhasználók saját eszközein található vállalati adatok biztonságáról. Az eszközöket nem szükséges regisztrálni az Intune szolgáltatásban. 

Az Intune-nal létrehozott alkalmazásvédelmi szabályzatok azokon az eszközökön is érvényesek lesznek, amelyeket nem a Microsoft által kínált eszközkezelési megoldással kezelnek. Az eszközön található személyes adatokra nincs hatással a rendszer: az informatikai szolgálat kizárólag a vállalati adatokat kezeli. 

A vállalati adatok védelméhez alkalmazásvédelmi szabályzatokat állíthat be az Office-mobilalkalmazásokhoz Windows, iOS és Android rendszereken. A szabályzatokkal beállíthat alkalmazásalapú PIN-kódokat, titkosíthatja a vállalati adatokat, de olyan speciális beállításokat is alkalmazhat, amelyek a felhasználó által a felügyelt és a nem felügyelt alkalmazások között használt kivágási, másolási, beillesztési vagy mentés másként műveleteket korlátozzák. Emellett anélkül törölheti az eszközről a vállalati adatokat, hogy a felhasználónak regisztrálnia kellene az eszközt. 

Az Intune alkalmazásvédelmi szabályzatai függetlenek az eszközkezeléstől. Az alkalmazásvédelmi szabályzatokkal Office-mobilalkalmazásokat lehet kezelni akár nem felügyelt eszközön, akár az Intune-nal felügyelt eszközökön, sőt a nem a Microsoft által kínált mobileszköz-kezelési megoldásokkal felügyelt eszközökön is. 

## <a name="before-you-begin"></a>Előkészületek

A lentebb ismertetett cselekvési terv az alábbi feltételek teljesülése esetén használható:
* A vállalat készen áll a felhőre való biztonságos áttérésre.
* A vállalat Office 365 Exchange Online-t, SharePoint Online-t, OneDrive vállalati verziót vagy Yammert használ.
* A vállalat rendelkezik licenccel a Microsoft 365, az Enterprise Mobility + Security (EMS) vagy az Azure Information Protection egyikéhez.
* A vállalat engedélyezi a felhasználóknak, hogy saját vagy céges tulajdonú, Windows, iOS vagy Android rendszerű eszközeikről hozzáférjenek a vállalati adatokhoz. 
* A vállalat nem szeretné megkövetelni a személyes tulajdonú eszközök eszközkezelési szolgáltatásban való regisztrálását. 

## <a name="action-plan"></a>Műveletterv

iOS és Android rendszerű eszközök esetén: 

1. Ismerje meg az [alkalmazásvédelmi szabályzatok](app-protection-policy.md) működését.
2. Ismerje meg az [alkalmazásvédelmi szabályzatok létrehozását és telepítését](app-protection-policies.md) Office-mobilalkalmazások esetén. 
3. [Figyelje a létrehozott és érvénybe léptetett alkalmazásvédelmi szabályzatokat](app-protection-policies-monitor.md). 

Windows 10-es eszközök esetén: 

1. Ismerje meg a [Azure Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) működését. 
2. Készüljön fel az [alkalmazásvédelmi szabályzatok Windows 10 rendszeren](app-protection-policies-configure-windows-10.md) történő konfigurálására.
3. [Hozzon létre és alkalmazzon WIP alkalmazásvédelmi szabályzatokat az Intune-nal](windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>Miről kell tájékoztatni az alkalmazottakat és a tanulókat?

További tájékoztatás érdekében ossza meg az alábbi hivatkozások közül a helyzetnek megfelelőt: 
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a>További lépések

Segítségre van szüksége ennek, illetve az egyéb EMS- vagy Office 365-forgatókönyvek lehetővé tételéhez? Ha legalább 150 Microsoft 365- , Enterprise Mobility + Security- vagy Prémium szintű Azure Active Directory-licenccel rendelkezik, használja [FastTrack-juttatásait](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 