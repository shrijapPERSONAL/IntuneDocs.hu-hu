---
title: Eszközkezelési lehetőségeit a Microsoft Intune-ban
description: Ebből a témakörből megtudhatja, hogyan segíthet az Intune kezelni az Ön által regisztrált mobileszközöket.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 415005ee58367a189986e9d7bd0ef693f14bc5c9
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048373"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>A Microsoft Intune regisztrált eszközök kezelésével kapcsolatos képességei

A Microsoft Intune segítségével sokféle eszközt kezelhet úgy, hogy *regisztrálja* őket a szolgáltatásban. Egyes eszköztípusokat regisztrálhat saját maga, vagy regisztrálhatják a felhasználók a *Vállalati portál* alkalmazással. A regisztráció lehetővé teszi őket a tallózással keresse meg és alkalmazásokat telepíteni, győződjön meg arról, hogy eszközeik megfeleljenek a vállalati szabályzatoknak, és forduljon az IT-támogatási.

Ez a cikk biztosít után az eszközök regisztrációjának első a képességek teljes listáját.

Felügyeleti, a leltárt, az alkalmazás telepítését, a létesítést és a használatból való kivonást egyaránt lehet kezelni az Intune az Azure Portalon.

A felhasználók hozzáférést kapnak a vállalati portálhoz, és ennek segítségével alkalmazásokat telepíthetnek, eszközöket regisztrálhatnak vagy távolíthatnak el, és segítségért az informatikai osztályhoz vagy a segélyszolgálathoz fordulhatnak.



## <a name="device-security-and-configuration"></a>Eszközvédelem és -beállítás

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Konfigurációs szabályzatok<br><br>Egyéni házirendek| Lehetővé teszi számos beállítás és funkció kezelését a szervezethez tartozó mobileszközökön. Például megkövetelheti jelszó használatát, korlátozhatja a sikertelen bejelentkezési kísérletek számát, megadhatja, hogy a képernyő hány perc után zárolódjon, beállíthatja a jelszó lejárati idejét, és letilthatja a korábban használt jelszavak ismételt használatát. Szabályozhatja továbbá a hardveres és szoftveres funkcióknak (például az eszköz kamerájának és a webböngészőnek) a használatát.<br><br>Egyéni szabályzat használata, amikor a konfigurációs szabályzatok nem tartalmazzák a kívánt beállítást. iOS-eszközök esetén importálhatja az Apple Configurator eszközből exportált beállításokat. Más eszközök esetében az Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállítások segítségével konfigurálhatja a beállításokat és a szolgáltatásokat az eszközön.|[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](device-compliance-get-started.md)|
|Távoli törlés, távoli zárolás és PIN-kód alaphelyzetbe állítása|Az eszköz elvesztése vagy eltulajdonítása esetén törli a bizalmas adatokat. Távolról zárolhatja például az eszközt, visszaállíthatja a gyári beállításokat vagy törölheti csak a vállalati adatokat.<br><br>Ha a felhasználók nem tudnak hozzáférni egy eszközhöz, alaphelyzetbe állíthatja a PIN-kódokat, zárolhatja az eltűnt vagy ellopott eszközöket, vagy törölhet róluk minden adatot.|Az adatok védelme érdekében [távoli zárolás](device-remote-lock.md) és [PIN-kód alaphelyzetbe állítása](device-passcode-reset.md)|
|Teljes képernyős mód|Lehetővé teszi a mobileszközök bizonyos funkciói, például a képernyőfelvétel-készítés és a kikapcsolás zárolását. Emellett az eszközt egyetlen meghatározott alkalmazás futtatására korlátozhatja. |[iOS-eszközök konfigurációs házirendjének beállításai a Microsoft Intune-ban](device-restrictions-ios.md)|

