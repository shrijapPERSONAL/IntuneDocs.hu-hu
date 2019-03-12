---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 3c80028fd995675e7664b27d7e4051c9a9d0e669
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57736857"
---

Ezek a megjegyzések meg fontos információkat, amelyek segítségével előkészítése az Intune jövőbeli változtatásokat és szolgáltatásokat. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>A vállalati iOS-eszközök beállítási Asszisztenssel való hitelesítés közben az Intune vállalati portálon a regisztrációs folyamat módosítása <!-- 1927359 -->
Az iOS-eszközök Apple vállalati tulajdonú eszközök regisztrálási módszerei – az Apple Configurator, Apple üzleti vezető, az Apple School Manager vagy az Apple eszköz beléptetési Program (DEP) keresztül munkafolyamata egy közelgő változásokat használata esetén a telepítő Segéd a hitelesítéshez. Ez a változás csak a felhasználói affinitással rendelkező regisztrált eszközökre vonatkozik.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ha ez a változás bevezetési ~~március~~ április, regisztrációs profilokat az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Továbbfejlesztett munkafolyamatot az iOS-eszközök regisztrálása a fenti módszerek keresztül lesz. Megjegyezés:

- Amikor új eszközök regisztrációja és hitelesítése a beállítási asszisztens, képes lesz-e automatikusan telepíthető a vállalati portál alkalmazás kiválasztása. A végfelhasználók már nem jelenik meg a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban.  
- A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök lépéseket kell tennie, ha azt szeretné, a feltételes hozzáférés engedélyezéséhez. Egy adott xml leküldéses le ezeket az eszközöket a vállalati portál alkalmazás-konfigurációs házirend konfigurálása kell. Ehhez irányban a blogbejegyzés, a további információk hivatkozáson találhatók. Ha elküldi a vállalati portál ezen a módon kikapcsolja, végfelhasználók számára már nem jelennek meg, a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban. 
- Után ez a változás bevezetési, ha még nem telepítette a céges portált a fent említett az alkalmazás konfigurációs profil, és ha a végfelhasználók letöltése a céges portál alkalmazást az App Store áruházból, fog tudjon jelentkezni, de azok fog hibaüzenetet kap. Nem tudják használni az alkalmazást a feltételes hozzáférés. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha a módosított munkafolyamat használatát tervezi, szeretné frissíteni a végfelhasználói útmutató, amely szerint:

- Végfelhasználók számára már nem jelennek meg a fent említett a regisztrációs folyamat két képernyő. 
- Jelentkezzen be a vállalati portálon, hogy telepítésekor automatikusan, és ne töltse le az app store lesz szükséges. 

Ha szeretné, hozzon létre egy alkalmazáskonfigurálási szabályzat most szükség esetén ez a változás előkészítéséhez. Amikor az új munkafolyamatot vezet be, látni fogja a frissített beléptetési profilok a konzolon. Azt fogjuk is értesíti a felhasználókat a Bevezetés az üzenet központon keresztül. Ezt követően kell, hogy a végfelhasználók beléptethetik az DEP Programon keresztül és a beállítási Asszisztenssel hitelesítéséhez és a feltételes hozzáférés is használhatja a vállalati portál, hajtsa végre a műveletet.

Tekintse meg a további információk hivatkozáson erről a változásról további részletekért tegye közzé kérdéseit támogatási blogon.

#### <a name="additional-information"></a>További információ 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Vállalati portál IOS-eszközök 12.2 regisztrálása az Intune-ban változás
A Microsoft megosztott MC172534, amely az Apple bejelentette, hogy néhány módosítás az iOS-eszközök regisztrálása a mobileszköz-felügyeleti (MDM) szolgáltatásra. A módosítás a március 2019 hamarosan IOS-es kiadása, valamint az összes jövőbeli iOS kiadások valószínűleg lesz látható. A vállalati portálon, az Apple változásainak néhány frissítést végzünk. 
 
