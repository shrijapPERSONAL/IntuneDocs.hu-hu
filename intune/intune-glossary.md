---
title: Microsoft Intune-szószedet
titleSuffix: Microsoft Intune
description: A Microsoft Intune-ban használt szakkifejezések jelentésének ismertetése.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 07/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bfab6f5f9c3b083ebcb0cee8820149fed7ce5c94
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188057"
---
# <a name="microsoft-intune-glossary"></a>Microsoft Intune-szószedet
A Microsoft Intune gyakori kifejezéseinek definíciói.

## <a name="a"></a>A

|||
|-|-|
|Alkalmazás-hozzárendelés|Lehetővé teszi a felhasználók számára, hogy [megkeressék, letöltsék és telepítsék](/intune/app-management) a szükséges alkalmazásaikat. Ezt korábban *alkalmazások üzembe helyezésének* nevezték.|
|Alkalmazáskonfigurációs profil <br/><br/>Alkalmazáskonfigurációs szabályzat|Szállítóspecifikus konfigurációval rendelkező mobilalkalmazásoknál érhető el. Futtatásuk előtt adott beállításokkal konfigurálja az [iOS](/intune/app-configuration-policies-use-ios)- és [Android](/intune/app-configuration-policies-use-android)-alkalmazásokat.|
|Alkalmazások monitorozása|Lehetővé teszi az alkalmazás-hozzárendeléssel kapcsolatos [legutóbbi állapotok és tevékenységek felülvizsgálatát](/intune/apps-monitor).|
|Alkalmazásvédelem adateltávolítási feladata|[Eltávolítja az alkalmazásadatokat](/intune/app-protection-policies) a felhasználó eszközéről.|
|Alkalmazásvédelmi szabályzat|Az Enterprise Mobility + Security- (EMS-) technológiával integrált mobilalkalmazásoknál érhető el. Biztosítja, hogy a felhasználó alkalmazásai megfeleljenek a [cégnél érvényes adatvédelmi szabályzatoknak](/intune/app-protection-policies).|
|App SDK|A [Microsoft Intune App SDK](/intune/app-sdk) segítségével olyan funkciókat adhat hozzá a cégen belül írt alkalmazásokhoz, amelyek lehetővé teszik az alkalmazásoknak az Intune-alapú alkalmazásvédelmi szabályzatokkal történő felügyeletét.|
|Alkalmazáseltávolítási művelet|Lehetővé teszi [alkalmazások eltávolítását](/intune/apps-deploy) a felhasználó eszközeiről.|
|Alkalmazásburkoló eszköz|[Parancssori alkalmazás](/intune/apps-prepare-mobile-application-management), amely egy burkolót hoz létre egy üzletági alkalmazás körül. Ez a burkoló lehetővé teszi, hogy az alkalmazást Intune-alapú alkalmazásvédelmi szabályzattal felügyeljék.|
|Hozzárendelési művelet|Egy [alkalmazás hozzárendelésekor](/intune/apps-deploy) az Ön által meghozott döntés. Az alkalmazás telepítését kötelezővé vagy választhatóvá teheti, vagy eltávolíthatja az alkalmazást.|
|Elérhető telepítés|Ha ezt a műveletet rendeli egy alkalmazáshoz, akkor az megjelenik a céges portálon, és a felhasználók [igény szerint telepíthetik](/intune/apps-deploy).|
|Azure Portal|Az Intune új konzolja. [További információ](/intune/what-is-intune).|

## <a name="b"></a>B

|||
|-|-|
|BYOD|Saját eszközök használata ([Bring Your Own Device](/intune/device-enrollment)). A felhasználók telepítik az eszközeikre az Intune Céges portál alkalmazást, majd regisztrálják az eszközüket, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és adatok, valamint az ügyfélszolgálat.|

## <a name="c"></a>C

