---
title: Egyéni beállítások a Microsoft Intune-ban Windows Holographic for Business esetén
titlesuffix: ''
description: A Windows Holographic for Business egyéni profiljaiban használható egyéni beállítások ismertetése.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5cdba24c10b90756d9a2b9f08fd7d4dcd727303
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>A Windows Holographic for Business rendszert futtató eszközökre vonatkozó egyéni eszközbeállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 A Microsoft Intune Windows Holographic for Businesshez készült **egyéni** profiljával az eszközfunkciók szabályozására szolgáló OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállításokat lehet telepíteni. A Windows Holographic for Business számos konfigurációs szolgáltatásból származó beállítást támogat. A konfigurációszolgáltatásokról a [Bevezetés a konfigurációszolgáltatásokba (CSP) informatikai szakértők számára](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) című témakörben olvashat. A Windows Holographic által támogatott konkrét konfigurációszolgáltatók listáját a [Windows Holographic által támogatott CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben találja.

Ha egy adott beállítást keres, ne feledje, a [Windows Holographic for Business eszközkorlátozási profil](device-restrictions-windows-holographic.md) számos olyan beállítást tartalmaz, amely be van építve az Intune-ba, és nem követeli meg egyéni értékek megadását.

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. OMA-URI beállítások hozzáadásához a **Profil létrehozása** panelen válassza a **Beállítások** lehetőséget.
3. Az **Egyéni OMA-URI beállítások** panelen a **Hozzáadás** elemre kattintva adhat meg új értéket. Az **Exportálás** elemre kattintva az összes Ön által konfigurált értéket exportálhatja egy csv-fájlba.
4. Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat:
    - **Beállítás neve** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Beállítás leírása** – Itt adhatja meg a beállítás leírását (nem kötelező).
    - **Adattípus** – Válasszon egyet a következő lehetőségek közül:
        - **Karakterlánc**
        - **Karakterlánc (XML)**
        - **Dátum és időpont**
        - **Egész**
        - **Lebegőpontos szám**
        - **Logikai**
    - **OMA-URI (megkülönbözteti a kis- és nagybetűket)** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.
1. Miután elkészült, lépjen vissza a **Profil létrehozása** panelre, és kattintson a **Létrehozás** elemre.
Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="recommended-custom-settings"></a>Ajánlott egyéni beállítások

Az alábbi beállítások a Windows Holographic for Business rendszert futtató eszközökön lehetnek hasznosak:


|Beállítás neve|OMA-URI|Adattípus  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Egész szám<br>0 – Nem engedélyezett<br>1 – engedélyezett (alapértelmezés)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Egész szám<br>0 – Nem engedélyezett<br>1 – engedélyezett (alapértelmezés)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Egész szám<br>0 – A frissítési szolgáltatás nincs engedélyezve <br>1 – A frissítési szolgáltatás engedélyezve van (alapértelmezés).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Karakterlánc<br>URL – Az eszköz frissítéseket keres a WSUS-kiszolgálótól a megadott URL-címen.<br>Nincs beállítva – Az eszköz a Microsoft Update szolgáltatásból keres frissítéseket.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Egész szám<br>0 – Nincs konfigurálva. Az eszköz minden alkalmazható frissítést telepít.<br>1 – Az eszköz csak azokat a frissítéseket telepíti, amelyek alkalmazhatók és a jóváhagyott frissítések listáján is szerepelnek. Állítsa ezt a szabályzatot 1 értékre, ha azt szeretné, hogy az informatikai részleg vezérelje az eszközfrissítések üzembe helyezését, például ha az üzembe helyezés előtt tesztelésre van szükség.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Fontos**<br>El kell olvasnia és el kell fogadnia a végfelhasználói nevében a frissítési licencfeltételeket. Amennyiben ezt nem teszi meg, az a jogi vagy szerződéses kötelezettségek megszegésének számít.|A frissítések jóváhagyásának és a licencfeltételek a végfelhasználók nevében történő elfogadásának csomópontja.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Fontos**<br>Az AppLocker CSP-cikk escape-karakterrel jelölt XML-példákat használ. A beállítások egyéni Intune-profilokkal való konfigurálásához hagyományos XML-t kell használnia.|Karakterlánc<br>További információt az [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) cikkben találhat.

## <a name="how-to-find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A [Windows Holographic for Business által támogatott CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben megtalálja Windows Holographic által támogatott konfigurációszolgáltatók teljes listáját. Nem minden beállítás kompatibilis a Windows Holographic összes verziójával. A Windows-cikkben szereplő táblázatból kiolvasható, hogy az egyes konfigurációszolgáltatók mely verziókat támogatják.

Ezen felül az Intune sem támogatja a cikkben felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó cikket. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.
