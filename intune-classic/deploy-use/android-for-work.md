---
title: "Az Android for Work áttekintése | Microsoft Docs"
description: "Az Intune az Android for Work felügyeletével további felügyeleti lehetőségeket és adatvédelmet biztosít, amikor a felhasználók Android-eszközt használnak munkavégzésre."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: b5651e311bc3cd6619f9d7fd8782de4d5db4630c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="manage-android-for-work-devices-with-intune"></a>Az Android for Work-eszközök felügyelete az Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Android for Work azon, Android-eszközökhöz készült funkciók és szolgáltatások együttese, amelyek elkülönítik a személyes alkalmazásokat és adatokat a munkahelyi alkalmazásokat és adatokat tartalmazó munkahelyi profiltól. Az Android for Work további felügyeleti lehetőségeket és adatvédelmet biztosít, amikor a felhasználók Android-eszközt használnak munkavégzésre. Az Intune-nal úgy telepítheti az alkalmazásokat és a vállalati erőforrásokat az Android for Work-eszközökre, hogy elkülöníti egymástól a munkához kapcsolódó és a személyes adatokat. A sikeres telepítést követően az alkalmazások és az általuk használt adatok kizárólag az Android for Work-környezetben lesznek elérhetők az eszközön.

## <a name="supported-devices"></a>Támogatott eszközök

