---
title: "Intune Endpoint Protection-beállítások Windows 10 rendszerhez"
titlesuffix: Azure portal
description: "Ez a cikk azt mutatja be, hogy Windows 10 rendszerű eszközökön milyen Intune-beállításokkal szabályozhatja az olyan Endpoint Protection szolgáltatások beállításait, mint például a BitLocker."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19c20ac5dd73b45dc06d1df6a7d08cc6bac42982
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune Endpoint Protection-beállítások Windows 10 és újabb rendszerekhez

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Endpoint Protection-profillal a Windows 10-es eszközök olyan biztonsági szolgáltatásait szabályozhatja, mint például a BitLocker és a Windows Defender.

A következő témakör az Endpoint Protection-profilok létrehozását mutatja be.

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection-profil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az eszközfunkció-profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listából válassza az **Endpoint Protection** lehetőséget.
7. A **Windowsos titkosítás** panelen adja meg, milyen beállításokkal szeretné működtetni a rendszert. A következő témakörben leírtak alapján megértheti, milyen funkciót látnak el az egyes beállítások. Ha elkészült, válassza az **OK** elemet.
8. Lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** lehetőséget.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="windows-defender-smartscreen-settings"></a>A Windows Defender SmartScreen beállításai

- **SmartScreen használata alkalmazások és fájlok esetén** –  A Windows SmartScreen használata fájlok és alkalmazások futtatásához.
- **Nem ellenőrzött fájlok futtatása** – Letilthatja a végfelhasználóknál a Windows SmartScreen által nem ellenőrzött fájlok futtatását.

## <a name="windows-encryption-settings"></a>A Windowsos titkosítás beállításai

### <a name="windows-settings"></a>Windowsos beállítások

- **Az eszközök titkosítása kötelező (csak asztali számítógépen)** – Ha bekapcsolja ezt a beállítást, a rendszer kérni fogja a felhasználótól, hogy engedélyezze az eszköz titkosítását. Ezen túlmenően rá fog kérdezni, hogy nincs-e engedélyezve másik szolgáltató titkosítási funkciója. Az eszköz ugyanis instabillá válhat, ha a windowsos titkosítást úgy kapcsolják be, hogy közben egy másik titkosítási módszer aktív marad.
- **A tárolókártya titkosítása kötelező (csak mobileszközön)** – Ha engedélyezi ezt a beállítást, az eszközhöz használt minden cserélhető tárolókártyát titkosítani fog a rendszer.


### <a name="bitlocker-base-settings"></a>BitLocker-alapbeállítások

- **Titkosítási módszerek konfigurálása** – Ha engedélyezi ezt a beállítást, különböző titkosítási algoritmusokat állíthat be az operációs rendszerhez, a rendszeren található adatokhoz és a cserélhető meghajtókhoz.
    - **Operációsrendszer-meghajtók titkosítása** – Az operációs rendszer meghajtóihoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
    - **Rögzített adatmeghajtók titkosítása** – A rögzített (beépített) adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
    - **Cserélhető adatmeghajtók titkosítása** – A cserélhető adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Ha a cserélhető meghajtót olyan eszközökkel is használja, amelyeken nem Windows 10 operációs rendszer fut, az AES-CBC algoritmus használatát javasoljuk.


### <a name="bitlocker-os-drive-settings"></a>Operációsrendszer-meghajtók BitLocker-beállításai

- **További hitelesítés megkövetelése indításkor** -
    - **BitLocker nem kompatibilis TPM-lapkával** -
    - **TPM-indítás** – Ezzel a beállítással adható meg, hogy a TPM-lapka (Trusted Platform Module – platformmegbízhatósági modul) használata engedélyezett, nem engedélyezett vagy kötelező legyen-e.
    - **TPM-indítási PIN-kód** – Ezzel a beállítással adható meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítási PIN-kód használatát.
    - **TPM-indítási kulcs** – Ezzel a beállítással adhatja meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítókulcs használatát.
    - **TPM-indítási kulcs és PIN-kód** – Ezzel a beállítással adhatja meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítókulcs és PIN-kód használatát.
