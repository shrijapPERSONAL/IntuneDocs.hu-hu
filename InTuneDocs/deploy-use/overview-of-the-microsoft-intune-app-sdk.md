---
title: "A Microsoft Intune App SDK áttekintése | Microsoft Docs"
description: "Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi a Microsoft Intune mobilalkalmazás-felügyeleti funkcióinak használatát."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 99f3aa3c8640dd41133584b3e1cb056dfd493efa
ms.lasthandoff: 12/20/2016


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>A Microsoft Intune App SDK áttekintése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi a Microsoft Intune mobilalkalmazás-felügyeleti funkcióinak használatát. Emellett segít csökkenteni a fejlesztők részéről szükséges kódmódosításokat.

Az SDK legtöbb funkcióját alkalmazása viselkedésének módosítása nélkül is engedélyezheti. Ha hatékonyabbá szeretné tenni a végfelhasználók és a rendszergazdák munkáját, az API-jainkkal személyre szabhatja alkalmazása működését olyan funkciók tekintetében, amelyek használatához az alkalmazás közreműködése szükséges.

Az alkalmazás engedélyezése után a rendszergazdák szabályzatokat telepíthetnek az Intune által felügyelt alkalmazásokhoz, és a vállalati adatok hatékonyabb védelmére használhatják ezeket a funkciókat.

## <a name="features"></a>Jellemzők
### <a name="control-users-ability-to-move-corporate-documents"></a>Vállalati dokumentumok felhasználók általi áthelyezésének szabályozása
A rendszergazdák az Intune által felügyelt alkalmazásokban szabályozhatják a vállalati dokumentumok áthelyezését. Telepíthetnek például olyan szabályzatot, amely letiltja a fájlokról biztonsági másolatot készítő alkalmazások számára, hogy biztonsági másolatot készíthessenek a vállalati adatokról a felhőbe.  

### <a name="configure-clipboard-restrictions"></a>Vágólappal kapcsolatos korlátozások beállítása
A rendszergazdák konfigurálhatják a vágólap működését az Intune által felügyelt alkalmazásokban. Telepíthetnek például olyan szabályzatot, amely letiltja a végfelhasználók számára, hogy a vágólap használatával adatokat vágjanak ki vagy másoljanak egy Intune által felügyelt alkalmazásból, és egy nem felügyelt alkalmazásba illesszék be azokat.

### <a name="enforce-encryption-on-saved-data"></a>Mentett adatok titkosításának kényszerítése
A rendszergazdák olyan szabályzatot alkalmazhatnak, amely biztosítja az alkalmazás által az eszközre mentett adatok titkosítását.

### <a name="remotely-wipe-corporate-data"></a>Vállalati adatok távoli törlése
A rendszergazdák távolról törölhetik az Intune által felügyelt alkalmazásokból a vállalati adatokat, amikor megszüntetik az eszköz Microsoft Intune-beli regisztrációját. Ez a funkció identitásalapú, és csak azokat a fájlokat törli, amelyek az adott végfelhasználó vállalati identitásához kapcsolódnak. A szolgáltatásnak ehhez az alkalmazás közreműködésére van szüksége. Az alkalmazás a felhasználói beállítások alapján határozza meg azt az identitást, amelyhez a törlést végre kell hajtani. Ilyen felhasználói beállítások hiányában alapértelmezés szerint az alkalmazás könyvtára lesz törölve, és a végfelhasználó értesítést kap arról, hogy a vállalati erőforrásokhoz való hozzáférését visszavonták.

### <a name="enforce-the-use-of-a-managed-browser"></a>Felügyelt böngésző használatának kényszerítése
A rendszergazdák kényszeríthetik egy felügyelt böngésző használatát az Intune által felügyelt alkalmazásokban található hivatkozások megnyitásakor. Ha a végfelhasználók a Microsoft Intune által felügyelt böngészőt használják, azzal biztosítható, hogy az Intune által felügyelt levelezőprogramban megtekintett e-mailekben megjelenő hivatkozások csak az Intune által felügyelt alkalmazások tartományán belüli helyekre mutassanak.

### <a name="enforce-a-pin-policy"></a>PIN-kód használatára vonatkozó szabályzat alkalmazása
A rendszergazdák PIN-kód használatára vonatkozó szabályzat alkalmazását kényszeríthetik az Intune által felügyelt alkalmazások indításakor. Ezzel a szabályzattal meggyőződhetnek arról, hogy az alkalmazásokat indító felhasználók ugyanazok a végfelhasználók, akik a Microsoft Intune-ban regisztrálták eszközeiket. Amikor a végfelhasználók beállítják PIN-kódjukat, az Intune App SDK az Azure Active Directory segítségével összehasonlítja a hitelesítő adataikat az eszközregisztrációs hitelesítő adatokkal.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Hitelesítő adatok kérése a felhasználóktól az alkalmazások indításához
A rendszergazdák megkövetelhetik, hogy a végfelhasználók az Intune által felügyelt alkalmazások indítása előtt megadják hitelesítő adataikat. Az Intune App SDK az Azure Active Directory segítségével lehetővé teszi az egyszeri bejelentkezés használatát. Ez azt jelenti, hogy a hitelesítő adatokat elég egyszer megadni, a későbbi bejelentkezések során újra ezeket fogja használni a rendszer. Az SDK az [Azure Active Directoryval összevont](/active-directory/active-directory-aadconnect-federation-compatibility) identitáskezelési megoldások hitelesítését is támogatja.

### <a name="check-device-health-and-compliance"></a>Eszközök állapotának és megfelelőségének ellenőrzése
A rendszergazdák ellenőrizhetik az eszközök állapotát és vállalati szabályzatoknak való megfelelőségét, mielőtt a végfelhasználók hozzáférhetnének az Intune által felügyelt alkalmazásokhoz. Az iOS platformon a szabályzat ellenőrzi, hogy az eszköz jailbreakelve lett-e. Az Android platformon a szabályzat ellenőrzi, hogy az eszköz rootolt-e.  