#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ha a végfelhasználók számára frissíteni kell az eszközét, iOS 12.2-re vagy újabb, tudja, hogy a módosított munkafolyamat és azok további lépéseket kell végrehajtani az Intune-ban regisztráció elvégzését. A márciusi frissítés után az Intune-hoz a következő lesz dolgukat –  

- A regisztráció megkezdéséhez a céges portál alkalmazásban a felügyeleti profil letöltése
- Lépjen a beállítások > Általános > profilok és a egy piros jelvény értesítési keressen
- Válassza ki a megfelelő profilt, és kattintson az Install
- Térjen vissza a céges portálon való teljes regisztráció

A regisztrációs folyamat kapcsolatos részletes információkért kattintson a további információt.

Kivéve, ha az Ön regisztrációját megszüntetik, és a egy friss beléptetési, eszközök, amelyek már regisztrált és a frissítés az iOS 12.2 kell, és a fentiekben nem lesz hatással. Regisztrációs folyamatának 12,1 vagy régebbi iOS-eszközök az Apple által az új kiadás nem fognak változni. Az egyik vagy az Apple vállalati regisztrációs módszerek (Készülékregisztrációs Program, az Apple School Manager vagy az Apple üzleti vezető) regisztrált eszközöket ez nem vonatkozik.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Meg kell terveznie a dokumentációját, valamint a végfelhasználói útmutató frissítése. Érdemes azt is, ahhoz, hogy a segélyszolgálat ismeri ezeket a módosításokat. Folyamatosan tájékoztatjuk Önt folyamatosan értesíteni az Újdonságok oldalát, amikor ez a változás élesíti keresztül. 

Ha azt szeretné, hogy igénybe vehesse a céges portál módosításokat vezetünk be, kérje meg a végfelhasználók számára az új IOS-es verzióra frissítik az eszközt, miután az Intune a márciusi frissítés szolgáltatást, ha a vállalati portál alkalmazás verziója 3.9.0. akkor szabadul fel.

Kattintson ide további információ a céges portál változásainak előzetes képernyőképeket támogatási blogbejegyzést.

