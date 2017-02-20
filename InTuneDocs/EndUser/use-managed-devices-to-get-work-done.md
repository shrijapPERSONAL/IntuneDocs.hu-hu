---
title: "Munkavégzés felügyelt eszközökkel | Microsoft Docs"
description: "További információ a Céges portál alkalmazásról."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 1ca19828902585bf6011713ab214619b7f8c12c5


---

# <a name="using-managed-devices-to-get-work-done"></a>Munkavégzés felügyelt eszközökkel
A Microsoft Intune olyan szoftveres megoldás, amely lehetővé teszi a cégek számára a különböző eszközök (például okostelefonok, táblagépek és személyi számítógépek), az alkalmazások, valamint az e-mailhez hasonló más vállalati erőforrások felügyeletét. Ezáltal a rendszer módot ad rá, hogy az alkalmazottak bárhonnan, bármilyen eszközről elérhessék a munkahelyi adatokat, ugyanakkor segít megőrizni a vállalati adatok biztonságát.

Az eszköznek az Intune felügyelete alá történő regisztrálása lehetővé teszi az informatikai osztály számára a munkahelyi vagy iskolai erőforrások kezelését és védelmét, miközben Ön mint alkalmazott szabadon választott eszközön végezheti feladatait. Ezt alapvetően úgy érheti el, hogy a Céges portálon regisztrálja az eszközt a felügyeleti rendszerben.

A Vállalati portált kétféleképpen szerezheti be:

- Telepítheti az eszközére a Vállalati portál alkalmazást. A Céges portál alkalmazást általában az eszköz alkalmazásáruházából lehet telepíteni, de a rendszergazda is telepítheti Önnek azt.
- Megnyithatja a rendszergazdája által beállított [Céges portál webhelyet](http://portal.manage.microsoft.com).

## <a name="whats-the-difference-between-the-app-and-the-website"></a>Az alkalmazás és a webhely közötti különbség
A Vállalati portál alkalmazás és webhely között van néhány kisebb eltérés, de a legtöbb feladatot bármelyiken elvégezheti. Néhány olyan feladat, amelyet elvégezhet:

- Az eszközök regisztrálása felügyelet céljából
- Az eszközök állapotának megtekintése
- Ajánlott és kötelező vállalati alkalmazások letöltése
- Átnevezheti az eszközét
- Az eszköz PIN-kódjának vagy jelszavának alaphelyzetbe állítása
- Segítség kérése az informatikai részlegtől

A Vállalati portál webhelyen, illetve az alkalmazásban elvégezhető feladatok közti különbséget az alábbi hivatkozások egyikén tekintheti meg:

- [Android-eszköz használata](using-your-android-device-with-intune.md)
- [iOS vagy macOS rendszerű eszköz használata](using-your-ios-or-macOS-device-with-intune.md)
- [Windows-eszköz használata](using-your-windows-device-with-intune.md)
- [A Munkahelyi portál webhely használata](using-the-intune-company-portal-website.md)

## <a name="what-happens-when-you-add-a-computer-or-device-to-the-company-portal"></a>Mi történik, ha hozzáadok egy számítógépet vagy egy eszközt a Vállalati portálhoz?
Ha hozzáad egy számítógépet vagy egy eszközt a vállalati portálhoz, előfordulhat, hogy települ néhány szoftver, vagy letöltődik egy alkalmazás (eszköztől függően). Egyúttal az eszközön található vállalati információk védelme céljából engedélyezi a rendszergazdának az eszköz felügyeletét.

Ha meg szeretné tudni, hogy a rendszergazda mit lát az eszközén, kövesse a használt eszköz típusának megfelelő hivatkozást:

- [A Céges portál alkalmazás telepítése Android rendszerű eszközön](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-android.md)
- [A Céges portál alkalmazás telepítése iOS és macOS rendszerű eszközökön](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)
- [A Céges portál alkalmazás telepítése Windows rendszerű eszközön](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md)

## <a name="what-kind-of-computers-or-devices-can-you-add-to-the-company-portal"></a>Milyen számítógépeket és eszközöket lehet hozzáadni a Vállalati portálhoz?
-   iOS (például iPhone és iPad) és macOS (például MacBook és iMac) rendszerű Apple-eszközök
-   Androidos eszközök
-   Windows-eszközök
    -   Windows 10 mobil verzió
    -   Windows 10 asztali verzió
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Eltávolítható egy számítógép vagy eszköz a Vállalati portálról?
Igen, a Vállalati portálról eltávolíthat vagy alaphelyzetbe állíthat egy számítógépet vagy eszközt. Az **eltávolítás** és az **alaphelyzetbe állítás** között azonban van különbség.

Számítógép vagy eszköz *eltávolításakor* az eszköz regisztrációja az Intune-ból is törlődik. A regisztráció törlése után az adott eszközről többé nem fér hozzá a Vállalati portálhoz, és az is előfordulhat, hogy egyes vállalati adatok törlődnek az eszközről. Az eszközöknek a Vállalati portálról való eltávolításáról információt az alábbi hivatkozások egyikén találhat:

- [Android rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-android.md)
- [iOS és macOS rendszerű eszközök regisztrációjának törlése](unenroll-your-device-from-intune-ios.md)
- [Windows rendszerű eszköz regisztrációjának törlése](unenroll-your-device-from-intune-windows.md)

Számítógép vagy eszköz *alaphelyzetbe állításakor* a Vállalati portál megpróbálja a gyártó alapértelmezett beállításai szerinti helyzetbe állítani a számítógépet vagy eszközt. Az eszköz alaphelyzetbe állításával töröl minden vállalati és személyes adatot az eszközről! Ha elvesztette az eszközét, akkor távolról, a Vállalati portál webhelyéről is alaphelyzetbe állíthatja.

Az eszközök alaphelyzetbe állításáról az alábbi hivatkozások egyikén találhat további információkat:

- [Android rendszerű eszköz alaphelyzetbe állítása (törlése)](reset-erase-your-lost-or-stolen-device-android.md)
- [iOS vagy macOS rendszerű eszköz alaphelyzetbe állítása (törlése)](reset-erase-your-lost-or-stolen-device-ios.md)
- [Windows rendszerű eszköz alaphelyzetbe állítása](reset-erase-your-lost-or-stolen-device-windows.md)
- [Az eszköz alaphelyzetbe állítása a Munkahelyi portál webhelyről](reset-your-device-cpwebsite.md)

## <a name="what-if-i-cant-see-my-device-in-the-company-portal"></a>Mi a teendő, ha nem látom a saját eszközt a Céges portálon?
Az eszközök csak akkor láthatók, ha hozzáadja őket a Vállalati portálhoz. Látogasson el a rendszergazda által beállított Céges portálra, és kövesse az eszközére vonatkozó lépéseket. A vállalat által birtokolt vagy kezelt eszközöket sem fogja látni.

## <a name="if-you-have-questions-contact-your-it-admin"></a>Ha kérdése van, lépjen kapcsolatba a rendszergazdával
Ha segítségre van szüksége, lépjen kapcsolatba a rendszergazdával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Feb17_HO2-->


