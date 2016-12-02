---
title: "Támogatott mobileszközök és böngészők | Microsoft Intune"
description: "Az Intune által támogatott mobileszközök és számítógépek"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Támogatott mobileszközök és számítógépek

Az alábbi eszköztípusok regisztrálására és kezelésére nyílik mód:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Az eszközök regisztrálása [ezen funkciókat](/Intune/get-started/choose-how-to-manage-devices) biztosítja.

A Windows rendszerű számítógépeket másik lehetőségként az Intune PC ügyfélszoftver segítségével is kezelheti. Az Intune-számítógépügyfél a Windows 7 és újabb rendszerekkel használható, kivéve a Windows 10 Home rendszert. A számítógépek ügyfélszoftverrel történő felügyelete az [alábbi funkciókat](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) biztosítja.

A Nagyvállalati felügyeleti csomaggal rendelkező ügyfelek az Azure Active Directory (Azure AD) használatával is regisztrálhatják Windows 10 rendszerű eszközeiket.

## <a name="microsoft-intune-supported-web-browsers"></a>A Microsoft Intune által támogatott webböngészők

A különféle felügyeleti tevékenységek elvégzésére a következő két felügyeleti webhely valamelyikét kell használnia.

- [Office 365 portál](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune felügyeleti konzol](https://admin.manage.microsoft.com/)

> [!Note]
> A Microsoft Edge és a mobilböngészők nem támogatottak a felügyeleti konzolon, mivel nem támogatják a [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) összetevőt. Az Intune-konzol egy idő múlva kikerül a Silverlight-megoldásból, és az Intune összes mobileszköze és alkalmazásfelügyeleti funkciója végül [az új Microsoft Azure portálon válik majd elérhetővé](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Intune-funkció |Támogatott böngészők|
|---------|---------|
|Intune felügyeleti konzol     |  Internet Explorer 10 vagy újabb<br /><br />Google Chrome (42-es vagy korábbi verziók)<br /><br />Mozilla Firefox (a Silverlightot engedélyezni kell)<br /><br />**Megjegyzés:** A Microsoft Edge és a mobilböngészők használata nem támogatott a felügyeleti konzolon.                      
|Office 365 felügyeleti portál     |Minden böngésző, beleértve a mobilböngészőket és a felügyelt böngészőket  |
|Munkahelyi portál webhely     |**Mobileszközökön:** használja a támogatott platformhoz tartozó alapértelmezett webböngészőt   <br /><br />**Windows rendszerű számítógépeken:** Internet Explorer 10 vagy újabb, illetve Microsoft Edge<br /><br />**Mac OS X 10.9 vagy újabb:** Apple Safari    |

> [!Note]
> A Microsoft Edge és a mobilböngészők nem támogatottak a felügyeleti konzolon, mivel nem támogatják a [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) összetevőt. Az Intune-konzol egy idő múlva kikerül a Silverlight-megoldásból, és az Intune összes mobileszköze és alkalmazásfelügyeleti funkciója végül [az új Microsoft Azure portálon válik majd elérhetővé](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Office 365 portál](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Bérlői rendszergazdaként ezen a portálon kezelheti előfizetését**, beleértve a következő feladatokat, ha a rendszergazdai szerepköre lehetővé teszi őket:

- Az előfizetéshez tartozó felhasználói fiókok kezelése és a helyszíni Active Directoryból való címtár-szinkronizálás beállítása.
- A felhasználók biztonsági csoport nevű csoportjainak kezelése.
- Az Intune használatához szükséges licencek kiosztása a felhasználók számára.
- Az előfizetéshez használt tartománynév beállítása. A tartománynév határozza meg a fiókot, amellyel a felhasználók bejelentkeznek.
- Az előfizetés és a vásárlások adatainak kezelése, beleértve a birtokolt licencek számát, illetve a felhasználható felhőbeli tárhely mennyiségét.
- Az Intune szolgáltatás állapotának megtekintésére szolgáló hivatkozások használata.
- Bérlői rendszergazdaként az Office 365 portálra bejelentkezve kezelheti az előfizetést, akkor is, ha a fiókjához nincs hozzárendelve az Intune használatához szükséges licenc.
- Az Intune-licenccel rendelkező, ugyanakkor nem rendszergazdai felhasználók e portál segítségével állíthatják alaphelyzetbe a fiókjelszavukat, illetve módosíthatják a profiljukat.
- Az Office 365 portál eléréséhez a fióknak **Engedélyezett** bejelentkezési állapotúnak kell lennie. Ez az állapot nem ugyanaz, mint amikor a fióknak licence van az előfizetéshez. Alapértelmezés szerint az összes felhasználói fiók **Engedélyezett** állapotú.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Microsoft Intune felügyeleti konzol](https://manage.microsoft.com/)

**Szolgáltatás-rendszergazdaként ezen a portálon kezelhetők a napi tevékenységek**, beleértve az alábbiakat:

- Számítógépekre és mobileszközökre vonatkozó házirendek beállítása.
- Szoftverek, például szoftverfrissítések és alkalmazások feltöltése és telepítése.
- A számítógépeken futó Endpoint Protection szolgáltatás kezelése.
- Eszközállapot megtekintése és jelentések futtatása.
- Jelentkezzen be a portálra. A portálra szolgáltatás-rendszergazdák, valamint globális rendszergazda szerepkörrel rendelkező bérlői rendszergazdák jelentkezhetnek be.


A portálra szolgáltatás-rendszergazdák, valamint globális rendszergazda szerepkörrel rendelkező bérlői rendszergazdák jelentkezhetnek be. A felügyeleti konzol eléréséhez a fióknak az Intune használatához szükséges licenccel, illetve **Engedélyezett** bejelentkezési állapottal kell rendelkeznie.



<!--HONumber=Nov16_HO4-->


