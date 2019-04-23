---
title: fájl belefoglalása
description: fájl belefoglalása
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513667"
---
Ezek a megjegyzések meg fontos információkat, amelyek segítségével előkészítése az Intune jövőbeli változtatásokat és szolgáltatásokat. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>A vállalati iOS-eszközök beállítási Asszisztenssel való hitelesítés közben az Intune vállalati portálon a regisztrációs folyamat módosítása <!-- 1927359 -->
Az iOS-eszközök Apple vállalati tulajdonú eszközök regisztrálási módszerei – az Apple Configurator, Apple üzleti vezető, az Apple School Manager vagy az Apple eszköz beléptetési Program (DEP) keresztül munkafolyamata egy közelgő változásokat használata esetén a telepítő Segéd a hitelesítéshez. Ez a változás csak a felhasználói affinitással rendelkező regisztrált eszközökre vonatkozik.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ha ez a változás bevezetési ~~március~~ április, regisztrációs profilokat az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Továbbfejlesztett munkafolyamatot az iOS-eszközök regisztrálása a fenti módszerek keresztül lesz. 

- Amikor új eszközök regisztrációja és hitelesítése a beállítási asszisztens, képes lesz-e automatikusan telepíthető a vállalati portál alkalmazás kiválasztása. A végfelhasználók már nem jelenik meg a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban.  
- A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök lépéseket kell tennie, ha azt szeretné, a feltételes hozzáférés engedélyezéséhez. Egy adott xml leküldéses le ezeket az eszközöket a vállalati portál alkalmazás-konfigurációs házirend konfigurálása kell. Ehhez irányban a blogbejegyzés, a további információk hivatkozáson találhatók. Ha elküldi a vállalati portál ezen a módon kikapcsolja, végfelhasználók számára már nem jelennek meg, a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban. 
- Után ez a változás az egyik tagján jelennek meg, ha még nem telepítette a vállalati portál alkalmazás konfigurációs profil a fent említett, és ha a vállalati portál alkalmazást az App Store áruházból, figyelemmel felhasználóknak a bejelentkezéshez, a végfelhasználók letöltése, de fog hibaüzenetet kap. Nem tudják használni az alkalmazást a feltételes hozzáférés. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha a módosított munkafolyamat használatát tervezi, szeretné frissíteni a végfelhasználói útmutató, amely szerint:

- Végfelhasználók számára már nem jelennek meg a fent említett a regisztrációs folyamat két képernyő. 
- Jelentkezzen be a vállalati portálon, hogy telepítésekor automatikusan, és ne töltse le az app store lesz szükséges. 

Ha szeretné, hozzon létre egy alkalmazáskonfigurálási szabályzat most szükség esetén ez a változás előkészítéséhez. Amikor az új munkafolyamatot vezet be, látni fogja a frissített beléptetési profilok a konzolon. Azt fogjuk is értesíti a felhasználókat a Bevezetés az üzenet központon keresztül. Ezt követően kell, hogy a végfelhasználók beléptethetik az DEP Programon keresztül és a beállítási Asszisztenssel hitelesítéséhez és a feltételes hozzáférés is használhatja a vállalati portál, hajtsa végre a műveletet.

Tekintse meg a további információk hivatkozáson erről a változásról további részletekért tegye közzé kérdéseit támogatási blogon.

#### <a name="additional-information"></a>További információ 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Tervezett módosítás: Felhasználóiélmény-frissítést az iOS-hez készült Intune vállalati portál alkalmazás
Örömmel megosztására, hogy az Intune hamarosan adunk ki az IOS-es céges portál alkalmazás egy nagyszabású felhasználóiélmény-frissítést. A frissítés egy vizuális átalakulás a kezdőlap ügyfélszolgálatnak a speciális szűrők és az alkalmazások és könyvek gyorsabb hozzáférést.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A felhasználói élmény frissítése, miközben fenntartja az IOS-es céges portál funkciókat, ügyfélszolgálatnak:
- Egy natív iOS megjelenését és működését érintő kezdőlapján 
- A tartalom listák és a keresés, szűrés a tartalomtípus (alkalmazások vagy e-könyvek) és a rendelkezésre állás (Eszközkezelés kötelező vagy elérhető legyen, regisztráció nélkül) például szűrési képességek
- E-könyvek kereshetővé
- Keresési előzmények alkalmazásokhoz és e-könyvek