## <a name="app-management"></a>Alkalmazáskezelés

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Alkalmazások telepítése és kezelése|Számos eszközt kínál, amelyek segítségével kezelheti a mobilalkalmazásokat teljes életciklusukon keresztül, beleértve a telepítési fájlokból és alkalmazás-áruházakból történő telepítést, az alkalmazás állapotának részletes megfigyelését, valamint az alkalmazás eltávolítását.|[Alkalmazások telepítése a Microsoft Intune-ban](apps-deploy.md)|
|Megfelelő és nem megfelelő alkalmazások|Lehetővé teszi a szabályzatnak megfelelő (így a felhasználók által telepíthető) és nem megfelelő (így a felhasználók által nem telepíthető) alkalmazások listájának megadását.|[iOS-szabályzatbeállítások a Microsoft Intune-ban](device-restrictions-ios.md)|
|Mobilalkalmazás-kezelés|A mobilalkalmazás-felügyelet révén korlátozásokat konfigurálhat az alkalmazásokra vonatkozóan az Intune-nal kezelt eszközökre és a nem az Intune-nal kezelt eszközökre egyaránt. Növelheti a vállalati adatok biztonságát, műveletek, például a másolás és beillesztés, az adatok külső biztonsági mentése és az adatok alkalmazások közötti átvitelének korlátozásával.|[Mobilalkalmazás-kezelési házirendek konfigurálása és telepítése a Microsoft Intune-konzolon](app-wrapper-prepare-android.md)|
|iOS-mobilalkalmazás konfigurálása|A mobilalkalmazás-konfigurációs szabályzatokkal automatikusan megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy iOS-alkalmazást futtat. Előfordulhat például, hogy az alkalmazás portszám vagy bejelentkezési beállítások megadását kéri a felhasználótól. Leegyszerűsíthető az alkalmazások konfigurálása, és csökkentheti a segélyszolgálatra beérkező hívások száma.|[iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](app-configuration-policies-use-ios.md)|
|iOS-mobilalkalmazás létesítési profiljai|Segít létesítési profilokat telepíteni a lejárathoz közelítő iOS-alkalmazásokhoz. |[Az iOS-mobileszközös létesítésiprofil-szabályzatok segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak](app-provisioning-profile-ios.md)|
|Felügyelt böngésző|Konfigurálja a felügyeltböngésző-szabályzatokat, amelyekkel szabályozható, hogy az eszköz felhasználói mely webhelyeket látogathatják meg. Emellett mobilalkalmazás-kezelési házirendeket is alkalmazhat a felügyelt böngészőre.|[Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](app-configuration-managed-browser.md)|
|Vállalati Windows Hello|Lehetővé teszi az integrációt a Vállalati Windows Hello nevű, a Windows 10-ben használható alternatív bejelentkezési módszerrel. Ez a helyi Active Directoryt vagy az Azure Active Directoryt használja jelszavak, intelligens kártyák vagy virtuális intelligens kártyák helyett.|[A Vállalati Windows Hello beállításainak szabályozása az eszközökön a Microsoft Intune-nal](windows-hello.md)|
|Mennyiségi licencszerződés keretében vásárolt alkalmazások|Segít a mennyiségi licencszerződés keretében vásárolt alkalmazások felügyeletében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt telepítsen, mint amennyit vásárolt.|[Mennyiségi programban vásárolt alkalmazások felügyelete a Microsoft Intune-nal](vpp-apps.md)|

## <a name="company-resource-access"></a>Vállalati erőforrások elérése

|Képesség|Részletek|További információ|
|--------------|-----------|--------------------|
|Tanúsítványprofilok|Létrehozhat és telepíthet megbízhatótanúsítvány-profilokat és egyszerű tanúsítványigénylési protokollon (SCEP) alapuló tanúsítványokat, amelyek segítségével biztonságossá teheti és hitelesítheti a Wi-Fi-, VPN- és e-mail-profilokat.|[Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](certificates-configure.md)|
|Wi-Fi profilok|Vezeték nélküli hálózati beállításokat léptethet érvénybe a felhasználók számára. E beállítások érvénybe léptetésével csökkentheti a vállalati hálózat eléréséhez szükséges felhasználói beavatkozást.|[Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-settings-configure.md)|
|E-mail profilok|Hoz létre, és e-mail-beállításokat telepít eszközöket úgy, hogy a felhasználók férhetnek hozzá vállalati levelezésükhöz saját eszközeik semmit sem kell beállítaniuk eszközeiken.|[Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal a Microsoft Intune-ban](email-settings-configure.md)|
|VPN-profilok|VPN-beállításokat léptethet érvénybe a szervezethez tartozó felhasználók és eszközök számára. A beállítások központi telepítésével csökkentheti a vállalati hálózatban lévő erőforrások eléréséhez szükséges felhasználói beavatkozást.|[VPN-kapcsolatok a Microsoft Intune-ban](device-profiles.md#vpn)|
|Feltételes hozzáférési házirendek|A Microsoft Exchange-levelezéshez és a SharePoint Online-hoz való hozzáférés felügyelete a nem az Intune által felügyelt eszközökön.|[Az e-mailek és a SharePoint elérésének korlátozása a Microsoft Intune használatával](app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>További lépések

[Tekintse meg a felügyelt eszközök listáját](device-management.md).
