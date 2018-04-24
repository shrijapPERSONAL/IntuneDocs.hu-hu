---
title: Céges adatszivárgások megelőzése az Office 365 alkalmazásokban
description: Az Intune mobilalkalmazás-kezelési (MAM) szabályzataival megvédheti az Office 365 mobilalkalmazásaiban és egyéb üzletági alkalmazásokban tárolt szervezeti adatait a céges adatszivárgásoktól.
keywords: ''
author: jeffgilb
ms.author: jeffgilb
manager: dougeby
ms.date: 11/22/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 85233c06d9cbbc697aecabc75ba538612c0fa5fa
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Rövid útmutató: Céges adatszivárgások megelőzése az Office 365 mobilalkalmazásaiban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A Microsoft Intune mobilalkalmazás-kezelési (MAM) házirendjeivel megvédheti az Office 365 mobilalkalmazásaiban és egyéb üzletági alkalmazásokban tárolt szervezeti adatait a céges adatszivárgásoktól. A végfelhasználók az eszközeik az Intune mobileszköz-kezelésben (MDM) történő regisztrálása nélkül is használhatják az Intune MAM-házirendjeit. Így ha felhasználói nem szeretnék regisztrálni saját iOS- vagy Android-mobileszközüket a Microsoft MDM-megoldásainak egyikében (Intune, Configuration Manager, EAS), ha a felhasználók eszközeinek kezelése nélkül szeretné megvédeni a vállalati adatokat, vagy már egy nem Microsoft által szolgáltatott MDM-megoldást használ, az Intune segít a céges adatbiztonság megerősítésében.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Ez a nekem megfelelő útmutató?
Szeretné, hogy a végfelhasználók elérhessék az Office 365-ben, illetve az üzletági alkalmazásokban tárolt adatait iOS- és Android-eszközeiken anélkül, hogy egy mobileszköz-kezelési megoldásban regisztrálnák az eszközt, mindezt úgy, hogy Ön szabja meg, milyen engedélyekkel rendelkeznek az alkalmazások használatához (például azok átmásolása személyes alkalmazásokba)?

Ha igen, a Microsoft Intune az Ön számára megfelelő alkalmazás. Az Intune-nal MAM-házirendeket állíthat be az Office 365 iOS- és Android-mobilalkalmazásain, így többek között korlátozhatja a másolás és kivágás funkciókat, letilthatja a mentés másként funkciót, PIN-kódos védelmet állíthat be, és távolról törölheti a MAM által védett adatokat.  Így a céges adatok védelme érdekében a felhasználóknak nem kell egy MDM-megoldásban regisztrálni eszközeiket, mégis megmarad a gördülékeny végfelhasználói élményük az Office mobilalkalmazásaival.

## <a name="how-do-i-do-it"></a>Mit kell ehhez tennem?
1.  Ismerkedjen meg az [Intune mobilalkalmazás-kezelés (MAM)](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) működésével.
2.  Tájékozódjon a [mobilalkalmazás-kezelési (MAM) házirendek az Azure-portálon történő létrehozásának feltételeiről](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune).
3.  [Hozza létre és telepítse a MAM-házirendeket](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) az Intune-nal.

### <a name="additional-information"></a>További információ:
- [Végfelhasználói élmény](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) a MAM -kompatibilis alkalmazások esetében.
- [Üzletági alkalmazások előkészítése az Intune mobilalkalmazás-kezeléséhez](/intune/apps-prepare-mobile-application-management)
- <a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank">A Microsoft Intune MAM-kompatibilis alkalmazásokat nyújtó alkalmazáspartnereinek listája&rarr;</a>

## <a name="what-should-i-do-next"></a>További lépések
[Áttelepítés nem Microsoft által szolgáltatott MDM-megoldásról a Microsoft Intune-ra](/intune-classic/deploy-use/migrate-to-intune)

[Eszközök regisztrálása az Intune MDM-ben](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
