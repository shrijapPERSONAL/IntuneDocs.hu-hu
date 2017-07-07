---
title: "A Lookout-integráció hibaelhárítása"
description: "Ez a témakör a Lookout-integráció leggyakoribb problémáinak hibaelhárítását ismerteti"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cd3c2809161aa438eb7aef91a65d68cb0f657607
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="troubleshoot-lookout-integration-with-intune"></a>A Lookout Intune-nal való integrációjának hibaelhárítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör ismertet néhány gyakori problémát, amely a Lookout mobilfenyegetések elleni védelem (MTP) beállításával kapcsolatban merülhet fel.

**Bejelentkezési hibák**

## <a name="403-errors"></a>403-as hibák
A [Lookout MTP-konzolra](https://aad.lookout.com) való bejelentkezéskor a következő 403-as hibaüzenet jelenik meg: **Ön nem jogosult hozzáférni a szolgáltatáshoz** Erre abban az esetben kerülhet sor, ha az Ön által megadott felhasználónév nem tagja a Lookout MTP eléréséhez konfigurált Azure Active Directory (AD) csoportnak.

A Lookout MTP csak konfigurált Azure AD-csoportból engedélyezi a felhasználóknak a szolgáltatás elérését. Ha szeretné megtudni, hogy melyik csoporthoz állítottak be Lookout MTP-hozzáférést, forduljon a Lookout támogatási csapatához.

* E-mail: enterprisesupport@lookout.com
* Jelentkezzen be az [MTP-konzolon](http://aad.lookout.com) és keresse meg a **Támogatás** modult.
* A https://enterprise.support.lookout.com/hc/requests webhelyen nyújtson be támogatási kérést.

## <a name="unable-to-sign-in"></a>Ha nem tud bejelentkezni
Az alábbi hibát látja, ha az Azure AD globális rendszergazdája nem fogadta el a kezdeti Lookout-telepítést.

![képernyőfelvétel, amelyen a Lookout bejelentkezési képernyője bejelentkezési hibát mutat](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

A probléma megoldásához a globális rendszergazda jelentkezzen be a https://aad.lookout.com/les?action=consent oldalon és fogadja el a telepítés indításáról szóló kérést. Ezzel kapcsolatban bővebb információt a [Lookout MTP-előfizetés beállítása](../deploy-use/setup-your-lookout-mtd-subscription.md) című témakörben talál

**Eszközállapottal kapcsolatos problémák**

## <a name="device-missing-from-lookout-device-list"></a>Hiányzik egy eszköz a Lookout eszközlistájáról

Ez az alábbi esetek valamelyikében fordulhat elő:
* Az eszköz tulajdonosa nem tagja a **Lookout MTP-konzolon** megadott **Regisztrációs csoportnak**.  A [Lookout-konzolon](http://aad.lookout.com) lépjen a **System** (Rendszer)  > **Intune Connector** (Intune-összekötő) > **Enrollment Management** (Regisztráció kezelése) pontra.  Tekintse át a regisztrációhoz konfigurált Azure AD-csoportokat, és ellenőrizze, hogy a felhasználó tagja-e az egyik Azure AD-csoportnak.  Miután hozzáadta a felhasználót a regisztrációs csoporthoz, a beállított lekérdezési időköz elteltéig tarthat (ami alapértelmezés szerint 5 perc), amíg az eszköz megjelenik a Lookout MTP-konzol **Devices** (Eszközök) moduljában.
* Ha az eszközt nem támogatja a Lookout MTP.  A nem támogatott eszközök a Lookout MTP-konzolon az összekötő beállításainak **Kezelt eszközök** részében jelennek meg.

### <a name="device-reported-as-pending"></a>**Függőben lévő** állapotúként jelentett eszköz

Az eszköz **függőben lévőként** jelenik meg, ha végfelhasználó még nem nyitotta meg a Lookout for Work alkalmazást, és nem koppintott az **Aktiválás** gombra. Ha továbbiakat szeretne megtudni az eszköz Lookout for Work alkalmazással való aktiválásáról, olvassa el [A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) vagy [A rendszer felszólítja a Lookout for Work telepítésére az iOS-eszközön](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios) című szakaszt

## <a name="device-whos-active-but-has-no-device-id"></a>Aktív, de eszközazonosító nélküli eszköz
Ha a Lookout MTP-konzolon egy aktív eszköz nem rendelkezik eszközazonosítóval, akkor az eszköz felhasználója nem tartozik a regisztrációs csoporthoz. Az eszköz abban az esetben kerülhet ebbe az állapotba, ha az eszköz tulajdonosát eltávolították a regisztrációs csoportból, vagy ha eltávolították a regisztrációs csoportot.

A [Lookout-konzolon](http://aad.lookout.com) lépjen a **System** (Rendszer)  > **Intune Connector** (Intune-összekötő) > **Enrollment** (Regisztráció) pontra.  Tekintse át az Azure AD-csoportokat, és ellenőrizze, hogy a felhasználó tagja-e az egyik Azure AD-csoportnak.

Amíg az eszköz ebben az állapotban van, a Lookout továbbra is értesíti a felhasználót az észlelt fenyegetésekről, de nem küld fenyegetés-információkat az Intune-hoz.

## <a name="device-reported-as-disconnected"></a>**Leválasztott** állapotúként jelentett eszköz

A **Leválasztott** állapot azt jelenti, hogy a beállított időközön belül, ami alapértelmezés szerint legalább 7 nap, de legfeljebb 30 nap, az eszköz nem volt szinkronizálva a Lookout MTP-vel. A Céges portál vagy a Lookout for Work alkalmazás hiányzik az eszközről. A probléma megoldásához újra kell telepíteni ezeket az alkalmazásokat. Amikor a felhasználó megnyitja és aktiválja a Lookout for Work alkalmazást, az eszköz újraszinkronizálja magát a Lookout MTP-vel és az Intune-nal.

### <a name="forcing-a-device-sync"></a>Eszköz szinkronizálásának kényszerítése
A Lookout MTP-konzol **Eszközök** moduljából a rendszergazda kiválaszthatja és törölheti az eszközt.   Amikor a felhasználó legközelebb megnyitja a Lookout for Work alkalmazást és az **Aktiválás** elemre koppint, az eszköz teljes újraszinkronizálást hajt végre.

## <a name="device-has-a-new-user"></a>Az eszköznek új felhasználója van
Végre kell hajtani az eszköz adatainak teljes törlést, és meg kell kérni az új felhasználót, hogy regisztráljon.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza ki az eszközt, kattintson a jobb egérgombbal, majd válassza a **Kivonás/Teljes törlés** lehetőséget az eszköz felügyelet alól való kivonásához. Kivonása után törölheti az eszközt.

![képernyőfelvétel az Intune felügyeleti konzolon megjelenő kivonás/teljes törlés lehetőségről](../media/mtp/mtp-retire-device-intune-console.png)

Megnyithatja a **Devices** (Eszközök) modult a [Lookout-konzolon](http://aad.lookout.com) is, és választhatja a **Delete** (Törlés) lehetőséget.

Amennyiben az új felhasználó tagja valamelyik Lookout MTP-hez tartozó regisztrációs csoportnak, az eszköz megjelenik, miután az Azure AD társítja azt az új felhasználóval.

## <a name="compliance-remediation-workflows"></a>Megfelelőség-helyreállítási munkafolyamatok
- [A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön]( http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)
- [El kell hárítania egy fenyegetést, amit a Lookout for Work talált az Android-eszközön](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [El kell hárítania egy fenyegetést, amit a Lookout for Work talált az iOS-eszközön](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>További információ
[Az előfizetés konfigurálása a Lookout MTP használatához](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)
