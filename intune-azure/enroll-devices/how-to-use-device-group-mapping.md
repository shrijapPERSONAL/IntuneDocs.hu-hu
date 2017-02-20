---
title: "Eszközkategóriák használata az Intune-ban | Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: az a témakör azon eszközkategóriák használatát ismerteti, amelyek közül a felhasználók választhatnak eszközük Intune-os regisztrálásakor."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1609ed2f127fe9d7d1f1c3b3e923bd12f1088200
ms.openlocfilehash: 41b3cfb8006a7390094d01b4f0fdc38417e858be


---

# <a name="map-device-groups"></a>Eszközcsoportok leképezése


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune eszközkategóriáival az eszközöket a definiált kategóriák alapján automatikusan felveheti csoportokba, így egyszerűsítve az eszközfelügyeletet.

Az eszközkategóriák a következő munkafolyamatot használják:
1.    Hozzon létre kategóriákat, amelyek közül a felhasználók választani fognak az eszközük regisztrálásakor
4.    Amikor a végfelhasználók regisztrálják eszközüket, csak az Ön által meghatározott kategórialistából választhatnak. Ha az eszköz már regisztrálva van, a Vállalati portál alkalmazás következő használatakor a végfelhasználónak választani kell egy kategóriát.


Bármilyen tetszés szerinti eszközkategóriát létrehozhat, például:
- Pénztári eszközök
- Bemutatóeszközök
- Értékesítés
- Könyvelés
- Manager

## <a name="how-to-configure-device-categories"></a>Az eszközkategóriák konfigurálása

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. lépés - Eszközkategóriák létrehozása az Azure Portal Intune panelén
1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök regisztrálása** lehetőséget.
3. A **Beléptetés** panelen válassza az **Eszközkategóriák** elemet.
4. Az **Eszközkategóriák** lapon a **Létrehozás** elemmel hozhat létre új kategóriát.
5. A következő panelen töltse ki az új kategória **Név** és **Leírás** mezőjét (utóbbi nem kötelező).
6. Ha végzett, kattintson a **Létrehozás** gombra. Az imént létrehozott kategória bekerül a listába.

Azure Active Directory biztonsági csoportok létrehozásakor az eszközkategória nevét fogja használni a 2. lépésben.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. lépés - Azure Active Directory biztonsági csoportok létrehozása
Ebben a lépésben az eszközkategória és az eszközkategória-név alapján dinamikus csoportokat fog létrehozni az Azure-portálon.

A folytatáshoz tekintse meg a [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) (Speciális szabályok létrehozása attribútumok használatával) című témakört az Azure Active Directory dokumentációjában. 

Ezen szakasz információi alapján hozzon létre speciális szabállyal egy eszközcsoportot a **deviceCategory** attribútum segítségével, például így: (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Ha vannak konfigurált eszközcsoportok, amikor a felhasználók regisztrálják eszközüket, meg fog jelenni számukra az Ön által beállított kategóriák listája. A kategória kiválasztását és a regisztráció befejezését követően az eszköz a kiválasztott kategóriának megfelelő Active Directory biztonsági csoportba kerül.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>A felügyelt eszközök kategóriáinak megtekintése
1.    Az Azure Portal Intune panelén válassza az **Eszközök és csoportok** lehetőséget.

2.    A **Felügyelet** alatt kattintson a **Minden eszköz** elemre.

3.    Az eszközlistában keresse meg a **Kategória** oszlopot.

Ha a **Kategória** oszlop nem látható, kattintson az **Oszlopok** elemre, a listából válassza a **Kategória** elemet, és kattintson az **Alkalmaz** gombra.

### <a name="to-change-the-category-of-a-device"></a>Eszköz kategóriájának módosítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök és csoportok** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Felügyelet** > **Minden eszköz** lehetőséget.
5. Az eszközlistából válassza ki a kívánt eszközt, majd az eszköz tulajdonságainak panelén válassza a **Felügyelet** > **Tulajdonságok** lehetőséget.
6. A következő panelen a kijelölt eszköz **Eszközkategória** tulajdonságát átállíthatja a korábban konfigurált kategórianevek bármelyikére.



## <a name="further-information"></a>További információ
- Az Azure Portalon szerkesztheti az eszközkategóriákat, de ha így tesz, akkor manuálisan kell módosítania az Azure Active Directoryban az adott kategóriára hivatkozó biztonsági csoportokat.

- Ha törli valamelyik kategóriát, az ahhoz rendelt eszközöknél a **Nincs hozzárendelve** kategórianév jelenik meg.





<!--HONumber=Feb17_HO2-->

