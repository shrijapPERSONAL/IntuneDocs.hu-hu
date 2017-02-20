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
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: 21e83b68bb68384a8916db8d7f779cddde18a8a6


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel
Ahelyett, hogy [a Windows rendszerű számítógépeket mobileszközökként regisztrálná](set-up-windows-device-management-with-microsoft-intune.md), a számítógépeket az Intune ügyfélszoftver telepítésével is regisztrálhatja és felügyelheti.

Az Intune a Windows rendszerű számítógépek felügyeletéhez a Windows Server Active Directory tartományi szolgáltatások (AD DS) csoportházirend-objektumaihoz (GPO-khoz) hasonló szabályzatokat használ. Ha Active Directory-tartományhoz csatlakoztatott számítógépeket felügyel az Intune segítségével, akkor [győződjön meg róla, hogy az Intune-szabályzatok nem ütköznek a szervezet csoportházirend-objektumaival](resolve-gpo-and-microsoft-intune-policy-conflicts.md). További információ a [csoportszabályzat-objektumokról](https://technet.microsoft.com/library/hh147307.aspx).

Jóllehet az Intune-szoftverügyfél a szoftverfrissítések, a Windows tűzfal és az Endpoint Protection végpontvédelmi megoldás kezelésével támogatja a [számítógépek védelmét szolgáló felügyeleti funkciókat](policies-to-protect-windows-pcs-in-microsoft-intune.md), az Intune-szoftverügyfél által felügyelt számítógépek nem lehetnek egyéb Intune-szabályzatok, így a mobileszköz-felügyeletet szolgáló **Windows**-szabályzatok célpontjai. 

Az Intune-szoftverügyfél Windows rendszerű számítógépek kezelésére való használatakor csak a **Számítógép-kezelés** szakaszban látható szabályzatokat használhatja.

  ![Új windowsos PC-szabályzat sablonjának kiválasztása](../media/select-template-for-pc-policy.png)

A beállítható szabályzatok részletes leírásáért lásd:

- [Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [A Windows rendszerű számítógépek védelme Windowsos tűzfalszabályzatok használatával a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Emellett az alkalmazások telepítésekor csak a Windows Installert (.exe, .msi) használhatja.

  ![Platform és hely kiválasztása a PC-s ügyfélszoftver fájljaihoz](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> A Windows 8.1-es vagy újabb rendszerű eszközöket kezelheti számítógépekként az Intune-ügyféllel, vagy mobileszközökként a mobileszköz-felügyeleti (MDM) szolgáltatással. A két módszert együttesen nem használhatja, ezért járjon el körültekintően, mielőtt a számítógépek az Intune-os szoftverügyfél használatával történő felügyelete mellett dönt. Ez a témakör kizárólag az Intune-szoftverügyféllel számítógépként kezelt eszközökre vonatkozik.

## <a name="requirements-for-intune-pc-client-management"></a>Az Intune-számítógépügyfél általi felügyelet követelményei

**Hardver**: Az Intune-ügyfél a következő minimális hardverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

**Szoftver**: Az ügyfél az alábbi szoftverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Operációs rendszer | Windows Vista vagy újabb rendszert futtató eszköz. </br></br>**A Home Edition verziók nem támogatottak.**|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie az eszközön.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.<br /><br />A Windows Installer verziójának megtekintése egy számítógépen:<br /><br />  A számítógépen kattintson a jobb gombbal a **%windir%\System32\msiexec.exe** fájlra, majd a **Tulajdonságok** menüpontra.<br /><br />A Windows Installer legújabb verzióját letöltheti a Microsoft Developer Network webhelyen található [Windows Installer újraterjeszthető csomagok](http://go.microsoft.com/fwlink/?LinkID=234258) oldalról.|
|Nem kompatibilis ügyfélszoftver eltávolítása|Az Intune-ügyfélszoftver telepítése előtt el kell távolítania a számítógépen esetleg megtalálható Configuration Manager-, Operations Manager-, Operations Management Suite- és Service Manager-ügyfélszoftvert.|

## <a name="computer-management-capabilities-with-the-intune-software-client"></a>Számítógép-felügyeleti képességek az Intune-os szoftverügyféllel

Az Intune-ügyfélszoftver telepítése után a következő felügyeleti funkciók állnak rendelkezésre: 

- [Alkalmazásfelügyelet](deploy-apps-in-microsoft-intune.md)

- [Valós idejű figyelés és Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

 > [!NOTE]
 > Az Endpoint Protection ugyanaz, mint a Windows Defender. Az Endpoint Protection a Windows 7 és Windows 8 rendszerre vonatkozik. A Windows 10 és újabb verziókban a termék neve Windows Defenderre változott.

- [A Windows tűzfal beállításainak felügyelete](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), hardver- és szoftverleltár, távvezérlés (távsegítségre vonatkozó kéréseken keresztül)

- [Szoftverfrissítési beállítások](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Megfelelőségi beállítások jelentése

Az Intune felügyeleti konzoljának bizonyos részei, mint például az „Updates” (Frissítések), a „Protection” (Védelem) és a „Licenses” (Licencek) csak akkor jelennek meg, ha regisztrált eszközöket az Intune-os szoftverügyfél használatával.

  ![A felügyeleti konzol csak a számítógépügyfél esetén megjelenített elemei](../media/admin-console-settings-only-for-pc-agent.png)

Az Intune felügyeleti konzolján más [általános számítógép-felügyeleti feladatokat](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) is elvégezhet olyan Windows rendszerű számítógépeken, amelyeken az ügyfél telepítve van:

-   Felügyelt számítógépek hardver- és szoftverleltárjára vonatkozó információk megtekintése

-   Számítógépek távoli újraindítása

-   Számítógépek kivonása a szoftverügyfél eltávolításához és kivételükhöz az Intune-felügyelet alól

-   Felhasználók hozzákapcsolása adott felügyelt számítógépekhez

-   Válasz távsegítségre vonatkozó kérésre

## <a name="management-limitations-of-the-intune-software-client"></a>Az Intune-os szoftverügyfél felügyeleti korlátozásai

Az Intune-os szoftverügyfél használatával felügyelt számítógépeknél nem használhat egyes olyan felügyeleti lehetőségeket, amelyek segítségével számítógépekként kezelheti a mobileszközöket:

-   Teljes törlés (a szelektív törlés elérhető)

-   Feltételes hozzáférés

## <a name="help-with-troubleshooting"></a>Segítség a hibaelhárításhoz

Az Intune-ügyfélügynök általában a háttérben fut, és ritkán van csak szükség felhasználói beavatkozásra vagy hibaelhárításra. Ha számítógép-felügyelettel kapcsolatos problémák megoldására van szükség, tekintse meg a naplókat. Az Intune-os szoftverügyfél és a hozzá tartozó naplók a % Program Files%\Microsoft\OnlineManagement könyvtárba vannak telepítve.

Emellett áttekintheti [Az ügyfél a Microsoft Intune-ban való beállításának hibaelhárítása](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) témakört az előforduló problémák megkereséséhez és esetleges megoldásához vagy megkerüléséhez.



<!--HONumber=Feb17_HO2-->


