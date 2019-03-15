---
title: Állítson be egy egyéni tartománynevet
titlesuffix: Microsoft Intune
description: Egyéni tartománynév hozzáadása a Microsoft Intune-előfizetéshez
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba1759b04d2319b9a9d7fd911a885e297c4f23f6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460818"
---
# <a name="configure-a-custom-domain-name"></a>Állítson be egy egyéni tartománynevet

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ez a témakör arról tájékoztatja a rendszergazdákat, hogy miképpen szabhatják testre a bejelentkezést egy DNS CNAME rekord létrehozásával a Microsoft Intune-ban.

Amikor egy szervezet előfizet a Microsoft egy felhőszolgáltatására, például az Intune-ra, a következőhöz hasonló, az Azure Active Directoryban (AD) tárolt kezdeti tartománynevet kap: **tartomanynev.onmicrosoft.com**. Ebben a példában a **tartomanynev** a regisztrációkor választott tartománynév, az **onmicrosoft.com** pedig az előfizetéshez hozzáadott fiókokhoz rendelt utótag. Saját szervezete egyéni tartományát konfigurálhatja az Intune elérésére az előfizetéskor megadott tartománynév helyett.

Mielőtt felhasználói fiókokat hozna létre, vagy szinkronizálná a helyi Active Directoryt, célszerű eldöntenie, hogy az .onmicrosoft.com tartományt fogja-e használni, vagy egyéni tartományneve(ke)t kíván-e hozzáadni. Az egyéni tartomány beállítása a felhasználók hozzáadása előtt egyszerűbbé teheti a felhasználók kezelését. Ez lehetővé teszi, hogy a felhasználók a tartomány egyéb erőforrásainak elérésére használt hitelesítő adatokkal jelentkezhessenek be.

Amikor előfizet egy felhőalapú Microsoft-szolgáltatásra, az adott szolgáltatáspéldány az identitás- és címtárszolgáltatásokat biztosító [Microsoft AD-bérlőjévé](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) válik. És mivel az Ön szervezetének egyéni tartománynevét használja az Intune konfigurálása ugyanaz, mint a más Azure AD-bérlőt, használhatja az adatokat, és eljárások található [a tartomány hozzáadása](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Az egyéni tartományok kapcsolatos további információkért lásd: [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) (Az Azure Active Directoryban használt egyéni tartománynevek elméleti áttekintése) .

A kezdeti onmicrosoft.com tartománynév nem nevezhető át és nem távolítható el. Hozzáadhat, ellenőrizhet vagy eltávolíthat az Intune-nal használt egyéni tartományneveket vállalata egyértelmű identitásának megőrzése érdekében.

## <a name="to-add-and-verify-your-custom-domain"></a>Egyéni tartomány hozzáadása és hitelesítése

1. Lépjen a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com/) , és jelentkezzen be a rendszergazdai fiókjával.

2. A navigációs ablakban kattintson a **Beállítás** &gt; **Tartományok** elemre.

3. Kattintson a **Tartomány felvétele** gombra, és írja be az egyéni tartománynevet. Kattintson a **Tovább** gombra.
   ![Képernyőkép a Microsoft 365 felügyeleti központ > tartományok kiválasztásáról és a egy új tartomány neve, hozzáadott](./media/domain-custom-add.png)
4. A megnyíló **Tartomány hitelesítése** párbeszédpanelen megtalálhatja a DNS-szolgáltatón létrehozandó TXT-rekord értékeit.
    - **GoDaddy-felhasználók**: A Microsoft 365 felügyeleti központban átirányítja a GoDaddy bejelentkezési oldalára. A hitelesítő adatok megadása és a tartományváltást engedélyező megállapodás elfogadása után a TXT-rekord automatikusan létrejön. Alternatív módszerként [a TXT-rekord manuálisan is létrehozható](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Register.com-felhasználók**: Kövesse a [részletesen](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) a TXT-rekord létrehozásához.

Az egyéni tartományok hozzáadásának és hitelesítésének lépései [az Azure Active Directoryban is végrehajthatók](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Tudjon meg többet [a kezdeti onmicrosoft.com tartománnyal kapcsolatban (Office 365)](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A).
