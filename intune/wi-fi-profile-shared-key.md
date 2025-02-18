---
title: WiFi-profil létrehozása előmegosztott kulccsal az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Egyéni profil segítségével létrehozhat egy előmegosztott kulcsú Wi-Fi-profilt. A cikkben találhat XML-mintakódot Android-, Windows- és EAP-alapú Wi-Fi-profilok Microsoft Intune-ban való létrehozásához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bf859075e675ef0205b24e0575fca5ab74f312c
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490632"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key---intune"></a>Előmegosztott kulccsal ellátott WiFi-profil létrehozása egyéni eszközprofil segítségével – Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az előmegosztott kulcsok (PSK-k) segítségével hitelesítheti a felhasználókat a vezeték nélküli helyi hálózatokon. Az Intune-nal hozhat létre egy előmegosztott kulccsal ellátott WiFi-profilt. A profil létrehozásához először készítenie kell egy **egyéni eszközkonfigurációs profilt** az Intune-ban. A cikk emellett tartalmaz néhány példát az EAP-alapú Wi-Fi-profilok létrehozásához is.

> [!IMPORTANT]
>- Az előmegosztott kulcsok Windows 10 rendszerben való használata szervizelési hiba megjelenéséhez vezet az Intune-ban. E hiba megjelenésekor a Wi-Fi-profilt a rendszer megfelelően hozzárendeli az eszközhöz, és a profil a várt módon fog működni.
>- Az előmegosztott kulcsot tartalmazó Wi-Fi-profilok exportálásakor gondoskodjon a fájlok védelméről. A kulcs egyszerű szövegként szerepel, ezért az Ön felelőssége a kulcs védelme.

## <a name="before-you-begin"></a>Előkészületek

- Egyszerűbb lehet, ha a kódot egy, az adott hálózathoz már csatlakozó számítógépről másolja. Ennek leírását a cikk későbbi részében megtalálhatja.
- További OMA-URI-beállítások megadásával több hálózatot és kulcsot is hozzáadhat.
- iOS-rendszereken a profil létrehozásához használja az Apple Configurator programot egy Mac munkaállomáson.
- Az előmegosztott kulcsokhoz egy 64 hexadecimális számból álló sztringet vagy egy 8–63 nyomtatható ASCII-karakterből álló jelszót kell megadnia. Bizonyos karakterek, például a csillag ( * ), nem támogatottak.

## <a name="create-a-custom-profile"></a>Egyéni profil létrehozása
Hozhat létre előmegosztott kulcsot tartalmazó egyéni profilt Androidhoz vagy Windowshoz, illetve EAP-alapú Wi-Fi-profilt. A profil Azure Portallal való létrehozásáról az [Egyéni eszközbeállítások létrehozása](custom-settings-configure.md) című témakörben tájékozódhat. Az eszközprofil létrehozásakor válassza az eszköz platformjához tartozó **Egyéni** lehetőséget. Ne válassza a Wi-Fi-profil lehetőséget. Az Egyéni lehetőség választása után: 

