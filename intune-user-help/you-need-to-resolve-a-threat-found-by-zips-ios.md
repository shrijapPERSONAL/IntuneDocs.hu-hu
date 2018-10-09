---
title: A Zimperium zIPS által talált fenyegetések elhárítása iOS rendszeren | Microsoft Docs
description: Megtudhatja, hogyan hárítsa el az iOS-eszközön észlelt fenyegetéseket.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: eaccd9c0-cd46-48e2-8675-4c022c74f672
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.openlocfilehash: 8b77eeb57bb3887e28242ca845ec6e83d4e9a817
ms.sourcegitcommit: 2d30ec70b85f49a7563adcab864c1be5a63b9947
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48863073"
---
# <a name="resolve-a-threat-found-by-zimperium-zips"></a>A Zimperium zIPS által azonosított fenyegetések elhárítása

A Zimperium zIPS egy mobilfenyegetés elleni védelmi szolgáltatás, amely lehetséges fenyegetéseket azonosít iOS-eszközein. Ezek a fenyegetések a Céges portál alkalmazásnak lesznek jelentve, és megoldatlan nem megfelelőségi problémákként jelennek meg. Amíg az eszköze nem megfelelőként van azonosítva, előfordulhat hogy nem lesz lehetősége a következőkre:

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
  
## <a name="troubleshoot-an-app-threat"></a>Alkalmazásfenyegetés hibaelhárítása

Az eszközére nézve fenyegetőnek ítélt alkalmazás telepítésekor értesítést kap a Zimperium zIPS-ben. Amíg az érintett alkalmazás az eszközén marad, Ön nem fog hozzáférni a vállalati erőforrásokhoz.  

A megoldáshoz jelölje ki az alkalmazást a fenyegetéseknek a Zimperium zIPS-ben megjelenő listájában. Ezután kövesse a képernyőn megjelenő utasításokat az alkalmazás eltávolításához.  

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).   
