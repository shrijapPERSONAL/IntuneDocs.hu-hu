---
title: "Számítógépek felügyelete az ügyfélszoftverrel | Microsoft Intune"
description: "Windows rendszerű számítógépek felügyelete az Intune ügyfélszoftverrel."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: fb862178e0791936243ebb21c6b70ea808d07d16


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel
Ahelyett, hogy [a Windows rendszerű számítógépeket mobileszközökként regisztrálná](set-up-windows-device-management-with-microsoft-intune.md), a számítógépeket az Intune ügyfélszoftver telepítésével is regisztrálhatja és felügyelheti.

Az Intune a Windows rendszerű számítógépek felügyeletéhez a Windows Server Active Directory tartományi szolgáltatások (AD DS) és csoportházirend-objektumok (GPO-k) által alkalmazottakhoz hasonló szabályzatokat használ. Ha Active Directory-tartományhoz csatlakoztatott számítógépeket felügyel az Intune segítségével, akkor [győződjön meg róla, hogy az Intune-szabályzatok nem ütköznek a szervezet csoportházirend-objektumaival](resolve-gpo-and-microsoft-intune-policy-conflicts.md).

Jóllehet az Intune-szoftverügyfél a szoftverfrissítések, a Windows tűzfal és az Endpoint Protection végpontvédelmi megoldás kezelésével támogatja a [számítógépek védelmét szolgáló felügyeleti funkciókat](policies-to-protect-windows-pcs-in-microsoft-intune.md), az Intune-szoftverügyfél által felügyelt számítógépek nem lehetnek egyéb Intune-szabályzatok, így a mobileszköz-felügyeletet szolgáló **Windows**-szabályzatok célpontjai.

> [!NOTE]
> A Windows 8.1-es vagy újabb rendszerű eszközök felügyelhetők az Intune ügyfélszoftverrel vagy mobileszközökként. A jelen témakör az Intune szoftverügyfelet futtató számítógépekre vonatkozik. Az Intune-számítógépügyfél telepítése és a mobileszköz-felügyeletbe történő regisztrálás együttes végrehajtása nem támogatott.

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
|Operációs rendszer | Windows Vista vagy újabb rendszert futtató eszköz. A Home Edition verziók nem támogatottak.|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie az eszközön.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.<br /><br />A Windows Installer verziójának megtekintése egy számítógépen:<br /><br />– A számítógépen kattintson a jobb gombbal a **%windir%\System32\msiexec.exe** fájlra, majd a **Tulajdonságok** menüpontra.<br /><br />A Windows Installer legújabb verzióját letöltheti a Microsoft Developer Network webhelyen található [Windows Installer újraterjeszthető csomagok](http://go.microsoft.com/fwlink/?LinkID=234258) oldalról.|
|Nem kompatibilis ügyfélszoftver eltávolítása|Az Intune-ügyfélszoftver telepítése előtt el kell távolítania a számítógépen esetleg megtalálható Configuration Manager-, Operations Manager-, Operations Management Suite- és Service Manager-ügyfélszoftvert.|

## <a name="computer-management-with-the-intune-computer-client"></a>Számítógép-felügyelet az Intune-számítógépügyféllel
Az Intune ügyfélszoftver telepítését követően egyebek között a következő felügyeleti képességek érhetők el: [alkalmazásfelügyelet](deploy-apps-in-microsoft-intune.md), [valós idejű figyelés és Endpoint Protection-védelem](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md), [a Windows Firewall beállításainak kezelése](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), hardver- és szoftverleltár, (távsegítségre vonatkozó kéréseken keresztüli) távvezérlés, [a szoftverfrissítések beállításai](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) és a megfelelőségi beállításokra vonatkozó jelentéskészítés.

A mobil eszközökként kezelt számítógépek esetében elérhető felügyeleti opciók egy része nem érhető el az ügyfélszoftver által kezelt számítógépek esetében, pl.:

-   Teljes törlés (a szelektív törlés elérhető)
-   Feltételes hozzáférés
-   A **Számítógép-felügyeleti** szabályzatokon kívüli egyéb Windows-szabályzatok

![Szabályzatsablon Windows rendszerű számítógépekhez](../media/pc_policy_template.png)

Az Intune-ügyfélügynök által különálló számítógépeken helyileg elvégzett műveleteken túl az Intune felügyeleti konzolján egyéb [általános számítógép-felügyeleti feladatokat](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) is elvégezhet azokon a Windows rendszerű számítógépeken, amelyekre az ügyfél telepítve van. Például:

-   Felügyelt számítógépek hardver- és szoftverleltárjára vonatkozó információk megtekintése

-   Számítógépek távoli újraindítása

-   Számítógépek kivonása az ügyfélszoftver eltávolításához és kivételükhöz az Intune-felügyelet alól

-   Felhasználók hozzákapcsolása adott felügyelt számítógépekhez

-   Válasz távsegítségre vonatkozó kérésre

Az Intune-ügyfélügynök általában a háttérben fut, és ritkán van csak szükség felhasználói beavatkozásra vagy hibaelhárításra. Ha azonban segítségre van szüksége a számítógép-felügyeleti problémák elhárításához, több olyan [forrásanyag is elérhető, amelyek segítséget nyújthatnak](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Nov16_HO1-->


