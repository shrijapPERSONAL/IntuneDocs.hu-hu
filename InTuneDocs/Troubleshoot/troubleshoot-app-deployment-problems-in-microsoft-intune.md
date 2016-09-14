---
title: "Alkalmazástelepítéssel kapcsolatos problémák elhárítása| Microsoft Intune"
description: "Ez a témakör a Microsoft Intune-ban jelentkező, alkalmazástelepítéssel kapcsolatos problémák megoldásához nyújt segítséget."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa96cf3a1909e3ea2187a3beb0aede3228894504
ms.openlocfilehash: 9f4b91bd523c82665bcac54902b2e8cc9c72ef75


---

# Alkalmazástelepítéssel kapcsolatos problémák elhárítása a Microsoft Intune-ban
Ha problémába ütközik az alkalmazások Intune-nal történő telepítése vagy felügyelete során, kezdje itt. Ez a témakör néhány gyakori problémát és azok megoldását ismerteti.

## Gyakori alkalmazástelepítési problémák

### Ha hiányzik az IT-csoport elérhetőségével kapcsolatos információ a vállalati portálról

1.  Az Intune felügyeleti konzoljában válassza a **Felügyelet** &gt; **Vállalati portál** lehetőséget.

2.  Adja meg az **IT-csoport elérhetőségi** adatait.

### Ha bizonyos alkalmazások nem jelennek meg a listában

1.  Győződjön meg arról, hogy olyan felhasználó vagy eszköz esetében ellenőrzi az alkalmazáslistát, aki vagy amely számára telepítette az alkalmazást.

2.  Győződjön meg arról, hogy az eszköz megfelel az alkalmazás követelményeinek.

### Ha hibaüzenetet kap egy alkalmazás letöltése közben

1.  Ellenőrizze, hogy nincs-e felhasználónként egyszerre több letöltés folyamatban. Minden felhasználó egyszerre csak egy alkalmazást tölthet le.

2.  Győződjön meg arról, hogy fiókonként nincs-e folyamatban túl sok egyidejű letöltés. Várjon néhány percet, és próbálkozzon újra.

3.  Ha olyan natív iOS-üzenetet kap, amely szerint a telepítés nem lehetséges, a telepítés megszakadt, vagy újra kell próbálkoznia, lehetséges, hogy megnőtt az adatforgalom. Várjon néhány percet, és próbálkozzon újra.

4.  Ha az iOS-alkalmazás letöltése befejeződött, de az alkalmazástelepítés sikertelen, lehetséges, hogy gond van a megadott alkalmazásfájlokkal.


### Ha az alkalmazás feltöltése nem fejeződik be

1.  Az alkalmazás feltöltésekor a rendszer először a metaadatokat, majd az alkalmazáscsomagot tölti fel. A metaadatok feltöltése után az alkalmazás feltöltése „folyamatban lévőként” jelenik meg. Ha azt látja, hogy az alkalmazás szokatlanul hosszú ideig marad folyamatban lévő feltöltési állapotban, törölje az alkalmazást, majd töltse fel újra.

2.  Amíg az alkalmazás folyamatban lévő feltöltési állapotban van, ne avatkozzon be az alkalmazás telepítésébe.

### Ha hibát tapasztal egy iOS-alkalmazás telepítésekor

1.  Győződjön meg arról, hogy a szervezet tűzfala lehetővé teszi a hozzáférést az Apple üzembe helyezési és hitelesítő webhelyeihez.

2.  További információt az Apple fejlesztői dokumentációjában talál.

### Ha a felügyelt alkalmazások nem jelentik a telepítési állapotot

A rendszer nem gyűjtötte be a felügyelt alkalmazások telepítési állapotát a Microsoft Intune 2014 novemberi szolgáltatásfrissítése előtt. Olyan eszközöknél, amelyeken e szolgáltatásfrissítés előtt telepített felügyelt alkalmazásokat, frissítse az egyes alkalmazástelepítéseket a megfelelő telepítési művelettel (például: **Elérhető telepítés**). Minden eszköz frissíteni fogja az alkalmazást az elérhető alkalmazások automatikus ellenőrzésekor. További információ: [Alkalmazások frissítése a Microsoft Intune-nal](/intune/deploy-use/update-apps-using-microsoft-intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Alkalmazástelepítési hibakódok
A következő táblázat az Intune-alkalmazástelepítés közben gyakran előforduló hibákat, a valószínű okokat és a hibakereséshez szükséges lehetséges megoldásokat tartalmazza.

|Hibakód|Lehetséges probléma|Javasolt megoldás|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (ügyfélhiba)|Az alkalmazás telepítéséhez közvetlen telepítést lehetővé tevő rendszerrel kell rendelkeznie.|Győződjön meg arról, hogy az alkalmazáscsomag megbízható aláírással rendelkezik, és olyan tartományhoz csatlakoztatott eszközön van telepítve, amelyen engedélyezve van az AllowAllTrustedApps házirend, vagy olyan Windows-alapú közvetlen telepítést lehetővé tevő licenccel rendelkező eszközön van telepítve, amelyen engedélyezve van az AllowAllTrustedApps házirend (ezt a Windows RT rendszerű eszközök regisztrációjakor alkalmazza a szolgáltatás).|
|0x80073CF0|A csomag nem nyitható meg.|Lehetséges okok:<br /><br />-   A csomag nincs aláírva.<br />-   A közzétevő neve nem egyezik meg az aláíró tanúsítvány tulajdonosával.<br /><br />További információt az AppxPackagingOM eseménynaplóban talál.|
|0x80073CF3|Nem sikerült ellenőrizni a csomag frissítéseit, függőségeit vagy ütközéseit|Lehetséges okok:<br /><br />-   A bejövő csomag ütközik egy telepített csomaggal.<br />-   Nem található a megadott csomagfüggőség.<br />-   A csomag nem támogatja a megfelelő processzorarchitektúrát.<br /><br />További információt az AppXDeployment-Server eseménynaplóban talál.|
|0x80073CFB|A megadott csomag már telepítve van, és a csomag újratelepítése le van tiltva.|Ez a hiba akkor fordulhat elő, ha olyan csomagot telepít, amely nem azonos a már telepített csomaggal. Ellenőrizze, hogy a csomag tartalmaz-e digitális aláírást. Ha újraépít vagy újra aláír egy csomagot, a csomag nem lesz bitenként azonos az előzőleg telepített csomaggal. Ez a hiba kétféleképpen javítható ki:<br /><br />-   Növelje az alkalmazás verziószámát, majd építse és írja alá újra a csomagot.<br />-   Az új csomag telepítése előtt távolítsa el a régi csomagot a rendszer minden felhasználója esetében.|
|0x87D1041C|Az alkalmazás telepítése sikeres volt, de a rendszer nem ismeri fel az alkalmazást.|- Az alkalmazást az Intune sikeresen telepítette, azonban a későbbiekben valaki (valószínűleg a végfelhasználó) eltávolította. Kérje meg a felhasználót, hogy telepítse újra az alkalmazást a vállalati portálról. A kötelező alkalmazások újratelepítése automatikusan megtörténik az eszköz következő bejelentkezésekor.|

### További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.



<!--HONumber=Aug16_HO5-->


