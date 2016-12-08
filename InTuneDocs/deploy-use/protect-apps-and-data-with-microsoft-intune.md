---
title: "Alkalmazások és adatok védelme | Microsoft Intune"
description: "Ez a témakör ismerteti azokat a különböző Intune-funkciókat és képességeket, amelyek a rendelkezésére állnak a vállalati alkalmazások és adatok védelme érdekében."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3e302c50d931bd2545116dc510ddf2f1d7aa4f93


---

# <a name="protect-apps-and-data-with-microsoft-intune"></a>Alkalmazások és adatok védelme a Microsoft Intune-nal


Az Intune a vállalati adatokat több technológiai réteg segítségével védi. Az identitáskezelő rétegben a feltételes hozzáférés gondoskodik a védelemről: a szolgáltatásokhoz csak felügyelt, illetve a szabályoknak megfelelő eszközökkel lehet hozzáférni. Az ügyfélalkalmazási rétegben a mobilalkalmazás-kezelés (MAM) gondoskodik az adatvesztés elleni védelemről. Ennek részeként megakadályozza az adatok nem védett alkalmazásokba vagy tárhelyekre történő áthelyezését, illetve az eszköz elvesztése vagy ellopása esetén törli az adatokat. Azt javasoljuk, hogy az adatvédelem megvalósítása mellett a mobil munkaerő termelékenységének megőrzése érdekében e két védelmi réteget együttesen kell használni.

A céges adatok védelmének első fontos lépése a feltételes hozzáférés bevezetése. Azért vezeti be, hogy az adatokhoz hozzáférő eszközön megfelelő biztonsági védelem legyen, például erős jelszó és titkosítás, valamint megóvja őket a feltöréstől. Az Intune lehetőséget biztosít olyan feltételek megadására, amelyeknek az eszközöknek meg kell felelniük ahhoz, hogy hozzáférést kapjanak a vállalati e-mailekhez és adatokhoz.

A [feltételes hozzáférést](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) két, az Intune-ban megadható házirendtípus határozza meg:
- A [Megfelelőségi szabályzatok](introduction-to-device-compliance-policies-in-microsoft-intune.md) segítségével határozza meg az eszközök megfelelőségét. A következőkhöz hasonló beállításokat és feltételeket értékelik ki:
  - PIN-kód és jelszavak: Létrehozhatók olyan szabályok, amelyek jelszót kérnek egy adott eszköz feloldásához, vagy a jelszó összetettségi követelményeit és egyéb jelszóbeállításokat adnak meg.
  - Titkosítás: A hozzáférés a titkosított eszközökre korlátozható.
  - Az eszköz nincs függetlenítve vagy feltörve: Az Intune észleli, ha egy regisztrált eszköz függetlenítve van. Beállíthat egy szabályzatot is az ilyen típusú eszközök hozzáférésének letiltására.
- [Feltételes hozzáférési házirendek](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) egy adott szolgáltatáshoz állíthatók be, például az Exchange Online vagy a SharePoint Online számára. Minden egyes szolgáltatás esetében meghatározhatja, hogy a házirendek melyik felhasználói csoportokra vonatkozzon. Biztosíthatja például, hogy a pénzügyi részleg dolgozói csak a regisztrált és a házirendeknek megfelelő eszközökről férhessenek hozzá a vállalati e-mailekhez.

A vállalati erőforrásokhoz való hozzáférés biztosítása csak első lépése a vállalati adatok védelmének. Arra is szükség van, hogy az eszközön már elért adatokat is meg lehessen védeni. Az adatok ezután már másolhatók, áthelyezhetők, másik helyre menthetők vagy megoszthatók. Az Intune ezt a problémát azáltal oldja meg, hogy lehetővé teszi az adatmozgás korlátozását szabályzatok létrehozásával, például:
- A másolás és a beillesztés letiltása, vagy a munkahelyi környezeten kívülre történő adatátvitel megakadályozása.
- Személyes felhőalapú tárhelyre készített biztonsági mentés letiltása, a Mentés másként parancs letiltása.
- Az alkalmazások elérésének védelme PIN-kód/jelszó vagy vállalati hitelesítő adatok kérésével.
- Webes hivatkozások megnyitása kizárólag az Intune Managed Browser böngészőben.

A szabályzatoknak ezt a csoportját [mobilalkalmazás-felügyeleti (MAM) szabályzatoknak](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) nevezzük. Olyan eszközökön futó alkalmazásokhoz is hozzárendelhet MAM-szabályzatokat, amely eszközöket nem ön felügyel.  

A vállalati adatait védheti MAM-szabályzatokkal olyan eszközökön, amelyek **regisztrálva vannak az Intune-ban**, **harmadik fél MDM-e által regisztrált és felügyelt** eszközökön, illetve olyan eszközökön, amelyek **egy MDM-megoldásban sincsenek regisztrálva**, például alkalmazottak tulajdonában lévő eszközök.

Ahhoz, hogy egy alkalmazáshoz MAM-szabályzat legyen társítható, az alkalmazásnak tartalmaznia kell a Microsoft Intune szoftverfejlesztői készletet (SDK), vagy használhatja az alkalmazásburkoló eszközt.

Egyes alkalmazások, mint például a Microsoft Office beépítve tartalmazzák az Intune alkalmazásfejlesztő készletet (SDK-t). A támogatott alkalmazások teljes listáját a [Microsoft Intune mobilalkalmazás-galériában](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), a Microsoft Intune alkalmazáspartnerek oldalán láthatja. Ha szeretné megtekinteni a támogatott forgatókönyveket és platformokat, illetve, hogy az alkalmazás támogatja-e a többszörös identitást, válassza ki az adott alkalmazást.

[Egyéni kialakítású üzleti alkalmazásait](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) is alkalmassá teheti a MAM-szabályzatokkal való használatra.

Ha egy eszközt elveszítenek vagy ellopnak, vagy ha a felhasználó már nem dolgozik a vállalatnál, akkor az adatmozgás korlátozása mellett alkalmazható [a vállalati adatok szelektív törlése](wipe-managed-company-app-data-with-microsoft-intune.md), ami csak a személyes adatokat hagyja meg.



<!--HONumber=Nov16_HO5-->


