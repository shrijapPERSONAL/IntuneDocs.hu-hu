---
title: "iOS-alkalmazások közti adatátvitel kezelése"
description: "Olvassa el ezt a témakört az iOS Megnyitás a követezőben funkciója használatának, valamint az alkalmazások közötti adatátvitel kezeléséhez szükséges mobilalkalmazás-kezelési szabályzatok megismeréséhez."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6314f6b13ec7fa23c0b3b46ecd3418a75d581db1
ms.sourcegitcommit: abd8f9f62751e098f3f16b5b7de7eb006b7510e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/20/2017
---
# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>iOS-alkalmazások közti adatátvitel felügyelete a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>IOS-alkalmazások felügyelete
A vállalati adatok védelmébe tartozik annak biztosítása, hogy csak a vállalat által felügyelt alkalmazásokkal lehessen fájlokat átvinni.  Az iOS-alkalmazásokat az alábbi módokon felügyelheti:

-   A vállalati adatok elvesztésének megakadályozása az alkalmazások számára konfigurált alkalmazásvédelmi szabályzatokkal. Az ilyen alkalmazásokat **szabályzattal felügyelt** alkalmazásoknak nevezzük.

-   Az **MDM-csatornán** keresztül is telepíthet és felügyelhet alkalmazásokat.  Ehhez az eszközöket az MDM-megoldásba kell regisztrálni. Ezek **házirenddel felügyelt** alkalmazások vagy más felügyelt alkalmazások is lehetnek.

Az iOS-eszközök **Megnyitási engedélyek felügyelete** szolgáltatásával a fájlátvitel az **MDM-csatornával** telepített alkalmazásokra korlátozható. A Megnyitási engedélyek felügyeletének korlátozásai a konfiguráció beállításaiban adhatók meg, és a mobileszköz-kezelési megoldás használatával telepíthetők.  Amikor a felhasználó telepíti a központilag telepített alkalmazást, a rendszer alkalmazza a beállított korlátozásokat.

##  <a name="manage-data-transfer-between-ios-apps"></a>iOS-alkalmazások közti adatátvitel kezelése
Az alkalmazásvédelmi szabályzatok az iOS **Megnyitási engedélyek felügyelete** szolgáltatásával együtt használhatók a vállalati adatok védelméhez, a következő módokon:

-   **Alkalmazottak tulajdonában lévő, mobileszköz-kezelési megoldás által nem kezelt eszközök:** az [alkalmazásvédelmi szabályzat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) beállításait beállíthatja a következőre: **Az alkalmazás átadhat adatokat házirend által felügyelt alkalmazásoknak**. Ha a végfelhasználó nem házirenddel felügyelt alkalmazásban nyit meg egy védett fájlt, a fájl nem olvasható.

-   **Az Intune által felügyelt eszközök:** az Intune-ban regisztrált eszközök esetén az alkalmazásvédelmi szabályzatokkal rendelkező és az Intune használatával telepített egyéb felügyelt iOS-alkalmazások közötti adatátvitel automatikusan engedélyezett. Az alkalmazásvédelmi szabályzatokkal rendelkező alkalmazások közötti adatátvitel engedélyezéséhez aktiválja **Az alkalmazás átadhat adatokat szabályzat által felügyelt alkalmazásoknak** beállítást. Az Intune-nal telepített alkalmazások között a **Megnyitási engedélyek felügyelete** funkcióval vezérelhető az adatátvitel.   