Ha Ön az Apple TestFlight programjában, értesíteni fogjuk az Intune céges portál alkalmazás frissítése IOS-az előzetes verzióval kapcsolatos mikor válik elérhetővé. Ha Ön nem Apple TestFlight programjában, nincs késő regisztrálni. Regisztrálása lehetővé teszi, hogy a frissített vállalati portál alkalmazást használja, mielőtt a végfelhasználók számára elérhető. A visszajelzés közvetlenül a az Intune csapatával.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Nem kell semmit sem kell; Ezeket a változásokat egy közelgő iOS CP alkalmazás kiadásban elérhető lesz. 

#### <a name="additional-information"></a>További információ
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Jelölje be a "Szoftverfrissítések késleltetés láthatóságát" beállítást az Intune-ban 

Tudjuk, hogy mi volt a mozgó néhány beállítást a konzolon MC171466 megosztott. A márciusi frissítéssel az Intune-hoz teljes mértékben eltávolítjuk a "Szoftver késleltetés látható-e frissítések" beállítás az IOS-es frissítési szabályzat panelen. Ez nem módosítja a alkalmazni az ütemezett szoftverfrissítések módon, de ez hatással lehet a mennyi ideig késik egy olyan frissítés látható-e a végfelhasználók számára. Szükség lehet a március vége előtt művelet végrehajtása, ha ezt a beállítást használja. 

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A február az Intune-szolgáltatásfrissítésbe követően azt láthatja, hogy a beállítás jelenik meg a szoftver frissítése panelen a házirendek frissítéséhez a konzolon és az IOS-es eszközkorlátozási profilokhoz a is. Amikor megjelenik a módosítás megjelenik a konzolon, Íme mi is kell tennie.

- A meglévő IOS-frissítési szabályzatok: Ha egyéni konfigurálva ez a beállítás az alapértelmezett értékre 30 nap, és a meglévő konfigurációk a késleltetés látható-e beállítás számára, hogy továbbra is március végén alkalmazni, hozzon létre egy új IOS-es eszközkorlátozási profilt kell. Itt a késleltetés láthatósági kell ugyanazokat az értékeket, mint a meglévő iOS-frissítési szabályzat rendelkezik, és ugyanazok a csoportok megcélozni. A március szolgáltatás frissítése után, már nem szerkesztheti ezt a beállítást meglévő iOS-frissítési szabályzatok értékeit, mivel már nem lesz látható, ezen a panelen. Ez a beállítás helyette az új profilok fogja beállítani.
  Késleltetheti számú napig az érték látható-e nem egyezik a mindkét helyen, a konfigurált egyéni beállítást értékek, a beállítás nem fog működni, késleltetés látható-e, és a végfelhasználók látni fogja a frissített saját eszközeiken, amint érhető el. Ez előfordulhat, hogy lehet csak minimális hatással van a legtöbb ügyfél számára, mert a szoftverfrissítési szabályzat panelen a többi beállítás elsőbbséget mindig végrehajtása ezzel a beállítással a konzolon keresztül.
- Az új IOS-frissítési szabályzatok: Ha meg új szabályzatokat hozhat létre a szoftverek frissítések panel az Intune-ban február szolgáltatás frissítése után, látni fogja a szürkén jelenik meg ez a beállítás. Megjelenik egy megjegyzés a konzolon, átirányítjuk az eszköz konfigurációs panelen, ha szeretné késleltetheti a frissítések láthatóságát.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Nem kell semmit, ha nem szeretné, hogy a végfelhasználók számára látható-e szoftverfrissítéseket késleltetés vagy ne használja ezt a beállítást.

