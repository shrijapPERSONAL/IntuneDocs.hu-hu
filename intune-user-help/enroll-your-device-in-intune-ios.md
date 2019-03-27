---
title: A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása | Microsoft Docs
description: Ismerteti az iOS-eszközök Intune-felügyelet alá helyezését
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490642"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása  

Regisztrálja iOS-eszközét az Intune Céges portál alkalmazással, hogy biztonságos hozzáférést kapjon vállalata levelezéséhez, fájljaihoz és alkalmazásaihoz.

Szellemi tulajdont képező adatokat az vállalati vagy személyes eszközökről férjenek hozzá, akkor kell az eszköz felügyelt. Miután az eszköz felügyelete, a szervezet rendeli szabályzatokat és alkalmazásokat az eszközre egy mobileszköz-felügyelet (MDM) szolgáltató, például az Intune segítségével. 

Ahhoz, hogy eszközéről folyamatosan hozzáférjen a munkahelyi vagy iskolai információkhoz, eszközét a vállalat által előnyben részesített beállításoknak megfelelően kell konfigurálnia. Ez a cikk ismerteti a vállalati portál használatával a regisztrálás eszközt, és a szervezet követelmények karbantartása. 

> [!NOTE]
> Ha a vállalati e-maileket a Mail alkalmazással próbálta elérni, és kapott egy felszólítást, hogy helyezze felügyelet alá az eszközét, akkor a megfelelő helyen jár. Ahhoz, hogy iOS-eszközén is hozzá tudjon férni a céges e-mailekhez és más erőforrásokhoz, kövesse az alábbi útmutatót.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Ami a Céges portál alkalmazástól elvárható  

### <a name="security"></a>Biztonság  
Első beállítása során az alkalmazás megköveteli, hogy hitelesítse magát vállalatánál. Ez után tájékoztatja az összes eszközbeállításról, amelyeket frissítenie kell. A vállalatok gyakran megadják például a jelszavak minimális vagy maximális karakterszámát, és ezt Önnek be kell tartania.     

### <a name="protection"></a>Protection  
Eszköze regisztrálása után a Céges portál alkalmazás folyamatosan gondoskodik az eszköz védelméről. Ha például nem megbízható forrásból telepít valamit, az alkalmazás riasztást küld Önnek, és olykor meg is vonja a vállalati adatokhoz való hozzáférést. Ehhez hasonló szabályzat gyakori a szervezetekben, és milyen gyakran van szükség, hogy távolítsa el a nem megbízható alkalmazás, mielőtt újra hozzáférést kaphatnak.  

### <a name="setting-notifications"></a>Értesítések beállítása  
Ha a regisztráció után a vállalat új biztonsági követelményt, például többtényezős hitelesítést vezet be, a Céges portál alkalmazás értesíti Önt. Lehetősége lesz módosítani beállításait, hogy továbbra is dolgozhasson az eszközéről.  

További információk a regisztrációval kapcsolatban: [Mi történik a Céges portál alkalmazás telepítésekor és az eszköz regisztrálásakor?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios)  

## <a name="enroll-your-ios-device"></a>IOS-eszköz regisztrálása   

> [!IMPORTANT]
> Ebben a szakaszban a képernyőképek a élmény iOS-verziót futtató 12,1 és a korábbi eszközök megjelenítéséhez. Adott esetben bővítettük utasításokat az adott IOS-es verzióra 12.2 és újabb verziók. Ha azt tapasztalja, hogy a felhasználói élmény eltér a képernyőképek látható, tekintse meg a 12.2 utasításokat.      

Nyissa meg az App Store áruházból, töltse le és telepítse a [Intune vállalati portál alkalmazás](install-and-sign-in-to-the-intune-company-portal-app-ios.md) az eszközre. A beléptetés során is szüksége lesz egy Wi-Fi-kapcsolat és a Safari való hozzáférést. 

Ha felfüggeszti a regisztráció során több percig, előfordulhat, hogy zárja be az az alkalmazás, vagy a telepítő befejezése. Ha ez történik, nyissa meg a céges portál alkalmazást, és próbálkozzon újra.  

1. Nyissa meg a vállalati portálon, és jelentkezzen be munkahelyi vagy iskolai fiókjával. 

    ![Példa Képernyőkép a céges portál alkalmazást, jelentkezzen be.](./media/ios-01-cp-enroll-1903.PNG)  

2. Amikor a rendszer kéri a vállalati portál értesítések fogadása, koppintson **engedélyezése.** Céges portál értesítéseket riasztást küldjön, ha például az eszköz beállításait frissíteni kell kell használja. 

    ![Példa Képernyőkép a céges portál kezdőlapjára, "Értesítések" parancssort.](./media/ios-04-cp-enroll-1903.PNG)  

3. Az a **hozzáférés beállítása** képernyőn válassza ki **megkezdéséhez.**  

     ![Példa képernyőfelvétel a vállalati portált, "Hozzáférés beállítása" képernyő.](./media/ios-05-cp-enroll-1903.PNG)  

