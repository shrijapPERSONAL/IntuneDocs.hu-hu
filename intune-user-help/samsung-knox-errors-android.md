---
title: A felügyelt Samsung Knox-eszközök gyakori problémáinak elhárítása | Microsoft Docs
description: Módszerek a Samsung Knox-eszközökkel gyakran előforduló problémák megoldására.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 78c08b30-dc5f-46d9-9ee8-6cc8dee1e404
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f78c2460130068652b91b27ddcf5726a077e59e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "55833463"
---
# <a name="fix-common-issues-with-your-samsung-knox-device"></a>A Samsung Knox-eszközök gyakori problémáinak elhárítása

Időnként előfordulhatnak olyan problémák a Samsung Knox-eszközökkel kapcsolatban, melyeket megoldhat hibaelhárítási lépések végrehajtásával. Az alábbiakban látható azon korábban tapasztalt gyakori problémák listája, amelyeket először megpróbálhat önállóan megoldani. Összetettebb problémák esetén javasoljuk, hogy [forduljon az androidos Céges portál csapatához](https://github.com/MicrosoftDocs/IntuneDocs/blob/master/intune-user-help/send-logs-to-microsoft-android.md).

## <a name="network-activation-error"></a>Hálózati aktiválási hiba

A megjelenő üzenet a következőhöz hasonló lehet:

|Hibaüzenet|Lehetséges megoldás|
|---|---|
|**Samsung Knox-aktiválási hiba** – Nem sikerült aktiválni a Samsung Knox-licencet. Váltson másik vezeték nélküli vagy mobilhálózatra az újrapróbálkozáshoz.|Az eszközt a jelenlegi hálózaton nem lehet aktiválni. Ha mobiladat-forgalmat használ, váltson egy Wi-Fi-hálózatra (vagy fordítva), majd próbálkozzon újra.|

## <a name="license-activation-error"></a>Licencaktiválási hiba

A megjelenő üzenet a következőhöz hasonló lehet:

|Hibaüzenet|Lehetséges megoldás|
|---|---|
|**Samsung Knox-aktiválási hiba** – Nem sikerült aktiválni a Samsung KNOX-licencet. Ennek az lehet az oka, hogy be van kapcsolva az energiatakarékos üzemmód. Kapcsolja ki az energiatakarékos üzemmódot az eszközbeállításoknál, majd próbálkozzon újra.|Az eszközt olyan okokból nem sikerült aktiválni, melyeket a Microsoftnak meg kell vizsgálnia. Küldjön visszajelzést, és megkeressük a javítás lehetséges módszereit.|

## <a name="power-saving-mode-error"></a>Energiatakarékos üzemmód által okozott hiba

A megjelenő üzenet a következőhöz hasonló lehet:

|Hibaüzenet|Lehetséges megoldás|
|---|---|
|**Samsung Knox-aktiválási hiba** – Nem sikerült aktiválni a Samsung KNOX-licencet. Ennek az lehet az oka, hogy be van kapcsolva az energiatakarékos üzemmód. Kapcsolja ki az energiatakarékos üzemmódot az eszközbeállításoknál, majd próbálkozzon újra. |Előfordulhat, hogy az eszköz energiagazdálkodási beállításai nem megfelelőek a céges erőforrások használatához. További információ az [energiatakarékos üzemmód beállításáról](power-saving-mode-android.md).|

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
