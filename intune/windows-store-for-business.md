---
title: "A Vállalati Windows Áruházban vásárolt alkalmazások felügyelete"
titleSuffix: Intune on Azure
description: "Útmutató a Vállalati Windows Áruházból származó alkalmazások Intune-ba való szinkronizálásához, és ezután azok hozzárendeléséhez és nyomon követéséhez.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de6ed7623e33a50bdf8452cbf1bad9c648b13d04
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


A [Vállalati Windows Áruház](https://www.microsoft.com/business-store) az a hely, ahol alkalmazásokat vásárolhat a szervezete számára egyenként vagy nagyobb mennyiségben. Az áruházat a Microsoft Intune-nal összekapcsolva a mennyiségi licencszerződés keretében vásárolt alkalmazásokat az Intune-portálról kezelheti. Példa:
* Szinkronizálhatja az áruházban vásárolt alkalmazások listáját az Intune-nal.
* A szinkronizált alkalmazások megjelennek az Intune felügyeleti konzolján; ezen alkalmazásokat a többi alkalmazáshoz hasonlóan oszthatja ki.
* Az Intune felügyeleti konzolján nyomon követheti a szabad és a használatban lévő licencek számát.
* Ha nincs elegendő elérhető licenc, az Intune letiltja az alkalmazások kiosztását és telepítését.

## <a name="before-you-start"></a>Előkészületek

Mielőtt elkezdi a Vállalati Windows Áruházból származó alkalmazások szinkronizálását és kiosztását, tekintse át a következő információkat:

- Állítsa be az Intune-t a szervezet mobileszköz-kezelő szolgáltatójaként.
- Rendelkeznie kell fiókkal a Vállalati Windows Áruházban.
- Miután összekapcsolta a Vállalati Windows Áruház-fiókját az Intune-nal, később nem választhat hozzá másik fiókot.
- Az áruházban vásárolt alkalmazások manuálisan nem vehetők fel és nem törölhetők az Intune-ban. Az alkalmazások csak a Vállalati Windows Áruházzal szinkronizálhatók.
- Az Intune a Vállalati Windows Áruházban vásárolt online és offline licencelt alkalmazásokat egyaránt szinkronizálja.
- Az Intune az offline alkalmazások közül csak az ingyeneseket szinkronizálja.
- Az eszközök akkor használhatják ezt a lehetőséget, ha csatlakoztatva vannak az Active Directory Domain Services szolgáltatáshoz vagy egy munkahelyhez.
- A regisztrált eszközöknek a Windows 10 1511-es vagy újabb verzióját kell használniuk.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>A Vállalati Windows Áruház-fiók összekapcsolása az Intune-nal
Mielőtt engedélyezné a szinkronizálást az Intune-konzolon, konfigurálnia kell az áruházbeli fiókját az Intune használatára felügyeleti eszközként:
1. Ügyeljen arra, hogy a Vállalati Áruházba való bejelentkezéshez ugyanazt a bérlői fiókot használja, mint az Intune-ba való bejelentkezéshez.
2. A Vállalati Áruházban válassza a **Beállítások** > **Felügyeleti eszközök** lehetőséget.
3. A Felügyeleti eszközök lapon válassza a **Felügyeleti eszköz hozzáadása**, majd a **Microsoft Intune** lehetőséget.

> [!NOTE]
> Korábban csak egyetlen felügyeleti eszközt társíthatott a Windows Vállalati Áruházhoz az alkalmazások kiosztására. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel).

Most már folytathatja a műveletet, és beállíthatja a szinkronizálást az Intune-konzolon.

## <a name="configure-synchronization"></a>A szinkronizálás konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1. A **Mobilalkalmazások** panelen válassza a **Beállítás** > **Vállalati Windows Áruház** lehetőséget.
2. Kattintson az **Engedélyezés** lehetőségre.
3. Ha még nem tette meg, kattintson a Vállalati Windows Áruházba történő regisztráció hivatkozására, és a fent leírtaknak megfelelően társítsa a fiókját.
5. A **Nyelv** legördülő listából válassza ki, hogy mely nyelven jelenjenek meg a Windows Üzleti Áruházból származó alkalmazások az Intune-portálon. Az alkalmazások a megjelenítés nyelvétől függetlenül a végfelhasználó nyelvén lesznek telepítve (ha elérhető).
6. Kattintson a **Szinkronizálás** lehetőségre a Windows Áruházból megvásárolt alkalmazások Intune-ba való felvevéséhez.

## <a name="synchronize-apps"></a>Az alkalmazások szinkronizálása

1. A **Mobilalkalmazások** területen válassza a **Beállítás** > **Vállalati Windows Áruház** elemet.
2. Kattintson a **Szinkronizálás** lehetőségre a Windows Áruházból megvásárolt alkalmazások Intune-ba való felvevéséhez.

## <a name="assign-apps"></a>Alkalmazások hozzárendelése

Az Áruházból származó alkalmazásokat ugyanúgy rendelheti hozzá, mint a többi Intune-alkalmazást. További információ: [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal). Az **Összes alkalmazás** oldal helyett azonban a **Licencelt alkalmazások** oldalról rendelheti hozzá az alkalmazásokat.

Az offline alkalmazások célcsoportjai lehetnek felhasználói csoportok, eszközcsoportok, valamit felhasználókat és eszközöket egyaránt tartalmazó csoportok.
Az offline alkalmazások telepíthetők egy eszköz adott felhasználója vagy az összes felhasználója számára. 


A Vállalati Windows Áruházból származó alkalmazások hozzárendelésekor az alkalmazást telepítő minden felhasználóhoz meg kell adnia egy-egy licencet. Ha felhasználja egy kiosztott alkalmazás összes elérhető licencét, akkor nem oszthat ki több példányt. Válasszon a következő lehetőségek közül:
* Távolítsa el az alkalmazást néhány eszközről.
* Szűkítse le az aktuális hozzárendelés hatókörét annyi felhasználóra, ahány elérhető licenccel rendelkezik.
* Vásároljon további példányokat az alkalmazásból a Vállalati Windows Áruházban.


