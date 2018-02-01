---
title: "Wi-Fi-profil létrehozása előmegosztott kulccsal"
titleSuffix: Azure portal
description: "Előmegosztott kulccsal ellátott Wi-Fi profil létrehozása egyéni Intune-eszközprofillal.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 395a7136630a9393f44037c65e3c8db760149c38
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2018
---
# <a name="use-a-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Előmegosztott kulccsal ellátott Wi-Fi-profil létrehozása egyéni eszközprofil segítségével
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ebből a cikkből megtudhatja, hogyan hozhat létre előmegosztott kulccsal ellátott Wi-Fi profilt az Intune **Egyéni konfiguráció** funkciójával. A témakörben szereplő példa pedig elmagyarázza, hogyan hozzon létre EAP-alapú Wi-Fi-profilt.

> [!NOTE]
-   Előfordulhat, hogy egyszerűbb másolni a kódot egy olyan számítógépről, amely már csatlakozik a kívánt hálózathoz. Ennek leírását lásd alább.
- Android-rendszerek esetén használhatja a Johnathon Biersack által biztosított [Android PSK Generator](http://intunepskgenerator.johnathonb.com/) programot is.
-   További OMA-URI-beállítások megadásával több hálózatot és kulcsot is hozzáadhat.
-  iOS-rendszereken a profil létrehozásához használja az Apple Configurator programot egy Mac munkaállomáson. Alternatív megoldásként használja a Johnathon Biersack által biztosított [iOS PSK Mobile Config Generator](http://intunepskgenerator.johnathonb.com/) programot.


1.  Ha androidos vagy windowsos rendszerhez hoz létre előmegosztott kulcsos Wi-Fi-profilt, illetve EAP-alapú Wi-Fi-profilt, akkor az eszközprofil létrehozásakor ne valamelyik Wi-Fi-profilt válassza, hanem az eszköz platformjának megfelelő **Egyéni** lehetőséget.

2.  Adjon meg egy nevet és egy leírást.
3.  Adjon hozzá egy OMA-URI beállítást:

   a.   Adjon nevet a Wi-Fi-hálózat ezen beállításának.

   b.   Írja be az OMA-URI-beállítás leírását, vagy hagyja üresen a mezőt.

   c.   **Adattípus**: állítsa be a **Karakterlánc** értéket.

   d.   **OMA-URI**:

    - **Android rendszerhez**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Windows rendszerhez**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Ne hagyja ki a karaktersor elején található pontot.

    Az SSID az az SSID, amelyhez létrehozza a házirendet. Például: `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e. **Érték mező**: ide illessze be az XML-kódot. Íme egy példa. Az értékeket saját hálózati beállításainak megfelelően adja meg. Útmutatásért tekintse át a kód megjegyzéseket tartalmazó részét.
4. Kattintson az **OK** gombra, mentsen, majd telepítse a szabályzatot.

    > [!NOTE]
    > Ez a szabályzat kizárólag felhasználói csoportokhoz rendelhető.

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

## <a name="best-practices"></a>Gyakorlati tanácsok
A Wi-Fi-profil PSK használatával való üzembe helyezése előtt ellenőrizze, hogy az eszköz tud-e közvetlenül kapcsolódni a végponthoz.

Kulcsok (jelszavak és hozzáférési kódok) cseréjekor számítson üzemszünetre, és az üzembe helyezést ennek figyelembe vételével tervezze meg. A Wi-Fi-profilok leküldését ajánlatos munkaidőn kívülre időzíteni. A felhasználókat is figyelmeztesse a kapcsolat esetleges kimaradására.

A zökkenőmentes átállás érdekében gondoskodjon róla, hogy a felhasználó eszköze más módon csatlakozzon az internethez. A felhasználónak például vissza kell tudni váltani a Vendég Wi-Fi-hálózatra (vagy egy másik Wi-Fi-hálózatra), vagy mobilhálózati kapcsolattal kell rendelkeznie, amellyel kommunikálhat az Intune-nal. A felhasználó így továbbra is megkaphatja a szabályzatfrissítéseket, amíg a vállalati Wi-Fi-hálózat frissül az eszközön.
