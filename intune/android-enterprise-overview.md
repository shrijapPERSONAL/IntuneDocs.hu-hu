---
title: Androidos munkahelyi profilos eszközök kezelése a Microsoft Intune-ban
titlesuffix: ''
description: A Microsoft Intune az androidos munkahely profilos eszközök felügyeletével további felügyeleti lehetőségeket és adatvédelmet biztosít, amikor a felhasználók Android-eszközt használnak munkavégzésre.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9c3184ff01252d2f53b5bfcce286df3424da23c2
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909167"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Androidos munkahelyi profilos eszközök kezelése az Intune-nal

A vállalati Android olyan funkciókat jelent, amelyekkel elkülöníthetőek a személyes alkalmazások és adatok a munkahelyi alkalmazásoktól és adatoktól. A vállalati Android további felügyeleti lehetőségeket és adatvédelmet biztosít, amikor a felhasználók Android-eszközt használnak munkavégzésre. 

## <a name="supported-devices"></a>Támogatott eszközök

A vállalati Android számos felügyeleti funkciója az újabb Android operációs rendszerek szolgáltatásain alapul. A vállalati Android támogatására nem képes eszközökön továbbra is az Android hagyományos felügyeleti funkciói érhetők el. További információt a [Vállalati Android követelményei](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) című témakörben talál.

## <a name="onboarding"></a>Bevezetés

Az androidos munkahelyi profilos eszközök regisztrálása előtt el kell végeznie néhány bevezető lépést. Ezek a lépések kapcsolatot építenek ki az Intune-bérlője és a Google Play for Work szolgáltatás között. További információt a [Regisztráció engedélyezése az androidos munkahelyi profilos eszközökhöz](android-work-profile-enroll.md) című cikkben talál.

## <a name="work-profile-management"></a>Munkahelyi profilok kezelése

Amikor az Intune használatával felügyeli az androidos munkahelyi profilos eszközöket, nem kell felügyelnie az egész eszközt. A felügyeleti funkciók csak az eszközön a regisztráció során létrehozott munkahelyi profilra vonatkoznak. Minden olyan alkalmazás, amelyet az Intune-nal helyez üzembe az eszközön, a munkahelyi profilba települ. A munkahelyi profilban megjelenő alkalmazásikonok elkülönülnek az eszközön található személyes alkalmazásoktól. A vállalati Android hatókörén kívül eső összes Android-alkalmazás és adat személyes marad az eszközön, és a végfelhasználó felügyelete alá tartozik. Az eszköz személyes részén a felhasználók bármilyen alkalmazást telepíthetnek. A rendszergazdák a munkahelyi profil hatókörébe tartozó alkalmazásokat és műveleteket felügyelhetik és figyelhetik.

Az Intune az androidos munkahelyi profilos eszközökön konfigurálható, beépített általános beállítások széles választékát kínálja. További információt az [Androidos munkahelyi profilos eszközökre vonatkozó szabályzatbeállítások](compliance-policy-create-android-for-work.md) című témakörben talál.

## <a name="app-publishing-and-distribution"></a>Alkalmazások közzététele és terjesztése

A Google Play for Work szolgáltatása szerves részét képezi a vállalati Android alkalmazásterjesztésének és -felügyeletének. Az androidos munkahelyi profilos eszközök munkahelyi profiljának részébe telepített alkalmazások mindegyike a Felügyelt Google Play szolgáltatásból származik. A Play áruházban található alkalmazások felügyeletéhez és üzembe helyezéséhez a Google-felügyeletre kijelölt céges rendszergazdai hitelesítő adatokkal kell bejelentkezni a Google Play webhelyére. Azok az alkalmazások, amelyeknél jóvá van hagyva a vállalati Android rendszerre való telepítés, megjelennek az eszközök munkahelyi profiljában. Ezek az alkalmazások az Intune-konzolra szinkronizálódnak, ahol ezután telepíthetők és felügyelhetők az Intune-nal. A cége által fejlesztett üzletági (LOB) alkalmazásokat közzé kell tenni a Felügyelt Google Play szolgáltatásban a Google androidos alkalmazás-közzétételi konzoljával. Az üzletági alkalmazásokat az androidos alkalmazás-közzétételi konzolon kell konfigurálni a szervezethez való hozzáférés korlátozásához.

Az alkalmazások felhasználói beavatkozás nélkül telepíthetők, és az sem szükséges, hogy a felhasználó engedélyezze az **ismeretlen forrásból történő telepítést**. A választható vagy elérhető alkalmazások tallózásához és telepítéséhez a felhasználók a Play for Work áruházat használhatják az eszközükön. További információt az [Alkalmazások hozzárendelése androidos munkahelyi profilos eszközökhöz az Intune-ban](apps-add-android-for-work.md) című témakörben talál.

## <a name="app-configuration"></a>Alkalmazáskonfiguráció

A vállalati Android infrastruktúrát biztosít az olyan alkalmazások alkalmazáskonfigurációs értékeinek megadására, amelyek támogatják ezt a lehetőséget. A munkahelyi alkalmazások konfigurációs értékeinek megadásával biztosíthatja, hogy az alkalmazások megfelelően legyenek beállítva, amikor a felhasználók először indítják el őket. Az alkalmazáskonfiguráció támogatásához az alkalmazásfejlesztőknek úgy kell létrehozniuk az Android-alkalmazásaikat, hogy azok támogassák a felügyelt konfigurációs értékek használatát. Ilyen esetben az Intune-nal adhatja meg és alkalmazhatja ezeket a konfigurációs beállításokat. További információt az [Alkalmazáskonfigurációs szabályzatok hozzáadása kezelt Android-eszközökhöz](app-configuration-policies-use-android.md) című témakörben talál.

