---
title: "Számítógépek felügyelete az ügyfélszoftverrel | Microsoft Docs"
description: "Windows rendszerű számítógépek felügyelete az Intune ügyfélszoftverrel."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel
A windowsos PC-ket alapértelmezés szerint [mobileszközként érdemes regisztrálni](set-up-windows-device-management-with-microsoft-intune.md) az Intune-ba, de ehelyett a jelen témakörben ismertetett módon, az Intune-ügyfélszoftver telepítése után is regisztrálhatók és felügyelhetők.

Az Intune a Windows rendszerű számítógépek felügyeletéhez a Windows Server Active Directory tartományi szolgáltatások (AD DS) csoportházirend-objektumaihoz (GPO-khoz) hasonló szabályzatokat használ. Ha Active Directory-tartományhoz csatlakoztatott számítógépeket felügyel az Intune segítségével, akkor [győződjön meg róla, hogy az Intune-szabályzatok nem ütköznek a szervezet csoportházirend-objektumaival](resolve-gpo-and-microsoft-intune-policy-conflicts.md). További információ a [csoportszabályzat-objektumokról](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Szabályzatok és alkalmazástelepítések működése az Intune-ügyfélszoftverrel

Jóllehet az Intune-ügyfélszoftver a szoftverfrissítések, a Windows tűzfal és az Endpoint Protection kezelésével támogatja a [PC-k védelmét szolgáló felügyeleti funkciókat](policies-to-protect-windows-pcs-in-microsoft-intune.md), az Intune-szoftverügyfél által felügyelt PC-ket nem lehet egyéb Intune-szabályzatokkal, így a mobileszköz-felügyeletet szolgáló **Windows**-szabályzatokkal célozni. 

Ha az Intune-ügyfélszoftverrel felügyel windowsos PC-ket, csak a **Számítógép-kezelés** szakaszban látható szabályzatokat használhatja.

  ![Új windowsos PC-szabályzat sablonjának kiválasztása](../media/select-template-for-pc-policy.png)

A beállítható szabályzatok részletes leírásáért lásd:

- [Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [A Windows rendszerű számítógépek védelme Windowsos tűzfalszabályzatok használatával a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Emellett az alkalmazások telepítésekor csak a Windows Installert (.exe, .msi) használhatja.

  ![Platform és hely kiválasztása a PC-s ügyfélszoftver fájljaihoz](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> A Windows 8.1-es vagy újabb rendszerű eszközöket kezelheti PC-ként az Intune-ügyféllel, vagy mobileszközként a mobileszköz-felügyeleti (MDM) szolgáltatással. A két módszert együttesen nem használhatja, ezért járjon el körültekintően, mielőtt a PC-k Intune-ügyfélszoftver használatával történő felügyelete mellett dönt. Ez a témakör kizárólag az Intune-szoftverügyféllel PC-ként kezelt eszközökre vonatkozik.

## <a name="requirements-for-intune-pc-client-management"></a>Az Intune-számítógépügyfél általi felügyelet követelményei

**Hardver**: Az Intune-ügyfélszoftver a következő minimális hardverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

**Szoftver**: Az ügyfélszoftver az alábbi szoftverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Operációs rendszer | Windows Vista vagy újabb rendszert futtató eszköz. </br></br>**A Home Edition verziók nem támogatottak.**|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie az eszközön.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.<br /><br />A Windows Installer verziójának megtekintése egy számítógépen:<br /><br />  A számítógépen kattintson a jobb gombbal a **%windir%\System32\msiexec.exe** fájlra, majd a **Tulajdonságok** menüpontra.<br /><br />A Windows Installer legújabb verzióját letöltheti a Microsoft Developer Network webhelyen található [Windows Installer újraterjeszthető csomagok](http://go.microsoft.com/fwlink/?LinkID=234258) oldalról.|
|Nem kompatibilis ügyfélszoftver eltávolítása|Az Intune-ügyfélszoftver telepítése előtt el kell távolítania a számítógépen esetleg megtalálható Configuration Manager-, Operations Manager-, Operations Management Suite- és Service Manager-ügyfélszoftvert.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Számítógép-felügyeleti képességek az Intune-os ügyfélszoftverrel

Az Intune-ügyfélszoftver telepítése után a következő felügyeleti funkciók állnak rendelkezésre: 

- [Alkalmazásfelügyelet](deploy-apps-in-microsoft-intune.md)

- [Valós idejű figyelés és Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – Az Endpoint Protection ugyanaz, mint a Windows Defender. Az Endpoint Protection a Windows 7 és Windows 8 rendszerre vonatkozik. A Windows 10-es és újabb verzióiban a termék neve Windows Defenderre változott.

- [A Windows tűzfal beállításainak felügyelete](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), hardver- és szoftverleltár, távvezérlés (távsegítségre vonatkozó kéréseken keresztül)

- [Szoftverfrissítési beállítások](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Megfelelőségi beállítások jelentése

Az Intune felügyeleti konzoljának bizonyos részei, mint például az „Updates” (Frissítések), a „Protection” (Védelem) és a „Licenses” (Licencek) csak akkor jelennek meg, ha vannak az Intune-ügyfélszoftverrel regisztrált eszközök.

  ![A felügyeleti konzol csak a számítógépügyfél esetén megjelenített elemei](../media/admin-console-settings-only-for-pc-agent.png)

Az Intune felügyeleti konzolján más általános számítógép-felügyeleti feladatokat is elvégezhet azokon a windowsos PC-ken, amelyeken az ügyfél telepítve van:

-   Felügyelt számítógépek hardver- és szoftverleltárjára vonatkozó információk megtekintése
-   Számítógépek távoli újraindítása
-   Számítógépek kivonása az ügyfélszoftver eltávolításához és kivételükhöz az Intune-felügyelet alól
-   Felhasználók hozzákapcsolása adott felügyelt számítógépekhez
-   Válasz távsegítségre vonatkozó kérésre

A fenti feladatokról az [általános számítógép-felügyeleti feladatokat](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) ismertető témakörben olvashat részletesebben.

## <a name="management-limitations-of-the-intune-client-software"></a>Az Intune-ügyfélszoftver felügyeleti korlátozásai

Az Intune-ügyfélszoftverrel felügyelt PC-knél nem használhat bizonyos olyan felügyeleti lehetőségeket, amelyek segítségével PC-ként kezelheti a mobileszközöket:

-   Teljes törlés (a szelektív törlés elérhető)

-   Feltételes hozzáférés

## <a name="help-with-troubleshooting"></a>Segítség a hibaelhárításhoz

Az Intune-ügyfélszoftver általában a háttérben fut, és csak ritkán igényel felhasználói beavatkozást vagy hibaelhárítást. Ha számítógép-felügyelettel kapcsolatos problémák megoldására van szükség, tekintse meg a naplókat. Az Intune-ügyfélszoftver és a hozzá tartozó naplók a %Program Files%\Microsoft\OnlineManagement könyvtárba vannak telepítve.

Emellett áttekintheti [Az ügyfél a Microsoft Intune-ban való beállításának hibaelhárítása](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) témakört az előforduló problémák megkereséséhez és esetleges megoldásához vagy megkerüléséhez.

