---
title: Az Intune App SDK előnyei
titlesuffix: Microsoft Intune
description: Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi a Microsoft Intune mobilalkalmazás-felügyeleti funkcióinak használatát.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fc49d7ba7cdc5b986c06f8a84ececc8339a812a2
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2018
ms.locfileid: "49425104"
---
# <a name="intune-app-sdk-overview"></a>Az Intune App SDK áttekintése
Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi az alkalmazások számára az Intune alkalmazásvédelmi szabályzatainak használatát. Arra törekszik, hogy minimálisra csökkentse az alkalmazásfejlesztő által végzendő kódmódosítás mennyiségét. Az SDK legtöbb funkcióját alkalmazása működésének módosítása nélkül is engedélyezheti. Ha hatékonyabbá szeretné tenni a végfelhasználók és a rendszergazdák munkáját, az API-jainkkal személyre szabhatja alkalmazása működését olyan funkciók tekintetében, amelyek használatához az alkalmazás közreműködése szükséges.

Miután engedélyezte az alkalmazás számára az alkalmazásvédelmi szabályzatok használatát, a rendszergazda érvénybe tudja léptetni ezeket a szabályzatokat az alkalmazásban tárolt céges adatok védelme érdekében.

## <a name="app-protection-features"></a>Alkalmazásvédelmi funkciók

Az alábbiakban példákat talál az SDK-val engedélyezhető Intune-alapú alkalmazásvédelmi funkciókra.

### <a name="control-users-ability-to-move-corporate-files"></a>Vállalati fájlok felhasználók általi áthelyezésének szabályozása
A rendszergazdák szabályozhatják az alkalmazásban tárolt munkahelyi vagy iskolai adatok áthelyezésének helyét. Érvénybe léptethetnek például olyan szabályzatot, amely megakadályozza, hogy az alkalmazás biztonsági másolatot készítsen a vállalati adatokról a felhőbe.

### <a name="configure-clipboard-restrictions"></a>Vágólappal kapcsolatos korlátozások beállítása
A rendszergazdák konfigurálhatják a vágólap működését az Intune által felügyelt alkalmazásokban. Érvénybe léptethetnek például olyan szabályzatot, amely megakadályozza, hogy a végfelhasználók adatokat másoljanak vagy vágjanak ki az alkalmazásból, és beillesszék azokat egy nem felügyelt, személyes alkalmazásba.

### <a name="enforce-encryption-on-saved-data"></a>Mentett adatok titkosításának kényszerítése
A rendszergazdák olyan szabályzatot alkalmazhatnak, amely biztosítja, hogy az alkalmazás által az adott eszközre mentett adatok titkosítva legyenek.

### <a name="remotely-wipe-corporate-data"></a>Vállalati adatok távoli törlése
A rendszergazdák távolról törölhetik a vállalati adatokat az Intune által felügyelt vállalati alkalmazásokból. Ez a funkció identitásalapú, ezért csak azokat a fájlokat törli, amelyek az adott végfelhasználó vállalati identitásához kapcsolódnak. A szolgáltatásnak ehhez az alkalmazás közreműködésére van szüksége. Az alkalmazás a felhasználói beállítások alapján határozza meg azt az identitást, amelyhez a törlést végre kell hajtani. Ilyen felhasználói beállítások hiányában alapértelmezés szerint az alkalmazás könyvtára fog törlődni, és a végfelhasználó értesítést kap arról, hogy a hozzáférését visszavonták.

### <a name="enforce-the-use-of-a-managed-browser"></a>Felügyelt böngésző használatának kényszerítése
A rendszergazdák kényszeríthetik az alkalmazásban lévő webes hivatkozások [Intune Managed Browser alkalmazással](app-configuration-managed-browser.md) való megnyitását. Ez a funkció garantálja, hogy a vállalati környezetben megjelenő hivatkozások az Intune által felügyelt alkalmazások tartományán belül maradjanak.

### <a name="enforce-a-pin-policy"></a>PIN-kód használatára vonatkozó szabályzat alkalmazása
A rendszergazdák kötelezhetik a végfelhasználót PIN-kód megadására az alkalmazásban lévő céges adatok elérése előtt. Ezzel ellenőrizni lehet, hogy az alkalmazást használó személy ugyanaz-e, mint aki eredetileg bejelentkezett a munkahelyi vagy iskolai fiókkal. Amikor a végfelhasználók beállítják a PIN-kódjukat, az Intune App SDK az Azure Active Directory segítségével összehasonlítja a végfelhasználók hitelesítő adatait a regisztrált Intune-fiókkal.