Az Android for Work számos felügyeleti funkciója az újabb Android operációs rendszerek szolgáltatásain alapul. Az Android for Work jelenleg az Android 5.0 Lollipop és újabb rendszerű, a munkahelyi profilt támogató eszközökön használható. Az Android for Work támogatására nem képes eszközökön továbbra is az Android hagyományos felügyeleti funkciói érhetők el. Tekintse át az [Android for Work követelményeit](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Bevezetés

Az Android for Work-eszközök regisztrálása előtt el kell végeznie néhány bevezető lépést. Ide tartozik az Intune-bérlő és a Google Play for Work szolgáltatás közötti kapcsolat létrehozása. Ez a szolgáltatás szerves része az Android for Work alkalmazásterjesztési és felügyeleti folyamatának. További információk az [Android for Work regisztrálásáról](/intune-classic/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Munkahelyi profilok kezelése

Amikor az Intune használatával felügyeli az Android for Work-eszközöket, nem kell felügyelnie az egész eszközt. A felügyeleti funkciók csak az eszközön a regisztráció során létrehozott munkahelyi profilra vonatkoznak. Minden olyan alkalmazás, amelyet az Intune-nal helyez üzembe az eszközön, a munkahelyi profilba települ. A munkahelyi profilhoz tartozó alkalmazások ikonjain egy narancssárga aktatáska látható, hogy megkülönböztethesse a munkahelyi alkalmazásokat az eszközön lévő személyes alkalmazásaitól. Az Android for Work hatókörén kívül eső összes Android-alkalmazás és adat személyes marad az eszközön, és a végfelhasználó felügyelete alá tartozik. A felhasználók bármilyen alkalmazást telepíthetnek az eszköz személyes részére, a rendszergazdák pedig felügyelhetik és figyelhetik a munkahelyi profil hatókörébe eső alkalmazásokat és műveleteket.

Az Intune az Android for Work-eszközökön konfigurálható, beépített általános beállítások széles választékát kínálja. Tekintse át az [Android for Work szabályzatbeállításait](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="app-publishing-and-distribution"></a>Alkalmazások közzététele és terjesztése

A Google Play for Work szolgáltatása szerves részét képezi az Android for Work alkalmazásterjesztésének és -felügyeletének. Az Android for Work-eszközök munkahelyi profiljának részébe telepített alkalmazások a Play for Work szolgáltatásból származnak. A Play Store-ban található alkalmazások felügyeletéhez és üzembe helyezéséhez a Google-felügyeletre kijelölt céges rendszergazdai hitelesítő adatokkal kell bejelentkezni a Google Play webhelyére. Azok az alkalmazások, amelyeknél jóvá van hagyva az Android for Work rendszerre való telepítés, megjelennek az eszközök munkahelyi profiljában. Ezek az alkalmazások az Intune-konzolra szinkronizálódnak, ahol ezután telepíthetők és felügyelhetők az Intune-nal. A szervezete által fejlesztett üzletági (LOB) alkalmazásokat közzé kell tenni a Play for Work szolgáltatásban a Google androidos alkalmazás-közzétételi konzoljával. Az üzletági alkalmazásokat az androidos alkalmazás-közzétételi konzolon kell konfigurálni a szervezethez való hozzáférés korlátozásához.

Az alkalmazások felhasználói beavatkozás nélkül telepíthetők, és az sem szükséges, hogy a felhasználó engedélyezze az **ismeretlen forrásból történő telepítést**. A választható vagy elérhető alkalmazások tallózásához és telepítéséhez a felhasználók a Play for Work áruházat használhatják az eszközükön. További információk: [Alkalmazások telepítése Android for Work-eszközökre](/intune-classic/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>Alkalmazáskonfiguráció

Az Android for Work infrastruktúrát biztosít az olyan alkalmazások alkalmazáskonfigurációs értékeinek megadására, amelyek támogatják ezt a lehetőséget. A munkahelyi alkalmazások konfigurációs értékeinek megadásával biztosíthatja, hogy az alkalmazások megfelelően legyenek beállítva, amikor a felhasználók először indítják el őket. Az alkalmazáskonfiguráció támogatásához az alkalmazásfejlesztőknek úgy kell létrehozniuk az Android-alkalmazásaikat, hogy azok támogassák a felügyelt konfigurációs értékek használatát. Ilyen esetben az Intune-nal adhatja meg és alkalmazhatja ezeket a konfigurációs beállításokat. További információk az [Android for Work konfigurációs beállításairól](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>E-mail-konfiguráció

Az Android for Work nem biztosít alapértelmezett levelezőalkalmazást vagy natív e-mail-profil objektumot úgy, mint az iOS. Ehelyett e-mail-konfigurációk adhatók meg az alkalmazáskonfigurációs beállítások használatával az olyan levelezőalkalmazásokhoz, amelyek támogatják ezt. A Play Áruház két olyan Exchange ActiveSync (EAS) ügyfélalkalmazást tartalmaz, amely támogatja az Android for Work alkalmazáskonfigurációjának használatát, ez a Gmail és a Nine Work.

Az Intune konfigurációsablonokat biztosít a Gmail és a Nine Work alkalmazáshoz, ha azok munkahelyi alkalmazásként vannak felügyelve. Az alkalmazáskonfigurációs profilokat támogató más levelezőalkalmazások mobilalkalmazás-konfigurációs szabályzatokkal konfigurálhatók.

Ha Exchange ActiveSync feltételes hozzáférést használ az Android for Work-eszközökhöz, a Gmail vagy a Nine Work levelezőalkalmazást kell használnia. Szintén támogatott az Android rendszerhez készült Microsoft Outlook alkalmazás, illetve bármely olyan levelezőalkalmazás, amely modern ADAL-hitelesítést használ. [Ebből a cikkből részletesebben tájékozódhat a vállalati levelezéshez használható e-mail-profilokról](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

Az érvényben lévő alkalmazásvédelmi szabályzatokat a munkahelyi és a személyes profil egyaránt teljes mértékben támogatja. Az üzletági alkalmazásokat a https://play.google.com/apps/publish címen elérhető androidos alkalmazás-közzétételi konzolon teheti közzé. Ez a konzol tartalmaz egy beállítást, amellyel az alkalmazások privátként jelölhetők meg a szervezet számára. Tekintse át az [Android for Work-alapú megfelelőségi szabályzatok beállításait](afw-compliance-policy-settings-in-microsoft-intune.md). Az alkalmazásvédelmi szabályzatokról az [Alkalmazásszabályzatok](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) című cikkben tájékozódhat.

## <a name="vpn-profiles"></a>VPN-profilok

A VPN-támogatás az Android VPN-profilokhoz hasonlít. Ugyanazon VPN-szolgáltatók és általános beállítási lehetőségek érhetők el az eszközök az Android for Work segítségével való kezeléséhez, két eltéréssel:

-  **Munkahelyi profil hatókörű VPN** – A VPN-kapcsolatok a munkahelyi profilban üzembe helyezett alkalmazásokra vannak korlátozva. Csak az Android for Work által felügyelt alkalmazások használhatják a VPN-kapcsolatot. Az eszközön lévő saját alkalmazások nem használhatnak felügyelt VPN-kapcsolatot.

-  **Alkalmazásspecifikus VPN** – Ha egy VPN-szolgáltató támogatja az alkalmazásspecifikus VPN konfigurációját, és lehetővé teszi az alkalmazásonkénti VPN konfigurálását az Android for Work alkalmazáskonfigurációs profilján keresztül, akkor az alkalmazásspecifikus VPN konfigurálható az Intune-ban. Kérdezze meg a VPN-szolgáltatót, hogy támogatja-e ezt a funkciót. További információk a [VPN-kapcsolatok profiljairól](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Tanúsítványprofilok

Az Android for Work-eszközökön a tanúsítványprofilok ugyanazon konfigurációs beállításai érhetők el, mint az Android-felügyelet esetében. Az Android for Work kibővített tanúsítványkezelési API-kat kínál. A kibővített tanúsítványkezelés a következő funkciókat tartalmazza:

- Biztosítja, hogy a tanúsítványok telepítése csendes módban és a felhasználó számára zökkenőmentesen történjen.
-  Biztosítja a telepített tanúsítványok teljes eltávolítását, amikor az eszközöket kivonják az Intune-ból, és törlik a munkahelyi profilt.
-  Továbbfejlesztett üzenetküldést biztosít, amely tájékoztatja a felhasználókat arról, hogy az informatikai részleg telepítette és konfigurálta a tanúsítványt a felügyeleti szolgáltatáson keresztül.

További információk a [tanúsítványprofilokról](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Wi-Fi profilok

Az Android for Work által felügyelt Wi-Fi profilok el lesznek távolítva, amikor az eszközt kivonják az Intune-ból, és törlik a munkahelyi profilt. További információk a [Wi-Fi profilokról](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>További lépések
[Az Android for Work-eszközök regisztrálásának engedélyezése](/intune-classic/deploy-use/set-up-android-for-work)

[Alkalmazások telepítése Android for Work-eszközökre](/intune-classic/deploy-use/android-for-work-apps)

