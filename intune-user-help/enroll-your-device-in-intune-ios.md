---
title: A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása | Microsoft Docs
description: Ismerteti az iOS-eszközök Intune-felügyelet alá helyezését
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
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
ms.openlocfilehash: 4c8dfdea552d035c036828bfd2e6695cc5e4cb7b
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402735"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>A céges erőforrásokhoz iOS-eszközzel történő hozzáférés beállítása  

Regisztrálja iOS-eszközét az Intune Céges portál alkalmazással, hogy biztonságos hozzáférést kapjon vállalata levelezéséhez, fájljaihoz és alkalmazásaihoz.

Miután az eszköz regisztrálva van, akkor *felügyelt*. A szervezet rendelhet a szabályzatokat és alkalmazásokat az eszközre egy mobileszköz-felügyelet (MDM) szolgáltató, például az Intune segítségével.  

A munkahelyi vagy iskolai adatokat az eszközről való hozzáférés fenntartása kell egyeznie a kívánt beállításokat a szervezet az eszköz konfigurálása. Ez a cikk ismerteti a vállalati portál használatával a regisztrálás eszközt, és a szervezet követelmények karbantartása.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Ha a vállalati e-maileket a Mail alkalmazással próbálta elérni, és kapott egy felszólítást, hogy helyezze felügyelet alá az eszközét, akkor a megfelelő helyen jár. Ahhoz, hogy iOS-eszközén is hozzá tudjon férni a céges e-mailekhez és más erőforrásokhoz, kövesse az alábbi útmutatót.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Ami a Céges portál alkalmazástól elvárható  

### <a name="security"></a>Biztonság  
Első beállítása során az alkalmazás megköveteli, hogy hitelesítse magát vállalatánál. Ez után tájékoztatja az összes eszközbeállításról, amelyeket frissítenie kell. A vállalatok gyakran megadják például a jelszavak minimális vagy maximális karakterszámát, és ezt Önnek be kell tartania.

### <a name="protection"></a>Protection  
Eszköze regisztrálása után a Céges portál alkalmazás folyamatosan gondoskodik az eszköz védelméről. Ha például nem megbízható forrásból telepít valamit, az alkalmazás riasztást küld Önnek, és olykor meg is vonja a vállalati adatokhoz való hozzáférést. Az ilyen típusú szabályzat gyakori a szervezetekben, és milyen gyakran van szükség, hogy távolítsa el a nem megbízható alkalmazás, mielőtt újra hozzáférést kaphatnak.  

### <a name="setting-notifications"></a>Értesítések beállítása  
Ha a regisztráció után a vállalat új biztonsági követelményt, például többtényezős hitelesítést vezet be, a Céges portál alkalmazás értesíti Önt. Lehetősége lesz módosítani beállításait, hogy továbbra is dolgozhasson az eszközéről.  

További információk a regisztrációval kapcsolatban: [Mi történik a Céges portál alkalmazás telepítésekor és az eszköz regisztrálásakor?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios)  

## <a name="enroll-your-ios-device"></a>IOS-eszköz regisztrálása  

Nyissa meg az App Store áruházból, töltse le és telepítse a [Intune vállalati portál alkalmazás](install-and-sign-in-to-the-intune-company-portal-app-ios.md) az eszközön. Is kell egy Wi-Fi-kapcsolat fenntartását, és a Safari hozzáféréssel rendelkeznek a regisztráció során. 

Felfüggesztés regisztráció során több percig, előfordulhat, hogy az alkalmazás bezárása vagy a telepítés befejezéséhez. Ha ez történik, nyissa meg a céges portál alkalmazást, és próbálkozzon újra.  

1. Nyissa meg a vállalati portálon, és jelentkezzen be munkahelyi vagy iskolai fiókjával. 

    ![Példa Képernyőkép a céges portál alkalmazást, jelentkezzen be.](./media/ios-01-cp-enroll-1904.PNG)  

2. Amikor a rendszer kéri a vállalati portál értesítések fogadása, koppintson **engedélyezése.** Céges portál értesítéseket riasztást küldjön, ha például az eszköz beállításait frissíteni kell kell használja. 

    ![Példa Képernyőkép a céges portál kezdőlapjára, "Értesítések" parancssort.](./media/ios-02-cp-enroll-1904.PNG)  

3. Az a **hozzáférés beállítása** képernyőn válassza ki **megkezdéséhez.**  

     ![Példa képernyőfelvétel a vállalati portált, "Hozzáférés beállítása" képernyő.](./media/ios-03-cp-enroll-1904.PNG)  

4. Olvassa végig az eszközadatokat a szervezet láthat és mit nem listája. Koppintson a **Folytatás**.  

5. Olvassa el az utasításokat a a **mit tartogat a jövő?** képernyő. Amikor készen áll töltse le és telepítse a felügyeleti profilt, koppintson **Folytatás**.  

 > [!IMPORTANT]
> A következő lépéseket és képernyők az IOS-es verziójától függően eltérőek lehetnek. Kövesse a lépéseket az iOS-verzió. 

