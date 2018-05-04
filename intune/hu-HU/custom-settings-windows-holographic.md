---
title: A Windows Holographic for Business rendszert futtató eszközökre vonatkozó egyéni beállítások a Microsoft Intune-ban – Azure | Microsoft Docs
description: 'Létrehozhat egy egyéni profilt, amelyet a Microsoft Intune-ban Windows Holographic for Business rendszert futtató eszközök OMA-URI-beállításaihoz használhat. Az alábbi beállításokat adhatja meg: AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates, valamint az ApplicationLaunchRestrictions szabályzatkonfigurációs szolgáltató (CSP) beállításait.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1825d99243654c9fecac7729153a95234d435ff
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2018
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>A Windows Holographic for Business rendszert futtató eszközökre vonatkozó egyéni eszközbeállítások az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 A Microsoft Intune Windows Holographic for Businesshez készült **egyéni** profiljával az eszközfunkciók szabályozására szolgáló OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállításokat lehet telepíteni. A Windows Holographic for Business számos konfigurációs szolgáltatásból származó beállítást támogat. A konfigurációszolgáltatásokról a [Bevezetés a konfigurációszolgáltatásokba (CSP) informatikai szakértők számára](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) című témakörben olvashat. A Windows Holographic által támogatott konkrét konfigurációszolgáltatók listáját a [Windows Holographic által támogatott CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben találja.

Ha egy adott beállítást keres, ne feledje, a [Windows Holographic for Business eszközkorlátozási profil](device-restrictions-windows-holographic.md) számos olyan beállítást tartalmaz, amely be van építve az Intune-ba, és nem követeli meg egyéni értékek megadását.

## <a name="create-the-custom-oma-uri-profile"></a>Az egyéni OMA-URI-profil létrehozása
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

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Egész szám<br>0 – Nem engedélyezett<br>1 – engedélyezett (alapértelmezés)|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Egész szám<br>0 – Nem engedélyezett<br>1 – engedélyezett (alapértelmezés)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Egész szám<br>0 – A frissítési szolgáltatás nincs engedélyezve <br>1 – A frissítési szolgáltatás engedélyezve van (alapértelmezés).|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Karakterlánc<br>URL – Az eszköz frissítéseket keres a WSUS-kiszolgálótól a megadott URL-címen.<br>Nincs beállítva – Az eszköz a Microsoft Update szolgáltatásból keres frissítéseket.|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Egész szám<br>0 – Nincs konfigurálva. Az eszköz minden alkalmazható frissítést telepít.<br>1 – Az eszköz csak azokat a frissítéseket telepíti, amelyek alkalmazhatók és a jóváhagyott frissítések listáján is szerepelnek. Állítsa ezt a szabályzatot 1 értékre, ha azt szeretné, hogy az informatikai részleg vezérelje az eszközfrissítések üzembe helyezését, például ha az üzembe helyezés előtt tesztelésre van szükség.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br><br>**Fontos**<br>El kell olvasnia és el kell fogadnia a végfelhasználói nevében a frissítési licencfeltételeket. Amennyiben ezt nem teszi meg, az a jogi vagy szerződéses kötelezettségek megszegésének számít.|A frissítések jóváhagyásának és a licencfeltételek a végfelhasználók nevében történő elfogadásának csomópontja.<br/><br/>További információ: [Frissítési CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

---
|OMA-URI|Adattípus  |
|---------|---------|
|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Fontos**<br>Az AppLocker CSP-cikk escape-karakterrel jelölt XML-példákat használ. A beállítások egyéni Intune-profilokkal való konfigurálásához hagyományos XML-t kell használnia.|Karakterlánc<br>További információ: [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).|

## <a name="find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A [Windows Holographic for Business által támogatott CSP-k](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben megtalálja Windows Holographic által támogatott konfigurációszolgáltatók teljes listáját. Nem minden beállítás kompatibilis a Windows Holographic összes verziójával. A Windows-cikkben szereplő táblázatból kiolvasható, hogy az egyes konfigurációszolgáltatók mely verziókat támogatják.

Ezen felül az Intune sem támogatja a cikkben felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó cikket. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.