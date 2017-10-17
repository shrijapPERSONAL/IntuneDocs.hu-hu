---
title: "Eszközök regisztrálásának lehetővé tétele"
description: "A mobileszköz-kezelő szolgáltató (MDM-szolgáltató) beállítása és az iOS-, Windows-, Android- és Mac-eszközök regisztrálásának engedélyezése"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6b860e0cb2475542a5b079508f71af096c4285b6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="enable-enrollment-for-mobile-devices"></a>Mobileszközök regisztrálásának lehetővé tétele

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakor azt mutatja be, hogy miképpen tehetik lehetővé az Intune-rendszergazdák a mobileszközök regisztrálását. Az Intune-nak a telefonján való használatáról a [Munkavégzés felügyelt eszközökkel](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) című cikk nyújt tájékoztatást.

Az Intune-nal történő mobileszköz-felügyelet beállításához először meg kell adnia a *mobileszköz-kezelő szolgáltatót* (ez azonosítja azt a szolgáltatást, amely felügyelheti a fiókjához tartozó eszközöket). Ez az útmutató abból indul ki, hogy Ön az Intune szolgáltatást fogja használni a System Center Configuration Manager helyett. A mobileszköz-kezelő szolgáltató beállítása után engedélyezheti a különféle eszközplatformok felügyeletét, majd regisztrálhatja az eszközöket a Munkahelyi portál alkalmazásban.

## <a name="enable-device-enrollment"></a>Eszközök regisztrálásának lehetővé tétele

1. **Az Intune beállítása mobileszköz-kezelő szolgáltatóként** Az [Intune felügyeleti konzoljában](https://manage.microsoft.com/) válassza a **Felügyelet** > **Mobileszköz-kezelés** elemet, majd kattintson a **Feladatok** csoport **Mobileszköz-kezelő szolgáltató megadása** elemére.  

2. Kattintson a Mobileszköz-kezelő szolgáltató párbeszédpanel **Igen** gombjára.

    ![Felügyeleti konzol. Mobileszköz-kezelés beállítása az Intune-hoz](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>Az eszközök regisztrálási módjának kiválasztása

Az Intune többféleképpen tudja kezelni az eszközöket, annak megfelelően, amire a cégnek szüksége van. A saját eszközök használata (BYOD), a céges eszközök, a saját eszköz kiválasztása (CYOD) és a teljes képernyős módú eszközök csak néhány példa a rendelkezésre álló különféle regisztrációs forgatókönyvekre.

[Az ebben a cikkben ismertetett lépésekkel válassza ki az eszközök regisztrálásának módját](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Mobileszköz-kezelés engedélyezése az eszközplatformhoz
A regisztrációt engedélyezni kell az iOS-, a Mac- és az Android for Work-eszközökre vonatkozóan, hogy kapcsolat jöjjön létre a platformszolgáltató és az Ön Intune-bérlője között. A Windows és az Android rendszerű eszközök esetében nincs szükség további lépésekre, de a Windows-eszközök regisztrálását még tovább egyszerűsítheti felhasználói számára azzal, hogy létrehoz egy speciális DNS-bejegyzést a beállításjegyzékben.

Engedélyezze mobileszköz-kezelést a felügyelni kívánt eszközplatformra vonatkozóan. A követelmények a platformtól függően eltérőek:

- [iOS és macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Windows 10 és Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [Windowsos PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune ügyfélszoftver)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

A regisztráció engedélyezését követően a felhasználók letölthetik az eszközükre a Munkahelyi portál alkalmazást, és elvégezhetik az eszköz regisztrálását.

### <a name="enable-company-owned-device-enrollment"></a>A céges eszközök regisztrálásának engedélyezése
A [céges eszközök regisztrálásának](/intune-classic/deploy-use/manage-corporate-owned-devices) különféle módozatait is engedélyezheti:
- [Apple Device Enrollment Program (Apple Készülékregisztrációs program)](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Regisztrálás az Apple Configurator és a Beállítási asszisztens segítségével](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator – közvetlen regisztráció](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Eszközregisztráció-kezelő](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>További lépések
Gratulálunk! Ezzel befejezte az *Intune – Első lépések útmutatójának* utolsó lépését. Most, hogy a kezdeti konfigurálást befejezte, további MDM-funkciók engedélyezését is fontolóra veheti.

>[!div class="step-by-step"]
>[&larr; **Eszközök regisztrálása**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Konfigurációt követő feladatok** &rarr;](.\post-configuration-tasks.md)  
