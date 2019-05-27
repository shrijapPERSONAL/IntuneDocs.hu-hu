---
title: Egyéni beállítások hozzáadása Windows 10-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Hozzáadhat vagy létrehozhat egy egyéni profilt, amelyet a Windows 10 rendszerű eszközök OMA-URI-beállításaihoz használhat a Microsoft Intune-ban. Egyéni beállítások hozzáadásához használjon egyéni profilt.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f1935ff839b9e2aa97d002bd98d1f5dac87c390
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043038"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Egyéni beállítások használata Windows 10 rendszerű eszközökhöz az Intune-ban

A Microsoft Intune-nal egyéni beállításokat adhat hozzá vagy hozhat létre a Windows 10-eszközökhöz „egyéni profilok” használatával. Az egyéni profilok az Intune részét képezik. Akkor hasznosak, ha olyan eszközbeállításokat és funkciókat szeretne használni, amelyek nem érhetők el beépítetten az Intune-ban.

A Windows 10 egyéni profiljai az Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállításokat használják a különböző funkciók konfigurálásához. Ezekkel a beállításokkal általában a mobileszközgyártók vezérlik az eszközök funkcióit. 

A Windows 10 számos konfigurációszolgáltatói beállítást tesz elérhetővé, ilyen például a [Szabályzat-konfigurációszolgáltató (Policy Configuration Service Provider, Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Ha egy adott beállítást keres, ne feledje, hogy a [Windows 10 eszközkorlátozási profil](device-restrictions-windows-10.md) számos beépített beállítást tartalmaz. Így nem feltétlenül kell egyéni értékeket megadnia.

Ez a cikk:

- bemutatja, hogyan hozhat létre egyéni profilokat Windows 10-eszközökhöz;
- tartalmazza a javasolt OMA-URI-beállítások listáját;
- példaként bemutat egy egyéni profilt, amely megnyit egy VPN-kapcsolatot.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő beállításokat:

    - **Név**: Adja meg egy nevet a profilnak, például `windows 10 custom profile`.
    - **Description** (Leírás): Adja meg a profil leírását.
    - **Platform**: Válasszon **Windows 10 és újabb**.
    - **Profil típusa**: Válasszon **egyéni**.

4. Az **Egyéni OMA-URI-beállítások** menüben válassza a **Hozzáadás** lehetőséget. Adja meg a következő beállításokat:

    - **Név**: Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Description** (Leírás): Adjon meg egy leírást, amely áttekintést ad a beállítást, és bármilyen egyéb fontos részleteket.
    - **OMA-URI** (megkülönbözteti a kis-és nagybetűket): Adja meg az OMA-URI beállításai használni kívánt.
    - **Adattípus**: Válassza ki az adatokat fogja használni az OMA-URI-beállítás. A választható lehetőségek:

        - Sztring
        - Sztring (XML-fájl)
        - Dátum és időpont
        - Egész szám
        - Lebegőpontos szám
        - Logikai
        - Base64 (fájl)

    - **Érték**: A megadott OMA-URI társítani kívánt adatok értéket adjon meg. Az érték a választott adattípustól függ. A **Dátum és idő** típus esetén például a dátumválasztóból választhat értéket.

    Néhány beállítás megadása után válassza az **Exportálás** lehetőséget. Az **Exportálás** a hozzáadott értékek listáját hozza létre egy vesszővel tagolt (.csv) fájlban.

5. Válassza ki **OK** a módosítások mentéséhez. Szükség szerint adjon hozzá további beállításokat.
6. Ha elkészült, az Intune-profil létrehozásához kattintson az **OK** > **Létrehozás** lehetőségre. Ha a profil elkészült, megjelenik az **Eszközkonfiguráció – Profilok** listában.

## <a name="example"></a>Példa

A következő példa a **Connectivity/AllowVPNOverCellular** beállítás engedélyezését mutatja be. Ez a beállítás lehetővé teszi, hogy a Windows 10-es eszköz VPN-kapcsolatot nyisson meg mobilhálózaton keresztül.

![VPN-beállításokat tartalmazó egyéni szabályzat – példa](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A Windows 10 által támogatott konfigurációszolgáltatók (CSP-k) teljes listájáért lásd a [konfigurációszolgáltatók referenciáját](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Nem minden beállítás kompatibilis a Windows 10 összes verziójával. A [Konfigurációszolgáltatók referenciája](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) című témakörből megtudhatja, hogy az egyes CSP-k mely verziókat támogatják.

Az Intune nem támogatja a [konfigurációszolgáltatók referenciájában](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) felsorolt összes beállítást. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó cikket. Minden beállítás oldalán szerepelnek az általa támogatott műveletek. Az Intune használatára, a beállításnak támogatnia a **Hozzáadás**, **cserélje le**, és **első** műveleteket. Ha az értéket ad vissza a **első** művelet által megadott érték nem egyezik a **Hozzáadás** vagy **cserélje le** műveleteket, majd az Intune-jelentések megfelelőségi hibát.

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Következő lépésként [végezze el a profil hozzárendelését](device-profile-assign.md).
