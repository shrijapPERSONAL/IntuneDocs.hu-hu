---
title: "Egyéni VPN-profilok létrehozása a Microsoft Intune-nal | Microsoft Docs"
description: "Egyéni konfigurációkat használhat VPN-profilok létrehozásához Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: e92593062ad2ed7a4098922715106f47f4e78d4f


---

# <a name="how-to-create-custom-vpn-profiles-with-microsoft-intune"></a>Egyéni VPN-profilok létrehozása a Microsoft Intune-nal

## <a name="create-a-custom-configuration"></a>Egyéni konfiguráció létrehozása
Egyéni Intune-konfigurációs szabályzatokkal VPN-profilok hozhatók létre a következőkhöz:

* Android 4 vagy újabb rendszerű eszközök
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* A Windows Phone 8.1-es vagy újabb verzióját futtató eszközök
* A Windows 10 asztali verzióját futtató regisztrált eszközök 
* Windows 10 Mobile-t futtató eszközök

Az ilyen típusú szabályzat akkor lehet hasznos, ha a szabványos Intune VPN-szabályzatok nem tartalmazzák a használni kívánt beállításokat.

## <a name="to-create-a-custom-configuration-policy"></a>Egyéni konfigurációs szabályzat létrehozása:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
5. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
6. A **Profil létrehozása** panelen töltse ki az egyéni VPN-profil **Név** és **Leírás** mezőjét.
7. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a VPN-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet egyéni eszközbeállításokat megadni:
    - **Android**
    - **iOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **macOS** (egy Apple Configuratorból exportált fájllal konfigurálva)
    - **Windows Phone 8.1**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza az **Egyéni** lehetőséget.
7. Az **Egyéni OMA-URI beállítások** panelen minden egyes megadni kívánt URI-beállításhoz válassza a **Hozzáadás** elemet, adja meg a kért adatokat, majd kattintson az **OK** gombra. Például:

   ![VPN-profil egyéni konfigurációjának párbeszédpanelje](./media/Intune_Add_VPN_URI.png)

4.  Miután megadta az összes szükséges URI-beállítást, kattintson az **OK** gombra, majd a **Profil létrehozása** panelen válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha a profilt csoportokhoz szeretné hozzárendelni, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.

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






<!--HONumber=Feb17_HO1-->


