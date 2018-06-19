---
title: Eszközmegfelelőségi szabályzatok
description: Ez a témakör az eszközmegfelelőségi szabályzatokat és működésüket ismerteti.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c9c93d29ddee6d01e057c01a44c81950b857213
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31031753"
---
# <a name="device-compliance-policies-in-microsoft-intune"></a>Eszközmegfelelőségi szabályzatok a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>Mi a megfelelőségi szabályzat?
A vállalati adatok védelme érdekében gondoskodnia kell arról, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek bizonyos szabályoknak. Ilyen szabály lehet például, hogy PIN-kódot kell használni az eszközök eléréséhez, és titkosítani kell az eszközökön tárolt adatokat. Az ilyen szabályok összességét megfelelőségi szabályzatnak nevezzük.

## <a name="how-should-i-use-compliance-policies"></a>Hogyan kell használni a megfelelőségi szabályzatokat?
A megfelelőségi szabályzatokhoz feltételes hozzáférési szabályzatokat társíthat, hogy kizárólag olyan eszközök férhessenek hozzá az e-mailekhez és egyéb szolgáltatásokhoz, amelyek eleget tesznek a megfelelőségi szabályzatnak . A kétféle szabályzat együttes alkalmazásáról [Az e-mailek és az O365-szolgáltatások elérésének korlátozása](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című témakör nyújt tájékoztatást.

Megfelelőségi szabályzatokat feltételes hozzáféréstől függetlenül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Előfordulhat például, hogy arról szeretne jelentést, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak függetlenítve vagy feltörve. De ha önállóan alkalmazza a megfelelőségi szabályzatokat, akkor nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi.
Arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot, [Az eszközök beállításainak és funkcióinak kezelése](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies) című cikk nyújt tájékoztatást.

A következő táblázat felsorolja, hogy milyen típusú eszközökre lehet megfelelőségi szabályzatokat alkalmazni. Azt is ismerteti a táblázat, hogy miképpen történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

-----------------------------

|Házirend-beállítás| Windows 8.1 és újabb| Windows Phone 8.1 és újabb verziók| iOS 8.0 és újabb verziók|Android 4.0 és újabb verziók<br/>Samsung Knox Standard 4.0-s és újabb verzió|
|-----|----|----|----|----|
|**PIN-kód vagy jelszó konfigurálása** |Kijavítva|Kijavítva|Kijavítva|Karanténba helyezve|
|**Eszköztitkosítás**|Nem alkalmazható|Kijavítva|Kijavítva (PIN-kód beállításával)|Karanténba helyezve|
|**Jailbreakelt vagy rootolt eszköz**|Nem alkalmazható|Nem alkalmazható|Karanténba helyezve (nem beállítás)|Karanténba helyezve (nem beállítás)|
|**E-mail profil**|Nem alkalmazható|Nem alkalmazható|Karanténba helyezve|Nem alkalmazható|
|**Operációs rendszer minimális verziója**|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|
|**Operációs rendszer maximális verziója**|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|
|**Windows-állapotigazolás**|Karanténba helyezve: Windows 10 és Windows 10 Mobile<br /><br />Nem alkalmazható: Windows 8.1|Nem alkalmazható|Nem alkalmazható|Nem alkalmazható|

------------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

-   A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.

-   A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="next-steps"></a>További lépések
[Eszközmegfelelőségi szabályzat létrehozása](create-a-device-compliance-policy-in-microsoft-intune.md)

[Eszközmegfelelőségi szabályzat üzembe helyezése és figyelése](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Lásd még:
[Az e-mailek és az O365-szolgáltatások elérésének korlátozása](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
