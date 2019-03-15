---
title: Munkavégzés felügyelt eszközökkel | Microsoft Docs
description: Tudja meg, mit jelent az eszköz regisztrálása az Intune-felügyeletben.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: robstack
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7b67f1484ed74bd538cad53f02babd542b77fff
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838835"
---
# <a name="use-managed-devices-to-access-work-or-school-resources"></a>Felügyelt eszközök használata munkahelyi vagy iskolai erőforrások elérésére
A Microsoft Intune az eszközkezelési rendszer, amely lehetővé teszi a szervezetek az eszközöket, alkalmazásokat és e-mail-hozzáférés kezelése. Kezelés lehetővé teszi, és más alkalmazottai és tanulók, a munkahelyi információkhoz szinte bárhonnan, szinte bármilyen eszközön. Akkor is, ha távolról dolgozik, Ön és a szervezet adatait biztonságban tudhassa.

A Microsoft Intune nem a vállalat használ a biztonsági és a vonatkozó követelmények konfigurálása a szoftvert. Amikor elkészült, az eszköz felügyelt, az Intune vállalati portál alkalmazást fogja használni. Az ehhez az alkalmazáshoz választott eszközön használatával hozzáférés munkahelyi vagy iskolai erőforrások. 

## <a name="what-information-can-my-company-see-when-i-get-my-device-managed"></a>Milyen információk láthatók a cég láthatja, amikor jelenik meg az eszköz felügyelt?
Ön telepítése után a vállalati portálon, a cég informatikai támogatási szolgálata csak munkával, információk jelennek meg. Azonban nem tekinthetik meg a személyes adatok. Ez különösen fontos tudnivaló, ha személyes eszközt regisztrál munkahelyi használatra. Ismerje meg, hogy pontosan milyen azok [láthat és mit nem a következő cikkben](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

## <a name="how-do-i-get-company-portal"></a>Hogyan szerezhetem be a vállalati portálon?
Get céges portál által:

- A céges portál alkalmazás telepítése az eszközön. A Céges portál alkalmazást általában az eszköz alkalmazásáruházából lehet telepíteni, de a cég informatikai támogató szolgálata is telepítheti Önnek azt.
- Ugrás a [céges portál webhelyen](https://go.microsoft.com/fwlink/?linkid=2010980) , hogy a cég támogatási szolgálata fel.

## <a name="whats-the-difference-between-the-app-and-the-website"></a>Az alkalmazás és a webhely közötti különbség
Minden Windows 10-es, iOS, macOS és Android rendszerhez készült céges portál alkalmazás zökkenőmentesen integrálható az adott platform az eszközén. A webhely bármely eszközről elérhető, és a függetlenül attól, hogy melyik eszközt használja a azonos, univerzális élményt biztosít. 

Céges portál útmutatást találhat az eszköz-platformhoz, kezdve a regisztrációhoz az alábbi hivatkozások alatt:  

- [Android-eszköz használata](using-your-android-device-with-intune.md)
- [iOS-eszköz használata](using-your-ios-device-with-intune.md)
- [macOS-eszköz használata](using-your-macos-device-with-intune.md)
- [Windows-eszköz használata](using-your-windows-device-with-intune.md)
- [A Munkahelyi portál webhely használata](using-the-intune-company-portal-website.md)

## <a name="what-happens-when-you-add-a-computer-or-device-to-the-company-portal"></a>Mi történik, ha hozzáadok egy számítógépet vagy egy eszközt a Vállalati portálhoz?
Ha hozzáad egy számítógépet vagy egy eszközt a vállalati portálhoz, előfordulhat, hogy települ néhány szoftver, vagy letöltődik egy alkalmazás (eszköztől függően). Egyúttal az eszközön található vállalati információk védelme céljából engedélyezi a cég informatikai támogató szolgálatának az eszköz felügyeletét.

Ha meg szeretné tudni, hogy a cég informatikai támogató szolgálata mit lát az eszközén, kövesse a használt eszköz típusának megfelelő hivatkozást:

- [A Céges portál alkalmazás telepítése Android rendszerű eszközön](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-android.md)
- [A Céges portál alkalmazás telepítése iOS rendszerű eszközön](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)
- [A Céges portál alkalmazás telepítése macOS rendszerű eszközön](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-macos.md)
- [A Céges portál alkalmazás telepítése Windows rendszerű eszközön](about-cp-app-for-windows-10.md)

## <a name="what-kind-of-computers-or-devices-can-you-add-to-the-company-portal"></a>Milyen számítógépeket és eszközöket lehet hozzáadni a Vállalati portálhoz?
-   iOS (például iPhone és iPad) és macOS (például MacBook és iMac) rendszerű Apple-eszközök
-   Androidos eszközök
-   Windows-eszközök
    -   Windows 10 mobil verzió
    -   Windows 10 asztali verzió
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Eltávolítható egy számítógép vagy eszköz a Vállalati portálról?
Igen, a Vállalati portálról eltávolíthat vagy alaphelyzetbe állíthat egy számítógépet vagy eszközt. Az **eltávolítás** és az **alaphelyzetbe állítás** között azonban van különbség.

Számítógép vagy eszköz a Céges portálról való *eltávolításakor* az eszköz regisztrációja az Intune-ból is törlődik. A regisztráció törlése után az adott eszközről többé nem fér hozzá a Vállalati portálhoz, és az is előfordulhat, hogy egyes vállalati adatok törlődnek az eszközről. Az eszközöknek a Vállalati portálról való eltávolításáról információt az alábbi hivatkozások egyikén találhat:

- [Android rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-android.md)
- [iOS rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-ios.md)
- [macOS rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-macos.md)
- [Windows rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-windows.md)

Számítógép vagy eszköz *alaphelyzetbe állításakor* a Vállalati portál megpróbálja a gyártó alapértelmezett beállításai szerinti helyzetbe állítani a számítógépet vagy eszközt. Az eszköz alaphelyzetbe állításával töröl minden vállalati és személyes adatot az eszközről! Ha elvesztette az eszközét, akkor távolról, a Vállalati portál webhelyéről is alaphelyzetbe állíthatja.

Az eszköz alaphelyzetbe állításáról itt olvashat:

- [Az eszköz alaphelyzetbe állítása (törlése) a Céges portál webhelyről](reset-erase-your-device-cpwebsite.md)

## <a name="what-if-i-cant-see-my-device-in-the-company-portal"></a>Mi a teendő, ha nem látom a saját eszközt a Céges portálon?
Az eszközök csak akkor láthatók, ha hozzáadja őket a Vállalati portálhoz. Látogasson el a rendszergazda által beállított Céges portálra, és kövesse az eszközére vonatkozó lépéseket. A vállalat által birtokolt vagy kezelt eszközöket sem fogja látni.

## <a name="where-else-can-i-go-for-help"></a>Hol találhatok még segítségét?
A Microsoft azt javasolja, hogy először próbálja meg saját maga megoldani a problémát. Az Intune által támogatott mindegyik platformhoz megadtuk azon módszerek listáját, amelyekkel próbálkozhat a problémák megoldása érdekében.

- [Androidos eszközök gyakori problémáinak elhárítása](troubleshoot-your-device-android.md)
- [Az iOS-eszközök gyakori problémáinak elhárítása](troubleshoot-your-device-ios.md)
- [A macOS-eszközök gyakori problémáinak elhárítása](troubleshoot-your-device-macos.md)
- [A Windows-eszközök gyakori problémáinak elhárítása](troubleshoot-your-device-windows.md)

Alább hozzászólva segítséget kérhet, de mivel minden munkahely különböző követelményeket támaszt, előfordulhat, hogy nem mindig tudjuk megválaszolni a felmerülő kérdéseket. A leggyorsabb és leginkább megfelelő választ valószínűleg a cég informatikai támogató szolgálatához fordulva fogja kapni. A rendszergazdák elérhetőségét fel kell tüntetni a [Céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