További információ [https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Tervezett módosítás: A munkafolyamat-módosítások az IOS-eszközök 12 regisztrálása az Intune-ban
Az Apple bejelentette, hogy néhány módosítás az iOS-eszközök regisztrálása a mobileszköz-felügyeleti (MDM) szolgáltatásra. A módosítás a spring 2019 kiadásban az IOS-es, valamint az összes jövőbeli iOS-kiadások valószínűleg lesz látható.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A végfelhasználók számára az új verzió 12 IOS-eszközeiket tavasszal frissíti, ha tudja, hogy a módosított munkafolyamat és azok kell Intune-ba való regisztrálást végrehajtani, további lépések végrehajtására. Apple ezeket a változásokat vezet be, amikor a végfelhasználók számára való fog rendelkezni:

- A regisztráció megkezdéséhez a céges portál alkalmazásban a felügyeleti profil letöltése
- Lépjen a beállítások > Általános > profilok
- Válassza ki a megfelelő profilt, és kattintson az Install
- Térjen vissza a céges portálon való teljes regisztráció 

Addig, amíg Ön regisztrációját megszüntetik, és a egy friss regisztráció, a már regisztrált eszközökre van szükség, és frissítése az új IOS-es kiadás nem lesz hatással.

Regisztrációs folyamatának 12,1 vagy régebbi iOS-eszközök az Apple által az új kiadás nem fognak változni.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Meg kell terveznie a dokumentációját, valamint a végfelhasználói útmutató frissítése. Érdemes azt is, ahhoz, hogy a segélyszolgálat ismeri ezeket a módosításokat. Folyamatosan tájékoztatjuk Önt folyamatosan értesíteni az üzenet központon keresztül, és az Újdonságok oldalát, amikor ez a változás élesíti.

#### <a name="additional-information"></a>További információ
[Támogatja a képernyőképek és a várt regisztrációs folyamat videó blogbejegyzés](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Tervezett módosítás: Felhasználóiélmény-frissítést az iOS-hez készült Intune vállalati portál alkalmazás
Örömmel megosztására, hogy az Intune hamarosan adunk ki az IOS-es céges portál alkalmazás egy nagyszabású felhasználóiélmény-frissítést. A frissítés egy vizuális átalakulás a kezdőlap ügyfélszolgálatnak a speciális szűrők és az alkalmazások és könyvek gyorsabb hozzáférést.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A felhasználói élmény frissítése, miközben fenntartja az IOS-es céges portál funkciókat, ügyfélszolgálatnak:
- Egy natív iOS megjelenését és működését érintő kezdőlapján 
- A tartalom listák és a keresés, szűrés a tartalomtípus (alkalmazások vagy e-könyvek) és a rendelkezésre állás (Eszközkezelés kötelező vagy elérhető legyen, regisztráció nélkül) például szűrési képességek
- E-könyvek kereshetővé
- Keresési előzmények alkalmazásokhoz és e-könyvek

Ha Ön az Apple TestFlight programjában, értesíteni fogjuk az Intune céges portál alkalmazás frissítése IOS-az előzetes verzióval kapcsolatos mikor válik elérhetővé. Ha Ön nem Apple TestFlight programjában, nincs késő regisztrálni. Regisztrálása lehetővé teszi, hogy a frissített vállalati portál alkalmazást használja, mielőtt a végfelhasználók számára elérhető. Fogja is adhat visszajelzést közvetlenül, az Intune csapatával.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Nem kell semmit sem kell; Ezeket a változásokat egy közelgő iOS CP alkalmazás kiadásban elérhető lesz. 

#### <a name="additional-information"></a>További információ
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Emlékeztető: Meglévő Exchange Online-t az Intune összekötő eltávolítása <!-- 3105122 -->
MC165575 hogy a megosztott, hogy azt kellene lennie eltávolítása az Exchange online-hoz az Intune-ban "Service to Service" összekötő funkció a közeljövőben egy frissítést. A február frissítéssel az Intune szolgáltatásba a gombra kattintva új összekötők beállítása fog letiltjuk. Azt tervezi, hogy március 2019 az összes meglévő Exchange Online-t az Intune-összekötő eltávolítása.
 
#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ezt az üzenetet azért küldtük Önnek, mert adataik szerint, hogy lehet használni a "Service to Service" összekötő funkció a környezetben. A "Service to Service" összekötő az eszközök Exchange Active Sync csak az Intune felügyeleti támogatja az Exchange online-hoz, és nem támogatja a helyszíni infrastruktúrával. Ezt az összekötőt, akkor jelenik meg a konzolon módja miatt jelenik meg, hogy a feltételes hozzáféréssel (CA), szükségesek a valóságban ez nem szükségesek a hitelesítésszolgáltató. Előfordulhat, hogy már használja ezt az összekötőt a használatelemzés az Exchange Online feltételes hozzáférés alkalmazása előtt. Ezt az információt a Microsoft 365 felügyeleti központ által már biztosított. Itt megtalálhatja használati jelentést kínál, 7, illetve 180 nap közötti, használja az Exchange Online alkalmazást is beleértve írja. További információ: [Office 365 jelentéseket a felügyeleti központ – E-mail alkalmazások használati](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Ez az összekötő használatakor a környezetben nem képes figyelésre vagy törölhetik az Exchange Active Sync csak az Intune-ban után összekötők februárban le vannak tiltva. Ez a módosítás során várható fennakadást a végfelhasználók számára van.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha a Service to Service connector beállításához és az Exchange Active Sync csak olyan eszközöket, váltson a más módszerek az eszközök felügyeletét. A következő lehetőségek állnak rendelkezésére:

- A mobileszköz-felügyeleti (MDM) eszközök regisztrálása 
- Az Intune alkalmazásvédelmi szabályzatok használata az eszközök kezeléséhez 
- Az Exchange vezérlőkkel dokumentációjában leírt módon [Itt](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) 

#### <a name="additional-information"></a>További információ  
https://docs.microsoft.com/intune/exchange-service-connector-configure




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
