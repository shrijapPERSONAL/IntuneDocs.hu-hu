---
title: "Az Intune App SDK által nyújtott előnyök | Microsoft Docs"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Az Intune App SDK áttekintése
Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi a Microsoft Intune mobilalkalmazás-felügyeleti funkcióinak használatát. Arra törekszik, hogy minimálisra csökkentse az alkalmazásfejlesztő által végzendő kódmódosítás mennyiségét. Az SDK legtöbb funkcióját alkalmazása működésének módosítása nélkül is engedélyezheti. Ha hatékonyabbá szeretné tenni a végfelhasználók és a rendszergazdák munkáját, az API-jainkkal személyre szabhatja alkalmazása működését olyan funkciók tekintetében, amelyek használatához az alkalmazás közreműködése szükséges. 

Az alkalmazás engedélyezése után a rendszergazdák szabályzatokat telepíthetnek az Intune által felügyelt alkalmazásokhoz, és a vállalati adatok hatékonyabb védelmére használhatják ezeket a funkciókat.

## <a name="regular-features"></a>Normál funkciók

### <a name="control-users-ability-to-move-corporate-documents"></a>Vállalati dokumentumok felhasználók általi áthelyezésének szabályozása
A rendszergazdák az Intune által felügyelt alkalmazásokban szabályozhatják a vállalati dokumentumok áthelyezését. Telepíthet például olyan szabályzatot, amely megakadályozza, hogy az adott fájlról biztonsági másolatot készítő alkalmazások biztonsági másolatot készítsenek a vállalati adatokról a felhőbe.

### <a name="configure-clipboard-restrictions"></a>Vágólappal kapcsolatos korlátozások beállítása
A rendszergazdák konfigurálhatják a vágólap működését az Intune által felügyelt alkalmazásokban. Üzembe helyezhetnek például olyan szabályzatot, amely megakadályozza, hogy a végfelhasználók a vágólap segítségével adatokat másoljanak vagy vágjanak ki az Intune által felügyelt alkalmazásokból, és nem felügyelt személyes alkalmazásokba illesszék be őket.

### <a name="enforce-encryption-on-saved-data"></a>Mentett adatok titkosításának kényszerítése
A rendszergazdák olyan szabályzatot alkalmazhatnak, amely biztosítja, hogy az alkalmazás által az adott eszközre mentett adatok titkosítva legyenek.

### <a name="remotely-wipe-corporate-data"></a>Vállalati adatok távoli törlése
A rendszergazdák távolról törölhetik a vállalati adatokat az Intune által felügyelt vállalati alkalmazásokból. Ez a funkció identitásalapú, ezért csak azokat a fájlokat törli, amelyek az adott végfelhasználó vállalati identitásához kapcsolódnak. A szolgáltatásnak ehhez az alkalmazás közreműködésére van szüksége. Az alkalmazás a felhasználói beállítások alapján határozza meg azt az identitást, amelyhez a törlést végre kell hajtani. Ilyen felhasználói beállítások hiányában alapértelmezés szerint az alkalmazás könyvtára fog törlődni, és a végfelhasználó értesítést kap arról, hogy a hozzáférését visszavonták.

### <a name="enforce-the-use-of-a-managed-browser"></a>Felügyelt böngésző használatának kényszerítése
A rendszergazdák kötelezően előírhatják az Intune Managed Browser alkalmazás használatát az Intune által felügyelt alkalmazásokban található hivatkozások megnyitásakor. Ez garantálja, hogy a vállalati környezetben megjelenő hivatkozások az Intune által felügyelt alkalmazások tartományán belül maradjanak.

