---
title: "A Vállalati Microsoft Áruházban vásárolt alkalmazások felügyelete"
titlesuffix: Azure portal
description: "Útmutató a Vállalati Microsoft Áruházból származó alkalmazások Intune-ba való szinkronizálásához, és ezután azok kiosztásához és nyomon követéséhez.”"
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
ms.openlocfilehash: 649766b26a1061c4bce11235c04dcbe8570fcdc4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>A Vállalati Microsoft Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


A [Vállalati Microsoft Áruház](https://www.microsoft.com/business-store) az a hely, ahol alkalmazásokat vásárolhat a szervezete számára egyenként vagy mennyiségi program keretében. Az áruházat a Microsoft Intune-nal összekapcsolva a mennyiségi programban vásárolt alkalmazásokat az Azure Portalról kezelheti. Példa:
* Szinkronizálhatja az áruházban vásárolt alkalmazások listáját az Intune-nal.
* A szinkronizált alkalmazások megjelennek az Intune felügyeleti konzolján; ezen alkalmazásokat a többi alkalmazáshoz hasonlóan oszthatja ki.
* Az Intune felügyeleti konzolján nyomon követheti a szabad és a használatban lévő licencek számát.
* Ha nincs elegendő elérhető licenc, az Intune letiltja az alkalmazások kiosztását és telepítését.

## <a name="before-you-start"></a>Előkészületek

Mielőtt elkezdené a Vállalati Microsoft Áruházból származó alkalmazások szinkronizálását és hozzárendelését, tekintse át a következő információkat:

- Állítsa be az Intune-t a szervezet mobileszköz-kezelő szolgáltatójaként.
- Rendelkeznie kell fiókkal a Vállalati Microsoft Áruházban.
- Miután összekapcsolta a Vállalati Windows Áruház-fiókját az Intune-nal, később nem választhat hozzá másik fiókot.
- Az áruházban vásárolt alkalmazások manuálisan nem vehetők fel és nem törölhetők az Intune-ban. Az alkalmazások csak a Vállalati Microsoft Áruházzal szinkronizálhatók.
- Az Intune a Vállalati Microsoft Áruházban vásárolt online és offline licencelt alkalmazásokat egyaránt szinkronizálja.
- Az Intune az offline alkalmazások közül csak az ingyeneseket szinkronizálja.
- Az eszközök akkor használhatják ezt a lehetőséget, ha csatlakoztatva vannak az Active Directory Domain Services szolgáltatáshoz vagy egy munkahelyhez.
- A regisztrált eszközöknek a Windows 10 1511-es vagy újabb verzióját kell használniuk.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>A Vállalati Microsoft Áruházbeli fiók összekapcsolása az Intune-nal
Mielőtt engedélyezné a szinkronizálást az Intune-konzolon, konfigurálnia kell az áruházbeli fiókját az Intune használatára felügyeleti eszközként:
1. Ügyeljen arra, hogy a Vállalati Áruházba való bejelentkezéshez ugyanazt a bérlői fiókot használja, mint az Intune-ba való bejelentkezéshez.
2. A Vállalati Áruházban válassza a **Beállítások** > **Felügyeleti eszközök** lehetőséget.
3. A Felügyeleti eszközök lapon válassza a **Felügyeleti eszköz hozzáadása**, majd a **Microsoft Intune** lehetőséget.

> [!NOTE]
> Korábban csak egyetlen felügyeleti eszközt társíthatott a Vállalati Microsoft Áruházhoz az alkalmazások hozzárendeléséhez. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel).

Most már folytathatja a műveletet, és beállíthatja a szinkronizálást az Intune-konzolon.

## <a name="configure-synchronization"></a>A szinkronizálás konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1. A **Mobilalkalmazások** panelen válassza a **Beállítás** > **Vállalati Microsoft Áruház** lehetőséget.
2. Kattintson az **Engedélyezés** lehetőségre.
3. Ha még nem tette meg, kattintson a Vállalati Microsoft Áruházban való regisztrálás hivatkozására, és a fent leírtaknak megfelelően társítsa a fiókját.
5. A **Nyelv** legördülő listából válassza ki, hogy milyen nyelven jelenjenek meg a Vállalati Microsoft Áruházból származó alkalmazások az Azure Portalon. Az alkalmazások a megjelenítés nyelvétől függetlenül a végfelhasználó nyelvén lesznek telepítve (ha elérhető).
6. Kattintson a **Szinkronizálás** lehetőségre a Microsoft Áruházból megvásárolt alkalmazások Intune-ba való felvételéhez.

## <a name="synchronize-apps"></a>Az alkalmazások szinkronizálása

1. A **Mobilalkalmazások** területen válassza a **Beállítás** > **Vállalati Microsoft Áruház** elemet.
2. Kattintson a **Szinkronizálás** lehetőségre a Microsoft Áruházból megvásárolt alkalmazások Intune-ba való felvételéhez.

## <a name="assign-apps"></a>Alkalmazások hozzárendelése

Az Áruházból származó alkalmazásokat ugyanúgy rendelheti hozzá, mint a többi Intune-alkalmazást. További információ: [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal). Az **Összes alkalmazás** oldal helyett azonban a **Licencelt alkalmazások** oldalról rendelheti hozzá az alkalmazásokat.

Az offline alkalmazások célcsoportjai lehetnek felhasználói csoportok, eszközcsoportok, valamit felhasználókat és eszközöket egyaránt tartalmazó csoportok.
Az offline alkalmazások telepíthetők egy eszköz adott felhasználója vagy az összes felhasználója számára. 


A Vállalati Microsoft Áruházból származó alkalmazások hozzárendelésekor az alkalmazást telepítő minden felhasználó egy-egy licencet használ fel. Ha felhasználja egy kiosztott alkalmazás összes elérhető licencét, akkor nem oszthat ki több példányt. Válasszon a következő lehetőségek közül:
* Távolítsa el az alkalmazást néhány eszközről.
* Szűkítse le az aktuális hozzárendelés hatókörét annyi felhasználóra, ahány elérhető licenccel rendelkezik.
* Vásároljon további példányokat az alkalmazásból a Vállalati Microsoft Áruházban.


