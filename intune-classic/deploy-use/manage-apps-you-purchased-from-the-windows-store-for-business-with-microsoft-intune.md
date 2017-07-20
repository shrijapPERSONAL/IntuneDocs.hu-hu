---
title: "Vállalati Windows Áruházbeli alkalmazások felügyelete"
description: "Csatlakoztassa a Microsoft Intune-t a Vállalati Windows Áruházhoz, ha szeretné az Intune-konzolról felügyelni a mennyiségi programban vásárolt alkalmazásokat"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 888d825fb9955e97b49e54a0c36ab882055076d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A [Vállalati Windows Áruház](https://www.microsoft.com/business-store) az a hely, ahol alkalmazásokat vásárolhat a szervezete számára egyenként vagy nagyobb mennyiségben. Az áruházat a Microsoft Intune-nal összekapcsolva a mennyiségi programban vásárolt alkalmazásokat az Intune-konzolról kezelheti. Példa:
* Szinkronizálhatja az áruházban vásárolt alkalmazások listáját az Intune-nal.
* A szinkronizált alkalmazások megjelennek az Intune felügyeleti konzolján, és a többi alkalmazáshoz hasonlóan telepítheti őket.
* Az Intune felügyeleti konzolján nyomon követheti a szabad és a használatban lévő licencek számát.
* Ha nincs elegendő elérhető licenc, az Intune letiltja az alkalmazások központi telepítését.

## <a name="before-you-start"></a>Előkészületek
Mielőtt elkezdi a Vállalati Windows Áruházból származó alkalmazások szinkronizálását és telepítését, tekintse át a következő információkat:
* Az Intune-t kell beállítania mobileszköz-kezelő szolgáltatóként a szervezetben. További tájékoztatást [A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md) című cikk tartalmaz.
* Rendelkeznie kell fiókkal a Vállalati Windows Áruházban.
* Miután összekapcsolta a Vállalati Windows Áruház-fiókját az Intune-nal, később nem választhat hozzá másik fiókot.
* Az áruházban vásárolt alkalmazások manuálisan nem vehetők fel és nem törölhetők az Intune-ban. Az alkalmazások csak a Vállalati Windows Áruházzal szinkronizálhatók.
* Az Intune csak a Vállalati Windows Áruházban vásárolt, online licenccel rendelkező alkalmazásokat szinkronizálja.
* Az eszközök akkor használhatják ezt a funkciót, ha csatlakoztak az Active Directory Domain Serviceshez vagy egy munkahelyhez.
* A regisztrált eszközöknek a Windows 10 1511-es verzióját kell használniuk.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>A Vállalati Windows Áruház-fiók összekapcsolása az Intune-nal
Mielőtt engedélyezné a szinkronizálást az Intune-konzolon, konfigurálnia kell az áruházbeli fiókját az Intune használatára felügyeleti eszközként:
1. Ügyeljen arra, hogy a Vállalati Áruházba való bejelentkezéshez ugyanazt a bérlői fiókot használja, mint az Intune-ba való bejelentkezéshez.
2. A Vállalati Áruházban válassza a **Beállítások** > **Felügyeleti eszközök** lehetőséget.
3. A Felügyeleti eszközök lapon válassza a **Felügyeleti eszköz hozzáadása**, majd a **Microsoft Intune** lehetőséget.

> [!NOTE]
> Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel).

Most már folytathatja a műveletet, és beállíthatja a szinkronizálást az Intune-konzolon.

## <a name="configure-synchronization"></a>A szinkronizálás konfigurálása

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Felügyelet** elemet.
2. A **Felügyelet** munkaterületen bontsa ki a **Mobileszköz-kezelés**  >   **Windows** elemet, majd válassza a **Vállalati Áruház** elemet.
3. A **Vállalati Windows Áruház** lapon hajtsa végre a következő műveletet:
 * Ha még nem tette meg, kattintson a Vállalati Windows Áruházba való regisztráció hivatkozására.
 * Miután regisztrálta magát, válassza a **Szinkronizálás konfigurálása** elemet.
4. **A Vállalati Windows Áruházzal való alkalmazásszinkronizálás konfigurálása** párbeszédpanelen válassza a **Vállalati Windows Áruházzal való szinkronizálás engedélyezése** lehetőséget.
5. A **Nyelv** legördülő listán válassza ki azt a nyelvet, amelyet a Vállalati Windows Áruházból származó alkalmazásoknak az Intune-konzolon való megjelenítéséhez kíván használni. Az alkalmazások a végfelhasználó nyelvén lesznek telepítve (ha ez elérhető), függetlenül a megjelenítéshez választott nyelvtől.
6. Kattintson az **OK**gombra.

## <a name="synchronize-apps"></a>Az alkalmazások szinkronizálása

1. Az áruházban vásárolt alkalmazásoknak az Intune-nal való szinkronizálásához a **Vállalati Windows Áruház** lapon válassza a **Szinkronizálás** elemet.
2. Az **Alkalmazások** munkaterületen válassza az **Alkalmazások** > **Mennyiségi licencszerződés keretében vásárolt alkalmazások** elemet. Ekkor láthatja a telepíthető alkalmazásokat, és ellenőrizheti, hogy a megvásárolt alkalmazások importálása hibátlanul megtörtént-e. Az ebben a csomópontban található alkalmazásoknál megjelenik az Ön összes licencének és az Ön által elérhető licenceknek a száma.
Megvásárolhatja például a Céges portál alkalmazást (online licenccel) a Vállalati Windows Áruházban, szinkronizálhatja az Intune-konzollal, és szükséges alkalmazásként telepítheti a kívánt Windows 10 rendszerű eszközökre. 


## <a name="deploy-apps"></a>Alkalmazások telepítése

Az Áruházból származó alkalmazásokat ugyanúgy telepítheti, mint a többi Intune-alkalmazást. További információk: [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md).
A Vállalati Windows Áruházból származó alkalmazások központi telepítésekor az alkalmazást telepítő minden felhasználóhoz meg kell adnia egy-egy licencet. Ha felhasználja egy telepített alkalmazás összes elérhető licencét, akkor nem telepíthet több példányt. Végre kell hajtania a következő műveletek valamelyikét:
* Távolítsa el az alkalmazást néhány eszközről.
* Csökkentse az aktuális telepítés hatókörét annyi felhasználóra, ahány elérhető licenccel rendelkezik.
* Vásároljon további példányokat az alkalmazásból a Vállalati Windows Áruházban.

> [!Important]
> A telepített alkalmazásokhoz csak az a felhasználó férhet hozzá, aki eredetileg regisztrálta az eszközt. Más felhasználók nem férhetnek hozzá az alkalmazásokhoz.


### <a name="see-also"></a>További információ
[Alkalmazások hozzáadása Microsoft Intune-beli mobileszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md)