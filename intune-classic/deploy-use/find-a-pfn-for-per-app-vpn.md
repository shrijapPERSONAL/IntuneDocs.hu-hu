---
title: Csomagcsaládnév (FPN) keresése alkalmazásonkénti VPN-hez
description: PFN megkeresése egy alkalmazásonkénti VPN konfigurálásához.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c6bbc1bd477cde7eecb78b78c8efa4bfde46976f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Csomagcsalád nevének (PFN) megkeresése az alkalmazásonkénti VPN-konfigurációkhoz

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Ahhoz, hogy egy alkalmazásonkénti VPN-t be tudjon állítani, két lehetősége is van a PFN megkeresésére.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Egy Windows 10 rendszerű számítógépre telepített alkalmazás PFN-jének megkeresése

Ha a használt alkalmazás már telepítve van egy Windows 10 rendszerű számítógépre, a [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell-parancsmag használatával is beolvashatja a PFN-t.

A Get-AppxPackage szintaxisa a következő:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
> Előfordulhat, hogy a PFN lekéréséhez rendszergazdaként kell futtatnia a PowerShellt.

Ha például a számítógépre telepített összes univerzális alkalmazásra vonatkozó adatot szeretné lekérni, használja a `Get-AppxPackage` parancsot.

Ha olyan alkalmazás adatait szeretné lekérni, amelynek ismeri a nevét vagy annak egy részét, használja a `Get-AppxPackage *<app_name>` parancsot. Érdemes megfigyelni a helyettesítő karakter használatát. Ez különösen akkor hasznos, ha nem tudja biztosan az alkalmazás teljes nevét. A OneNote adatainak lekéréséhez például használja a `Get-AppxPackage *OneNote` parancsot.


A OneNote-ra vonatkozóan lekért adatok a következők:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>A PFN megkeresése, ha az alkalmazás nincs telepítve a számítógépre

1.  Lépjen a https://www.microsoft.com/store/apps lapra.
2.  Írja be az alkalmazás nevét a keresősávba. A jelen példában keressen rá a OneNote-ra.
3.  Válassza az alkalmazásra mutató hivatkozást. Figyelje meg, hogy az URL-cím végén egy több betűből álló betűsorozat található. A példánkban az URL-cím a következőképpen néz ki `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.  Egy másik lapon illessze be a következő URL-címet: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Cserélje le az `<app id>` azonosítót a https://www.microsoft.com/store/apps webhelyről származó alkalmazásazonosítóra – vagyis a 3. lépésben ismertetett, az URL-cím végén található betűsorra. Ebben a példában, a OneNote esetében a következő URL-t kell beillesztenie: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

A Microsoft Edge böngészőben megjelennek a kívánt adatok; az Internet Explorerben válassza a **Megnyitás** parancsot az adatok megtekintéséhez. A PFN értéke az első sorban található. A jelen példában az eredmények a következők:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
