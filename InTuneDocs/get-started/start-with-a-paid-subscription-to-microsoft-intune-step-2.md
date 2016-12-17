---
title: "Egyéni tartománynév beállítása | Microsoft Intune"
description: "Egyéni tartománynév felvétele az Intune-előfizetésbe"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 26b019b2b4c079daa89d15c783be0abf2b61dfee


---


# <a name="configure-a-custom-domain-name"></a>Állítson be egy egyéni tartománynevet

Amikor egy szervezet előfizet a Microsoft egy felhőszolgáltatására, például az Intune-ra, egy, a következőhöz hasonló, az Azure Active Directoryban (AD) tárolt kezdeti tartománynevet kap: **tartomanynev.onmicrosoft.com**. Ebben a példában a **tartomanynev** a regisztrációkor választott tartománynév, az **onmicrosoft.com** pedig az előfizetéshez hozzáadott fiókokhoz rendelt utótag. Ha a szervezete egyéni tartománnyal rendelkezik, saját Intune-példányát beállíthatja arra, hogy ezt a tartományt használja az előfizetéskor megadott tartománynév helyett.

Mielőtt felhasználói fiókokat hozna létre, vagy szinkronizálná a helyi Active Directoryt, célszerű eldöntenie, hogy az .onmicrosoft.com tartományt fogja-e használni, vagy egyéni tartományneve(ke)t kíván-e hozzáadni. Az egyéni tartománynév beállítása a felhasználók hozzáadása előtt megkönnyítheti az előfizetéshez tartozó felhasználói azonosítók kezelését, mivel így a felhasználók azokkal a hitelesítő adatokkal jelentkezhetnek be, amelyeket a tartomány egyéb erőforrásainak elérésére is használnak.

Amikor előfizet egy felhőalapú Microsoft-szolgáltatásra, az adott szolgáltatáspéldány az identitás- és címtárszolgáltatásokat biztosító [Microsoft AD-bérlőjévé](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) válik. És mivel az Intune-t ugyanúgy lehet beállítani arra, hogy az Ön szervezetének egyéni tartománynevét használja, mint bármely más Azure AD-bérlőt, az [Add your domain](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) (Egyéni tartomány felvétele) című témakör útmutatását követheti.

> [!TIP]
> További információt az egyéni tartománynak egy felhőalapú Microsoft-szolgáltatással való használatáról az [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) (Az Azure Active Directoryban használt egyéni tartománynevek elméleti áttekintése) című témakör tartalmaz.

A kezdeti tartománynév nem nevezhető át és nem távolítható el. Az Intune-nal azonban hozzáadhat, hitelesíthet és eltávolíthat egyéni tartományneveket, ami segít az üzleti identitás megtartásában.

## <a name="to-add-and-verify-your-custom-domain"></a>Egyéni tartomány hozzáadása és hitelesítése

1. Nyissa meg az [Office 365 felügyeleti portálját](https://portal.office.com/Admin/Default.aspx), és jelentkezzen be a rendszergazdai fiókjával.

2. A navigációs ablakban kattintson a **Beállítások** &gt; **Tartományok** elemre.

3. Kattintson a **Tartomány felvétele** gombra, és írja be az egyéni tartománynevet.

4. A megnyíló **Tartomány hitelesítése** párbeszédpanelen megtalálhatja a DNS-szolgáltatón létrehozandó TXT-rekord értékeit.
    - **GoDaddy-felhasználók:** Az Office 365 felügyeleti portálja a GoDaddy bejelentkezési oldalára irányít át. A hitelesítő adatok megadása és a tartományváltást engedélyező megállapodás elfogadása után a TXT-rekord automatikusan létrejön. Alternatív módszerként [a TXT-rekord manuálisan is létrehozható](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Register.com-felhasználók:** Kövesse a TXT típusú rekord létrehozására vonatkozó [részletes utasításokat](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify).

    > [!TIP]
    > A DNS-szolgáltató módosításakor hozzon létre egy DNS-aliast (CNAME) a [Windows-eszközök regisztrációjához](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

Az egyéni tartományok hozzáadásának és hitelesítésének lépései [az Azure Active Directoryban is végrehajthatók](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Tudjon meg többet [a kezdeti onmicrosoft.com tartománnyal kapcsolatban (Office 365)](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US).

>[!div class="step-by-step"]

>[&larr; **Bejelentkezés az Intune-ba**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Felhasználók hozzáadása az Intune-hoz** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Dec16_HO2-->


