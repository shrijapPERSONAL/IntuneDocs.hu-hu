---
title: Általános hibaelhárítási tippek
description: Általános forrásanyagok az Intune-nal kapcsolatos problémák megoldásához.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/08/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 944c5771e00d8e256944fe5767217f138797bde2
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Általános hibaelhárítási tippek a Microsoft Intune rendszerhez

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Előfordulhat, hogy a Microsoft Intune telepítése után problémák merülnek fel a konfigurációval vagy az ügyféleszközökkel kapcsolatban. Az alábbi információk segítségével megtalálhatja a probléma okát, és így megoldhatja a problémát.

> [!NOTE]
> Ha támogatási kérelmet szeretne létrehozni, vagy egy meglévő kérelmet kíván megtekinteni, [nyissa meg az Office 365 felügyeleti központját](https://portal.office.com/admin/default.aspx). A támogatási lehetőségekről a [Hogyan kérhet támogatást az Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben találhat további információkat.

## <a name="define-the-problem"></a>A probléma meghatározása

-   Milyen viselkedés tapasztalható?

-   Ki és milyen platformokon és eszközökön tapasztalja ezt a viselkedést?

-   Korábban megfelelően működött az eszköz?

-   Milyen módosításokat végzett az Intune vagy az eszköz konfigurációján?

-   A konfigurációs módosításokon kívül történtek-e egyéb módosítások a működési környezetben?

-   Milyen gyakran fordul elő ez a probléma? Időszakosan vagy állandóan jelentkezik?

-   Tapasztal-e a felhasználó hitelesítési problémát? Ha lehetséges, ellenőrizze, hogy a felhasználó be tud-e jelentkezni az Azure Active Directoryt használó egyéb szolgáltatásokba. Azt is ellenőrizze, hogy a felhasználó be tud-e jelentkezni egy másik eszközről.

-   Ellenőrizte a szolgáltatás állapotát? Az [Office 365 felügyeleti portálon](https://portal.office.com/Admin/Default.aspx) az Intune szolgáltatás állapota is figyelemmel követhető. Válassza a bal oldali panel **Szolgáltatás állapota** elemét.

## <a name="collect-available-data"></a>Rendelkezésre álló adatok összegyűjtése

-   Az alábbi források segítséget nyújtanak az eszköznaplók gyűjtésével kapcsolatban:
  - [Az Android diagnosztikai adatait tartalmazó naplófájlok elküldése USB-kábelen keresztül a rendszergazdának](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Az Android diagnosztikai adatait tartalmazó naplófájlok elküldése e-mailben a rendszergazdának](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Az Android regisztrálási hibáinak elküldése a rendszergazdának](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [Az iOS regisztrálási hibáinak elküldése a rendszergazdának](/intune-user-help/send-errors-to-your-it-admin-ios)

-   A felügyeleti konzol adatainak (például a szabályzat megvalósításával kapcsolatos problémának) birtokában vizsgálja meg az érintett szabályzatot, illetve állapotát a [Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) című témakörben leírtak szerint.

## <a name="research-the-solution"></a>Megoldás keresése

-   Keressen megoldást az interneten. Ha például a 0x80073CF0 hibakódot kapja, keressen rá az interneten a **technet intune 0x80073cf0** kifejezésre, és olvassa el az [Alkalmazástelepítéssel kapcsolatos problémák elhárítása a Microsoft Intune-ban](troubleshoot-app-deployment-problems-in-microsoft-intune.md) című témakört. Ebben a cikkben megtalálja a hiba kijavítására vonatkozó információkat.

-   Kérdéseire az [Intune TechNet fórumon](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod) is megkeresheti a választ.  Ha a kérdés korábban még nem merült fel, tegye fel, hátha a közösség hasznos javaslatokkal tud szolgálni.

-   Ezenfelül támogatási kérelmet is benyújthat. Az Intune támogatási szolgálata jobban tud segíteni a probléma megoldásában, ha meghatározza a problémát, és összegyűjti az elérhető adatokat.

    Ha támogatási kérelmet szeretne létrehozni, nyissa meg az [Office 365 felügyeleti központját](https://portal.office.com/admin/default.aspx). A támogatási lehetőségekről a [Hogyan kérhet támogatást az Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben találhat további információkat.

## <a name="find-community-resources"></a>Közösségi erőforrások keresése
A következő közösségi erőforrásokban találhat további hasznos információkat:

-   A [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) (A Microsoft Intune túlélési útmutatója) számos olyan forrás hivatkozását tartalmazza, melyek segíthetnek az Intune konfigurálásában, karbantartásában és hibáinak elhárításában.

-   [Az Intune blogja](http://blogs.technet.com/b/windowsintune/)

-   [Kövesse Twitteren az Intune-t](https://twitter.com/MSIntune)

-   [Az Intune fórumai](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>További lépések
Az alábbi témakörök konkrét problémák elhárításában nyújtanak segítséget. Ha ezek az információk nem segítettek megoldani a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.

[A Microsoft Intune Endpoint Protection hibaelhárítása](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Munkahelyi erőforrás-hozzáférési problémák megoldása a Microsoft Intune-nal](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Alkalmazástelepítéssel kapcsolatos problémák elhárítása a Microsoft Intune-ban](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Eszközök regisztrálásával kapcsolatos problémák elhárítása az Intune-ban](troubleshoot-device-enrollment-in-intune.md)

[Szabályzatokkal kapcsolatos problémák elhárítása a Microsoft Intune-ban](troubleshoot-policies-in-microsoft-intune.md)

[Az ügyfél a Microsoft Intune-ban való beállításának hibaelhárítása](troubleshoot-client-setup-in-microsoft-intune.md)

[A Microsoft Intune szoftverfrissítéseinek hibaelhárítása](troubleshoot-software-updates-in-microsoft-intune.md)