6. A Safari megnyitja az eszközön a céges portál webhelyen. Ha a konfigurációs profil letöltéséhez kéri, koppintson **engedélyezése**. Ha rendszerű eszközre:  
    * iOS-es 12.2 és újabb verziók: A letöltés befejeződése után koppintson **kész.** Folytassa a 7. lépés ebben a cikkben.
    * iOS-es 12,1 és korábbi verziók: Automatikusan átirányítjuk a beállítások alkalmazásra. Ugrás a 8. lépés ebben a cikkben.  
 
    Ha véletlenül koppintson **figyelmen kívül hagyása**, frissítse az oldalt. Nyissa meg a céges portál alkalmazás felszólítja. Koppintson az alkalmazás **töltse le újból**.

  > [!NOTE]
  > Telepítenie kell a felügyeleti profil 8 perccel töltse le a következő lépésben leírtak szerint. Ha nem, akkor a profil eltávolításra kerül, és indítsa újra a regisztrációs kell.  

7. iOS-es 12.2 és később egyetlen: Amikor a rendszer kéri, nyissa meg a vállalati portálon, koppintson **nyissa meg a**. A **felügyeleti profil telepítése** képernyő a profil telepítésének lépéseit sorolja fel.

    ![Példa Képernyőkép a céges portál, a felügyeleti profil telepítése képernyőn.](./media/ios-07-cp-enroll-1904.PNG)  

8. Nyissa meg a gépház alkalmazás, és koppintson **profil letöltött**.  

    Ha **profil letöltött** nem jelennek meg, nyissa meg **általános** > **profilok**. Ha továbbra sem látja a profil, szükség lehet töltse le újból.  

    ![Példaként szolgáló képernyőképen a beállítások alkalmazás profil letölti a beállítást.](./media/ios-1904-settings-badge.PNG)  

9. Koppintson a **Telepítés** elemre.  
    
10. Adja meg az eszköz jelszavát. Koppintson a **telepítése**.    

    ![A beállítások alkalmazás, a profil telepítése képernyőn a kurzorral a példaként szolgáló képernyőképen a ** telepítés ** gombra.](./media/ios-10-cp-enroll-1904.PNG)  


11. A következő képernyőn az eszközfelügyeleti szabványos rendszer figyelmeztetést. Koppintson a telepítés folytatásához **telepítése**. Ha a Távfelügyelet megbízhatóságának beállítása kéri, koppintson **megbízhatósági**.  

    ![Gépház alkalmazás, a standard szintű rendszer figyelmeztetési képernyő a legfelső szintű tanúsítvány és a mobileszköz-kezelés képernyőképet.](./media/ios-11-cp-enroll-1904.PNG)  

12. Koppintson a telepítés befejezése után **kész**. Győződjön meg arról, hogy a profil telepítése, keresse fel a **profilok és Eszközfelügyelet** beállításait. Megtekintheti a profil alatt felsorolt **mobileszköz-kezelés**.   

    ![Példa Képernyőkép a beállítások alkalmazást, profilok és Eszközfelügyelet beállításait, a felügyeleti profil megjelenítése.](./media/ios-12-cp-enroll-1904.PNG)  

13. Térjen vissza a céges portál alkalmazás. Céges portál elkezdi szinkronizálása, és konfigurálja az eszközt. Céges portál kérheti, hogy további eszközbeállítások frissítése. Ha azt, koppintson **Folytatás**.  

    ![Vállalati portált, "Hozzáférés beállítása" képernyő, és a követelmény beállítás melletti sárga háromszög képernyőképet.](./media/ios-13-cp-enroll-1904.PNG)  

14. Tudni fogja, hogy a telepítés befejeződött, ha a listában szereplő összes zöld körön megjelenítése. Koppintson a **Kész** gombra.   
    
    ![Példaként szolgáló képernyőképen a vállalati portál "készen vagyunk!" az összes zöld körök megjelenítő képernyő.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Ha a szervezet figyeli a hang- és korlátozások, vagy a vállalat által birtokolt eszközt biztosít, lehetséges, hogy néhány további lépésre. Ha az kéri, hogy telepítse a **Datalert** alkalmazás, lásd: [regisztrálja az eszközt a távközlésiköltség-kezelőben](enroll-your-device-with-telecom-expense-management-ios.md). Ha a szervezet Apple Device Enrollment Program része, ismerje meg, [a vállalat által birtokolt eszközök regisztrálási módjának](enroll-your-device-dep-ios.md).  

## <a name="it-administrator-support"></a>Informatikai rendszergazdai támogatás  
Ha egy informatikai rendszergazdája, és futtassa problémák eszközök regisztrálásakor, [iOS-eszközregisztrációs problémák a Microsoft Intune hibaelhárítási](https://support.microsoft.com/en-us/help/4039809). Ez a cikk felsorolja a gyakori hibák, azok okok, és lépéseket a problémák megoldásához.  

## <a name="next-steps"></a>További lépések  
Munkahelyi és iskolai segítségével alkalmazásokat kereshet. Ismerje meg, [hogyan az alkalmazások rendelkezésre álljanak](use-managed-apps-on-your-device-ios.md) Önnek a céges portálon keresztül.  

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).  
