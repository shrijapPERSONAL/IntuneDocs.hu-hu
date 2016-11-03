---
title: "A hozzáférés korlátozása mobil veszélyforrások elleni védelemmel | Microsoft Intune"
description: "A vállalati erőforrásokhoz való hozzáférés korlátozása az eszköz-, a hálózati és az alkalmazáskockázat alapján."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c3cf5e6b32ad24d4972fd147331dda7d2d43e8c6
ms.openlocfilehash: d4eadb73aac14a375f41c434a4303a885bfbae64


---

# A vállalati erőforrásokhoz való hozzáférés korlátozása az eszköz-, a hálózati és az alkalmazáskockázat alapján
A Lookout, a Microsoft Intune-nal integrált mobil veszélyforrások elleni védelmi megoldás (MTP) kockázatértékelése alapján korlátozható a vállalati erőforrások elérése mobileszközökről. A kockázatértékelés a Lookout MTP szolgáltatás által gyűjtött, az operációs rendszer biztonsági réseivel, a telepített rosszindulatú alkalmazásokkal és a hálózati profilokkal kapcsolatos telemetrikus adatokon alapul. A kockázatértékelés alapján feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, és engedélyezhetők vagy letilthatók azok az eszközök, amelyek az észlelt veszélyforrások alapján nem megfelelőnek minősülnek.  Jelenleg ez kizárólag a Microsoft Intune-ban regisztrált, **4.1-es vagy annál újabb** verziójú **Android** rendszert futtató eszközökön támogatott.  
## Milyen problémára nyújt ez megoldást?
A vállalatoknak és a szervezeteknek meg kell védeniük érzékeny adataikat a folyamatosan keletkező különböző veszélyforrásoktól, így a fizikai, az alkalmazás- és a hálózat alapú fenyegetésektől, valamint az operációs rendszer biztonsági réseitől.

A vállalatok hagyományosan a számítógépeiket védték a rosszindulatú támadásoktól. A mobileszközök olyan új, feltörekvő területet jelentenek, ahol gyakran elégtelen a védelem. Jóllehet a mobilplatformok operációs rendszerei rendelkeznek olyan beépített védelmi technikákkal, mint az alkalmazások elkülönítése és az ellenőrzött alkalmazásáruházak, e platformok továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Ahogy az alkalmazottak egyre nagyobb mértékben használják mobileszközeiket munkára, és érzékeny és értékes információkhoz férnek hozzá ezekkel az eszközökkel, az eszközöket meg kell védeni a kifinomult támadások sokaságától.

Az olyan MTP-megoldások, mint a Lookout által biztosított kockázatértékelés alapján az Intune lehetővé teszi a vállalati erőforrásokhoz és adatokhoz való hozzáférés ellenőrzését.

## Hogyan segít az Intune és a Lookout a vállalati erőforrások mobil veszélyforrások elleni védelmében?
A Lookout mobileszközökön futó alkalmazása (Lookout for Work) rögzíti a fájlrendszer, a hálózati verem és az eszközök és alkalmazások telemetrikus adatait (ha ezek elérhetők), és továbbítja azokat a Lookout mobil veszélyforrások elleni védelmi (MTP) felhőszolgáltatás felé, amely kiszámítja az eszköz összesített kockázatát a mobil veszélyforrások tekintetében. Az MTP-konzolon a fenyegetések kockázatiszint-besorolása igény szerint módosítható.  
Az Intune megfelelőségi szabályzata már tartalmaz egy új szabályt a Lookout mobil fenyegetések elleni védelemhez, amely a Lookout MTP kockázatértékelésén alapul. Ha ez a szabály engedélyezve van, akkor a Microsoft Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Amennyiben az eszköz az értékelés alapján nem felel meg a megfelelőségi szabályzatnak, akkor feltételes hozzáférési szabályzatok segítségével letiltható a hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A hozzáférés letiltása esetén a rendszer biztosít egy forgatókönyvet a végfelhasználók részére, amelynek segítségével megoldhatják a problémát, és helyreállíthatják hozzáférésüket a vállalati erőforrásokhoz. Ez a forgatókönyv a Lookout for Work alkalmazásból indítható.

## Példaforgatókönyvek
Néhány gyakori helyzet:
### Rosszindulatú alkalmazások jelentette fenyegetés:
Rosszindulatú alkalmazások, például kártevők észlelése esetén az eszközön, letiltható:
* Az eszköz hozzáférése a vállalati e-mailekhez a veszélyforrás megszüntetése előtt.
* A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazás segítségével.
* Az eszköz hozzáférése az üzleti szempontból kritikus fontosságú alkalmazásokhoz.

**Hozzáférés letiltása rosszindulatú alkalmazások észlelése esetén:**
![ábra, amely azt mutatja, ahogy a feltételes hozzáférési szabályzat letiltja a hozzáférést, ha az eszköz a rajta észlelt rosszindulatú alkalmazások alapján nem megfelelőnek minősül](../media/mtp/malicious-apps-blocked.png)

**A rendszer feloldja az eszköz letiltását és az eszköz újra hozzáférhet a vállalati erőforrásokhoz a fenyegetés kiküszöbölését követően:**

![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést, amikor a fenyegetés kiküszöbölését követően az eszköz ismét megfelelőnek minősül](../media/mtp/malicious-apps-unblocked.png)
### Hálózati fenyegetés:
Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást, és az eszköz jelentette kockázat alapján korlátozza a Wi-Fi-hálózatok elérését.

**Wi-Fi-hálózaton keresztüli hozzáférés letiltva:**
![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat a hálózati fenyegetések alapján letiltja a Wi-Fi-hálózat elérését](../media/mtp/network-wifi-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-wifi-unblocked.png)
### Hálózati fenyegetés (megakadályozza a hozzáférést a SharePoint Online-hoz):

Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**Hozzáférés letiltva a SharePoint Online-hoz az eszközön észlelt fenyegetés alapján:**

![Ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat letiltotta az eszköz hozzáférését a SharePoint Online-hoz az észlelt fenyegetés alapján](../media/mtp/network-spo-blocked.png)


**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![Ábra, amely azt mutatja, hogy a hálózati fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-spo-unblocked.png)

## További lépések
A legfontosabb lépések a megoldás megvalósítása érdekében:
1.  [Az előfizetés beállítása a Lookout mobilfenyegetések elleni védelemhez](set-up-your-subscription-with-lookout-mtp.md)
2.  [A Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md)
3.  [A Lookout for Work alkalmazások konfigurálása és központi telepítése](configure-and-deploy-lookout-for-work-apps.md)
4.  [Megfelelőségi szabályzat konfigurálása](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [A Lookout-integráció hibaelhárítása](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Sep16_HO3-->


