---
title: Alkalmazástelepítéssel kapcsolatos problémák elhárítása
description: Ez a témakör a Microsoft Intune-ban jelentkező, alkalmazástelepítéssel kapcsolatos problémák megoldásához nyújt segítséget.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 09/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: df00293335b23d8924887bdd7b70838f9bddfb65
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-app-deployment-problems-in-microsoft-intune"></a>Alkalmazástelepítéssel kapcsolatos problémák elhárítása a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Ha problémába ütközik az alkalmazások Intune-nal történő telepítése vagy felügyelete során, kezdje itt. Ez a témakör néhány gyakori problémát és azok megoldását ismerteti.

## <a name="common-app-deployment-error-codes"></a>Gyakori alkalmazástelepítési hibakódok

|Hibakód|Lehetséges probléma|Javasolt megoldás|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (ügyfélhiba)|Az alkalmazás telepítéséhez közvetlen telepítést lehetővé tevő rendszerrel kell rendelkeznie.|Győződjön meg arról, hogy megbízható az alkalmazáscsomag aláírása, és olyan tartományi eszközre van telepítve a csomag, amelyen engedélyezett az AllowAllTrustedApps házirend. Megfelelő az is, ha közvetlen telepítést biztosító licenccel rendelkező olyan windowsos eszközre van telepítve a csomag, amelyen engedélyezve van az AllowAllTrustedApps házirend.|
|0x80073CF0|A csomag nem nyitható meg.|Lehetséges okok:<br /><br />-   A csomag nincs aláírva.<br />-   A közzétevő neve nem egyezik meg az aláíró tanúsítvány tulajdonosával.<br /><br />További információt az AppxPackagingOM eseménynaplóban talál.|
|0x80073CF3|Nem sikerült ellenőrizni a csomag frissítéseit, függőségeit vagy ütközéseit|Lehetséges okok:<br /><br />-   A bejövő csomag ütközik egy telepített csomaggal.<br />-   Nem található a megadott csomagfüggőség.<br />-   A csomag nem támogatja a megfelelő processzorarchitektúrát.<br /><br />További információt az AppXDeployment-Server eseménynaplóban talál.|
|0x80073CFB|A megadott csomag már telepítve van, és a csomag újratelepítése le van tiltva.|Ez a hiba akkor fordulhat elő, ha olyan csomagot telepít, amely nem azonos a már telepített csomaggal. Ellenőrizze, hogy a csomag tartalmaz-e digitális aláírást. Ha újraépít vagy újra aláír egy csomagot, a csomag nem lesz bitenként azonos az előzőleg telepített csomaggal. Ez a hiba kétféleképpen javítható ki:<br /><br />-   Növelje az alkalmazás verziószámát, majd építse és írja alá újra a csomagot.<br />-   Az új csomag telepítése előtt távolítsa el a régi csomagot a rendszer minden felhasználója esetében.|
|0x87D1041C|Az alkalmazás telepítése sikeres volt, de a rendszer nem ismeri fel az alkalmazást.|- Az alkalmazást az Intune sikeresen telepítette, azonban a későbbiekben valaki (valószínűleg a végfelhasználó) eltávolította. Kérje meg a felhasználót, hogy telepítse újra az alkalmazást a vállalati portálról. A kötelező alkalmazások újratelepítése automatikusan megtörténik az eszköz következő bejelentkezésekor.|

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>A Microsoft Áruházból származó alkalmazások hibáinak elhárítása

A [Troubleshooting packaging, deployment, and query of Microsoft Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (A Microsoft Áruházbeli alkalmazások csomagolási, telepítési és lekérdezési hibáinak elhárítása) című cikkben foglaltak segítenek elhárítani az alkalmazásoknak a Microsoft Áruházból akár Intune-nal, akár más módon történő telepítésekor tapasztalt gyakori problémákat.

## <a name="troubleshooting-app-deployment-to-pcs-managed-by-the-intune-software-client"></a>Az Intune-szoftverügyféllel felügyelt számítógépekre való alkalmazástelepítés hibáinak elhárítása
Az Intune által felügyelt alkalmazásokra történő alkalmazástelepítés hibáinak elhárításában a következő két naplófájl tartalma segíthet:
- %ProgramFiles%\Microsoft\OnlineManagement\Logs mappa
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Ha támogatási esetet kell megnyitnia az Intune kapcsán, akkor hasznos, ha el is küldi ezeket a naplókat a Microsoftnak.


### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.
