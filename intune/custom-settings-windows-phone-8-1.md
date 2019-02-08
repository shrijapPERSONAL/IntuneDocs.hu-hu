---
title: Egyéni beállítások hozzáadása Windows Phone 8.1 rendszerű eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Hozzáadhat vagy létrehozhat egy egyéni profilt, amelyet a Windows Phone 8.1 rendszerű eszközök OMA-URI-beállításaihoz használhat a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 90ead0f7c00b1e451641042d8a3ef3cb8da957f3
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840297"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Egyéni beállítások használata Windows Phone 8.1 rendszerű eszközökhöz az Intune-ban

A Microsoft Intune-nal egyéni beállításokat adhat hozzá vagy hozhat létre a Windows Phone 8.1 rendszerű eszközökhöz „egyéni profilok” használatával. Az egyéni profilok az Intune részét képezik. Akkor hasznosak, ha olyan eszközbeállításokat és funkciókat szeretne használni, amelyek nem érhetők el beépítetten az Intune-ban.

A Windows Phone 8.1 egyéni profiljai az Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállításokat használják a különböző funkciók konfigurálásához. Ezekkel a beállításokkal általában a mobileszközgyártók vezérlik az eszközök funkcióit.

Ebből a cikkből megtudhatja, hogyan hozhat létre egyéni profilt Windows Phone 8.1 rendszerű eszközökhöz. 

## <a name="create-the-profile"></a>A profil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő beállításokat:

    - **Név**: Adja meg egy nevet a profilnak, például `windows phone custom profile`.
    - **Description** (Leírás): Adja meg a profil leírását.
    - **Platform**: Válasszon **Windows Phone 8.1-es**.
    - **Profil típusa**: Válasszon **egyéni**.

4. Az **Egyéni OMA-URI-beállítások** menüben válassza a **Hozzáadás** lehetőséget. Adja meg a következő beállításokat:

    - **Név**: Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Description** (Leírás): Adjon meg egy leírást, amely áttekintést ad a beállítást, valamint egyéb releváns információkkal segítségével keresse meg a profilt.
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

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Következő lépésként [végezze el a profil hozzárendelését](device-profile-assign.md).

Tekintse meg, hogyan hozhat létre egyéni profilt [Windows 10 rendszerű eszközökön](custom-settings-windows-10.md).
