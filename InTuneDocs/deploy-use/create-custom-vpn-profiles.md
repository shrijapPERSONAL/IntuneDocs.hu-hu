---
title: "Egyéni konfigurációk Microsoft Intune VPN-profilokhoz | Microsoft Docs"
description: "Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: 9dbb44981c1525e6137dd8a469b1582731ee9719
ms.lasthandoff: 12/20/2016


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

Ezt követően a megszokott módon [telepítse a szabályzatot](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

## <a name="example-uri-settings"></a>URI-példabeállítások

Az alábbi beállításokkal egy kitalált, Contoso nevű vállalat VPN-jéhez lehet egyéni konfigurációt létrehozni.
A használható beállításokról itt talál részletes tudnivalókat: [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Native Contoso VPN (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Ha bármilyen kérdése van a beállítások használatával kapcsolatban, illetve az ezen beállítások működésével kapcsolatos további információkra van szüksége, olvassa el a konfigurációszolgáltató (CSP) dokumentációját: https://msdn.microsoft.com/hu-hu/library/windows/hardware/dn914776(v=vs.85).aspx.

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