|||
|-|-|
|Tanúsítványprofil|Ezzel a szabályzattípussal tanúsítványokkal [teheti biztonságossá a vállalati erőforrások elérését](/intune/certificates-configure), amikor Wi-Fi-t, levelezést vagy VPN-profilokat használ.|
|Cég tulajdonában lévő eszközök (COD)|A [cég tulajdonában lévő eszközök](/intune/device-enrollment) többféleképpen is regisztrálhatók a cég igényeitől és a felügyelt eszközök típusától függően.|
|Céges portál|Olyan alkalmazás vagy webhely, amely a felhasználók számára [hozzáférést biztosít a vállalati adatokhoz és alkalmazásokhoz](/intune/company-portal-customize).|
|Megfelelőségi szabályzat|Gondoskodik róla, hogy az eszközök [megfeleljenek bizonyos szabályoknak](/intune/device-compliance), például használjanak PIN-kódot az eszközhöz való hozzáféréshez, illetve titkosítsák az eszközön tárolt adatokat.|
|Megfelelő és nem megfelelő alkalmazások|Ezek a beállítások egy [eszközkorlátozási profil](/intune/device-restrictions-configure) részét képezik, és lehetővé teszik a felhasználók által futtatható és nem futtatható alkalmazások listájának meghatározását. Az Intune ezt követően jelentésekben tájékoztatja arról, ha nem megfelelő alkalmazást telepítenek vagy futtatnak. Egyes platformok esetében az Intune le is tilthatja a nem megfelelő alkalmazások telepítését.|
|Feltételes hozzáférés|Csak az Ön által beállított szabályoknak megfelelő eszközökről [engedélyezi a céges levelezés, az Office 365 és más szolgáltatások elérését](/intune/conditional-access).|
|Egyéni szabályzat|Akkor [használja ezeket a szabályzatokat](/intune/custom-settings-configure), ha az általános konfigurációs szabályzat beépített beállításai nem felelnek meg Önnek. Egyéni szabályzattal lehetősége nyílhat más módon, például az Apple Configurator vagy OMA-URI használatával beállítást létrehozni.|

## <a name="d"></a>D

|||
|-|-|
|Környezet|Olyan művelet, amelynek során alkalmazást vagy szabályzatot küld egy Ön által felügyelt eszköznek vagy felhasználónak. Ezt a műveletet most már *hozzárendelésnek* nevezik.|
|Készülékregisztráció-kezelő|A cégek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az [készülékregisztráció-kezelői fiók (DEM-fiók)](/intune/device-enrollment-program-enroll-ios) egy, akár ezer eszköz regisztrálására is képes, speciális Intune-fiók.|
|Eszközprofilok|[Ezek a profilok](/intune/device-profile-create) lehetővé teszik számos funkció, illetve biztonsági és hozzáférési beállítások konfigurálását a felügyelt eszközökön.|

## <a name="e"></a>E

