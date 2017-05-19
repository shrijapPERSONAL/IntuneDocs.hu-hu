---
title: "Alkalmazástelepítéssel kapcsolatos problémák elhárítása| Microsoft Docs"
description: "Ez a témakör a Microsoft Intune-ban jelentkező, alkalmazástelepítéssel kapcsolatos problémák megoldásához nyújt segítséget."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 239371198cbbc01b1345c72b3f887055acd44462
ms.lasthandoff: 12/10/2016


---

# <a name="troubleshoot-app-deployment-problems-in-microsoft-intune"></a>Alkalmazástelepítéssel kapcsolatos problémák elhárítása a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ha problémába ütközik az alkalmazások Intune-nal történő telepítése vagy felügyelete során, kezdje itt. Ez a témakör néhány gyakori problémát és azok megoldását ismerteti.

## <a name="common-app-deployment-error-codes"></a>Gyakori alkalmazástelepítési hibakódok

|Hibakód|Lehetséges probléma|Javasolt megoldás|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (ügyfélhiba)|Az alkalmazás telepítéséhez közvetlen telepítést lehetővé tevő rendszerrel kell rendelkeznie.|Győződjön meg arról, hogy megbízható az alkalmazáscsomag aláírása, és olyan tartományi eszközre van telepítve a csomag, amelyen engedélyezett az AllowAllTrustedApps házirend. Megfelelő az is, ha közvetlen telepítést biztosító licenccel rendelkező olyan windowsos eszközre van telepítve a csomag, amelyen engedélyezve van az AllowAllTrustedApps házirend.|
|0x80073CF0|A csomag nem nyitható meg.|Lehetséges okok:<br /><br />-   A csomag nincs aláírva.<br />-   A közzétevő neve nem egyezik meg az aláíró tanúsítvány tulajdonosával.<br /><br />További információt az AppxPackagingOM eseménynaplóban talál.|
|0x80073CF3|Nem sikerült ellenőrizni a csomag frissítéseit, függőségeit vagy ütközéseit|Lehetséges okok:<br /><br />-   A bejövő csomag ütközik egy telepített csomaggal.<br />-   Nem található a megadott csomagfüggőség.<br />-   A csomag nem támogatja a megfelelő processzorarchitektúrát.<br /><br />További információt az AppXDeployment-Server eseménynaplóban talál.|
|0x80073CFB|A megadott csomag már telepítve van, és a csomag újratelepítése le van tiltva.|Ez a hiba akkor fordulhat elő, ha olyan csomagot telepít, amely nem azonos a már telepített csomaggal. Ellenőrizze, hogy a csomag tartalmaz-e digitális aláírást. Ha újraépít vagy újra aláír egy csomagot, a csomag nem lesz bitenként azonos az előzőleg telepített csomaggal. Ez a hiba kétféleképpen javítható ki:<br /><br />-   Növelje az alkalmazás verziószámát, majd építse és írja alá újra a csomagot.<br />-   Az új csomag telepítése előtt távolítsa el a régi csomagot a rendszer minden felhasználója esetében.|
|0x87D1041C|Az alkalmazás telepítése sikeres volt, de a rendszer nem ismeri fel az alkalmazást.|- Az alkalmazást az Intune sikeresen telepítette, azonban a későbbiekben valaki (valószínűleg a végfelhasználó) eltávolította. Kérje meg a felhasználót, hogy telepítse újra az alkalmazást a vállalati portálról. A kötelező alkalmazások újratelepítése automatikusan megtörténik az eszköz következő bejelentkezésekor.|

## <a name="troubleshooting-apps-from-the-windows-store"></a>A Windows Áruházból származó alkalmazások hibáinak elhárítása

A [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (A Windows Áruházbeli alkalmazások csomagolási, telepítési és lekérdezési hibáinak elhárítása) című cikkben foglaltak segítenek elhárítani azokat a gyakori problémákat, amelyeket alkalmazásoknak a Windows Áruházból akár Intune-nal, akár más módon történő telepítésekor tapasztal.

## <a name="troubleshooting-app-deployment-to-pcs-managed-by-the-intune-software-client"></a>Az Intune-szoftverügyféllel felügyelt számítógépekre való alkalmazástelepítés hibáinak elhárítása
Az Intune által felügyelt alkalmazásokra történő alkalmazástelepítés hibáinak elhárításában a következő két naplófájl tartalma segíthet:
- %ProgramFiles%\Microsoft\OnlineManagement\Logs mappa
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Ha támogatási esetet kell megnyitnia az Intune kapcsán, akkor hasznos, ha el is küldi ezeket a naplókat a Microsoftnak.


### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.