-   **Külső MDM-megoldás által felügyelt eszközök:** Az adatátvitel a felügyelt alkalmazásokra korlátozható az IOS **Megnyitási engedélyek felügyelete** funkciójával.
Annak biztosításához, hogy a harmadik féltől származó MDM megoldás segítségével központilag telepített alkalmazások is társítva legyenek az Intune-ban beállított alkalmazásvédelmi szabályzatokhoz, konfigurálnia kell a felhasználói UPN-beállítást, [A felhasználói UPN-beállítás konfigurálása](#configure-user-upn-setting-for-third-party-emm) című cikkben ismertetett lépések szerint.  Ha az alkalmazásokat a felhasználói UPN-beállítással telepítik, akkor az alkalmazásvédelmi szabályzatok érvénybe lépnek az alkalmazásra vonatkozóan, amikor a végfelhasználó a munkahelyi fiókjával jelentkezik be.

> [!IMPORTANT]
> A felhasználói UPN-beállításra csak a külső MDM által felügyelt eszközökre telepített alkalmazások esetén van szükség.  Az Intune-nal felügyelt eszközök esetében erre a beállításra nincs szükség.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Felhasználói UPN-beállítás konfigurálása külső EMM-megoldáshoz
A felhasználó UPN beállítását **kötelező** megadni olyan eszközök esetében, amelyeket küldő EMM-megoldás felügyel. Az alább leírt eljárás egy általános módszer az UPN-beállítás és az eredményül kapott végfelhasználói élmény konfigurálásához:


1.  Az Azure Portalon [konfiguráljon alkalmazásvédelmi szabályzatot](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) az iOS platformra. A vállalati igényeknek megfelelően konfigurálja a szabályzat beállításait, majd válassza ki az alkalmazásokat, amelyeknek ezzel a szabályzattal kell rendelkezniük.

2.  A felügyelni kívánt alkalmazásokat és az e-mail-profilt telepítse **saját külső MDM-megoldásával** az alábbi, általánosságban ismertetett lépések alapján. Ennek módjával az 1. példa is foglalkozik.

  1.  Telepítse az alkalmazást a következő alkalmazáskonfigurációs beállításokkal:

      **kulcs** = IntuneMAMUPN, **érték** = <username@company.com>

      Példa: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Telepítse a regisztrált eszközökre a „Megnyitási engedélyek felügyelete” szabályzatot a külső MDM-szolgáltató segítségével.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>1. példa: A rendszergazda teendői külső MDM-konzolon

1. Nyissa meg a külső MDM-szolgáltató felügyeleti konzolját. Nyissa meg a konzolnak azt a szakaszát, ahol a regisztrált iOS-eszközökre érvényes alkalmazáskonfigurációs beállításokat adja meg.

2. Az alkalmazások konfigurációjának megadására szolgáló szakaszban adja meg a következő beállítást:

  **kulcs** = IntuneMAMUPN, **érték** = <username@company.com>

  A kulcs-érték pár pontos szintaxisa függ a külső MDM-szolgáltatótól. Az alábbi táblázat külső MDM-szolgáltatókra és az esetükben megadandó kulcs-érték párra közöl példákat.

|Külső MDM-szolgáltató| Konfigurációs kulcs | Érték típusa | Konfigurációs érték|
| ------- | ---- | ---- | ---- |
| VMware AirWatch | IntuneMAMUPN | Karakterlánc | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Karakterlánc | $EMAIL$ **vagy** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Karakterlánc | ${userUPN} **vagy** ${userEmailAddress} |
| ManageEngine Mobile Device Manager | IntuneMAMUPN | Karakterlánc | %upn% |

### <a name="example-2-end-user-experience"></a>2. példa: A végfelhasználó teendői

1.  A végfelhasználó telepíti a Microsoft Word alkalmazást az eszközre.

2.  A végfelhasználó elindítja a felügyelt natív levelezőalkalmazást az e-mailjei eléréséhez.

3.  A végfelhasználó megpróbál megnyitni egy dokumentumot egy natív e-mailből a Microsoft Word programban.

4.  A Word elindulásakor a rendszer felkéri a végfelhasználót, hogy jelentkezzen be a munkahelyi fiókjával.  Ennek a végfelhasználó által, kérésre megadott munkahelyi fióknak meg kell egyeznie a Microsoft Word alkalmazás számára az alkalmazás konfigurációs beállításaiban megadott fiókkal.

    > [!NOTE]
    > A végfelhasználó más személyes fiókokat is hozzáadhat a Wordhöz, hogy elvégezhesse személyes munkáját. Így az alkalmazásvédelmi szabályzatok nem vonatkoznak rá, amikor személyes célra használja a Word alkalmazást.

5.  Ha sikeres a bejelentkezés, a rendszer érvényesíti az alkalmazásvédelmi szabályzat beállításait a Word alkalmazásra.

6.  Most, hogy a fájlátvitel sikerült, a dokumentum vállalati identitásként van megjelölve az alkalmazásban. Ezenkívül a rendszer munkahelyi környezetben kezeli a fájlt, és ennek megfelelően alkalmazza a szabályzatbeállításokat.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Külső EMM-megoldásban megadott UPN-beállítás ellenőrzése

A felhasználói UPN-beállítás konfigurálása után ellenőriznie kell, hogy az iOS-alkalmazás megkapja és betartja-e az Intune alkalmazásvédelmi szabályzatát.

Az **alkalmazás PIN-kódjának megadását megkövetelő** házirendbeállítást például egyszerű vizuálisan tesztelni az alkalmazáson. Ha a házirend-beállítás értéke **Igen**, a rendszernek kérnie kell a végfelhasználótól egy PIN-kód megadását, amikor megpróbálja elérni a vállalat adatait.

Először [hozzon létre és telepítsen egy alkalmazásvédelmi szabályzatot](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) az iOS-alkalmazás számára. Az alkalmazásvédelmi szabályzat teszteléséről [Az alkalmazásvédelmi szabályzatok ellenőrzése](validate-mobile-application-management.md) című témakör nyújt tájékoztatást.



### <a name="see-also"></a>További információ
[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal a Microsoft Intune segítségével](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
