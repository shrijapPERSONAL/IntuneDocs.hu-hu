---
title: "A Microsoft Intune előzetesének újdonságai | Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Ismerkedjen meg az Azure-beli Intune előzetesének újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>A Microsoft Intune előzetesének újdonságai


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


A nyilvános előzetes fejlődése során egyre több funkcióval bővül, mi pedig értesítjük Önt ezekről.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

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



<!--HONumber=Feb17_HO1-->


