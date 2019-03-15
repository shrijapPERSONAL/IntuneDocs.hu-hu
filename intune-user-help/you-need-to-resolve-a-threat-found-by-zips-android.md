---
title: A Zimperium zIPS által talált fenyegetések elhárítása Android rendszeren
description: Útmutató az Android-eszközén észlelt biztonsági és alkalmazásfenyegetések elhárításához.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ffbb656-93cd-4e0b-96c0-c5038cd2cf31
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5aebe07259e2fcee009e97bc3c12d7c02933360
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "55846927"
---
# <a name="resolve-a-threat-found-by-zimperium-zips"></a>A Zimperium zIPS által azonosított fenyegetések elhárítása

A Zimperium zIPS egy mobilfenyegetés elleni védelmi szolgáltatás, amely lehetséges fenyegetéseket azonosít Android-eszközein. Ezek a fenyegetések a Céges portál alkalmazásnak lesznek jelentve, és megoldatlan nem megfelelőségi problémákként jelennek meg. Amíg az eszköze nem megfelelőként van azonosítva, előfordulhat hogy nem lesz lehetősége a következőkre:

* Hozzáférés a vállalati e-mailekhez
* Hozzáférés a vállalati Wi-Fi-hez
* Hozzáférés a SharePoint Online-hoz
* Vállalati fájlok szinkronizálása a OneDrive-val
* Hozzáférés a vállalati alkalmazásokhoz

Ez a cikk a Zimperium zIPS fenyegetési riasztásainak felismerését és a fenyegetések elhárításának módját ismerteti. 

## <a name="troubleshoot-virus-or-security-threat"></a>Vírus vagy biztonsági fenyegetés elhárítása  
Vírus vagy biztonsági fenyegetés észlelésekor a Zimperium zIPS vállalata hozzáférési szabályzatainak megfelelő korlátozásokat érvényesít. Vállalati hozzáférési szabályzatai megakadályozhatják, hogy hozzáférjen a munkájához szükséges hálózathoz, alkalmazásokhoz és e-mailekhez az eszközéről.  

A Zimperium zIPS párbeszédablakban hívja fel a figyelmét a hozzáférés visszaszerzéséhez szükséges teendőkre. Jelölje ki a fenyegetést, és hárítsa el azt az alkalmazáson belüli utasításokat követve.

Mivel az alkalmazás integrálva van vállalata MDM-szolgáltatójával, a hozzáférés korlátozásáról is figyelmeztetést kap a Céges portál alkalmazásban. A figyelmeztetés felszólítja, hogy a vírus vagy biztonsági fenyegetés elhárításához nyissa meg a Zimperium zIPS-t.  

  ![Példa képernyőkép a Céges portál Eszközök oldaláról, a Zimperium zIPS figyelmeztetésével.](./media/CP-lookout-virus-banner-1808.png)  

Válassza az érintett eszköz alatt megjelenő figyelmeztető szalagcímet. Megnyílik a Zimperium zIPS, és tájékoztatja Önt a fenyegetés elhárításának módjáról.  

## <a name="resolve-an-app-threat"></a>Alkalmazásfenyegetés elhárítása

Az eszközére nézve fenyegetőnek ítélt alkalmazás telepítésekor értesítést kap a Zimperium zIPS-ben. Amíg az érintett alkalmazás az eszközén marad, Ön nem fog hozzáférni a vállalati erőforrásokhoz.  

A megoldáshoz jelölje ki az alkalmazást a fenyegetéseknek a Zimperium zIPS-ben megjelenő listájában. Ezután kövesse a képernyőn megjelenő utasításokat az alkalmazás eltávolításához.    

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980). 