- **PIN-kód minimális hossza** – Ha engedélyezi ezt a beállítást, megadhatja a TPM-indítási PIN-kód minimális hosszát.
    - **Karakterek minimális száma** – Ezzel a beállítással megadható, hogy hány karaktert kell tartalmaznia az indításkor beírandó PIN-kódnak. A PIN-kód hossza **4**-**20** karakter lehet.
- **Az operációs rendszer meghajtója helyreállításának engedélyezése** – Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett operációsrendszer-meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
    - **Tanúsítványalapú adat-helyreállítási ügynök** – Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett operációsrendszer-meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
    - **Helyreállítási jelszó felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.
    - **Helyreállítási kulcs felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
    - **A helyreállítási beállítások elrejtése a BitLocker beállító varázslójában** – Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
    - **A BitLocker helyreállítási adatainak mentése az AD DS-be** – Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
    - **A BitLocker-alapú helyreállítási adatok AD DS-beli tárolásának konfigurálása** – Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
        - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
        - **Csak a helyreállítási jelszavak biztonsági mentése**
    - **A helyreállítási adatok AD DS-ben való tárolásának megkövetelése a BitLocker engedélyezéséhez** – Ezzel a beállítással szabályozható, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.
- **Rendszerindítás előtti helyreállítási üzenet és URL engedélyezése** – Ezzel a beállítással engedélyezhető, hogy a rendszerindítás előtti kulcshelyreállítási képernyőn a rendszer megjelenítsen egy üzenetet és egy URL-címet.
    - **Rendszerindítás előtti helyreállítási üzenet** – Itt adhatja meg, milyen rendszerindítás előtti helyreállítási üzenet jelenjen meg a felhasználók számára. A következő lehetőségek közül választhat:
        - **Az alapértelmezett helyreállítási üzenet és URL-cím használata**
        - **Üres helyreállítási üzenet és URL-cím használata**
        - **Egyéni helyreállítási üzenet**
        - **Egyéni helyreállítási URL**


### <a name="bitlocker-fixed-data-drive-settings"></a>Rögzített adatmeghajtók BitLocker-beállításai

- **Írási hozzáférés letiltása a BitLockerrel nem védett rögzített adatmeghajtókon** – Ha ezt a beállítást engedélyezi, a rögzített vagy beépített adatmeghajtók csak azután lesznek írhatók, ha BitLocker-védelmüket engedélyezte a felhasználó.
- **Rögzített meghajtók helyreállításának engedélyezése** – Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett rögzített meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
    - **Adat-helyreállítási ügynök** – Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett rögzített meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
    - **Helyreállítási jelszó felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.  
    - **Helyreállítási kulcs felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
    - **A helyreállítási beállítások elrejtése a BitLocker beállító varázslójában** – Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
    - **A BitLocker helyreállítási adatainak mentése az AD DS-be** – Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
    - **A BitLocker-alapú helyreállítási adatok AD DS-beli tárolásának konfigurálása** – Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
        - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
        - **Csak a helyreállítási jelszavak biztonsági mentése**
    - **A helyreállítási adatok AD DS-ben való tárolásának megkövetelése a BitLocker engedélyezéséhez** – Ezzel a beállítással szabályozható, hogy a felhasználók addig ne tudják bekapcsolni a BitLockert, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.


### <a name="bitlocker-removable-data-drive-settings"></a>Cserélhető adatmeghajtók BitLocker-beállításai

- **A BitLocker által nem védett cserélhető adatmeghajtókhoz való írási hozzáférés megtagadása** – Ezzel a beállítással szabályozható, hogy kötelező-e BitLocker-titkosítással védeni a cserélhető adattárolókat.
    - **Írási hozzáférés letiltása a más szervezetben konfigurált eszközökön** – Ezt a beállítást használva megadhatja, hogy írhatnak-e a felhasználók más szervezethez tartozó cserélhető adatmeghajtókra.



## <a name="next-steps"></a>További lépések

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.
