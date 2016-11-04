---
title: "Vállalati adatok védelme adattitkosítással | Microsoft Intune"
description: "Jelen útmutató segítséget nyújt abban hogy, hogyan védheti meg vállalatát adatvesztéssel szemben azáltal, hogy jelszót és adattitkosítást kényszerít ki egy szabályzattal a mobilalkalmazásokon."
keywords: "titkosítás, PIN-kód, adat"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ms.reviewer: pchacon
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7d4f7d48e14a7d4f6a19cf3c459406ce241647a
ms.openlocfilehash: 0dd683017028dc594fc2326df7f8592c706843a2


---

# Első lépések: Céges adatok védelme adattitkosítással
A Microsoft Intune különféle módokon segíthet az Office mobilalkalmazások adatvesztésének megelőzésében:
- Vállalati adatok titkosítása az iOS és Android által biztosított legmagasabb szintű eszköztitkosítással.
- Olyan iOS- és Android-eszközökön, melyek nem regisztrálhatók mobileszköz-kezelésben adatvédelmi vagy jogi követelmények miatt.

A Microsoft Intune anélkül is segít az Office mobilalkalmazások adatvesztésének megelőzésében, és az Office 365 (O365) adatok biztosításában, hogy regisztrálnia kellene iOS vagy Android mobileszközét a teljes mobileszköz-kezelésben. Ez akkor is igaz, ha a mobileszközök kezelésére egy harmadik fél mobileszköz-kezelését használja. 

## Ez a nekem megfelelő útmutató?
Ez az útmutató akkor a leghasznosabb, ha eleget tesz a következő előfeltételeknek:
- Már használja, vagy rendelkezik O365 licencekkel, amiket használni szeretne, valamint Office mobilalkalmazásokat kezel.
- Office mobilalkalmazások használatát tervezi iOS vagy Android rendszeren. 
- Használ valamilyen mobileszköz-kezelést, legyen az Microsoft vagy nem Microsoft. Ha nem tud mobileszköz-kezelést használni a jogszabályok miatt, ez az útmutató a hasznára lehet. 

> [!NOTE] 
> A Windows még nem támogatott platform Office mobilalkalmazások esetén. A mobilalkalmazás-kezelés regisztráció nélkül egyelőre nem kompatibilis az Exchange-el vagy a helyszíni SharePointtal. Csak az online verziókban tárolt adatot tudja megvédeni.

Jelen útmutató segítséget nyújt abban hogy, hogyan védheti meg vállalatát adatvesztéssel szemben azáltal, hogy jelszavakat és adattitkosítást kényszerít ki szabályzatokkal olyan mobilalkalmazásokon, amelyeket a beosztottjai bizalmas adat eléréséhez használnak, bármilyen eszközkezelési megoldásba való teljes regisztráció nélkül. A Microsoft Intune lehetővé teszi, hogy mobilalkalmazás-kezelési (MAM) szabályzatokat állítson be az Office mobilalkalmazásokon [iOS](https://products.office.com/en-us/mobile/office-mobile-apps-for-ios) és [Android](https://products.office.com/en-us/mobile/office-mobile-apps-for-android) rendszereken. Így az O365 adatok védelme érdekében a felhasználóknak nem kell egy mobileszköz-kezelési megoldásban regisztrálni eszközeiket, mégis megmarad a gördülékeny végfelhasználói élményük az Office mobilalkalmazásaival. 

## Mit kell ehhez tennem?
1.  [Az alkalmazásadatok védelmének áttekintése](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) 
2.  [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 
3.  [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) 

## További információ:
- [Ismerje meg a végfelhasználói élményt a MAM használatát támogató alkalmazások esetében a Microsoft Intune-nal.](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal.](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- [A Microsoft Intune alkalmazáspartnereinek listájának megtekintése](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)



<!--HONumber=Oct16_HO3-->


