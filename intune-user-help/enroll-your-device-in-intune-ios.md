---
title: A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása | Microsoft Docs
description: Ismerteti az iOS-eszközök Intune-felügyelet alá helyezését
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7db319586b9375b8c88f177197e2fdf15378ab4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "55847301"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása

Regisztrálja iOS-eszközét az Intune Céges portál alkalmazással, hogy biztonságos hozzáférést kapjon vállalata levelezéséhez, fájljaihoz és alkalmazásaihoz.

Mielőtt jogosulttá válna szellemi tulajdont képező adatokhoz való hozzáférésre vállalati vagy személyes eszközről, felügyelet alá kell helyeznie eszközét. A már felügyelt eszközökhöz a vállalat szabályzatokat és alkalmazásokat fog hozzárendelni a mobileszköz-felügyeleti (MDM) szolgáltatón keresztül. 

Ahhoz, hogy eszközéről folyamatosan hozzáférjen a munkahelyi vagy iskolai információkhoz, eszközét a vállalat által előnyben részesített beállításoknak megfelelően kell konfigurálnia. Ez a cikk azt írja le, hogyan segít a Céges portál az eszközök vállalati követelményeknek megfelelő regisztrálásában, konfigurálásában és karbantartásában.

> [!NOTE]
> Ha a vállalati e-maileket a Mail alkalmazással próbálta elérni, és kapott egy felszólítást, hogy helyezze felügyelet alá az eszközét, akkor a megfelelő helyen jár. Ahhoz, hogy iOS-eszközén is hozzá tudjon férni a céges e-mailekhez és más erőforrásokhoz, kövesse az alábbi útmutatót.

## <a name="what-to-expect-from-the-company-portal-app"></a>Ami a Céges portál alkalmazástól elvárható

### <a name="security"></a>Biztonság
Első beállítása során az alkalmazás megköveteli, hogy hitelesítse magát vállalatánál. Ez után tájékoztatja az összes eszközbeállításról, amelyeket frissítenie kell. A vállalatok gyakran megadják például a jelszavak minimális vagy maximális karakterszámát, és ezt Önnek be kell tartania.    

### <a name="protection"></a>Protection
Eszköze regisztrálása után a Céges portál alkalmazás folyamatosan gondoskodik az eszköz védelméről. Ha például nem megbízható forrásból telepít valamit, az alkalmazás riasztást küld Önnek, és olykor meg is vonja a vállalati adatokhoz való hozzáférést. Az ehhez hasonló alkalmazásvédelmi szabályzatok gyakoriak a szervezeteknél. Gyakran megkövetelik a nem megbízható alkalmazás eltávolítását, mielőtt újból hozzáférést kapna.

### <a name="setting-notifications"></a>Értesítések beállítása
Ha a regisztráció után a vállalat új biztonsági követelményt, például többtényezős hitelesítést vezet be, a Céges portál alkalmazás értesíti Önt. Lehetősége lesz módosítani beállításait, hogy továbbra is dolgozhasson az eszközéről.  

További információk a regisztrációval kapcsolatban: [Mi történik a Céges portál alkalmazás telepítésekor és az eszköz regisztrálásakor?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios) 

## <a name="before-you-start"></a>Előkészületek

- Csak akkor kezdje meg a regisztrációt, ha egy munkamenetben végre tudja hajtani az egészet. Ha több percig is felfüggeszti, a telepítőprogram leállhat, és az egész folyamatot elölről kell kezdenie.  
- Ha a folyamat sikertelen, térjen vissza a Céges portál alkalmazásba, és próbálkozzon újra.  
- Ellenőrizze, hogy az eszközén működik-e a WiFi és a Safari.
- Töltse le és telepítse az [Intune céges portál alkalmazást](install-and-sign-in-to-the-intune-company-portal-app-ios.md).  


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Céges erőforrásokhoz történő hozzáférés beállítása a Céges portál alkalmazás használatával

