---
title: "Intune-szószedet | Microsoft Intune"
description: "A Microsoft Intune-ban használt szakkifejezések egy részének bemutatása"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
translationtype: Human Translation
ms.sourcegitcommit: 030db4b1520a4f06756c0feac69de352aab6f473
ms.openlocfilehash: 1dba9553c97e9e02fd4b080915756f4f23ed8635


---

# Microsoft Intune-szószedet

## Az

|||
|-|-|
|App SDK|A [Microsoft Intune App SDK](/intune/develop/intune-app-sdk) használatával olyan funkciókat adhat a vállalaton belül írt alkalmazásokhoz, amelyek lehetővé teszik az alkalmazásoknak az Intune mobilalkalmazás-felügyeleti szabályzatokkal való felügyeletét.|
|Alkalmazásburkoló eszköz|[Parancssori alkalmazás](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune), amely egy burkolót hoz létre az üzleti alkalmazás körül. Ez a burkoló lehetővé teszi, hogy az alkalmazást Intune mobilalkalmazás-felügyeleti szabályzattal felügyeljék.|
|Elérhető telepítés|Ha ezzel a művelettel telepít egy alkalmazást, akkor az megjelenik a vállalati portálon, és a felhasználók [igény szerint telepíthetik](/intune/deploy-use/deploy-apps).|
|Azure Portal|Az Intune-hoz hamarosan egy új konzol jelenik meg. Jelenleg az Azure Portalon hozhat létre [Intune MAM-szabályzatokat](/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) az eszközökhöz.|

## B
|||
|-|-|
|BYOD|Saját eszközök használata ([Bring Your Own Device](/intune/get-started/choose-how-to-enroll-devices1)). A felhasználók telepítik az eszközeikre az Intune Vállalati portál alkalmazást, majd regisztrálják az eszközüket, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és adatok, valamint az ügyfélszolgálat.| 