1. Adja meg a profil nevét és leírását.
2. Adjon hozzá egy új OMA-URI-beállítást az alábbi tulajdonságokkal: 

   a. Adjon nevet a Wi-Fi-hálózat ezen beállításának.

   b. (Nem kötelező) Írja be az OMA-URI-beállítás leírását, vagy hagyja üresen a mezőt.

   c. Állítsa az **Adattípus** beállítást a **Sztring** értékre.

   d. **OMA-URI**:

   - **Android rendszerhez**: ./Vendor/MSFT/WiFi/Profile/SSID/Settings
   - **Windows rendszerhez**: ./Vendor/MSFT/WiFi/Profile/SSID/WlanXml

     > [!NOTE]
     > Ne hagyja ki a karaktersor elején található pontot.

     Az SSID az az SSID, amelyhez létrehozza a házirendet. Például írja be a következőt: `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

   e. **Érték mező**: ide illessze be az XML-kódot. Tekintse át a cikkben található példákat. Módosítsa az értékeket a saját hálózati beállításainak megfelelően. A kódban található megjegyzések további információt nyújtanak.
3. Válassza az **OK** gombot, mentsen, majd társítsa a szabályzatot.

    > [!NOTE]
    > Ez a szabályzat kizárólag felhasználói csoportokhoz rendelhető.

Amikor az egyes eszközök legközelebb bejelentkeznek, a rendszer telepíti a szabályzatot, és létrehozza a Wi-Fi-profilt az eszközökön. Az eszköz így képes lesz automatikusan kapcsolódni a hálózathoz.

## <a name="android-or-windows-wi-fi-profile-example"></a>Android vagy Windows rendszerhez készült példa Wi-Fi-profil

Az alábbi példában megtalálhatja az Android vagy Windows rendszerhez készült Wi-Fi-profilhoz használható XML-kódot. A példa a megfelelő formátumot mutatja be, valamint részletesebb információkkal is szolgál. Ez azonban csak egy példa, és nem az Ön környezetéhez ajánlott konfiguráció.

> [!IMPORTANT]
>
> - A `<protected>false</protected>` tulajdonságot **false** (hamis) értékre kell állítania. Ha **true** (igaz) értékre állítja, előfordulhat, hogy az eszköz titkosított jelszót vár, és a kapott jelszót megpróbálja visszafejteni, melynek következtében a kapcsolódás meghiúsulhat.
>
> - A `<hex>53534944</hex>` helyére a `<name><SSID of wifi profile></name>` paraméter hexadecimális értékét kell beírni.
>  Előfordulhat, hogy Windows 10-eszközön a *0x87D1FDE8 Sikertelen szervizelés* hamis hibaüzenet jelenik meg, az eszköz azonban ettől függetlenül tartalmazni fogja a profilt.
>
> - XML speciális karaktereket is tartalmaz, mint például a `&` (és jel). Speciális karakterek használatával előfordulhat, hogy az XML-fájl működő a várt módon. 

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile-example"></a>EAP-alapú példa Wi-Fi-profil
Az alábbi példában megtalálhatja az EAP-alapú Wi-Fi-profilhoz használható XML-kódot: A példa a megfelelő formátumot mutatja be, valamint részletesebb információkkal is szolgál. Ez azonban csak egy példa, és nem az Ön környezetéhez ajánlott konfiguráció.


```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>XML-fájl létrehozása meglévő Wi-Fi kapcsolat alapján
Az XML-fájlt meglévő Wi-Fi-kapcsolat alapján is létrehozhatja az alábbi lépések követésével: 

1. Nyissa meg a következő mappát egy olyan számítógépen, amely kapcsolódik a kívánt vezeték nélküli hálózathoz, vagy a közelmúltban kapcsolódott hozzá: `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}`.

   Célszerű olyan számítógépet választania, amely nem csatlakozott sok vezeték nélküli hálózathoz. Máskülönben előfordulhat, hogy végig kell böngésznie az összes profilt a helyes profil megtalálásához.

2. Keresse meg az XML-fájlok között a megfelelő nevű fájlt.
3. Miután megtalálta a megfelelő XML-fájlt, másolja, majd illessze be az XML-kódot az OMA-URI-beállítások oldal **Adat** mezőjébe.

## <a name="best-practices"></a>Ajánlott eljárások
- A Wi-Fi-profil PSK használatával való üzembe helyezése előtt győződjön meg róla, hogy az eszköz tud közvetlenül kapcsolódni a végponthoz.

- Kulcsok (jelszavak és hozzáférési kódok) cseréjekor számítson üzemszünetre, és az üzembe helyezést ennek figyelembe vételével tervezze meg. A Wi-Fi-profilok leküldését ajánlatos munkaidőn kívülre időzíteni. A felhasználókat is figyelmeztesse a kapcsolat esetleges kimaradására.

- A zökkenőmentes átállás érdekében gondoskodjon róla, hogy a felhasználó eszköze más módon csatlakozzon az internethez. A felhasználónak például vissza kell tudni váltani a Vendég Wi-Fi-hálózatra (vagy egy másik Wi-Fi-hálózatra), vagy mobilhálózati kapcsolattal kell rendelkeznie, amellyel kommunikálhat az Intune-nal. E további kapcsolat révén a felhasználó továbbra is megkaphatja a szabályzatfrissítéseket, amíg a vállalati Wi-Fi-hálózat frissül az eszközön.