4. Olvassa végig az eszközadatokat a szervezet láthat és mit nem listája. [Ez a témakör további részleteit](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) keresztül tekintheti meg a **további** hivatkozásra. Ha elkészült, koppintson **Folytatás**.  

    ![Példa Képernyőkép a céges portál alkalmazás, "Mi szervezetem látható", a Folytatás gombra.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. A **mit tartogat a jövő?** képernyő a hátralévő lépéseket foglalja össze. Ezeket a lépéseket az IOS-es verziójától függően eltérő lehet. 
    * **iOS 12.2 és újabb verziók**: a felhasználói élmény inkább előfordulhat, hogy:  

        a. **Lehetővé teszi a felügyeleti profil letöltése**: A böngészőben nyissa meg a céges portál webhelyen, és kérni fogja, hogy engedélyezze a letöltést. A letöltés menti a rendszer a gépház alkalmazásban.  

        b. **Nyissa meg a beállítások alkalmazást, és telepítse a profilt**: Szüksége lesz a gépház alkalmazás megnyitásához, és a felügyeleti profil telepítésére.  

        c. **Térjen vissza a céges portál alkalmazás**: Térjen vissza a céges portál alkalmazás a telepítés végrehajtásához kell.  

    Ha készen áll a felügyeleti profil letöltéséhez, koppintson **Folytatás**.  

6. A Safari megnyitja a vállalati portál webhelyen. Ha a konfigurációs profil letöltéséhez kéri, koppintson **engedélyezése**.  
    * **iOS 12.2 és újabb verziók**: Várjon, amíg befejeződik a Safari böngészőt, és koppintson a letöltés a profil **kész**. Nyissa meg a **beállítások** alkalmazást az eszközön.  

    > [!IMPORTANT]
    > Akkor be kell lépnie a **beállítások** alkalmazást, és 8 perccel töltse le a profil telepítése. Ha nem, akkor a profil eltávolításra kerül, és indítsa újra a regisztrációs kell. 

7. Az a **beállítások** alkalmazást, koppintson **letöltött profil telepítése** > **telepítése**. Ha **letöltött profil telepítése** nem jelennek meg, nyissa meg **általános** > **profilok**. Ha továbbra sem látja a profil, szükség lehet töltse le újból.  

    ![A beállítások alkalmazás képernyőképet letöltött profil telepítése a beállítást, a legutóbb letöltött profilt jelző piros jelvény különbözteti.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. Ha a rendszer kéri, adja meg az eszköz jelszavát. Koppintson a **telepítése**.      

9. A következő képernyőn az eszközfelügyeleti szabványos rendszer figyelmeztetést. A szervezet láthat és mit nem láthat az eszközén további tudnivalókért olvassa el a megfelelő [Intune docs-cikk](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Koppintson a telepítés folytatásához **telepítése**. Ha a Távfelügyelet megbízhatóságának beállítása kéri, koppintson a **megbízhatósági**.  

    ![Gépház alkalmazás, a standard szintű rendszer figyelmeztetési képernyő a legfelső szintű tanúsítvány és a mobileszköz-kezelés képernyőképet.](./media/ios-15-cp-enroll-1903.PNG)  

10. Koppintson a telepítés befejezése után **kész**. Győződjön meg arról, hogy a profil telepítése, keresse fel a **profilok és Eszközfelügyelet** beállításait. Megtekintheti a profil alatt felsorolt **mobileszköz-kezelés**.   

    ![Példa Képernyőkép a beállítások alkalmazást, profilok és Eszközfelügyelet beállításait, a felügyeleti profil megjelenítése.](./media/ios-00-cp-enroll-1903.PNG)  


11. Lépjen vissza a **céges portál** alkalmazást. Céges portál elkezdi szinkronizálása, és konfigurálja az eszközt. Céges portál kérheti, hogy további eszközbeállítások frissítése. Ha azt, koppintson **Folytatás**.

    ![Vállalati portált, "Hozzáférés beállítása" képernyő, és a követelmény beállítás melletti sárga háromszög képernyőképet.](./media/ios-12-cp-enroll-1903.PNG)  

12. Tudni fogja, hogy a telepítés befejeződött, ha a listában szereplő összes zöld körön megjelenítése. Koppintson a **Kész** gombra.  
    
    ![Példaként szolgáló képernyőképen a vállalati portál "készen vagyunk!" az összes zöld körök megjelenítő képernyő.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Ha a szervezet figyeli a hang- és korlátozások, vagy a vállalat által birtokolt eszközt biztosít, lehetséges, hogy néhány további lépésre. Ha az kéri, hogy telepítse a **Datalert** alkalmazás, lásd: [regisztrálja az eszközt a távközlésiköltség-kezelőben](enroll-your-device-with-telecom-expense-management-ios.md). Ha a szervezet Apple Device Enrollment Program része, ismerje meg, [a vállalat által birtokolt eszközök regisztrálási módjának](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>További lépések  
Munkahelyi és iskolai segítségével alkalmazásokat kereshet. Ismerje meg, [hogyan az alkalmazások rendelkezésre álljanak](use-managed-apps-on-your-device-ios.md) Önnek a céges portálon keresztül.  

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).  
