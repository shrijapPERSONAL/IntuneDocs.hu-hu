---
title:
- "Mobilalkalmazás-kezelési hibaelhárítás | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Mobilalkalmazás-kezelési hibaelhárítás

Ha a mobilalkalmazás-kezeléssel kapcsolatos problémába ütközik, a megoldás keresését kezdje a jelen anyaggal. Ez a témakör néhány gyakori problémát és azok megoldását ismerteti.


**A probléma leírása:** Az Azure-konzolról kapott eszközregisztrációs szabályzat nélkül iOS- és Android-eszközökön a MAM nem kezeli a Skype Vállalati verzió alkalmazást.

Megoldás: A Skype Vállalati verzió alkalmazáshoz be kell állítani a modern hitelesítést.  Kövesse a [Bérlő engedélyezése modern hitelesítéshez](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) című részben található utasításokat a modern hitelesítés beállításához Skype-hoz.

**A probléma leírása:** Eszközregisztrációs szabályzatok nélkül az MAM nem kezel semmilyen (támogatott Office-alkalmazást) [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] egyetlen felhasználó esetében sem.
 
Megoldás: Győződjön meg róla, hogy a felhasználó rendelkezik Intune-licenccel.  

**A probléma leírása:** Az informatikai rendszergazda nem tud MAM-szabályzatokat konfigurálni az Azure-portálon

Megoldás: A következő szerepkörök rendelkeznek hozzáféréssel az Azure-portálhoz:

- Globális rendszergazda; ez a szerepkör az [Office-portálon](http://portal.office.com/) állítható be.
- Tulajdonos; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.
- Közreműködő; ez a szerepkör az [Azure-portálon](https://portal.azure.com/) állítható be.

A szerepkörök beállításával kapcsolatban a [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) című részben talál segítséget. 

**A probléma leírása:** Az alkalmazásjelentésben nem szerepelnek az(ok) a felhasználó(k), aki(ke)t nemrégiben céloztunk meg az MAM-szabályzattal.

Megoldás: Újonnan megcélzott felhasználó esetében akár 24 órát is igénybe vehet, hogy célzott felhasználóként megjelenjen a jelentésekben. 

**A probléma leírása:** A szabályzatok módosításainak / frissítéseinek életbe lépése akár 8 órát is igénybe vehet.  

Megoldás: A végfelhasználó jelentkezzen ki az alkalmazásból majd jelentkezzen be újra, ezzel kikényszeríti a szinkronizálást a szolgáltatással.  

**A probléma leírása:** Az MAM-szabályzat nem kezeli az Apple DEP-eszközöket

Megoldás: Győződjön meg róla, hogy Felhasználói affinitást használ az Apple Eszközregisztrációs programmal (DEP). Felhasználói affinitásra minden olyan alkalmazás esetében szükség van, amely felhasználói hitelesítést igényel DEP alatt.
Az iOS DEP-regisztrációról bővebben lásd: [Az Eszközregisztrációs program vállalati tulajdonú iOS-eszközeinek regisztrálása](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### További információ
- [A mobilalkalmazás-kezelés beállításának ellenőrzése](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


