---
title: "Regisztrált eszközök felügyeletét szolgáló képességek"
description: "Ebből a témakörből megtudhatja, hogyan segíthet az Intune kezelni az Ön által regisztrált mobileszközöket."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 5fc5e6108e7e7841ed142f24f463d85273ae8a12
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>A Microsoft Intune regisztrált eszközök kezelésével kapcsolatos képességei

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune segítségével sokféle eszközt kezelhet úgy, hogy *regisztrálja* őket a szolgáltatásban. Egyes eszköztípusokat regisztrálhat saját maga, vagy regisztrálhatják a felhasználók a *Vállalati portál* alkalmazással. Ez lehetővé teszi továbbá, hogy a felhasználók olyan műveleteket hajtsanak végre, mint a böngészés vagy az alkalmazások telepítése, biztosítva, hogy eszközeik megfeleljenek a vállalati szabályzatoknak és kommunikálnak az IT-támogatási szolgálattal.

Ez a témakör minden olyan lehetőséget ismertet, amely az eszközök regisztrálását követően válik elérhetővé.

A felügyeletet, a leltárt, az alkalmazások telepítését, a létesítést és a használatból való kivonást egyaránt az Intune felügyeleti konzoljával lehet kezelni. A felhasználók hozzáférést kapnak a vállalati portálhoz, és ennek segítségével alkalmazásokat telepíthetnek, eszközöket regisztrálhatnak vagy távolíthatnak el, és segítségért az informatikai osztályhoz vagy a segélyszolgálathoz fordulhatnak.