## C
|||
|-|-|
|Tanúsítványprofil|Ezzel a szabályzattípussal tanúsítványokkal [teheti biztonságossá a vállalati erőforrások elérését](/intune/deploy-use/secure-resource-access-with-certificate-profiles), amikor Wi-Fi-t, levelezést vagy VPN-profilokat használ.|
|Felhőtárhely|Egy hely, ahol a létrehozott alkalmazásokat és adataikat [tárolhatja](/intune/deploy-use/add-apps#cloud-storage-space).|
|Vállalat tulajdonában lévő eszközök (COD)|A [vállalat tulajdonában lévő eszközök](/intune/get-started/choose-how-to-enroll-devices1) (Company Owned Device, vállalati eszköz) többféleképpen is regisztrálhatók a szervezet igényeitől és a felügyelt eszközök típusától függően.|
|Vállalati portál|Olyan alkalmazás vagy webhely, amely a felhasználók számára [hozzáférést biztosít a vállalati adatokhoz és alkalmazásokhoz](/intune/get-started/microsoft-intune-company-portal).|
|Megfelelőségi szabályzat|Gondoskodik róla, hogy a vállalati alkalmazások és adatok elérésére használt eszközök [megfeleljenek bizonyos szabályoknak](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune), például használjanak PIN-kódot az eszközhöz való hozzáféréshez, illetve titkosítsák az eszközön tárolt adatokat.|
|Megfelelő és nem megfelelő alkalmazások|Ezek a beállítások egy [általános konfigurációs szabályzat](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) részét képezik, és lehetővé teszik a felhasználó által futtatható és nem futtatható alkalmazások listájának meghatározását. Az Intune ezután jelentést fog készíteni, ha nem megfelelő alkalmazást telepítenek vagy futtatnak. Egyes platformok esetében az Intune le is tilthatja a nem megfelelő alkalmazások telepítését.|
|Feltételes hozzáférés|Csak az Ön által beállított szabályoknak megfelelő eszközökről [engedélyezi a céges levelezés, az Office 365 és más szolgáltatások elérését](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).|
|Egyéni szabályzat|Akkor [használja ezeket a szabályzatokat](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), ha az általános konfigurációs szabályzat beépített beállításai nem felelnek meg Önnek. Egyéni szabályzattal lehetősége nyílhat más módon, például az Apple Configurator vagy OMA-URI használatával beállítást létrehozni.|

## D
|||
|-|-|
|Környezet|Olyan művelet, amelynek során alkalmazást vagy szabályzatot küld egy Ön által felügyelt eszköznek vagy felhasználónak.|
|Központi telepítési művelet|Egy [alkalmazás központi telepítésekor](/intune/deploy-use/deploy-apps-in-microsoft-intune) Ön által meghozott döntés. Az alkalmazás telepítését kötelezővé vagy választhatóvá teheti, vagy eltávolíthatja az alkalmazást.|
|Eszközregisztráció-kezelő|A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az [eszközregisztráció-kezelői](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) (DEM-) fiók egy akár ezer eszköz regisztrálására is képes, speciális Intune-fiók.|
|Eszközcsoport-leképezés|Segítségével [automatikusan adhat hozzá eszközöket a csoportokhoz](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) az eszköz kategóriája (pl. „Személyes” vagy „Értékesítés”) alapján, amelyet Ön vagy a végfelhasználó rendel az eszközhöz.|

## E
|||
|-|-|
|E-mail profil|Ezzel a szabályzattal [e-mail-elérési beállításokat](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) adhat meg mobileszközökön futó adott e-mail ügyfelekhez, hogy a végfelhasználónak csak minimális teendője legyen.|
|EMS|A Microsoft Enterprise Mobility + Security (korábbi nevén Nagyvállalati mobilitási csomag) megvédi céges adatait, és lehetővé teszi a felhasználóknak [a szükséges alkalmazások és tartalom elérését](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility).|
|Végfelhasználó|Olyan [eszközök, például telefonok és számítógépek felhasználói](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune), amelyeket Ön felügyel az Intune használatával.|
|Regisztrálás|A Microsoft Intune [regisztráció](/intune/deploy-use/enroll-devices-in-microsoft-intune) segítségével vonja felügyelet alá az eszközöket, és teszi lehetővé az erőforrásokhoz való hozzáférést.|

## F
|||
|-|-|
|FastTrack|[Microsoft szolgáltatás](https://technet.microsoft.com/library/mt228265.aspx) olyan Intune-felhasználók számára, akik a feltételeknek megfelelő csomaggal és 150 licenccel rendelkeznek. Ha ezt a szolgáltatást használja, a Microsoft szakemberei segítenek Önnek az Intune üzembe helyezésében.|

## G
|||
|-|-|
|Csoportok|A csoportok lehetővé teszik, hogy [összegyűjtse a logikailag kapcsolódó felhasználókat és eszközöket](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). Például létrehozhat egy csoportot, amely az összes windowsos számítógépet tartalmazza. Ezután alkalmazásokat és szabályzatokat telepíthet ezekre a csoportokra.|

## H
|||
|-|-|
|Hibrid|Olyan konfiguráció, amelyben az Intune-nal regisztrált eszközöket a [System Center Configuration Manager konzollal](/intune/get-started/integration-with-cloud-services) felügyelheti.|

## I
|||
|-|-|
|az Intune felügyeleti konzolja|A jelenlegi konzol, amelyet a legtöbb Intune felügyeleti művelethez használ.|
|Intune-szoftverügyfél|Egy másik módja a [windowsos számítógépek kezelésének](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). Ha segítségre van szüksége a megfelelő mód kiválasztásához, olvassa el [Az eszközkezelés módjának kiválasztása](/intune/get-started/choose-how-to-manage-devices) című részt.|
|Intune Software Publisher|Olyan eszköz, amellyel [meghatározhatja, milyen alkalmazásokat szeretne telepíteni, és feltöltheti őket a felhőbe](/intune/deploy-use/add-apps).|
|Leltár|Megtekintheti a felügyelt eszközök [hardvereit és a rájuk telepített szoftvereket](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune).|

## K
|||
|-|-|
|Teljes képernyős mód|Ez az [általános konfigurációs szabályzat](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) részeként beállított mód lehetővé teszi az eszközök lezárását. Például egy kiskereskedelmi eszközt beállíthat úgy, hogy csak egyetlen alkalmazás futtatását engedélyezze.|

## M
|||
|-|-|
|Felügyelt böngésző|Egy [webböngésző-alkalmazás](/intune/deploy-use/manage-internet-access-using-managed-browser-policies), amelyet a Microsoft Intune használatával telepíthet a szervezetében. A felügyeltböngésző-szabályzatban megadható egy engedélyezési vagy blokklista, amellyel korlátozhatók a felügyelt böngésző felhasználói által felkereshető webhelyek.|
|Mobilalkalmazás-kezelés|A [mobilalkalmazás-felügyelet (MAM)](/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) lehetővé teszi a felhasználók mobilalkalmazásainak közzétételét, leküldését, konfigurálását, védelmét, figyelését és frissítését.
|Mobil eszközök felügyelete|A [mobileszköz-felügyelet (MDM)](/intune/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) lehetővé teszi az eszközöknek az Intune-ban történő regisztrálását, így az adott eszközök kiépíthetők, konfigurálhatók, megfigyelhetők, illetve különböző műveletek végezhetők rajtuk. 
|MDM-szolgáltató|Az [MDM-szolgáltató](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) határozza meg azt a felügyeleti szolgáltatást, amely az eszközök kezelésére jogosult. MDM-szolgáltató lehet például maga az Intune, illetve a Configuration Managerbe és az Intune.|
|Mobilalkalmazás-létesítési szabályzat|iOS-szabályzat, amelynek segítségével garantálhatja, hogy az iOS-alkalmazásokhoz [létesített profilok](/intune/deploy-use/ios-mobile-app-provisioning-profiles) ne járjanak le.|
|Mobilalkalmazás-konfigurációs szabályzat|Az iOS-szabályzatokkal futtatáskor [beállításokat biztosíthat a kompatibilis iOS-alkalmazásokhoz](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) (például cégnevet vagy kiszolgálócímet).|

## O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Egy iparági szabványnak számító eszközfelügyeleti protokoll, amelyet számos hardvergyártó használ mobileszközök és PC-k szolgáltatásainak kezeléséhez.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Az OMA-DM szabványnak megfelelő egyéni eszközbeállítások azonosítására szolgál. Számos azonosító használható az [Intune egyéni szabályzatokban](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), ha nincs az Ön igényeinek megfelelő beépített beállítás.|

## P
|||
|-|-|
|Házirend|Az Intune-ból egy adott eszközre küldött [információcsomag](/intune/deploy-use/microsoft-intune-policy-reference). Szabályzat használatával például biztonsági beállítások vagy eszközmegfelelőségi információk telepíthetők az eszközre.|
|PIN-kód alaphelyzetbe állítása|Intune-szolgáltatás, amely lehetővé teszi, hogy a támogatott eszközökön a végfelhasználót [új PIN-kód beállítására](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) kötelezze.|

## R
|||
|-|-|
|Távoli zárolás|Intune-szolgáltatás, amellyel [zárolhatja a támogatott eszközöket](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) még akkor is, ha nincs birtokában az eszköznek.|
|Reports|Az Intune számos különböző [beépített jelentést](/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) biztosít, amelyek információkkal szolgálnak a felügyelt eszközökről.|
|Szükséges telepítés|Ha ezzel a művelettel telepít alkalmazást, akkor a telepítés [nem igényel felhasználói beavatkozást](/intune/deploy-use/deploy-apps) (habár egyes platformokon a végfelhasználónak bele kell egyeznie a telepítésbe).|
|Követelmények|[Alkalmazástelepítési művelet](/en-us/intune/deploy-use/add-apps), amellyel kiválaszthatja, hogy az alkalmazás telepítéséhez az eszköznek mely követelményeket kell teljesítenie. Például megadhatja, hogy az alkalmazás az iOS operációs rendszer melyik verziójának meglétét igényli a telepítéshez.|

## S
|||
|-|-|
|Szelektív törlés|A [szelektív törlés](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) a vállalati adatokat, többek között a mobilalkalmazás-felügyeleti (MAM-) adatokat (adott esetben), a beállításokat és az e-mail-profilokat távolítja el az eszközről. Szelektív törlés esetén a felhasználó személyes adatai az eszközön maradnak.|

## T
|||
|-|-|
|TeamViewer|Független gyártótól származó alkalmazás, amely az Intune-nal együttműködve biztosít [távsegítség-funkciókat](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) az Intune szoftverügyfél által felügyelt windowsos számítógépekhez.|
|használati feltételei|Szabályzattípus. Azokat az információkat tartalmazza, amelyeket a felhasználónak [el kell olvasnia és el kell fogadnia](/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) ahhoz, hogy használhassa a céges portált a regisztráláshoz és a munkához.|

## V
|||
|-|-|
|Mennyiségi licencszerződés keretében vásárolt alkalmazások|Egyes alkalmazás-áruházak lehetővé teszik, hogy több licencet is vásároljon a vállalatánál használni kívánt alkalmazásokhoz. Az Intune segít az [ilyen programok keretében vásárolt](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune) alkalmazások kezelésében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt használjon, mint amennyit vásárolt.|
|VPN-profil|Szabályzat, amely központilag telepíti a [VPN-beállításokat](/intune/deploy-use/vpn-connections-in-microsoft-intune) az Ön által felügyelt eszközökre, és a telepítéshez minimális végfelhasználói beavatkozást igényel.|

## W
|||
|-|-|
|Wi-Fi profil|Szabályzat, amely központilag telepíti a [vezeték nélküli hálózati beállításokat](/intune/deploy-use/wi-fi-connections-in-microsoft-intune) az eszközökre, hogy a felhasználók a beállítások ismerete és konfigurálása nélkül csatlakozhassanak a céges hálózathoz.






<!--HONumber=Sep16_HO4-->


