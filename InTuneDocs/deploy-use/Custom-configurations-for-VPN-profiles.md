---
title: "Egyéni konfigurációk VPN-profilokhoz | Microsoft Intune"
description: "Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fb3b6cccaa3e62be3a7271ae6a67e76f8cf8d858
ms.openlocfilehash: a1c7648a4ee4ab91e00f5305a8124a07570824fc


---

# <a name="custom-configurations-for-vpn-profiles"></a>Egyéni konfigurációk VPN-profilokhoz

## <a name="create-a-custom-configuration"></a>Egyéni konfiguráció létrehozása
Egyéni konfigurációk használatával VPN-profilok hozhatók létre az Intune-ban a következőkhöz:

* Android 4 vagy újabb rendszerű eszközök
* Android for Work-eszközök
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* A Windows Phone 8.1-es vagy újabb verzióját futtató eszközök
* A Windows 10 asztali és mobilverzióját futtató eszközök

Egyéni konfiguráció létrehozásához tegye a következőket:

   1. Az Intune felügyeleti konzoljában válassza a **Házirend** > **Házirend hozzáadása** > *Bontsa ki a platformot* > **Egyéni konfiguráció** > **Házirend létrehozása** lehetőséget.
   2. Adja meg a szabályzat nevét.
   3. Az egyes URI-beállításoknál válassza a **Hozzáadás** elemet, és adja meg a szükséges információkat. Például:

   ![VPN-profil egyéni konfigurációjának párbeszédpanelje](./media/Intune_Add_VPN_URI.png)

   4.  Miután minden URI-beállítást megadott, válassza a **Házirend mentése** elemet, és telepítse a házirendet.

## <a name="deploy-a-configuration-policy"></a>Konfigurációs szabályzat telepítése

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt szabályzatot, majd kattintson a **Központi telepítés kezelése** elemre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   **A házirend telepítése** – Válasszon egy vagy több olyan csoportot, amelynek telepíteni kívánja a házirendet, majd kattintson a **Hozzáadás** &gt; **OK** gombra.

    -   **A párbeszédpanel bezárása telepítés nélkül** – Kattintson a **Mégse** gombra.

Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat róla.

##<a name="example-of-uri-settings-for-a-custom-vpn-profile-configuration"></a>Példa egy egyéni VPN-profil konfigurációjának URI-beállításaira
Az alábbiakban egy kitalált, Contoso nevű vállalat VPN-profiljához tartozó egyéni konfiguráció létrehozásához szükséges URI-értékek megadására mutatunk példát. További tudnivalókért – például az egyes bejegyzések adattípusaival kapcsolatban – olvassa el a [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx) című témakört.

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

## <a name="uri-settings-for-android-perapp-vpn-on-pulsesecure"></a>URI-beállítások Android rendszerű alkalmazásonkénti VPN-hez a PulseSecure-ban
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
(VPN-kapcsolatok a Microsoft Intune-ban) [vpn-connections-in-microsoft-intune.md]



<!--HONumber=Nov16_HO1-->