### <a name="require-users-to-sign-in-with-work-or-school-account-for-app-access"></a>A felhasználók kötelezése munkahelyi vagy iskolai fiókkal való bejelentkezésre az alkalmazás eléréséhez
A rendszergazdák kötelezhetik a felhasználókat arra, hogy munkahelyi vagy iskolai fiókkal jelentkezzenek be az alkalmazás eléréséhez. Az Intune App SDK az Azure Active Directory segítségével teszi lehetővé az egyszeri bejelentkezést, ami azt jelenti, hogy a hitelesítő adatokat elég egyszer megadni, és a későbbi bejelentkezések során a rendszer ismét azokat használja. A rendszer az Azure Active Directoryval összevont identitáskezelési megoldások hitelesítését is támogatja.

### <a name="check-device-health-and-compliance"></a>Eszközök állapotának és megfelelőségének ellenőrzése
A rendszergazdák ellenőrizhetik az eszközök állapotát és az Intune-szabályzatoknak való megfelelőségét, mielőtt a végfelhasználók hozzáférhetnének az alkalmazáshoz. Az iOS rendszeren a szabályzat ellenőrzi, hogy az eszköz jailbreakelt-e. Az Android rendszeren a szabályzat ellenőrzi, hogy az eszköz rootolt-e.

### <a name="multi-identity-support"></a>Többszörös identitás támogatása
A többszörös identitás támogatása egy olyan szolgáltatása az SDK-nak, amely lehetővé teszi a szabályzatok által felügyelt (vállalati) és a felügyelet nélküli (személyes) fiókok ugyanazon alkalmazásban való egyidejű használatát.

Például sok felhasználó konfigurál vállalati és személyes e-mail-fiókot is az iOS vagy az Android rendszerhez készült Office-mobilalkalmazásokban. Amikor a felhasználó a vállalati fiókjával fér hozzá az adatokhoz, a rendszergazdának biztosnak kell lennie abban, hogy arra alkalmazva lesz az alkalmazásvédelmi szabályzat. Ugyanakkor ha a felhasználó a személyes e-mail fiókjához fér hozzá, az adatoknak a rendszergazda felügyeletén kívül kell esniük. Az Intune App SDK ezt úgy éri el, hogy az alkalmazásvédelmi szabályzatot **kizárólag** az alkalmazásban lévő vállalati identitásra alkalmazza.

A többszörös identitás támogatása megoldást kínál arra az adatvédelmi problémára, amellyel a munkahelyek a személyes és munkahelyi fiókokat egyaránt támogató tárolóalkalmazások használata során szembesülnek.
 
### <a name="app-protection-without-device-enrollment"></a>Alkalmazásvédelem eszközregisztráció nélkül

>[!IMPORTANT]
>Az Intune-alkalmazásvédelem az eszköz regisztrációja nélkül is elérhető az Intune alkalmazásburkoló eszközei, az Android vagy iOS rendszerhez készült Intune App SDK, valamint az SDK Xamarin-kötések használatával.

A saját eszközt használó felhasználók sok esetben anélkül szeretnének a vállalati adatokhoz hozzáférni, hogy eszközüket mobileszköz-felügyeleti (MDM) szolgáltatóban kellene regisztrálniuk. Az MDM-alapú regisztrációhoz globális irányítás szükséges az eszköz felett, a felhasználók pedig sok esetben nem szívesen biztosítanak saját eszközük felett ilyen mértékű irányítást a vállalatnak.

A regisztráció nélküli alkalmazásvédelemmel a Microsoft Intune szolgáltatás közvetlenül az alkalmazásokra léptethet érvénybe alkalmazásvédelmi szabályzatokat, mindehhez nincs szüksége eszközfelügyeleti csatornára.

### <a name="on-demand-application-vpn-connections-with-citrix-mvpn"></a>Igény szerinti VPN-alkalmazáskapcsolatok Citrix mVPN segítségével 
Az eszközöket és az alkalmazásokat a Citrix XenMobile MDX és a Microsoft Intune kombinációjával is kezelheti. Ez a kombináció lehetővé teszi, hogy az eszközök kezelésénél egyaránt igénybe vehesse az Intune alkalmazásvédelmi szabályzatát és a Citrix mVPN-technológiáját. A Citrix-integráció elérhető az iOS-es és androidos Intune App SDK-hoz és az iOS-es és androidos Intune alkalmazásburkoló eszközhöz is (a -citrix jelölővel használva).
 
A Citrix MDX-ről további információt [Az MDX Toolkit bemutatása](http://docs.citrix.com/en-us/mdx-toolkit/10/about-mdx-toolkit.html), a [Citrix MDX alkalmazásburkoló iOS-hez](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-ios.html) és a [Citrix MDX alkalmazásburkoló Androidhoz](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-android.html) című cikkekben talál.
