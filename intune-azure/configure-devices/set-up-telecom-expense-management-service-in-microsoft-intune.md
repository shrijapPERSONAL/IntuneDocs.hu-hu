---
title: "Távközlésiköltség-kezelő szolgáltatások beállítása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A Saaswedo távközlésiköltség-kezelő szolgáltatás konfigurálása az Intune-nal való integráláshoz."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Távközlésiköltség-kezelő szolgáltatások beállítása a következőben: Intune az Azure-on – előzetes
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune egy külső szoftverfejlesztő, a Saaswedo Datalert távközlésiköltség-kezelő megoldásával van integrálva. A Datalert olyan valós idejű távközlésiköltség-kezelő szoftver, amely lehetővé teszi a távközlési adatok használatának kezelését, valamint segít elkerülni az adathasználati és barangolási keret költséges és váratlan túllépését az Intune által felügyelt eszközökön. Az Intune és a Datalert integrációja lehetővé teszi, hogy központilag állítson be, figyeljen és alkalmazzon roaming- és belföldi adathasználati korlátokat automatikus riasztások használatával abban az esetben, ha a korlátok túllépnek meghatározott küszöbértékeket. A szolgáltatás konfigurálásával különféle műveleteket alkalmazhat személyekre vagy végfelhasználói csoportokra, például letilthatja a roamingot, ha a felhasználók túllépik a küszöbértéket. Az adathasználati és figyelési információkat biztosító jelentések a Datalert kezelőkonzolján érhetők el.

A Datalert szolgáltatás az Intune-nal való használatához beállításokat kell konfigurálnia a Datalert-konzolon és az Intune-ban. A kapcsolatot be kell kapcsolni a Datalert szolgáltatásban és az Intune-ban is. Ha a rendszer a Datalert oldalán engedélyezi a kapcsolatot, az Intune oldalán viszont nem, akkor az Intune fogadja ugyan a kommunikációt, de figyelmen kívül hagyja azt.

>[!NOTE]
>Ha engedélyezni szeretné ezt a funkciót a próbaverziós bérlőben, az aktiválás érdekében [forduljon a Microsoft támogatási szolgáltatáshoz](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), míg a szükséges szoftverlicencekért a Datalert támogatási szolgáltatáshoz.

## <a name="supported-platforms"></a>Támogatott platformok

- Samsung KNOX
- iOS 8.0 és újabb verziók

## <a name="prerequisites"></a>Előfeltételek

- Microsoft Intune-előfizetés
- Előfizetés a Datalert távközlésiköltség-kezelő szolgáltatásra

## <a name="list-of-telecom-expense-management-providers"></a>A távközlésiköltség-kezelő szolgáltatók listája

Az Intune jelenleg a következő távközlésiköltség-kezelő szolgáltatókkal képes együttműködni:

[Saaswedo Datalert távközlésiköltség-kezelő szolgáltatás](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Az Intune konfigurálása a Datalert szolgáltatással való együttműködéshez

 

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Beállítás** > **Távközlési költségek kezelése** lehetőséget.
2. A **Távközlési költségek kezelése** szakaszban válassza a **Kapcsolat állapota** lehetőséget.

3. Válassza a **TEM-szolgáltatók listája** lehetőséget, majd a megjelenő listából válassza ki a szolgáltatót. Ekkor megjelenik a szolgáltató specifikus oldala. A Saaswedo esetén a Datalert oldala jelenik meg. Előfizetés vásárlásához a Saaswedo Datalert szolgáltatást kell használnia.

4. A **Datalert** kezelőkonzolján:

    a. Nyissa meg a **Settings** (Beállítások) lapot, majd keresse meg az **MDM configuration** (MDM-konfiguráció) szakaszt.

    b. Válassza a **Unlock** (Zárolás feloldása) lehetőséget annak engedélyezéséhez, hogy megadhasson beállításokat a lapon.

    c. **Server MDM** (Kiszolgálói MDM) esetén válassza a **Microsoft Intune** elemet.

    d. A **Tenant ID** (Bérlőazonosító) elemnél adja meg Intune-bérlőazonosítóját, majd kattintson a **Connection** (Kapcsolat) gombra. Amikor a **Connection** (Kapcsolat) elemet választja, a Datalert szolgáltatás bejelentkezik az Intune-ba annak ellenőrzése érdekében, hogy nincsenek már meglévő kapcsolatok a Datalert és az Intune között. Néhány másodperc elteltével megjelenik a Microsoft bejelentkezési oldala, amelyet a Datalert Azure-beli hitelesítése követ.

    e. A Microsoft hitelesítési oldalán válassza az **Elfogadás** lehetőséget. Ekkor megnyílik a Datalert „thank you” („köszönjük”) lapja, amely néhány másodperc múlva bezárul. A Datalert ellenőrzi a kapcsolatot, majd az ellenőrzött elemek listája mellett zöld színű pipákat jelenít meg. Sikertelen ellenőrzés esetén vörös színű üzenet jelenik meg. Ebben az esetben forduljon segítségért a Datalert ügyfélszolgálatához.

5. Várjon pár percet, majd nyissa meg az Azure-portált, és ellenőrizze, hogy a kapcsolat **Aktív** állapotú-e. 

    >[!NOTE]
    >A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Térjen vissza a Datalert kezelőkonzoljára, majd konfigurálja az adatsorokat:

    a. Nyissa meg a **Settings** (Beállítások) lapot.

    b. Nyissa meg a **Setup** (Beállítás) varázslót, és kövesse a varázsló lépéseit.



A Datalert szolgáltatás most már aktív, és megkezdi az adathasználat figyelését, valamint a mobil és roaming-adatforgalom letiltását azokon az eszközökön, amelyek túllépik a beállított használati korlátokat.

## <a name="turning-off-the-datalert-service"></a>A Datalert szolgáltatás kikapcsolása

Ha letiltja a Datalert szolgáltatást az Azure-portálon:

- A rendszer az eszközökön a használati korlátok korábbi túllépései miatt végrehajtott valamennyi műveletet visszavonja.
- A felhasználók számára ettől kezdve nincs letiltva az adathozzáférés és a roaming.
- Az Intune továbbra is fogadja a szolgáltatástól érkező jeleket, de figyelmen kívül hagyja őket.

**A szolgáltatás kikapcsolása**

1. Az Azure Portal **Távközlési költségek kezelése** paneljén válassza a **Letiltás** lehetőséget.

2. Válassza a **Mentés** lehetőséget.

## <a name="viewing-data-usage-and-roaming-reports"></a>Az adathasználati és roamingjelentések megtekintése

Az adathasználati jelentések jelenleg csak a Saaswedo Datalert kezelőkonzolján érhetők el.



<!--HONumber=Feb17_HO2-->


