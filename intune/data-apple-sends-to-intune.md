---
title: Az Apple által az Intune-nak küldött adatok
titleSuffix: Microsoft Intune
description: Az Apple által az Intune-nak küldött adatok listája.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4362983bbcdb78f82ce7b16f675c6f61fbefd1e1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396327"
---
# <a name="data-apple-sends-to-intune"></a>Az Apple által az Intune-nak küldött adatok

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ha a következő Apple-szolgáltatások bármelyike engedélyezve van egy eszközön, a Microsoft Intune kapcsolatot létesít az Apple-lel, hogy felhasználói és eszközadatokat osszon meg vele:

- [Apple Készülékregisztrációs program (DEP)](device-enrollment-program-enroll-ios.md)
- [Apple MDM Push-tanúsítvány (APNs)](apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](vpp-apps-ios.md)

Mielőtt a Microsoft Intune létrehozhatná a kapcsolatot, Önnek létre kell hoznia egy Apple-fiókot minden Apple-szolgáltatáshoz.

A következő táblázat az Apple-eszközök által az Intune-nak küldött adatokat sorolja fel. [Az Intune is küld adatokat az Apple-nek](data-intune-sends-to-apple.md). 

| Szolgáltatás | Üzenet | Az Intune-nak küldött adat | Használt |
|:---:|:---:|:---:| ---|
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | MessageType | Az üzenet típusa: hitelesítés. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | Témakör | A témakör, amelyet az eszköz fogadni fog. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | MesUDID | Az eszköz UDID-azonosítója. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | OSVersion | Az eszköz operációs rendszerének verziója. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | BuildVersion | Az eszköz alverziószáma. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | Terméknév | Az eszköz termékneve. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | a sorozatszám | Az eszköz sorozatszáma. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | IMEI | Az eszköz IMEI-száma. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Hitelesítés | MEID | Az eszköz mobilkészülék-azonosító száma (MEID) |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Témakör | A témakör, amelyet az eszköz fogadni fog. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UDID | Az eszköz UDID-azonosítója. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Azonosító | Az eszköz leküldési azonosítója. A kiszolgálónak ezt a frissített azonosítót kell használnia, amikor leküldéses értesítéseket küld az eszközre. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | PushMagic | A leküldéses értesítés üzenetébe belefoglalandó PushMagic-sztring.  |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UnlockToken | Az eszköz zárolásának feloldására használható adatblob. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | AwaitingConfiguration | Ha igaz értékre van beállítva, akkor az eszköz egy DeviceConfigured MDM-parancsra vár mielőtt folytatná a Telepítési segéd következő lépésével.  |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kivétel | MessageType | Az üzenet típusa: kivétel. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kivétel | Témakör | A témakör, amelyet az eszköz fogadni fog. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kivétel | UDID | Az eszköz UDID-azonosítója |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM protokoll | Állapot | Állapot.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM protokoll | UDID |Az eszköz UDID-azonosítója.  |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM protokoll | CommandUUID | Annak a parancsnak az UUID-azonosítója, amelyre ez a válasz. |
| [APN szolgáltatás](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM protokoll | ErrorChain | A bekövetkezett hibasorozatot képviselő szótárakból álló tömb.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Sorozatszám | Az eszköz sorozatszáma. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | modell | Az eszköz modellneve. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Leírás | Az eszköz leírása. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Szín | Az eszköz színe. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Eszközcímke | Az eszköz eszközcímkéje. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Profil állapota | A profil telepítési állapota. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Profil UUID | A hozzárendelt profil UUID-azonosítója. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Profil hozzárendelésének időpontja | ISO 8601 formátumú időbélyeg, amely azt jelzi, hogy a profil mikor lett az eszközhöz rendelve. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Profil leküldésének időpontja | ISO 8601 formátumú időbélyeg, amely azt jelzi, hogy a profil mikor lett leküldve az eszközre.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Eszköz hozzárendelésének dátuma | ISO 8601 formátumú időbélyeg, amely azt jelzi, hogy mikor regisztrálták az eszközt a Készülékregisztrációs programban. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Az eszköz hozzárendelője | Az eszközt hozzárendelő személy e-mail-címe. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Operációs rendszer | Az eszköz operációs rendszere. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Készülékregisztrációs program jogkivonata | Eszközcsalád | Az eszköz Apple-termékcsaládja. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Apple felhasználói azonosító | Az Apple által generált felhasználói azonosító. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | alkalmazásleírás | VPP-alkalmazás leírása. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | alkalmazásikon | VPP-alkalmazás Apple által szolgáltatott ikonjának URL-címe. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Application Id | Az adamsId-ként is ismert Apple-alkalmazásazonosító. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | alkalmazásnév | VPP-alkalmazás neve. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | assignedCount | Az egy alkalmazáshoz rendelt licencek száma. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | availableCount | Az alkalmazáshoz hozzá nem rendelt licencek száma. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | bundleId | Alkalmazás csomagazonosítója. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | a szerzői jog | Alkalmazás szerzői jogi információi. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | CountryCode | VPP-program országkódja. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | deviceAssignable | Az Apple „igaz” értéket ad vissza, ha a rendszergazda eszközlicencet rendelhet egy alkalmazáshoz. Ha nem, akkor a visszatérési érték „hamis”. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | facilitatorMemberId | VPP-fiók egyeztető tagazonosítója.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | műfajok | Alkalmazás műfajai. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Intune UserId guid | Az Intune által létrehozott GUID. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | isIrrevocable | Az Apple „igaz” értéket ad vissza, ha a licenc nem vonható vissza. Ha visszavonható, akkor a visszatérési érték „hamis”. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Licencazonosító | Az Apple által egy adott licenc azonosítására generált azonosító. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Hely | Az Apple VPP-konfigurációs adatai között tárolt hely. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | A felügyelt AppleId egyszerű felhasználóneve | Felhasználó, rendszergazda vagy egyeztető tag Apple-azonosító e-mail-címe. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | OrganizationId | A szervezet Apple által kiadott azonosítója. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | pricingParam | Egy alkalmazás Apple-díjszabástípusa. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | productType | VPP-alkalmazás terméktípusa. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | retiredCount | Az egy alkalmazáshoz tartozó kivont licencek száma. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | totalCount | Az egy alkalmazáshoz megvásárolt licencek teljes száma. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | url | Alkalmazás iTunes áruházbeli URL-címe.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP-token | Felhasználói állapot | A felhasználó állapota Apple VPP-programokban. |


Ha nem szeretné használni az Apple szolgáltatásait az Intune-nal, és törölni szeretné az adatokat, le kell tiltania a Microsoft Intune Apple-jogkivonatot és törölnie kell az Apple-fiókját. A fiókkezelésről az Apple-fiókban tudhat meg többet.


