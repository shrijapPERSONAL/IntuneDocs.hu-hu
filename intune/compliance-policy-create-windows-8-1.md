---
title: Windows 8.1 megfelelőségi beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a Microsoft Intune-ban a Windows 8.1 és Windows Phone 8.1-es eszközök megfelelőségi beállításakor használható beállításokról. A minimális és maximális operációs rendszeren, jelszóra és hosszát, a megfelelőség ellenőrzése az adattárolási és további titkosítást.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ed863378616f8001beab89177c642404287e7d3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59893889"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Windows 8.1-beállítások az eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk felsorolja és ismerteti a különböző megfelelőségi beállítások az Intune-ban Windows 8.1-eszközökön konfigurálható. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat az egyszerű jelszavak blokkolása, állítsa be a minimális és maximális operációsrendszer-verzió még.

Ez a funkció az alábbiakra vonatkozik:

- Windows Phone 8.1
- Windows 8.1 és újabb

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform**válassza **Windows Phone 8.1-es** vagy **Windows 8.1 és újabb verziók**.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Operációs rendszer szükséges minimális verziója**: Adja meg a által támogatott minimális verzió. Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, a nem megfelelő rendszer jelenti. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Adja meg a megengedett maximális verziója. Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabályban megadott, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz nem fér hozzá a munkahelyi erőforrásokhoz, amíg nem módosítja a szabályt, amely engedélyezi az operációs rendszer verzióját.

Windows 8.1-es számítógépek esetén például a visszaadott verzió a **3**-as. Ha az operációs rendszer verziószabálya Windows 8.1 értéke: Windows, az eszköz akkor jelenik meg nem megfelelőként még akkor is, ha az eszköz Windows 8.1.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.

  Windows rendszerű, Microsoft-fiókon keresztül elért eszközök esetén a megfelelőségi szabályzat nem lesz helyesen kiértékelve:
  - Ha a jelszó minimális hossza nyolc karakternél nagyobb
  - Vagy ha a karakterkészletek minimális száma kettőnél több

- **Jelszó típusa**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).
  
  - **Jelszavak nem alfanumerikus karaktereinek száma**: Ha a **Jelszó kötelező** típusa **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
    - Kisbetűk
    - Nagybetűk
    - Szimbólumok
    - Számok

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk. A Microsoft-fiókkal elért eszközök esetén a megfelelőségi szabályzat kiértékelése helytelen, sikertelen:

    - Ha a jelszó minimális hossza nyolc karakternél nagyobb
    - Vagy ha a karakterkészletek minimális száma kettőnél több

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.

### <a name="encryption"></a>Encryption

- **Mobileszköz titkosításának kötelezővé tétele**: **Szükséges** az eszközök csak titkosítás csatlakozni az adattároló-erőforrásokat.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések

- [Nem megfelelő eszközök műveletek hozzáadása a](actions-for-noncompliance.md) és [használja a szűrő házirendek hatókörcímkék](scope-tags.md).
- [Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).
- Tekintse meg a [megfelelőségi szabályzat beállításai Windows 10-es és újabb verziók](compliance-policy-create-windows.md) eszközök.