|||
|-|-|
|E-mail-profil|Ezzel a szabályzattal [e-mail-hozzáférési beállításokat](/intune/email-settings-configure) adhat meg mobileszközökhöz, hogy a végfelhasználónak csak minimális teendője legyen.|
|EMS|A Microsoft Enterprise Mobility + Security (korábbi nevén Nagyvállalati mobilitási csomag) megvédi céges adatait, és lehetővé teszi a felhasználóknak [a szükséges alkalmazások és tartalom elérését](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|Végfelhasználó|[Különböző eszközök (például telefonok és számítógépek) felhasználói](/intune/end-user-educate), akiknek a felügyelete az Intune használatával történik.|
|Regisztrálás|A Microsoft Intune [regisztráció](/intune/device-enrollment) segítségével vonja felügyelet alá az eszközöket, és teszi lehetővé az erőforrásokhoz való hozzáférést.|

## <a name="f"></a>F

|||
|-|-|
|FastTrack|[Microsoft-szolgáltatás](https://technet.microsoft.com/library/mt228265.aspx) olyan Intune-felhasználók számára, akik a feltételeknek megfelelő csomaggal és 150 licenccel rendelkeznek. Ha ezt a szolgáltatást használja, a Microsoft szakemberei segíthetnek Önnek az Intune üzembe helyezésében.|

## <a name="g"></a>G

|||
|-|-|
|Csoportok|A csoportok lehetővé teszik, hogy [összegyűjtse a logikailag kapcsolódó felhasználókat és eszközöket](/intune/groups-get-started). Például létrehozhat egy csoportot, amely az összes windowsos számítógépet tartalmazza. Ezt követően ezekhez a csoportokhoz alkalmazásokat és profilokat rendelhet hozzá.|

## <a name="h"></a>H

|||
|-|-|
|Hibrid|Olyan konfiguráció, amelyben az Intune-nal regisztrált eszközöket a System Center Configuration Manager konzoljával felügyelheti.|

## <a name="i"></a>I

|||
|-|-|
|Azure Portal|Az Azure Portal azon része, amelyen keresztül a legtöbb Intune-alapú felügyeleti művelet elvégezhető.|
|Intune-szoftverügyfél|A [Windows rendszerű számítógépek felügyelete](/intune-classic/get-started/choose-how-to-manage-devices) cikkben ismertetett alternatív megoldások segíthetnek eldönteni, hogy melyik módszert érdemes alkalmaznia.|
|Intune Software Publisher|Olyan eszköz, amellyel [meghatározhatja, milyen alkalmazásokat szeretne telepíteni, és feltöltheti őket a felhőbe](/intune-classic/deploy-use/add-apps).|
|Leltár|Megtekintheti a felügyelt eszközök [hardvereit és a rájuk telepített szoftvereket](/intune/device-inventory).|

## <a name="k"></a>K

|||
|-|-|
|Teljes képernyős mód|Ez az [eszközkorlátozási profil](/intune/device-restrictions-configure) részeként beállított mód lehetővé teszi az eszközök lezárását. Például egy kiskereskedelmi eszközt beállíthat úgy, hogy csak néhány alkalmazás futtatását engedélyezze.|

## <a name="m"></a>M

|||
|-|-|
|Felügyelt böngésző|Egy [webböngésző-alkalmazás](/intune/app-configuration-managed-browser), amelyet az Intune használatával rendelhet hozzá a céges eszközeihez. A felügyeltböngésző-szabályzatban megadható egy engedélyezési vagy blokklista, amellyel korlátozhatók a felügyelt böngésző felhasználói által felkereshető webhelyek.|
|MDM-szolgáltató|Az [MDM-szolgáltató](/intune/mdm-authority-set) határozza meg azt a felügyeleti szolgáltatást, amely az eszközök kezelésére jogosult. MDM-szolgáltató lehet például maga az Intune, illetve a Configuration Manager és az Intune.|
|Mobilalkalmazás-konfigurációs szabályzat|Szállítóspecifikus konfigurációval rendelkező mobilalkalmazásoknál érhető el. Például olyan [iOS](/intune/app-configuration-policies-use-ios)- vagy [Android](/intune/app-configuration-policies-use-android)-szabályzat, amely bizonyos beállításokat (például cégnevet vagy kiszolgálócímet) léptethet érvénybe a kompatibilis alkalmazások futtatásakor.|
|Mobilalkalmazás-kiépítési szabályzat|iOS-szabályzat, amelynek segítségével garantálhatja, hogy az iOS-alkalmazásokhoz hozzárendelt [kiépítési profilok](/intune/app-provisioning-profile-ios) ne járjanak le.|
|Mobilalkalmazás-kezelés|A [mobilalkalmazás-felügyelet (MAM)](/intune/app-lifecycle) lehetővé teszi a felhasználók mobilalkalmazásainak közzétételét, leküldését, konfigurálását, védelmét, figyelését és frissítését.
|Mobileszköz-kezelés|A [mobileszköz-kezelés (MDM)](/intune/device-lifecycle) segítségével eszközöket regisztrálhat az Intune-ban, hogy azok kiépíthetők, konfigurálhatók, monitorozhatók, illetve felügyelhetők legyenek.



## <a name="o"></a>O

|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Egy iparági szabványnak számító eszközfelügyeleti protokoll, amelyet számos hardvergyártó használ mobileszközök és PC-k szolgáltatásainak kezeléséhez.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Ezek azonosítják az OMA-DM szabványnak megfelelő egyéni eszközbeállításokat. Ezek a beállítások az [egyéni Intune-profilokban](/intune/custom-settings-configure) használhatók, ha nincs az Ön igényeinek megfelelő beépített beállítás.|

## <a name="p"></a>P

|||
|-|-|
|PIN-kód alaphelyzetbe állítása|Intune-szolgáltatás, amely lehetővé teszi, hogy a támogatott eszközökön a végfelhasználót [új PIN-kód beállítására](/intune/device-passcode-reset) kötelezze.|

## <a name="r"></a>R

|||
|-|-|
|Távoli zárolás|Intune-funkció, amely lehetővé teszi a [támogatott eszközök zárolását](/intune/device-remote-lock), még akkor is, ha Ön nincs az eszköz birtokában.|
|Szükséges telepítés|Ha ezt a műveletet rendeli hozzá egy alkalmazáshoz, akkor annak telepítése nem igényel [felhasználói beavatkozást](/intune/apps-deploy). Egyes platformokon a végfelhasználónak bele kell egyeznie telepítésbe.|


## <a name="s"></a>S

|||
|-|-|
|Szelektív törlés|A [szelektív törlés](/intune/device-company-data-remove) csak az alkalmazásvédelmi szabályzatok által védett vállalati adatokat, például a beállításokat és az e-mail-profilokat távolítja el az eszközről. Szelektív törlés esetén a felhasználó személyes adatai az eszközön maradnak.|
|Közvetlen telepítés|Egy üzletági alkalmazás olyan telepítési művelete, amely során az adott alkalmazást nem az alkalmazás-áruházból telepítik.|
|Előfizetés|Az Ön által megkötött szerződés, amely lehetőséget nyújt egy Intune-bérlő elérésére.|

## <a name="t"></a>T

|||
|-|-|
|TeamViewer|Külső gyártótól származó alkalmazás, amely az Intune-nal együttműködve biztosít [távsegítség-funkciókat](/intune/device-profile-android-teamviewer) az Intune-nal felügyelt Android-eszközökhöz.|
|Bérlő|Az Intune szolgáltatás egyetlen példánya, amelyet elérhet egy előfizetés birtokában.|
|használati feltételei|Felhasználókhoz hozzárendelhető szabályzattípus. Olyan információkat tartalmaz, amelyeket a felhasználóknak [el kell olvasniuk és el kell fogadniuk](/intune/terms-and-conditions-create), hogy regisztrálhassanak a céges portálon, és hozzáférhessenek a munkájukhoz kapcsolódó anyagokhoz.|

## <a name="v"></a>V

|||
|-|-|
|Mennyiségi licencszerződés keretében vásárolt alkalmazások és könyvek|Egyes alkalmazás-áruházak lehetővé teszik, hogy több licencet is vásároljon a cégnél használni kívánt alkalmazásokhoz és könyvekhez. Az Intune segítséget nyújt az [ilyen szerződés keretében vásárolt](/intune/vpp-apps) alkalmazások és könyvek kezelésében. Importálhatja a licencadatokat az alkalmazás-áruházból, figyelemmel kísérheti a felhasznált licencek számát, és meggátolhatja, hogy a megvásároltnál több példányban telepítsen egy alkalmazást.|
|VPN-profil|Szabályzat, amely [VPN-beállításokat](/intune/vpn-settings-configure) rendel hozzá a felügyelt eszközökhöz, hogy a végfelhasználónak csak minimális teendője legyen.|

## <a name="w"></a>W

|               |                                                                                                                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wi-Fi-profil | Szabályzat, amely [vezeték nélküli hálózati beállításokat](/intune/wi-fi-settings-configure) rendel hozzá az eszközökhöz, hogy a felhasználók a beállítások ismerete és konfigurálása nélkül csatlakozhassanak a céges hálózathoz. |

