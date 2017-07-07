---
title: "Céges adatok védelme adattitkosítással"
description: "Jelen útmutató segítséget nyújt abban hogy, hogyan védheti meg vállalatát adatvesztéssel szemben azáltal, hogy jelszót és adattitkosítást kényszerít ki egy szabályzattal a mobilalkalmazásokon."
keywords: "titkosítás, PIN-kód, adat"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 42ae7cdedbcbd9bf6420ca9fd2cfa39a75174736
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="quick-start-guide-protect-company-data-with-data-encryption"></a>Első lépések: Céges adatok védelme adattitkosítással

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune különféle módokon segíthet az Office mobilalkalmazások adatvesztésének megelőzésében:
- Vállalati adatok titkosítása az iOS és Android által biztosított legmagasabb szintű eszköztitkosítással.
- Olyan iOS- és Android-eszközökön, melyek nem regisztrálhatók mobileszköz-kezelésben adatvédelmi vagy jogi követelmények miatt.

A Microsoft Intune anélkül is segít az Office mobilalkalmazások adatvesztésének megelőzésében, és az Office 365 (O365) adatok biztosításában, hogy regisztrálnia kellene iOS vagy Android mobileszközét a teljes mobileszköz-kezelésben. Ez akkor is igaz, ha a mobileszközök kezelésére egy harmadik fél mobileszköz-kezelését használja.

## <a name="is-this-quick-start-guide-right-for-me"></a>Ez a nekem megfelelő útmutató?
Ez az útmutató akkor a leghasznosabb, ha eleget tesz a következő előfeltételeknek:
- Már használja, vagy rendelkezik O365 licencekkel, amiket használni szeretne, valamint Office mobilalkalmazásokat kezel.
- Office mobilalkalmazások használatát tervezi iOS vagy Android rendszeren.
- Használ valamilyen mobileszköz-kezelést, legyen az Microsoft vagy nem Microsoft. Ha nem tud mobileszköz-kezelést használni a jogszabályok miatt, ez az útmutató a hasznára lehet.

> [!NOTE]
> A Windows még nem támogatott platform Office mobilalkalmazások esetén. A mobilalkalmazás-kezelés regisztráció nélkül egyelőre nem kompatibilis az Exchange-el vagy a helyszíni SharePointtal. Csak az online verziókban tárolt adatot tudja megvédeni.

Jelen útmutató segítséget nyújt abban hogy, hogyan védheti meg vállalatát adatvesztéssel szemben azáltal, hogy jelszavakat és adattitkosítást kényszerít ki szabályzatokkal olyan mobilalkalmazásokon, amelyeket a beosztottjai bizalmas adat eléréséhez használnak, bármilyen eszközkezelési megoldásba való teljes regisztráció nélkül. A Microsoft Intune lehetővé teszi, hogy mobilalkalmazás-kezelési (MAM) szabályzatokat állítson be az Office mobilalkalmazásokon [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) és [Android](https://products.office.com/mobile/office-mobile-apps-for-android) rendszereken. Így az O365 adatok védelme érdekében a felhasználóknak nem kell egy mobileszköz-kezelési megoldásban regisztrálni eszközeiket, mégis megmarad a gördülékeny végfelhasználói élményük az Office mobilalkalmazásaival.

## <a name="how-do-i-do-it"></a>Mit kell ehhez tennem?
1.  [Az alkalmazásadatok védelmének áttekintése](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
2.  [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
3.  [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="additional-information"></a>További információ:
- [Mit tapasztalnak a végfelhasználók a MAM használatát támogató alkalmazások és a Microsoft Intune használata esetén?](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a Microsoft Intune-nal történő mobilalkalmazás-kezelésre](/intune/apps-prepare-mobile-application-management)
- [A Microsoft Intune-alkalmazáspartnerek listájának megtekintése](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
