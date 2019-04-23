---
title: Az Intune Windows-eszközök regisztrálási módszerei
titleSuffix: Microsoft Intune
description: Az Intune-ban Windows-eszközök regisztrálhatók különböző módjait
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: 346b74871b7519e03ca3e68061f690ef1a4e6d6a
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514786"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Az Intune Windows-eszközök regisztrálási módszerei

Az Intune-ban eszközök felügyeletére, eszközöket először regisztrálni kell az Intune szolgáltatásban. Mindkét személyes tulajdonú és vállalati tulajdonú eszközök regisztrálása az Intune-felügyelethez. 

Az Intune-ban regisztrált eszközök két módja van:
- Felhasználók maguk is regisztrálhatják a Windows rendszerű számítógépek 
- Rendszergazdák konfigurálhatják a szabályzatok kényszerítése minden olyan felhasználó bevonása nélkül automatikus regisztráció

## <a name="user-self-enrollment-in-intune"></a>Felhasználó önregisztrációja az Intune-ban

Felhasználók maguk is regisztrálhatják Windows eszköz ezen módszerek egyikének használatával:

- [A saját eszközök használata (BYOD)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): Felhasználók személyes tulajdonban lévő eszközök regisztrálása úgy, hogy kapcsolódik egy **munkahelyi és iskolai** fiók **beállítások** az eszköz. Ez a folyamat:
    - Regisztrálja az eszközt az Azure Active Directory vállalati erőforrásokhoz, mint a levelezés elérésére.
    - Regisztrálja az eszközt, az Intune-ban, a személyes tulajdonban lévő eszközök (BYOD).
Ha egy rendszergazda által konfigurált automatikus regisztráció (az Azure AD premium előfizetéssel rendelkező érhető el), a felhasználó csak egyszer adja meg a hitelesítő adataikat fel. Ellenkező esetben rendelkeznek keresztül MDM-regisztráció csak külön regisztrálhatnak, és írja be újra a hitelesítő adataikat.  
- **MDM-regisztráció csak** lehetővé teszi, hogy a felhasználók regisztrálhatják egy meglévő munkacsoporthoz tartozik, az Active Directory vagy az Azure Active Directoryhoz csatlakoztatott PC-s Intune-bA. A felhasználók beléptethetik a beállítások a meglévő Windows-számítógépen. Ez a módszer nem ajánlott, mert az Azure Active Directoryba, nem regisztrálja az eszközt. Megakadályozza a szolgáltatások, például a feltételes hozzáférés használatának is.
- [Az Azure Active Directory (Azure AD) való csatlakozás](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) – csatlakoztatja az eszközt az Azure Active Directoryval, és lehetővé teszi a felhasználók bejelentkezni a Windows Azure AD-beli hitelesítő. Automatikus regisztráció engedélyezése esetén az eszköz automatikusan regisztrálva van az Intune-ban. Automatikus regisztráció előnye a felhasználó egyetlen lépésből álló folyamat. Ellenkező esetben rendelkeznek keresztül MDM-regisztráció csak külön regisztrálhatnak, és írja be újra a hitelesítő adataikat. A felhasználók regisztrálhatnak ilyen módon kezdeti Windows Kezdőélmény alatt, vagy a beállítások. Az eszköz vállalati tulajdonban lévő eszközt az Intune-ban van megjelölve.
- [Az autopilot](enrollment-autopilot.md) – automatizálja az Azure AD-csatlakozás, és regisztrálja azt a új vállalati tulajdonú eszközöket az Intune-ban. Ez a módszer out-of-box leegyszerűsíti, és szükségtelenné teszi a alkalmazni egyéni operációsrendszer-lemezképek az eszközökön. Amikor a segítségével a rendszergazdák az Intune Autopilot-eszközök felügyeletére, felügyelheti az házirendek, profilok, alkalmazások és több regisztrált.  Autopilot deployment két típusa van: [Önkiszolgáló-üzemmód telepítése](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (a kioszkok, digitális aláírási vagy közös használatú) és [felhasználói Driven módban](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (hagyományos számára). 

## <a name="administrator-based-enrollment-in-intune"></a>Rendszergazda-alapú regisztráció az Intune-ban

A rendszergazdák az alábbi módszerek a Regisztrálás, amelyek nem igényelnek felhasználói beavatkozást adható meg:

- [Hibrid Azure AD Join](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) lehetővé teszi, hogy a rendszergazdák beállíthatják az Active Directory csoportházirend segítségével, amelyek hibrid Azure AD-hez csatlakoztatott eszközök automatikus regisztrálása. 
- [Megosztott kezelés a Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview) lehetővé teszi, hogy a rendszergazdák a meglévő Configuration Manager által felügyelt eszközök regisztrálása az Intune-nal az Intune-ban és a Configuration Manager kettős előnyeit. 
- [Eszközregisztráció-kezelő](device-enrollment-manager-enroll.md) (DEM-) egy olyan speciális szolgáltatásfiók. DEM-fiókokat, amelyek lehetővé teszik több vállalati tulajdonú eszköz regisztrációjára és felügyeletére jogosult felhasználók engedélyekkel rendelkezik. Az ilyen típusú eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz. Ez a módszer is, például a feltételes hozzáférési funkciók használatának engedélyezése nem. 
- [Csoportos regisztráció](windows-bulk-enroll.md) lehetővé teszi, hogy egy jogosult felhasználó nagyszámú új vállalati tulajdonú eszközök csatlakoztatása az Azure Active Directory és az Intune-ban. A kiépítési csomagot hoz létre a Windows Configuration Designer (WCD) alkalmazással. Ezután USB-vel adathordozók a kezdeti Windows Kezdőélmény alatt, vagy ha a meglévő Windows-számítógép esetén a kiépítési csomagot az eszközök automatikus regisztrálása az Intune-ba való telepítését. 

## <a name="next-steps"></a>További lépések

[Ismerje meg, a képességeit a Windows-eszközök regisztrálási módszerei](enrollment-method-capab.md)