## <a name="device-security-and-configuration"></a>Eszközvédelem és -beállítás

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Beállítási házirendek<br><br>Egyéni házirendek| Lehetővé teszi számos beállítás és funkció kezelését a szervezethez tartozó mobileszközökön. Például megkövetelheti jelszó használatát, korlátozhatja a sikertelen bejelentkezési kísérletek számát, megadhatja, hogy a képernyő hány perc után zárolódjon, beállíthatja a jelszó lejárati idejét, és letilthatja a korábban használt jelszavak ismételt használatát. Szabályozhatja továbbá a hardveres és szoftveres funkcióknak (például az eszköz kamerájának és a webböngészőnek) a használatát.<br><br>Akkor használjon egyéni szabályzatokat, ha a konfigurációs szabályzatok nem tartalmazzák a kívánt beállítást. iOS-eszközök esetén importálhatja az Apple Configurator eszközből exportált beállításokat. Más eszközök esetében az Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállítások segítségével konfigurálhatja a beállításokat és a szolgáltatásokat az eszközön.|[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Távoli törlés, távoli zárolás és PIN-kód alaphelyzetbe állítása|Az eszköz elvesztése vagy eltulajdonítása esetén törli a bizalmas adatokat. Távolról zárolhatja például az eszközt, visszaállíthatja a gyári beállításokat vagy törölheti csak a vállalati adatokat.<br><br>Ha a felhasználók nem tudnak hozzáférni egy eszközhöz, alaphelyzetbe állíthatja a PIN-kódokat, zárolhatja az eltűnt vagy ellopott eszközöket, vagy törölhet róluk minden adatot.|[Eszközök védelme távoli zárolással és a jelszó alaphelyzetbe állításával](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Teljes képernyős mód|Lehetővé teszi a mobileszközök bizonyos funkciói, például a képernyőfelvétel-készítés és a kikapcsolás zárolását. Emellett az eszközt egyetlen meghatározott alkalmazás futtatására korlátozhatja.|[iOS-eszközök konfigurációs házirendjének beállításai a Microsoft Intune-ban](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Alkalmazáskezelés

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Alkalmazások telepítése és kezelése|Számos eszközt kínál, amelyek segítségével kezelheti a mobilalkalmazásokat teljes életciklusukon keresztül, beleértve a telepítési fájlokból és alkalmazás-áruházakból történő telepítést, az alkalmazás állapotának részletes megfigyelését, valamint az alkalmazás eltávolítását.|[Alkalmazások telepítése a Microsoft Intune-ban](/intune-classic/deploy-use/deploy-apps)|
|Megfelelő és nem megfelelő alkalmazások|Lehetővé teszi a szabályzatnak megfelelő (így a felhasználók által telepíthető) és nem megfelelő (így a felhasználók által nem telepíthető) alkalmazások listájának megadását.|[iOS-szabályzatbeállítások a Microsoft Intune-ban](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobilalkalmazás-kezelés|A mobilalkalmazás-felügyelet révén korlátozásokat konfigurálhat az alkalmazásokra vonatkozóan az Intune-nal kezelt eszközökre és a nem az Intune-nal kezelt eszközökre egyaránt. Ennek segítségével fokozhatja a vállalati adatok biztonságát bizonyos műveletek, például a másolás és beillesztés, az adatok külső biztonsági mentése, valamint az alkalmazások közötti adatátvitel korlátozásával.|[Mobilalkalmazás-kezelési házirendek konfigurálása és telepítése a Microsoft Intune-konzolon](/intune/app-wrapper-prepare-android)|
|iOS-mobilalkalmazás konfigurálása|A mobilalkalmazás-konfigurációs szabályzatokkal automatikusan megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy iOS-alkalmazást futtat. Előfordulhat például, hogy az alkalmazás portszám vagy bejelentkezési beállítások megadását kéri a felhasználótól. Ezzel leegyszerűsíthető az alkalmazások konfigurálása, és csökkenthető a segélyszolgálatra beérkező hívások száma.|[iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS-mobilalkalmazás létesítési profiljai|Segít létesítési profilokat telepíteni a lejárathoz közelítő iOS-alkalmazásokhoz. |[Az iOS-mobileszközös létesítésiprofil-szabályzatok segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Felügyelt böngésző|Konfigurálja a felügyeltböngésző-szabályzatokat, amelyekkel szabályozható, hogy az eszköz felhasználói mely webhelyeket látogathatják meg. Emellett mobilalkalmazás-kezelési házirendeket is alkalmazhat a felügyelt böngészőre.|[Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Vállalati Windows Hello|Lehetővé teszi az integrációt a Vállalati Windows Hello nevű, a Windows 10-ben használható alternatív bejelentkezési módszerrel. Ez a helyi Active Directoryt vagy az Azure Active Directoryt használja jelszavak, intelligens kártyák vagy virtuális intelligens kártyák helyett.|[A Vállalati Windows Hello beállításainak szabályozása az eszközökön a Microsoft Intune-nal](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Mennyiségi licencszerződés keretében vásárolt alkalmazások|Segít a mennyiségi licencszerződés keretében vásárolt alkalmazások felügyeletében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt telepítsen, mint amennyit vásárolt.|[Mennyiségi programban vásárolt alkalmazások felügyelete a Microsoft Intune-nal](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Vállalati erőforrások elérése

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Tanúsítványprofilok|Létrehozhat és telepíthet megbízhatótanúsítvány-profilokat és egyszerű tanúsítványigénylési protokollon (SCEP) alapuló tanúsítványokat, amelyek segítségével biztonságossá teheti és hitelesítheti a Wi-Fi-, VPN- és e-mail-profilokat.|[Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi profilok|Vezeték nélküli hálózati beállításokat léptethet érvénybe a felhasználók számára. E beállítások érvénybe léptetésével csökkentheti a vállalati hálózat eléréséhez szükséges felhasználói beavatkozást.|[Wi-Fi-kapcsolatok a Microsoft Intune-ban](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-mail profilok|E-mail-beállításokat hozhat létre és léptethet érvénybe az eszközökön. A felhasználók így külön beállítások elvégzése nélkül férhetnek hozzá vállalati levelezésükhöz saját eszközeiken.|[Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal a Microsoft Intune-ban](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN-profilok|VPN-beállításokat léptethet érvénybe a szervezethez tartozó felhasználók és eszközök számára. A beállítások központi telepítésével csökkentheti a vállalati hálózatban lévő erőforrások eléréséhez szükséges felhasználói beavatkozást.|[VPN-kapcsolatok a Microsoft Intune-ban](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Feltételes hozzáférési házirendek|A Microsoft Exchange-levelezéshez és a SharePoint Online-hoz való hozzáférés felügyelete a nem az Intune által felügyelt eszközökön.|[Az e-mailek és a SharePoint elérésének korlátozása a Microsoft Intune használatával](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Leltár és jelentéskészítés

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Leltár és jelentéskészítés|Információkat kereshet a felügyelt eszközökről és az általuk használt szoftverekről.|[A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|

