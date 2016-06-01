---
# required metadata

title: Újdonságok | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Újdonságok a Microsoft Intune-ban

## 2016. április
Mindezeket a funkciókat a hibrid ügyfelek is támogatják (tehát az Intune-nal integrált Configuration Manager is).
### Alkalmazáskezelés
- **A felhasználók mobilalkalmazás-felügyeleti megfelelősége.**
Már az Azure Active Directory- (AAD-) bérlőben szereplő bármely felhasználónál megtekintheti az alkalmazásfelügyeleti házirendek [állapotát](monitor-mobile-app-management-policies-with-Microsoft-Intune.md). Ez a következő teendőket foglalja magában:
   - Eszközök
   - Alkalmazások az eszközön

   Az állapot a következő értékeket veheti fel:

   **Beadva**: azt jelzi, hogy a házirend telepítve van a felhasználónál, az alkalmazást pedig használták munkahelyi környezetben, és sikeresen megkapta a házirendet.

    **Nincs beadva:** azt jelzi, hogy a házirend telepítve van a felhasználónál, de az alkalmazást egyszer sem használták a munkahelyi környezetben.


- **Az Outlook-névjegyek szinkronizálásának megakadályozása mobilalkalmazás-felügyelettel (Android).**
Új beállítás érhető el a [mobilalkalmazások eszközregisztráció nélküli felügyeletéhez](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md). Ezzel a beállítással megakadályozhatja, hogy az alkalmazás szinkronizálja a névjegyeket a natív címjegyzékbe az Android-eszközökön. Ha a beállítás engedélyezve van, a megcélzott alkalmazások nem menthetnek névjegyeket a natív címjegyzékbe. Ha a beállítás nincs engedélyezve, a megcélzott alkalmazások menthetik a névjegyeket a natív címjegyzékbe. Amikor [távolról törli egy eszköz vagy alkalmazás tartalmát](wipe-managed-company-app-data-with-Microsoft-Intune.md), a natív címjegyzék mentett összes névjegy törlődni fog. Ezt az új beállítást már az Android-eszközökön elérhető Outlook alkalmazás is támogatja.

### Eszközkezelés
- **A céges eszközök telefonszámos azonosítása.** A „Céges” eszközként besorolt telefonokat a rendszer már a teljes telefonszámukkal azonosítja, például amikor jelentést készít a mobileszközkészletről. A BYOD-eszközök telefonszámai továbbra is **** karakterekkel maszkolva, csak az utolsó 4 számjegyükkel jelennek meg.


### A Vállalati portál újdonságai
**Androidos Vállalati portál alkalmazás**
Azok a felhasználók, akik nem regisztrálták az eszközüket az Intune-ban, és akiknél nincs telepítve a megfelelő tanúsítvány, nem jelentkezhetnek be az androidos Vállalati portál alkalmazásba. Náluk a következő üzenet jelenik meg: „Nem tud bejelentkezni, mert az eszközön hiányzik egy szükséges tanúsítvány.” Az üzenettel együtt megjelenő „Útmutató a probléma megoldásához” hivatkozással a felhasználó megtekintheti a tanúsítvány telepítési lépéseit. A probléma felhasználó általi megoldásának lépéseit lásd: [Az eszközhöz hiányzik egy szükséges tanúsítvány](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing)..

**iOS rendszerű Vállalati portál alkalmazás**
A kezdőképernyőn szereplő tartalmak, például a felsorolt alkalmazások, eszközök és az IT elérhetőségi adatai már lefelé húzással is frissíthetők. A lehúzásos frissítési művelet a megfelelőséggel és házirenddel kapcsolatos adatokat nem ellenőrzi – ez az aktuális eszköz csempéjének kijelölésével és a **Szinkronizálás** gombbal végezhető el.

**Vállalati portál Windows 10 Mobile és Windows Phone 8.1 rendszerre**
A végfelhasználó számára az üzleti alkalmazások telepítésekor egy továbbfejlesztett környezet jelenik meg. Ha az alkalmazás telepítése hosszú ideig tart, a felhasználók manuálisan szinkronizálhatják az eszközt a szinkronizálási folyamat kényszerített folytatásához. A végfelhasználói lépéseket lásd: [Eszköz manuális szinkronizálása a lassú alkalmazástelepítések felgyorsítása érdekében](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually)..

**Munkahelyi portál webhely**
A Windows 10 Mobile- és a Windows Phone 8.1 -felhasználók az üzleti alkalmazások telepítésekor a következő új állapotokat láthatják, amelyek több részlettel szolgálnak számukra a telepítés előrehaladásáról:

* **Várakozás az eszköz szinkronizálására** – A felhasználó a „Telepítés” gombra kattintott, az eszköz pedig most megpróbál szinkronizálni az Intune-infrastruktúrával. A szinkronizálás szükséges a telepítés folytatásához. A „Várakozás az eszköz szinkronizálására” üzenet egyben hivatkozás is, amellyel a felhasználó megtekinthet egy [útmutatást](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) arról, hogyan szinkronizálhatja manuálisan az eszközét az Intune-nal, ha a szinkronizálási folyamat túl sokáig tart vagy elakad.
* **Letöltés** – A felhasználó letöltési kérelme feldolgozás alatt áll, az eszközön pedig folyamatban van az alkalmazás letöltése és telepítése.

A fenti állapotok megjelenése előtt a felhasználónál zavart okozhatott, ha egy alkalmazás telepítése hosszú ideig tartott, ugyanis csak a „Telepítés” állapotot láthatta, amely akár órákig is a képernyőn maradhatott. Az új állapotok bevezetésével a felhasználó a támogatási szolgálat felkeresése helyett a „Várakozás az eszköz szinkronizálására” hivatkozásra kattinthat, és az útmutatást követve folytatásra kényszerítheti a szinkronizálási folyamatot.

### Mi várható?

**A készülékregisztráció-kezelő (DEM-) fiókok változásai.** A jobb teljesítmény és méretezés érdekében az Intune a jövőben nem fogja megjeleníteni az összes készülékregisztráció-kezelő (DEM-) eszközt a Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.  Emellett az Intune-ból kivezetjük a DEM-fiókok használati lehetőségét az Apple Device Enrollment Programmal és az Apple Configurator eszközzel. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.  Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.

Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával..


## Az Intune korábbi kiadásai
Az Intune-ban az elmúlt hat hónapban bevezetett újdonságok listája [Az Intune korábbi kiadásai](previous-intune-releases.md) című cikkben olvasható.



### További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO1-->


