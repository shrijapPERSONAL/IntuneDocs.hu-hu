---
title: "A Microsoft Intune előzetesének újdonságai"
titleSuffix: Intune Azure preview
description: "Ismerkedjen meg az Azure-beli Intune előzetesének újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: ffbc91edbdec4abbb5c3c9e28c3b44df03117492
ms.lasthandoff: 02/18/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>A Microsoft Intune előzetesének újdonságai

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A nyilvános előzetes fejlődése során egyre több funkcióval bővül, mi pedig értesítjük Önt ezekről.

## <a name="february-2017"></a>2017. február

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>A mobileszköz-regisztrálás korlátozásának képessége <!--747600, 795782-->
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.

* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.  
* Csak az iOS és az Android esetében van még egy lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Az összes művelet megtekintése a felügyelt eszközökön<!--677150-->
Az új __Eszközműveletek__ jelentés megmutatja, hogy mely felhasználó hajtott végre távoli műveleteket az eszközön (például gyári alaphelyzetbe állítás), valamint megjeleníti az adott művelet állapotát is. Lásd: [Mi az eszközfelügyelet?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->
A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Eszközkategóriák megjelenítése <!--814654-->
Mostantól az eszközkategória külön oszlopként jelenik meg az eszközlistában. A kategória módosítására szintén van lehetőség az Eszköztulajdonságok panel Tulajdonságok szakaszában. Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps). 

## <a name="january-2017"></a>2017. január

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Üzletági alkalmazások kiosztása nem regisztrált eszközökre is <!--748823-->
Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Munkahelyi portál alkalmazás helyett a Munkahelyi portál webhelyen telepíthetik az alkalmazást. Lásd: [Mi az alkalmazáskezelés?](/intune-azure/manage-apps/what-is-app-management)

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>A következő probléma elhárítása: Az iOS-eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük
Ha a felhasználói eszközök elveszítik a kapcsolatot az Intune-nal, új hibaelhárítási lépések átadásával segítheti a felhasználókat a vállalati erőforrásokhoz való hozzáférés visszaszerzésében. Lásd: [Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>2016. december (eredeti kiadás)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Áruházból származó alkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Üzletági (LOB) alkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Mennyiségi konstrukcióban vásárolt alkalmazások telepítése és felügyelete iOS-es és windowsos eszközökön
- Webalkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Konfigurációs profilok felügyelt iOS-es alkalmazásokhoz
- Alkalmazásvédelmi szabályzatok konfigurálása és üzletági alkalmazások telepítése az Intune-ban nem regisztrált eszközökre
- VPN-profilok, alkalmazásonkénti VPN-, Wi-Fi-, e-mail- és tanúsítványprofilok
- Megfelelőségi szabályzatok
- Feltételes hozzáférés Azure AD-re
- Feltételes hozzáférés helyszíni Exchange-re
- Eszközök beléptetése
- Szerepköralapú hozzáférés-vezérlés

## <a name="deprecated-features-in-the-azure-portal"></a>Az Azure Portal elavult szolgáltatásai

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Hardverazonosítók soronkénti átnézésének támogatása
Az Azure Portalon nem lehetséges soronként átnézni az IMEI-számokból és az Apple-sorozatszámokból álló hardverazonosítókat. A klasszikus Intune-konzolon lehetőség van rá, hogy csv-fájlból importálja a részleteket, és felülírja az egyes hardverazonosítók korábbi részleteit. Az Azure Portal egységes, hatékony módszert kínál, amely automatikusan felülírja az összes hardverazonosító részleteit, vagy figyelmen kívül hagyja a korábbi azonosítók új részleteit.

#### <a name="how-this-affects-you"></a>Mit jelent ez az Ön számára?
Az Azure Portalon nem fog tudni soronként dönteni arról, hogy mely IMEI-számmal ellátott eszközöket szeretné módosítani. A klasszikus Intune-konzolon továbbra is elérhető lesz ez a lehetőség.

#### <a name="how-to-get-ready-for-this-change"></a>Felkészülés a változásra
Ezt az információt azért bocsátjuk közre előzetesen, hogy amennyiben Önt is érinti, értesíteni tudja róla az illetékes adminisztrátorokat. A változás az Azure Portalra való költözéssel egy időben, várhatólag 2017 első felében lép életbe.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Céges eszközregisztrációs profilok támogatása az Apple DEP-ben
Az Azure Portal az Apple Készülékregisztrációs program (DEP) eszköz-sorozatszámai esetében nem támogatja az alapértelmezett céges eszközregisztrációs profilt. A klasszikus Intune-konzol ezen funkcióját megszüntetjük, a profilok szándékolatlan hozzárendelését megelőzendő. Az Azure Portalon az Apple DEP-fiókokból szinkronizált sorozatszámokhoz a rendszer nem rendel alapértelmezett céges eszközregisztrációs profilt.

#### <a name="how-this-affects-you"></a>Mit jelent ez az Ön számára?
Az Azure Portalon nem fog tudni az összes Apple-eszközhöz alapértelmezett profilszabályzatot megadni. A klasszikus Intune-konzolon továbbra is elérhető lesz ez a lehetőség.

#### <a name="how-to-get-ready-for-this-change"></a>Felkészülés a változásra
Ezt az információt azért bocsátjuk közre előzetesen, hogy amennyiben Önt is érinti, értesíteni tudja róla az illetékes adminisztrátorokat. A változás az Azure Portalra való költözéssel egy időben, várhatólag 2017 első felében lép életbe.

