---
title: "Az Intune PC-szoftverügyfél képességei | Microsoft Docs"
description: "Ismerje meg az Intune funkcióit, amelyek akkor érhetők el, ha a Windows-számítógépeit az Intune-szoftverügyfél használatával felügyeli."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6
ms.lasthandoff: 12/16/2016


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Az Intune szoftverügyfél által biztosított felügyeleti funkciók Windows rendszerű számítógépekhez

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A legtöbb esetben célszerű regisztrálni az eszközöket az Intune-ban, mivel ez több funkciót biztosít. Ugyanakkor az Intune-szoftverügyféllel is felügyelheti a számítógépeket. Ekkor a következő funkciókat érheti el:

-   **[Szoftverfrissítések kezelése](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** - Naprakészen tarthatja a számítógépeit, és beállíthatja, hogy a rendszer mikor telepítse a frissítéseket.

-   **[Windows tűzfalházirend](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** - Ezzel biztosíthatja, hogy a vállalatnál használt számítógépeken ne legyen inaktív vagy nem megfelelően beállított Windows tűzfal.

-   **[Kártevők elleni védelem](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** - Az Intune Endpoint Protection védelmet használja, amely segít a számítógépes kártevők elleni védelmében.

-   **[Távsegítség](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** - Az Intune lehetővé teszi a felhasználóknak, hogy az Intune beépített távoli asztali funkciója segítségével kapcsolatba lépjenek az informatikai támogatási csapattal (ehhez a TeamViewer szoftver szükséges).

-   **[Szoftverlicenc-gazdálkodás](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** - Nyomon követheti az elérhető és a használatban lévő szoftverlicencek számát.
-   **[Alkalmazások központi telepítése](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** - Szoftvereket telepíthet a felügyelt számítógépekre. Ha a szoftverügyféllel felügyeli a számítógépeket, akkor bizonyos alkalmazásfelügyeleti funkciók nem érhetők el.


Az Intune a szoftverügyfél akár 7000 Windows-eszközön való telepítését is támogatja.

## <a name="operating-system-requirements"></a>Rendszerkövetelmények
Az Intune a Windows következő verzióival rendelkező számítógépek felügyeletére alkalmas (32 bites és 64 bites verziók egyaránt):


-   **Windows Vista** – Business, Enterprise és Ultimate verziók

-   **Windows 7** – Pro, Enterprise és Ultimate verziók (szervizcsomag nélkül vagy SP1-gyel)

-   **Windows 8** – Pro és Enterprise verziók

-   **Windows 8.1** – Pro és Enterprise verziók

- **Windows 10** - Pro, Education és Enterprise verziók


## <a name="minimum-hardware-requirements"></a>Minimális hardverkövetelmények
Az Intune-szoftverügyfél telepítésére vonatkozó minimális hardverkövetelmények a következők:

|Követelmény|Részletek|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

## <a name="further-requirements"></a>További követelmények
Az Intune-szoftverügyfél telepítésére vonatkozó szoftverkövetelmények a következők:

|Követelmény|Részletek|
|---------------|--------------------|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie a számítógépen.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.|
|Nem kompatibilis ügyfélszoftver eltávolítása|A számítógépes Intune ügyfélszoftver telepítése előtt távolítsa el a következő ügyfélszoftvereket a számítógépről:<br /><br />- A Configuration Manager bármely verziója<br />- A Microsoft Systems Management Server (SMS) bármely verziója|

### <a name="see-also"></a>További információ
[A Microsoft Intune regisztrált eszközök kezelésével kapcsolatos képességei](./mobile-device-management-capabilities-in-microsoft-intune.md)