### <a name="enforce-a-pin-policy"></a>PIN-kód használatára vonatkozó szabályzat alkalmazása
A rendszergazdák szabályzattal előírhatják a PIN-kód használatát az Intune által felügyelt alkalmazások indításának esetére. Ezzel ellenőrizni lehet, hogy az alkalmazást ugyanaz a felhasználó indítja-e el, mint aki eredetileg bejelentkezett egy regisztrált munkahelyi vagy iskolai fiókkal. Amikor a végfelhasználók beállítják PIN-kódjukat, az Intune App SDK az Azure Active Directory segítségével összehasonlítja a végfelhasználók hitelesítő adatait a regisztrált Intune-fiókkal.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Hitelesítő adatok kérése a felhasználóktól az alkalmazások indításához
A rendszergazdák megkövetelhetik, hogy a felhasználók az Intune által felügyelt alkalmazások indítása előtt adják meg hitelesítő adataikat. Az Intune App SDK az Azure Active Directory segítségével teszi lehetővé az egyszeri bejelentkezést, ami azt jelenti, hogy a hitelesítő adatokat elég egyszer megadni, és a későbbi bejelentkezések során a rendszer ismét azokat használja. A rendszer az [Azure Active Directoryval összevont](https://msdn.microsoft.com/library/azure/jj679342.aspx) identitáskezelési megoldások hitelesítését is támogatja.

### <a name="check-device-health-and-compliance"></a>Eszközök állapotának és megfelelőségének ellenőrzése
A rendszergazdák ellenőrizhetik az eszközök állapotát és vállalati szabályzatoknak való megfelelőségét, mielőtt a végfelhasználók hozzáférhetnének az Intune által felügyelt alkalmazásokhoz. Az iOS platformon a szabályzat ellenőrzi, hogy az eszköz jailbreakelve lett-e. Az Android platformon a szabályzat ellenőrzi, hogy az eszköz rootolt-e.

### <a name="sdk-multi-identity-support"></a>Az SDK többszörösidentitás-támogatása
A többszörös identitás támogatása lehetővé teszi a szabályzatok által felügyelt (vállalati) és a felügyelet nélküli (személyes) fiókok ugyanazon alkalmazásban való egyidejű használatát.

Például sok felhasználó konfigurál vállalati és személyes e-mail fiókot is az iOS vagy az Android rendszerhez készült Outlook alkalmazásban. Amikor a felhasználó a vállalati fiók adataihoz fér hozzá, a rendszergazdának biztosnak kell lennie abban, hogy arra alkalmazva lesz az MAM-szabályzatokon alapuló felügyelet. Ugyanakkor ha a felhasználó a személyes e-mail fiókjához fér hozzá, az adatoknak a rendszergazda felügyeletén kívül kell esniük. A Microsoft Intune ezt úgy éri el, hogy a felügyeleti szabályzatot az alkalmazásban csak a vállalati fiókra alkalmazza. A többszörös identitás támogatása megoldást kínál arra az adatvédelmi problémára, amellyel a szervezetek a személyes és munkahelyi fiókokat egyaránt támogató alkalmazások és eszközök használata során szembesülnek.

* **A többszörös identitás támogatásának módja:** A Microsoft Intune APP SDK API-jai lehetővé teszik egy egyszerű felhasználónév (UPN) megadását meghatározott – például vágólapalapú – adatműveletekhez, valamit fájlműveletekhez. Az SDK ellenőrzi, hogy a híváshoz használt UPN egyezik-e az eszköznek a Microsoft Intune szolgáltatásban való regisztrációjához használt UPN-nel. Ha az UPN-ek egyeznek, a hívást vállalati adatokra vonatkozó hívásként kezeli a rendszer, és gondoskodik az adatok védelméről. Ha az UPN-ek nem egyeznek, a rendszer a hívást személyes adatokra vonatkozó hívásként kezeli, és nem alkalmaz adatvédelmet.

### <a name="app-management-without-device-enrollment"></a>Alkalmazásfelügyelet eszközregisztráció nélkül

>[!IMPORTANT]
>Az Intune mobileszköz-felügyeleti funkciójának az eszköz regisztrációja nélküli használata egyelőre csak az Intune App SDK iOS-hez készült verziójával érhető el. 


A saját eszközt használó felhasználók sok esetben anélkül szeretnének vállalati adatokat megtekinteni és használni, hogy eszközüket mobileszköz-felügyeleti (MDM) termékben kellene regisztrálniuk. Az MDM-alapú regisztrációhoz globális irányítás szükséges az eszköz felett, a felhasználók pedig sok esetben nem szívesen biztosítanak saját eszközük felett ilyen mértékű irányítást a vállalatnak.

A regisztráció nélküli eszközfelügyelettel a Microsoft Intune szolgáltatás közvetlenül az alkalmazásokra alkalmazhat MAM-szabályzatokat, mindehhez nincs szüksége MDM-csatornára. Mivel nincs szükség MDM-csatornára, MDM-regisztráció sem szükséges.



<!--HONumber=Dec16_HO2-->


