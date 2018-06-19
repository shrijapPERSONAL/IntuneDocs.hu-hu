---
title: A vállalati erőforrások hozzáférésének engedélyezése
description: A Wi-Fi-, VPN- és e-mail-profilokkal hozzáférést biztosíthat a felhasználóknak a szükséges fájlokhoz és erőforrásokhoz.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5bfc02f5f10ce88b992d0ea250d7b36fdf3f66dc
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31017308"
---
# <a name="enable-access-to-company-resources-with-microsoft-intune"></a>A vállalati erőforrások hozzáférésének engedélyezése a Microsoft Intune-nal

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A Microsoft Intune-alapú Wi-Fi-, VPN- és e-mail-profilokkal hozzáférést biztosíthat a felhasználóknak a munkájuk elvégzéséhez szükséges fájlokhoz és erőforrásokhoz, bárhol legyenek is. A hozzáférés védelmét tanúsítványprofilok segítik.

## <a name="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms"></a>A [Wi-Fi-profilok](wi-fi-connections-in-microsoft-intune.md) és a támogatott platformok

Vezeték nélküli hálózati beállításokat telepíthet a felhasználók számára. Ezek a beállítások megkönnyítik a felhasználók számára a vállalati hálózathoz való csatlakozást.
#### <a name="supported-platforms"></a>Támogatott platformok

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX Standard|
|---------------------|---------------------------|---|-------|------------|
|Igen (Importálhat Windows-alapú Wi-Fi-profilt)|Igen (Konfigurálhat OMA-URI-beállítást) |Igen|Igen|Igen|

## <a name="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms"></a>A [VPN-profilok](vpn-connections-in-microsoft-intune.md) és a támogatott platformok
Virtuális magánhálózati (VPN-) beállításokat alkalmazhat a felhasználókra. Ezek a beállítások megkönnyítik a felhasználók számára a vállalati hálózathoz való csatlakozást.

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX Standard|
|---------------------|---------------------------|---|-------|------------|
|Igen|Igen|Igen|Igen|Igen|

## <a name="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms"></a>Az [e-mail-profilok](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) és a támogatott platformok
Segítségükkel létrehozhatja, érvénybe léptetheti és nyomon követheti a natív e-mail-ügyfélprogram beállításait a szervezetnél található eszközökön.


| Windows 8.1 és újabb | Windows Phone 8.1 és újabb verziók | iOS | Android | Samsung KNOX Standard |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          Nem           |             Igen             | Igen |   Nem    |          Igen          |

> [!NOTE]
> [Ez az Intune csapata által írt blogbejegyzés](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) tájékoztatást nyújt a Windows Phone 8.1 Wi-Fi-profilnak az OMA-URI-beállításokkal történő konfigurálásáról.

## <a name="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms"></a>A [tanúsítványprofilok](secure-resource-access-with-certificate-profiles.md) és a támogatott platformok
Segít a vállalati erőforrások elérésének biztonságossá tételében, beleértve a vezeték nélküli hálózatokat és a VPN-kapcsolatokat.


| Windows 8.1 és újabb | Windows Phone 8.1 és újabb verziók | iOS | Android | Samsung KNOX Standard |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          Igen          |             Igen             | Igen |   Igen   |          Igen          |

