---
title: Intune-funkciók regisztrációs módszer szerint Windows-eszközökhöz
titlesuffix: Microsoft Intune
description: Megtekintheti, mely funkciókat támogatják az egyes regisztrációs módszerek Windows-eszközökön.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 38bb88015261aa50d6c27aec026614f1205aebe8
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189809"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Funkciók regisztrációs módszer szerint Windows-eszközökhöz
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune lehetővé teszi a dolgozók eszközeinek és alkalmazásainak, illetve a céges adatokhoz való hozzáférésük kezelését. Az eszközöket először regisztrálni kell az Intune szolgáltatásban. A dolgozók eszközeit többféleképpen is lehet regisztrálni. Minden módszer eltérő ajánlott eljárásokkal és funkciókkal bír, ahogyan a lenti tábla mutatja.

## <a name="best-practices-by-enrollment-method"></a>Ajánlott eljárások regisztrációs módszer szerint
| **Gyakorlati tanácsok** | **[Azure AD-hez csatlakoztatva](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD-hez csatlakoztatva, Autopilot-eszközzel](enrollment-autopilot.md)** |**[Tömeges](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[CSOPORTHÁZIREND-OBJEKTUM](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Az EDU-ban gyakran használt|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Az eszközök megosztott eszközként használhatók|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|A személyes eszközöknek hozzá kell férniük a céges erőforrásokhoz|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|
|Alkalmazások önálló karbantartása|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Funkciók regisztrációs módszer szerint

| **Funkciók** | **[Azure AD-hez csatlakoztatva](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD-hez csatlakoztatva, Autopilot-eszközzel](enrollment-autopilot.md)** |**[Tömeges](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[CSOPORTHÁZIREND-OBJEKTUM](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Feltételes hozzáférés                                      |![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|
|A felhasználó az eszközhöz van rendelve                    |![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|
|Azure AD Premium szükséges                               |![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|
|Eszköz fel tudja mérni a CA által védett erőforrásokat             |![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|
|A felhasználók nem lehetnek rendszergazdák az eszközeiken               |![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Az eszközbeállítás konfigurálása        |![X](media/xmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Eszközök regisztrálása felhasználói beavatkozás nélkül      |![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|
|PowerShell-parancsfájlok futtatása                       |![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Támogatja az automatikus regisztrációt az AD-tartományhoz való csatlakozás után      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|
|Támogatja az automatikus regisztrációt a hibrid Azure AD-hoz való csatlakozás után|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Pipa](media/checkmark.png)|
|Támogatja az automatikus regisztrációt az Azure AD-hoz való csatlakozás után       |![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![Pipa](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>További lépések

[A Windows-regisztráció beállítása ](windows-enroll.md)