Ha késleltetheti a frissítések láthatóságát, indítsa el a beállítás konfigurálásával új profilokban Eszközkorlátozások az eszközkonfiguráció panel > Általános. Ha ez a beállítás egyéni konfigurált meglévő iOS frissítési szabályzatok, hozzon létre egy új egyenértékű eszközkorlátozási profilt a "days" késleltetheti a frissítések a felhasználók számára látható-e ugyanaz az érték, miután a februári frissítés, és előtt a márciusi frissítés bevezetésekor. 

Előfordulhat, hogy szeretné frissíteni az IT Pro útmutatást, és tájékoztatja a segélyszolgálathoz.

Tekintse meg a további információt Ez a beállítás konfigurálásával kapcsolatos részletekért tegye közzé kérdéseit támogatási blogon.

#### <a name="additional-information"></a>További információ 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Tervezett módosítás: Az Intune-ban Windows 10-es e-mail profilokkal kapcsolatos közelgő javítás <!--3904031-->
Frissítjük a módon Intune írja az e-mail profilok a Windows 10 a áprilisban frissítése az Intune szolgáltatáshoz, valamint a hiba elhárításához biztosítsa az e-mail-profilok továbbra is a jövőben működéséhez a Windows 10-es verziói. Nincs művelet kell tennie a javítás telepítését követően.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ez a módosítás hatással van, a Windows 10-es e-mail-profilok használatakor
- A natív Mail-ügyfelet a Windows 10 asztali vagy
- A Windows 10 Mobile, az Outlook e-mail ügyfél

Ez érint mindkét önálló és hibrid mobileszköz-felügyeleti (MDM).

Után az április frissítése figyelhetünk meg kell újra létre kell hoznia ezeket a profilokat az Intune-konzolon (a hibrid mobileszköz-kezelés használata a Configuration Manager felügyeleti konzol).

Ha nem ad meg a művelet, a következő látni az április frissítése előtt létrehozott profilok:

- Meglévő e-mail-profilok jelennek meg az Intune-konzolon vagy a Configuration Manager felügyeleti konzolban a hibás állapotú, de a végfelhasználók továbbra is hozzáférhetnek e-mailhez. Azonban Miután egy későbbi Windows update figyelhetünk meg ezeket a profilokat nem fog működni. Ezek a profilok a megcélzott eszközökön fog elvesznek a végfelhasználók hozzáférési e-mailhez.
- Ezek a profilok április nem tükröződnek az után végzett módosításokat megcélzott eszköz.
- Szelektív törlés eltávolítja ezeket a profilokat, áprilisban bevezetési a javítás után is nem működik.

Ha a művelet végrehajtása, és hozza létre újból az e-mail-profilok, a végfelhasználók kell meg hasonló lépéseket először egy e-mail-profil központi telepítésekor. Az e-mailjeikhez le lesz tiltva addig, amíg elfogadják az új profil a frissítés szinkronizálása.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Hajtsa végre a műveletet, csak azt követően a javítás bevezetési április frissítésével kell. Azt fogja Önnel az üzenetközpont keresztül amikor ez a változás élesíti, így újra létre kell hoznia a profilok az Intune-ban.

Ha Windows 10-es e-mail-profilokat használja az Intune-ban, szüksége lesz az alábbi lépéseket:

1. Win 10-es profil meglévő beállítások rögzítése
2. Hozzárendelésének megszüntetése és/vagy a meglévő profilok törlése
3. A rögzített beállításokkal új profilok létrehozása és az új profilok hozzárendelése ugyanazokhoz a csoportokhoz

A végfelhasználók értesítést, és lehetővé teszik a segélyszolgálat ismeri a módosítása szükségessé. Tekintse meg a támogatási blogbejegyzésben található további információ a hiba részleteit, és ezeket a profilokat újra létrehozására vonatkozó utasításokat.

#### <a name="additional-information"></a>További információ
https://aka.ms/Win10EmailProfiles

