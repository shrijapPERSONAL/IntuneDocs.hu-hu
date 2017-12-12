---
title: "Az Intune App SDK előnyei"
description: "Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi a Microsoft Intune mobilalkalmazás-felügyeleti funkcióinak használatát."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 08/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c711152d8afb75d688f5f820f6c50bbe6465efb7
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2017
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
A rendszergazdák kényszeríthetik az alkalmazásban lévő webes hivatkozások [Intune Managed Browser alkalmazással](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies) való megnyitását. Ez garantálja, hogy a vállalati környezetben megjelenő hivatkozások az Intune által felügyelt alkalmazások tartományán belül maradjanak.

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
>Az Intune-alkalmazásvédelem az eszköz regisztrációja nélkül is elérhető az Intune alkalmazásburkoló eszközei, az Android vagy iOS rendszerhez készült Intune App SDK, az SDK Xamarin összetevőjének és az SDK Cordova beépülő moduljának használatával.

A saját eszközt használó felhasználók sok esetben anélkül szeretnének a vállalati adatokhoz hozzáférni, hogy eszközüket mobileszköz-felügyeleti (MDM) szolgáltatóban kellene regisztrálniuk. Az MDM-alapú regisztrációhoz globális irányítás szükséges az eszköz felett, a felhasználók pedig sok esetben nem szívesen biztosítanak saját eszközük felett ilyen mértékű irányítást a vállalatnak.

A regisztráció nélküli alkalmazásvédelemmel a Microsoft Intune szolgáltatás közvetlenül az alkalmazásokra léptethet érvénybe alkalmazásvédelmi szabályzatokat, mindehhez nincs szüksége eszközfelügyeleti csatornára.
