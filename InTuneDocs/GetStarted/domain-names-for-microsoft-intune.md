---
title: "A Microsoft Intune szolgáltatásban használt tartománynevek | Microsoft Intune"
description: "Intune-tartománynév hozzáadása"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32723f5b2c92073dda43a0b1f36a48ded0e13ba3
ms.openlocfilehash: 2adbe1e4a92af5302550a8b78069bc49d725dbc3


---



# Egyéni Microsoft Intune-tartománynevek

Az egyéni tartományok hozzáadásának és hitelesítésének lépései [az Azure Active Directoryban is végrehajthatók](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Amikor egy szervezet előfizet a Microsoft egy felhőszolgáltatására, például az Intune-ra, egy, a következőhöz hasonló, az Azure Active Directoryban tárolt kezdeti tartománynevet kap: **tartomanynev.onmicrosoft.com**. Ebben a példában a **tartomanynev** a regisztrációkor választott tartománynév, az **onmicrosoft.com** pedig az előfizetéshez hozzáadott fiókokhoz rendelt utótag.

A kezdeti tartománynév nem nevezhető át és nem távolítható el. Az Intune-nal azonban hozzáadhat, hitelesíthet és eltávolíthat egyéni tartományneveket, ami segít az üzleti identitás megtartásában.

## Egyéni tartomány hozzáadása és hitelesítése 

1. Nyissa meg az [Office 365 felügyeleti portálját](https://portal.office.com/Admin/Default.aspx), és jelentkezzen be a rendszergazdai fiókjával.
    > [!IMPORTANT]
    > A Microsoft Intune felhasználóinak, csoportjainak és tartományainak kezelési helyéről részletes leírást     [Az Intune-fiókportál mostantól az Office 365 felügyeleti portállal közösen működik](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) című közleményen találhat.
2. A navigációs ablakban kattintson a **Beállítások** &gt; **Tartományok** elemre.
3. Kattintson a **Tartomány felvétele** gombra, és írja be az egyéni tartománynevet.
4. A megnyíló **Tartomány hitelesítése** párbeszédpanelen megtalálhatja a DNS-szolgáltatón létrehozandó TXT-rekord értékeit.
    - **GoDaddy-felhasználók:** Az Office 365 felügyeleti portálja a GoDaddy bejelentkezési oldalára irányít át. A hitelesítő adatok megadása és a tartományváltást engedélyező megállapodás elfogadása után a TXT-rekord automatikusan létrejön. Alternatív módszerként [a TXT-rekord manuálisan is létrehozható](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Register.com-felhasználók:** Kövesse a TXT típusú rekord létrehozására vonatkozó [részletes utasításokat](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify).

    > [!TIP] 
    > A DNS-szolgáltató módosításakor hozzon létre egy DNS-aliast (CNAME) a [Windows-eszközök regisztrációjához](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

Hibrid felhő használata estén az egyéni tartománynév megadása, valamint az után, hogy hitelesítettük, hogy a tartomány az Ön szervezetéhez tartozik, továbbra is a helyszíni Active Directoryban felügyelheti a felhasználói fiókokat, majd szinkronizálhatja a tartományt az Azure AD szolgáltatással.

## Helyszíni felhasználók szinkronizálása az Azure AD szolgáltatással##

1. [Adja hozzá az egyszerű felhasználónévi utótagot](https://technet.microsoft.com/en-us/library/cc772007.aspx) az egyéni tartományhoz a helyszíni Active Directoryban.
2. Állítsa be az egyszerű felhasználónévi utótagot az importálni kívánt helyszíni felhasználóknak.
3. Futtassa [az Azure AD Connect szinkronizálási szolgáltatást](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) a helyszíni felhasználók az Azure AD-val való integrálásához.
4. Miután a felhasználói fiókok adatait sikeresen szinkronizálta, az [Office 365 felügyeleti portállal](https://portal.office.com/Admin/Default.aspx) hozzájuk rendelheti a Microsoft Intune-licenceket.

### További információ

[A kezdeti onmicrosoft.com tartománnyal kapcsolatos információk (Office 365)](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


