---
title: "Windows rendszerű számítógépek felügyelete az Intune ügyfélprogrammal | Microsoft Intune"
description: "Windows rendszerű számítógépek felügyelete az Intune ügyfélszoftverrel."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa1d6105a5be9c329c75681857a9d6e553088b65
ms.openlocfilehash: be45b2ffb99eb75e71c0d591fc84089b83735905


---

# Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel
Ahelyett, hogy [a Windows rendszerű számítógépeket mobileszközökként regisztrálná](set-up-windows-device-management-with-microsoft-intune.md), a számítógépeket az Intune ügyfélszoftver telepítésével is felügyelheti.

Az Intune a Windows rendszerű számítógépek felügyeletéhez a Windows Server Active Directory tartományi szolgáltatások (AD DS) és csoportházirend-objektumok (GPO-k) által alkalmazottakhoz hasonló szabályzatokat használ. Ha Active Directory-tartományhoz csatlakoztatott számítógépeket felügyel az Intune segítségével, akkor [győződjön meg róla, hogy az Intune-szabályzatok nem ütköznek a szervezet csoportházirend-objektumaival](resolve-gpo-and-microsoft-intune-policy-conflicts.md).

Habár az Intune-ügyfél támogatja a [számítógépeket védő szabályzatok](policies-to-protect-windows-pcs-in-microsoft-intune.md) használatát, amelyek a szoftverfrissítések, a Windows tűzfal és a végpontvédelem felügyeletével segítenek a védelemben, de az Intune-ügyfél által felügyelt számítógépek nem lehetnek egyéb Intune-házirendek célpontjai.

> [!NOTE]
> A Windows 8.1-et vagy annál újabb verziót futtató eszközök kezelhetők az Intune ügyfélprogrammal vagy regisztrálhatók mobileszközként is. Az alábbi információ az Intune-ügyfélprogramot futtató számítógépekre érvényes. Az Intune-számítógépügyfél telepítésének és a Windows-eszköz mobileszköz-felügyeletbe való regisztrálásának együttes végrehajtása nem támogatott.

## Az Intune-számítógépügyfél általi felügyelet követelményei

**Hardver**: Az Intune-ügyfél a következő minimális hardverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

**Szoftver**: Az ügyfél az alábbi szoftverkövetelményekkel telepíthető:

|Követelmény|További információ|
|---------------|--------------------|
|Operációs rendszer | Windows 7 vagy újabb rendszert futtató eszköz. |
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie az eszközön.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.<br /><br />A Windows Installer verziójának megtekintése egy számítógépen:<br /><br />– A számítógépen kattintson a jobb gombbal a **%windir%\System32\msiexec.exe** fájlra, majd a **Tulajdonságok** menüpontra.<br /><br />A Windows Installer legújabb verzióját letöltheti a Microsoft Developer Network webhelyen található [Windows Installer újraterjeszthető csomagok](http://go.microsoft.com/fwlink/?LinkID=234258) oldalról.|
|Nem kompatibilis ügyfélszoftver eltávolítása|Az Intune-ügyfélszoftver telepítése előtt el kell távolítania minden Configuration Manager-, illetve System Management Server-ügyfélszoftvert az adott számítógépről.|

## Az Intune-számítógépügyfél telepítése
Az Intune-ügyfélszoftver a következő módokon telepíthető:

-   [A Microsoft Intune-ügyfélszoftver manuális telepítése](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Ennél a telepítési típusnál a rendszergazda letölti az Intune-ügyfélszoftvert, és manuálisan telepíti minden egyes számítógépen.

  Az Intune-ügyfélszoftver letöltéséhez nyissa meg az [Intune felügyeleti konzolját](https://manage.microsoft.com), és válassza a **Rendszergazda** > **Ügyfélszoftver letöltése** területen az **Ügyfélszoftver letöltése** parancsot.

-   A letöltött fájlokkal manuálisan is telepíti az Intune-ügyfelet a [tartományhoz csatlakoztatott számítógépekre az Active Directory csoportházirend-objektumaival](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy).

-   Végül egy [operációsrendszer-telepítés](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image) részeként is telepítheti az Intune-ügyfélszoftvert.

## Számítógép-felügyelet az Intune-számítógépügyféllel
Miután telepítette az Intune-ügyfelet, az ügyfélszoftver különböző számítógép-felügyeleti képességeket telepít, például [alkalmazásfelügyeletet](deploy-apps-in-microsoft-intune.md), Endpoint Protection védelmet, hardver- és szoftverleltárt, (távsegítségre vonatkozó kéréseken keresztüli) távvezérlést, szoftverfrissítéseket és a megfelelőségi beállítások jelentéseit.

A számítógépügyfél által engedélyezett számítógép-felügyeleti feladatok némelyikét Intune-házirendekkel lehet elvégezni, például a következőket:

-   A [Windows tűzfal beállításainak](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) konfigurálása a felügyelt számítógépeken.

-   [Szoftverfrissítési beállítások](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) konfigurálása felügyelt számítógépeken a szükséges szoftverfrissítések ellenőrzéséhez és letöltéséhez.

-   Felügyelt számítógépek védelmének elősegítése lehetséges fenyegetésekkel és rosszindulatú szoftverekkel szemben [valós idejű megfigyeléssel és az Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) kezelésével.

Az Intune-ügyfélügynök által különálló számítógépeken helyileg elvégzett műveleteken túl az Intune felügyeleti konzolján egyéb [általános számítógép-felügyeleti feladatokat](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) is elvégezhet azokon a Windows rendszerű számítógépeken, amelyekre az ügyfél telepítve van. Például:

-   Felügyelt számítógépek hardver- és szoftverleltárjára vonatkozó információk megtekintése

-   Számítógépek távoli újraindítása

-   Számítógépek kivonása az ügyfélszoftver eltávolításához és kivételükhöz az Intune-felügyelet alól

-   Felhasználók hozzákapcsolása adott felügyelt számítógépekhez

-   Válasz távsegítségre vonatkozó kérésre

Az Intune-ügyfélügynök általában a háttérben fut, és ritkán van csak szükség felhasználói beavatkozásra vagy hibaelhárításra. Ha azonban segítségre van szüksége a számítógép-felügyeleti problémák elhárításához, több olyan [forrásanyag is elérhető, amelyek segítséget nyújthatnak](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Aug16_HO1-->


