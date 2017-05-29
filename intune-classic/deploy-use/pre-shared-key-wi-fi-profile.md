---
title: "Wi-Fi használata előmegosztott kulccsal | Microsoft Docs"
description: "Wi-Fi-profil létrehozása előmegosztott kulccsal az Egyéni konfiguráció funkció segítségével."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6845097b768e67c7fbc6ff16bf41f27982c4b33e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017



---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Előmegosztott kulcsú Wi-Fi-profil létrehozása egyéni szabályzattal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ebből a cikkből megtudhatja, hogyan hozhat létre Wi-Fi profilt előmegosztott kulccsal az Intune **Egyéni konfiguráció** funkciója segítségével. A témakörben szereplő példa pedig elmagyarázza, hogyan hozzon létre EAP-alapú Wi-Fi-profilt.

> [!NOTE]
-    Előfordulhat, hogy egyszerűbb másolni a kódot egy olyan számítógépről, amely már csatlakozik a kívánt hálózathoz. Ennek leírását lásd alább.
- Android-rendszerek esetén használhatja a Johnathon Biersack által biztosított [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) programot is.
-    További OMA-URI-beállítások megadásával több hálózatot és kulcsot is hozzáadhat.
-  iOS-rendszereken a profil létrehozásához használja az Apple Configurator programot egy Mac munkaállomáson. Alternatív megoldásként használja a Johnathon Biersack által biztosított [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) programot.


1.    Ha Android- vagy Windows-rendszerre hoz létre előmegosztott kulcsos Wi-Fi-profilt, illetve EAP-alapú Wi-Fi-profilt, akkor a házirend létrehozásakor ne valamelyik Wi-Fi-profilt válassza, hanem az eszköz platformjának megfelelő **Egyéni konfiguráció** lehetőséget.

2.    Adjon meg egy nevet és egy leírást.
3.    Adjon hozzá egy OMA-URI beállítást:

   a.    Adjon nevet a Wi-Fi-hálózat ezen beállításának.

   b.    Írja be az OMA-URI-beállítás leírását, vagy hagyja üresen a mezőt.

   c.    **Adattípus**: állítsa be a következőt: „Karakterlánc (XML)”.

   d.    **OMA-URI**:

    - **Android rendszerhez**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Windows rendszerhez**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Ne hagyja ki a karaktersor elején található pontot.

    Az SSID az az SSID, amelyhez létrehozza a házirendet. Például: `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e. **Érték mező**: ide illessze be az XML-kódot. Íme egy példa. Az értékeket saját hálózati beállításainak megfelelően adja meg. Útmutatásért tekintse át a kód megjegyzéseket tartalmazó részét.
4. Mentéshez válassza az **OK** lehetőséget, majd telepítse a házirendet.

    > [!NOTE]
    > Ez a házirend kizárólag felhasználói csoportokra telepíthető.

Amikor az egyes eszközök legközelebb bejelentkeznek, a rendszer telepíti a szabályzatot, és létrehozza a Wi-Fi profilt az eszközökön. Az eszköz így képes lesz automatikusan kapcsolódni a hálózathoz.
## <a name="android-or-windows-wi-fi-profile"></a>Android vagy Windows rendszerhez készült Wi-Fi profil

Egy példa az Android vagy Windows rendszerhez készült Wi-Fi-profil esetén alkalmazandó XML-kódra:

> [!IMPORTANT]
> 
> `<protected>false</protected>`állítsa **false** (hamis) értékűre, mert **true** (igaz) érték esetén előfordulhat, hogy az eszköz titkosított jelszót vár, majd megpróbálja azt visszafejteni, ami a kapcsolat létrejöttének meghiúsulásához vezethet.
> 
>  A `<hex>53534944</hex>` helyére a `<name><SSID of wifi profile></name>` paraméter hexadecimális értékét kell beírni.
>  Előfordulhat, hogy Windows 10-eszközön a *0x87D1FDE8 Sikertelen szervizelés* hamis hibaüzenet jelenik meg, ám a profil kiépítése sikerül.

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
<hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>        </SSID>
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
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a>EAP-alapú Wi-Fi-profil
Itt láthat egy példát egy EAP-alapú Wi-Fi-profil esetén alkalmazandó XML-kódra:

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
Az XML-fájlt meglévő Wi-Fi kapcsolat alapján is létrehozhatja:
1. Nyissa meg a következő mappát egy olyan számítógépen, amely kapcsolódik a kívánt vezeték nélküli hálózathoz, vagy a közelmúltban kapcsolódott hozzá: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Érdemes olyan számítógépet választani, amely még nem kapcsolódott túl sok vezeték nélküli hálózathoz, mivel az összes profilt át kell néznie, hogy megtalálja a megfelelőt.
3.     Keresse meg a kívánt nevű XML-fájlt.
4.     Miután megtalálta a megfelelő XML-fájlt, másolja, majd illessze be az XML-kódot az OMA-URI-beállítások oldal Adat mezőjébe.

## <a name="deploy-the-policy"></a>A szabályzat telepítése

1.  A **Szabályzat** munkaterületen válassza ki a telepíteni kívánt szabályzatot, és kattintson a **Központi telepítés kezelése** elemre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   **A házirend telepítése** – Válasszon ki egy vagy több olyan csoportot, amelyhez telepíteni kívánja a házirendet, majd kattintson a **Hozzáadás** &gt; **OK** gombra.

    -   **A párbeszédpanel bezárása telepítés nélkül** – Kattintson a **Mégse** gombra.

Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat róla.

### <a name="see-also"></a>További információ
[Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md)

