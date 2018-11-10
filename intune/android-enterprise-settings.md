---
title: Androidos kioszkbeállítások a Microsoft Intune-ban – Azure | Microsoft Docs
description: Vállalati androidos kioszkeszközök konfigurálása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f49e0bc496f176434577d42d3a372fc4e8bc22d3
ms.sourcegitcommit: 7063072c94e43aefc6be0072780622a1da8485d5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46119103"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Vállalati androidos kioszkbeállítások az Intune-ban

Az androidos kioszkprofilok az alábbi konfigurációs beállításokat támogatják. A profil létrehozásakor ezek a beállítások akkor jelennek meg, amikor kiválasztja a **Profiltípus** > **Csak az eszköz tulajdonosa** > **Eszközkorlátozások** lehetőséget. A beállítások megjelenítéséhez nyissa meg egy Vállalati Android eszközkorlátozási profil **Tulajdonságait**, majd válassza a **Konfigurálás** lehetőséget.

## <a name="general-settings"></a>Általános beállítások

- **Képernyőfelvétel**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat az eszköz képernyőképének rögzítésében.
- **Kamera**: Válassza a **Tiltás** lehetőséget az eszköz kamerájának letiltásához.
- **Alapértelmezett engedélyezési szabályzat**: Ez a beállítás adja meg a futásidejű engedélykérésekre vonatkozó alapértelmezett engedélyezési szabályzatot. Lehetséges értékei többek között a következők:
    - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállításának használata.
    - **Rákérdezés**: A rendszer felszólítja a felhasználót az engedély jóváhagyására.
    - **Automatikus engedélyezés**: Az engedélyek automatikusan meg lesznek adva.
    - **Automatikus elutasítás**: Az engedélyek automatikusan meg lesznek tagadva.
- **Hangerő-módosítás**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az eszköz hangerejének módosításában.
- **Összes adat törlése**: A **Tiltás** lehetőség választásával megakadályozhatja, hogy a felhasználók minden adatot töröljenek az eszközről.
- **Csökkentett üzemmódú indítás**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az eszköz csökkentett módban való újraindításában.
- **Állapotsor**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az állapotsor, ezzel együtt az értesítések és a gyors beállítások elérésében.
- **Wi-Fi-beállítások módosítása**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az eszköz tulajdonosa által létrehozott Wi-Fi-konfigurációk módosításában. A felhasználók létrehozhatnak saját Wi-Fi-konfigurációkat.
- **Wi-Fi-hozzáférési pont konfigurálása**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat a Wi-Fi-konfigurációk létrehozásában és szerkesztésében.
- **Hibakeresési funkciók**: Az **Engedélyezés** lehetőség választásával engedélyezi, hogy a felhasználók használhassák a hibakeresési funkciókat.
- **Mikrofon-beállítások**: A **Tiltás** lehetőséggel megakadályozza a felhasználókat a mikrofon elnémításában vagy hangerejének módosításában.
- **Összes adat törlése elleni védelem e-mail-címei**: Válassza a **Google-fiók e-mail-címek** lehetőséget, majd adja meg az e-mail-címeket (pontosvesszővel elválasztva), amelyek feloldhatják az eszköz zárolását az összes adat törlése után. Ha nem ad meg e-mail-címet, akkor az összes adat törlése után bárki feloldhatja az eszközt.
- **Hálózati vészkijárat**: Válassza az **Engedélyezés** lehetőséget a hálózati vészkijárat funkció bekapcsolásához. Ha a rendszerindítás ideje alatt nem létesíthető hálózati kapcsolat, ez a vészkijárat felszólítja a felhasználót, hogy ideiglenesen csatlakozzon egy hálózathoz az eszköz szabályzatának frissítése érdekében. A szabályzat alkalmazása után a rendszer elfelejti az átmeneti hálózatot, és az eszköz folytatja a rendszerindítást. Ez megakadályozza, hogy ne lehessen hálózathoz csatlakozni, ha a legutóbbi szabályzatban nincs megfelelő hálózat, és az eszköz rendszerindításkor egy alkalmazást nyit meg feladatzárolási módban, vagy a felhasználó más okból nem tud hozzáférni az eszköz beállításaihoz.
- **Ismeretlen forrásból való telepítés engedélyezése**: Válassza az **Engedélyezés** lehetőséget, hogy a felhasználók ismeretlen forrásból is telepíthessenek.
- **Rendszerfrissítés**: A következő lehetőségek közül választva adja meg, hogyan kezeli az eszköz a vezeték nélküli frissítéseket:
    - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállításának használata.
    - **Automatikus**: A rendszer automatikusan, felhasználói beavatkozás nélkül telepíti a frissítéseket. Ennek a szabályzatnak a beállításakor minden függőben lévő frissítés azonnal települ.
    - **Elhalasztva**: A frissítések 30 nappal el lesznek halasztva. A 30 nap letelte után az Android felszólítja a felhasználót a frissítés telepítésére. Az eszközgyártók vagy a szolgáltatók megakadályozhatják (kivételként) a fontos biztonsági frissítések elhalasztását. A kivételként kezelt frissítések rendszerértesítést jelenítenek meg a felhasználó számára az eszközön. 
    - **Karbantartási időszak**: Automatikusan telepíti a frissítéseket az Ön által az Intune-ban beállított napi karbantartási időszakban. A telepítést 30 napon át naponta megkísérli. A telepítés sikertelen lehet, ha nincs elegendő lemezterület vagy akkumulátortöltés. 30 nap elteltével az Android felszólítja a felhasználót a telepítésre. Ez az időszak szolgál a Play-alkalmazások frissítéseinek telepítésére is. Ez a beállítás olyan dedikált eszközökhöz ajánlott, mint a kioszkeszközök, az egyalkalmazásos kioszk előtér-alkalmazása ugyanis frissíthető. 

## <a name="kiosk-settings"></a>Kioszkbeállítások

- **Kioszkmód**: Meghatározza, hogy az eszközön egyetlen alkalmazás, vagy több alkalmazás is futhat. További információ: [Android-eszközök kioszkbeállításai](android-kiosk-settings.md).
    - **Egyalkalmazásos kioszkmód**: A felhasználók csak egy alkalmazáshoz férnek hozzá.
    - **Többalkalmazásos kioszkmód**: A felhasználók az alkalmazások egy korlátozott köréhez férhetnek hozzá.

## <a name="device-password-settings"></a>Eszköz jelszóbeállításai

- **Kulcsőr**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat a Kulcsőr használatában az eszközön.
- **Megkövetelt jelszótípus**: Adja meg az eszközön megkövetelt jelszótípust.
- **Jelszó minimális hossza**: Adja meg a jelszónak az eszközön megkövetelt minimális hosszát.
- **Sikertelen bejelentkezések száma az eszközön lévő összes adat törléséig**: Adja meg, hány sikertelen bejelentkezésnek kell történnie ahhoz, hogy az eszközön tárolt adatok törölve legyenek.

## <a name="power-settings"></a>Energiaellátási beállítások

- **A képernyő zárolásáig eltelt idő**: Adja meg, mennyi tétlenség után legyen az eszköz zárolva.
- **Bekapcsolt képernyő, amikor az eszköz áramforráshoz van csatlakoztatva**: Válassza ki, mely áramforrások csatlakoztatásakor maradjon bekapcsolva az eszköz képernyője.

## <a name="users-and-accounts-settings"></a>Felhasználói és fiókbeállítások

- **Új felhasználók hozzáadása**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat új felhasználók hozzáadásában.
- **Felhasználó eltávolítása**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat felhasználók eltávolításában.
- **Fiókmódosítások**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat a fiókok módosításában.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).



