---
title: "Egyéni konfigurációk Microsoft Intune VPN-profilokhoz | Microsoft Intune"
description: "Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 634a2b72f2f4ae1b3164b0f063aba4b73f05f1fb
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Egyéni konfigurációk Microsoft Intune VPN-profilokhoz | Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Egyéni konfiguráció létrehozása
Egyéni Intune-konfigurációs szabályzatokkal VPN-profilok hozhatók létre a következőkhöz:

* Android 4 vagy újabb rendszerű eszközök
* Android for Work-eszközök
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* A Windows Phone 8.1-es vagy újabb verzióját futtató eszközök
* A Windows 10 asztali verzióját futtató regisztrált eszközök
* Windows 10 Mobile rendszerű eszközök

Az ilyen típusú szabályzat akkor lehet hasznos, ha a szabványos Intune VPN-szabályzatok nem tartalmazzák a használni kívánt beállításokat.

## <a name="to-create-a-custom-configuration-policy"></a>Egyéni konfigurációs szabályzat létrehozása:

   1. Az [Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** > **Házirend hozzáadása** > *Bontsa ki a platformot* > **Egyéni konfiguráció** > **Házirend létrehozása** lehetőséget.
   2. Adja meg a szabályzat nevét.
   3. A megadni kívánt URI-beállítások mindegyikénél válassza a **Hozzáadás** elemet, és adja meg a szükséges információkat. Például:

   ![VPN-profil egyéni konfigurációjának párbeszédpanelje](./media/Intune_Add_VPN_URI.png)

   4.  Miután minden URI-beállítást megadott, válassza a **Házirend mentése** elemet, és telepítse a házirendet.

Ezt követően a megszokott módon [telepítse a szabályzatot](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

## <a name="example-uri-settings"></a>URI-példabeállítások

Az alábbi beállításokkal egy kitalált, Contoso nevű vállalat VPN-jéhez lehet egyéni konfigurációt létrehozni.
A használható beállításokról itt talál részletes tudnivalókat: [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**Native Contoso VPN (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
Igaz

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

A beállítások használatával és működésével kapcsolatos további tudnivalókért lásd a [konfigurációszolgáltató (CSP) dokumentációját](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>URI-beállítások Android rendszerű alkalmazásonkénti VPN-hez a PulseSecure-ban
### <a name="custom-uri-for-package-list"></a>EGYÉNI URI CSOMAGLISTÁHOZ
-  Adattípus = Karakterlánc
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Érték = Elválasztott csomaglista.
   - Elválasztó karakter: pontosvessző (;), kettőspont (:), vessző (,), vonal (|)

Példák:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>EGYÉNI URI MÓDHOZ (NEM KÖTELEZŐ)
- Adattípus = Karakterlánc
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Megjegyzések
> - Használja azt a *nevet*, amelyet az egyéni profilhoz rendelt
> - A lehetséges értékek: *GLOBAL* (GLOBÁLIS), *WHITELIST* (ENGEDÉLYEZETT), *BLACKLIST* (LETILTOTT)
> - A *GLOBAL* (GLOBÁLIS) érték az alapértelmezett, amennyiben nem áll rendelkezésre PackageList (csomaglista) (visszamenőleges kompatibilitás rendszerszintű profilokkal).
> - Alapértelmezett a *WHITELIST* (ENGEDÉLYEZETT), ha rendelkezésre áll PackageList (csomaglista).


### <a name="see-also"></a>További információ
[VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md)
