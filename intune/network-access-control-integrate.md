---
title: Hálózati hozzáférés-vezérlés integrálása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A hálózati hozzáférés-vezérlési (NAC) megoldások az Intune-beli eszközök regisztrációját és megfelelőségét ellenőrzik. A NAC bizonyos működési módokat tartalmaz, és feltételes hozzáféréssel működik. Tekintse meg az előkészítés lépéseit, valamint a partneri megoldásokat.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a2d2d7eb609db07d4f41254f2937120412f2f4b1
ms.sourcegitcommit: 24d9ae0396ca410f72cc061a3c4c402835ef32a1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2018
ms.locfileid: "49643042"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Hálózati hozzáférés-vezérlés (NAC) integrálása az Intune-nal

Az Intune hálózati hozzáférés-vezérlő partnerekkel integráltan segít a szervezetek céges adatainak védelmében, amikor egy eszköz helyszíni erőforrásokhoz kísérel meg hozzáférni.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Hogyan védi az Intune és a NAC-megoldások együttese a szervezeti erőforrásokat?

A NAC-megoldások feladata az eszközregisztráció és a megfelelőségi állapot ellenőrzése az Intune-nál, hogy döntést hozhasson a hozzáférésről. Ha az eszköz nincs regisztrálva, vagy regisztrálva van, de nem tesz eleget az Intune eszközmegfelelőségi szabályzatainak, akkor az eszközt vissza kell irányítani az Intune-hoz regisztrációra és/vagy az eszközmegfelelőség ellenőrzésére.

### <a name="example"></a>Példa

Regisztrált és az Intune-nál megfelelőnek minősülő eszköz számára a NAC-megoldás engedélyezni fogja a vállalati erőforrásokhoz való hozzáférést. Engedélyezhető vagy letiltható például a felhasználók számára a vállalati Wi-Fi vagy VPN-erőforrásokhoz való hozzáférés.

## <a name="feature-behaviors"></a>Funkciók működési módjai

Azon eszközök, amelyek aktív szinkronizálást végeznek az Intune-nal, nem léphetnek **Megfelelő** / **Nem megfelelő** állapotból **Nem szinkronizált** (vagy **Ismeretlen**) állapotba. Az **Ismeretlen** állapot megfordul azon újonnan regisztrált eszközök számára, amelyek még nem estek át megfelelőségi ellenőrzésen.

Azon eszközök esetében, melyek erőforrásokhoz való hozzáférése le van tiltva, az ezt letiltó szolgáltatásnak minden felhasználót át kell irányítania a [felügyeleti portálra](https://portal.manage.microsoft.com) annak meghatározása érdekében, hogy az eszköz miért van letiltva.  Ha a felhasználók megnyitják az oldalt, az eszközeik megfelelőségét a rendszer szinkron módon újraértékeli.

## <a name="nac-and-conditional-access"></a>NAC és feltételes hozzáférés

A NAC feltételes hozzáférés használatával hoz hozzáférés-vezérlési döntéseket. További információ: [A feltételes hozzáférés használatának szokásos módjai az Intune-ban](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Az integrált hálózati hozzáférés-vezérlés működése

A követező listában megtalálhatja annak áttekintését, hogyan működik az integrált hálózati hozzáférés-vezérlés az Intune-nal való integráció esetén. Az első három (1-3.) lépés az előkészítési folyamatot mutatja be. A NAC-megoldás Intune-nal való integrálása után a 4.–9. lépés a folyamatos működést ismerteti.

![A NAC és az Intune együttműködése](./media/ca-intune-common-ways-2.png)

1. Partnertől származó NAC-megoldás regisztrációja az Azure Active Directoryban (AAD), és delegált engedélyek megadása az Intune NAC API számára.
2. Partnertől származó NAC-megoldás konfigurálása a megfelelő beállításokkal, beleértve az Intune-felderítési URL-címet.
3. Partnertől származó NAC-megoldás konfigurálása a tanúsítványalapú hitelesítéshez.
4. A felhasználó csatlakozik a vállalati Wi-Fi-hozzáférési ponthoz, vagy VPN kapcsolatot kezdeményez.
5. A partneri NAC-megoldás az Intune-nak továbbítja az eszközinformációkat, és lekérdezi az Intune-tól az eszköz regisztrációját és megfelelőségi állapotát.
6. Ha az eszköz nem felel meg vagy nincs regisztrálva, akkor a partneri NAC-megoldás felszólítja a felhasználót a regisztrálásra vagy az eszköz megfelelőségének javítására.
7. Az eszköz megkísérli újra jóváhagyatni megfelelőségét és/vagy regisztrációs állapotát.
8. Ha az eszköz már regisztrálva van és megfelel, a NAC-partnermegoldás megkapja az állapotát az Intune-tól.
9. Sikeresen létrejön a kapcsolat, amelyen keresztül az eszköz hozzáfér a vállalati erőforrásokhoz.

## <a name="next-steps"></a>További lépések

- [A Cisco ISE integrálása az Intune-nal](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [A Citrix NetScaler integrálása az Intune-nal](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [A HP Aruba Clear Pass integrálása az Intune-nal](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
- [Squadra Security Removable Media Manager integrálása az Intune-nal](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)