|Megjelenő kép|Magyarázat|
|---|---|
|![A Céges portál bejelentkezési képernyője, alul a „Bejelentkezés” gombbal.](./media/ios-01-cp-enroll-1802.PNG)|Nyissa meg a Céges portál alkalmazást, és koppintson a **Bejelentkezés** gombra.|
|![Azure AD-bejelentkezés kérése.](./media/ios-02-cp-enroll-1802.PNG)|Adja meg a céges e-mail-címét, majd koppintson a **Következő** elemre.|
|![Azure AD-jelszó kérése.](./media/ios-03-cp-enroll-1802.PNG)|Adja meg a jelszót, majd koppintson a **Bejelentkezés** elemre.|
|![Céges erőforrások betöltése kezdőképernyő.](./media/ios-04-cp-enroll-1802.PNG)|Várja meg, amíg a képernyő betöltődik.|
|![A használati feltételek oldala.](./media/ios-05-cp-enroll-1802.PNG)|Olvassa el, majd koppintson az **Összes elfogadása** elemre a feltételek és kikötések elfogadásához.|
|![Céges hozzáférés beállítása képernyő. Az eszköz felügyeletét és beállításait most kell kialakítani.](./media/ios-06-cp-enroll-1802.PNG)|Az **Kezdés** elemre koppintva kezdje meg az eszköz alkalmassá tételét a céges erőforrásokhoz történő hozzáféréshez. Ha jelenleg nem tudja megtenni ezt, választhatja az **Elhalasztás** műveletet, de ebben az esetben nem férhet hozzá az e-mailjeihez, dokumentumaihoz, stb.|
|![Mit láthat a cégem képernyő.](./media/ios-07-cp-enroll-1802.PNG)|Az alul látható hivatkozásra kattintva **További információkat** kaphat arról, ami a cég számára látható. Ha nem kívánja megtekinteni, koppintson a **Folytatás** elemre.|
|![Következő lépések képernyő.](./media/ios-08-cp-enroll-1802.PNG)|Ez képernyő végigvezeti a beállítás folyamatának lépésein. A Safari, a Beállítások, és a Céges portál alkalmazásokat fogja használni. Koppintson a **Tovább** gombra.|
|![Képernyő betöltése, miután a „Következő lépések” képernyőn a Következő elemre koppintott.](./media/ios-09-cp-enroll-1802.PNG)|Várja meg, amíg a képernyő betöltődik.|
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-cp-sent-to-safari-1808.png)|A rendszer átirányítja Önt a Safarira, hogy felügyeleti információkat szerezzen az eszközről.|
|![A rendszer arra kéri, hogy nyissa meg a Beállítások alkalmazást.](./media/ios-8-cp-enroll-1711.PNG)|Az **Engedélyezés** elemre koppintva nyissa meg a Beállítások alkalmazást a konfigurációs profil letöltéséhez. Ezt kell telepíteni ahhoz, hogy a cége kezelhesse a vállalati információkat az eszközén.|
|![Képernyőkép a Profil telepítése képernyőről az eszközbeállításokban.](./media/ios-9-cp-enroll-1711.PNG)|Koppintson a **Telepítés** elemre.|
|![A profil modális párbeszédpaneljének telepítése a képernyő aljáról.](./media/ios-10-cp-enroll-1711.PNG)|Koppintson a **Telepítés** elemre.|
|![A profil telepítése folyamatban betöltési képernyő.](./media/ios-11-cp-enroll-1711.PNG)|Várja meg, amíg a képernyő betöltődik.|
|![Profilkezelés figyelmeztetési képernyő.](./media/ios-12-cp-enroll-1711.PNG)|Ez az Apple által írt figyelmeztetés további információt nyújt arról, hogy milyen műveleteket lehet végrehajtani a felügyelt eszközökön. Részletes tudnivalókért lásd: [Milyen adatok láthatók a cég számára](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![A rendszer arra kéri, hogy adjon megbízást a távoli felügyeletre.](./media/ios-13-cp-enroll-1711.PNG)|A **Megbízom** elemre koppintással engedélyezze cégének, hogy a vállalati információkat és beállításokat felügyelje az eszközén.|
|![Profil telepítésének befejezése képernyő.](./media/ios-14-cp-enroll-1711.PNG)|Várja meg, amíg a képernyő betöltődik.|
|![A profil telepítése megtörtént képernyő.](./media/ios-15-cp-enroll-1711.PNG)|A profilja telepítve van, hamarosan megkezdődhet az eszközén található vállalati információk és beállítások felügyelete.|
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-16-cp-enroll-1711.PNG)|A rendszer ismét átirányítja a Safarira, hogy lezárulhasson az eszköz felügyeleti információinak bekérése. |
|![A rendszer arra kéri, hogy nyissa meg a Céges portált.](./media/ios-17-cp-enroll-1711.PNG)|Koppintson a **Megnyitás** gombra.|
|![Vállalati erőforrások betöltése képernyő.](./media/ios-21-cp-enroll-1802.PNG)|Várja meg, amíg a képernyő betöltődik.|
|![Válasszon eszközkategóriát a Céges portál alkalmazásban.](./media/ios-22-cp-enroll-1802.PNG)|Válassza ki az eszköznek leginkább megfelelő kategóriát. Ez általában attól függ, hogy ki az eszköz tulajdonosa, és hogy hol található az eszköz az idő legnagyobb részében.|
|![Kategória kiválasztva.](./media/ios-23-cp-enroll-1802.PNG)||
|![Eszközfelügyelet sikeres; most frissítenie kell a beállításokat.](./media/ios-24-cp-enroll-1802.PNG)|Sikeresen felügyelet alá helyezte az eszközt. Lehet, hogy még hátravan néhány beállítás, mint például a jelszó hossza, amelyet valószínűleg frissítenie kell a cég számára. A folytatáshoz koppintson a **Folytatás** parancsra.|
|![Eszközbeállítások megerősítése.](./media/ios-25-cp-enroll-1802.PNG)|A Céges portál ellenőrzi, hogy szükség van-e valamelyik beállítás frissítésére.|
|![A beállítások ellenőrzése lezárult, az operációs rendszer verziója nem megfelelő](./media/ios-26-cp-enroll-1802.PNG)|A Céges Portál javaslatokat ad a beállításokkal kapcsolatos problémák megoldására. A problémák megoldását követően koppintson a **Beállítások ellenőrzése** elemre.|
|![Eszközbeállítások megerősítése képernyő](./media/ios-27-cp-enroll-1802.PNG)|Az eszköz ellenőrzi, hogy a beállítások elég biztonságosak-e a céges erőforrások eléréséhez.|
|![Sikeresen regisztrált és frissítette beállításait](./media/ios-28-cp-enroll-1802.PNG)|Gratulálunk! Ezzel megtörtént az eszköz Intune-beli regisztrálása.|

> [!Note]
> Már csak néhány lépést kell megtennie, hogy az eszköz teljes felügyelet alá kerüljön. További információ a [távközlésiköltség-kezelőben való regisztrációról](enroll-your-device-with-telecom-expense-management-ios.md). Ha a cége az Apple Készülékregisztrációs programját használja, további információt [itt](enroll-your-device-dep-ios.md) találhat.

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).  