## <a name="email-configuration"></a>E-mail-konfiguráció

A vállalati Android nem biztosít alapértelmezett levelezőalkalmazást vagy natív e-mail-profil objektumot úgy, mint az iOS. Ehelyett e-mail-konfigurációk adhatók meg az alkalmazáskonfigurációs beállítások használatával az olyan levelezőalkalmazásokhoz, amelyek támogatják ezt. A Play Áruház két olyan Exchange ActiveSync (EAS) ügyfélalkalmazást tartalmaz, amely támogatja a vállalati Android alkalmazáskonfigurációjának használatát, ez a Gmail és a Nine Work.

Az Intune konfigurációsablonokat biztosít a Gmail és a Nine Work alkalmazáshoz, ha azok munkahelyi alkalmazásként vannak felügyelve. Az alkalmazáskonfigurációs profilokat támogató más levelezőalkalmazások mobilalkalmazás-konfigurációs szabályzatokkal konfigurálhatók.

Ha Exchange ActiveSync feltételes hozzáférést használ az androidos munkahelyi profilos eszközökhöz, használhatja a Gmail vagy a Nine Work levelezőalkalmazást. Szintén támogatott az Android rendszerhez készült Microsoft Outlook alkalmazás, illetve bármely olyan levelezőalkalmazás, amely modern ADAL-hitelesítést használ. További információt [Az e-mail-beállítások konfigurálása a Microsoft Intune-ban](email-settings-configure.md) című témakörben talál.

## <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

Az érvényben lévő alkalmazásvédelmi szabályzatokat a munkahelyi és a személyes profil egyaránt teljes mértékben támogatja. Az üzletági alkalmazásokat a https://play.google.com/apps/publish címen elérhető androidos alkalmazás-közzétételi konzolon teheti közzé. Ez a konzol tartalmaz egy beállítást, amellyel az alkalmazások privátként jelölhetők meg a szervezet számára. További információt az [Androidos munkahelyi profilos eszközök eszközmegfelelőségi szabályzatának hozzáadása az Intune-ban](compliance-policy-create-android-for-work.md) című témakörben talál. Az alkalmazásvédelmi szabályzatok létrehozásáról általános információ: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

## <a name="vpn-profiles"></a>VPN-profilok

A VPN-támogatás az Android VPN-profilokhoz hasonlít. Ugyanazon VPN-szolgáltatók és általános beállítási lehetőségek érhetők el az eszközök a vállalati Android segítségével való kezeléséhez, két eltéréssel:

-  **Munkahelyi profil hatókörű VPN** – A VPN-kapcsolatok a munkahelyi profilban üzembe helyezett alkalmazásokra vannak korlátozva. Csak a vállalati Android által felügyelt alkalmazások használhatják a VPN-kapcsolatot. Az eszközön lévő saját alkalmazások nem használhatnak felügyelt VPN-kapcsolatot. További információt a [Vállalati Android VPN-beállításai](vpn-settings-android.md#android-work-profile-device-vpn-settings) című témakörben talál.

-  **Alkalmazásspecifikus VPN** – Az alkalmazásspecifikus VPN akkor konfigurálható az Intune-ban, ha a VPN-szolgáltató támogatja:
    - alkalmazásspecifikus VPN konfigurációja
    - alkalmazásonkénti VPN konfigurációjának lehetősége a vállalati Android alkalmazáskonfigurációs profiljával.
    További információt az [Alkalmazásonkénti VPN-profil létrehozása androidos eszközökhöz egyéni Microsoft Intune-profillal](android-pulse-secure-per-app-vpn.md) című témakörben talál.

## <a name="certificate-profiles"></a>Tanúsítványprofilok

Az androidos munkahelyi profilos eszközökön a tanúsítványprofilok ugyanazon konfigurációs beállításai érhetők el, mint az Android-felügyelet esetében. A vállalati Android kibővített tanúsítványkezelési API-kat kínál. A kibővített tanúsítványkezelés a következő funkciókat tartalmazza:

-  Biztosítja, hogy a tanúsítványok telepítése csendes módban és a felhasználó számára zökkenőmentesen történjen.
-  Biztosítja a telepített tanúsítványok eltávolítását, amikor az eszközöket kivonják az Intune-ból, és törlik a munkahelyi profilt.
-  Továbbfejlesztett üzenetküldést biztosít, amely tájékoztatja a felhasználókat arról, hogy az informatikai részleg telepítette és konfigurálta a tanúsítványt a felügyeleti szolgáltatáson keresztül.

További információt az [Eszközök tanúsítványprofiljainak konfigurálása a Microsoft Intune-ban](certificates-configure.md) című témakörben talál.

## <a name="wi-fi-profiles"></a>Wi-Fi profilok

A vállalati Android által felügyelt Wi-Fi profilok el lesznek távolítva, amikor az eszközt kivonják az Intune-ból, és törlik a munkahelyi profilt. További információt [A Wi-Fi-beállítások konfigurálása a Microsoft Intune-ban](wi-fi-settings-configure.md) című témakörben talál.

## <a name="next-steps"></a>További lépések
- [Androidos eszközök regisztrálása](android-enroll.md)
- [Alkalmazások hozzárendelése androidos munkahelyi profilos eszközökhöz az Intune-ban](apps-add-android-for-work.md)