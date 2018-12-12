---
title: Alkalmazások telepítésével kapcsolatos problémák elhárítása
titlesuffix: Microsoft Intune
description: A Microsoft Intune hibaelhárítási paneljével elháríthatja az alkalmazások telepítésével kapcsolatos problémákat.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd43bfda69b42fb81a72d520d169fe1785161f65
ms.sourcegitcommit: 0f19bc5c76b7c0835bfd180459f2bbd128eec1c2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53267011"
---
# <a name="troubleshoot-app-installation-issues"></a>Alkalmazások telepítésével kapcsolatos problémák elhárítása

A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. A Microsoft Intune olyan adatokat szolgáltat az alkalmazástelepítésbeli hibákról, amelyekkel az ügyfélszolgálati operátorok és az Intune-rendszergazdák megtekinthetik az alkalmazásadatokat, és reagálhatnak az ügyfelek kérelmeire. Az Intune hibaelhárítási panelje megjeleníti a hibák adatait, így a felhasználói eszközökön kezelt alkalmazások információit is. Az alkalmazások végpontok közötti életciklusához tartozó adatok a **Felügyelt alkalmazások** panelen, az egyes eszközök alatt tekinthetők meg. Itt megtekintheti a telepítési problémákat, például az alkalmazás létrehozási, módosítási és célzási dátumát, valamint az eszközökre való továbbításának dátumát. 

## <a name="to-review-app-troubleshooting-details"></a>Az alkalmazás hibaelhárítási adatainak ellenőrzése

Az Intune az adott felhasználók eszközein telepített alkalmazások alapján szolgáltat hibaelhárítási információkat.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Hibaelhárítás** lehetőséget.
4. A felhasználó kiválasztásához kattintson a **Felhasználó kijelölése** lehetőségre. Ekkor megjelenik a **Felhasználók kijelölése** panel.
5. Jelöljön ki egy felhasználót a megfelelő név vagy e-mail cím beírásával. Kattintson a **Kijelölés** gombra a lap alján. A felhasználóval kapcsolatos hibaelhárítási információ a **Hibaelhárítás** panelen jelenik meg. 
6. Az **Eszközök** listában jelölje ki azt az eszközt, amelyen hibaelhárítást szeretne végezni.
    ![Az Intune Hibaelhárítás panelje.](media/troubleshoot-app-install-01.png)
7. A kijelölt eszköz paneljén válassza a **Felügyelt alkalmazások** lehetőséget. Megjelenik a felügyelt alkalmazások listája.
    ![Az Intune által kezelt eszköz adatai.](media/troubleshoot-app-install-02.png)
8. Válassza ki azt az alkalmazást, amelynél hibát jelez a **Telepítés állapota**.
    ![A kiválasztott alkalmazás, amelynél megjelennek a telepítési hiba adatai.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Ugyanazt az alkalmazást eltérő alkalmazásműveleti szándékkal rendelhetik hozzá különböző csoportokhoz. Egy alkalmazás feloldott szándéka például **Kizárva** értéket jelez, ha az alkalmazás ki van zárva egy felhasználó számára az alkalmazás-hozzárendelés során. További információ: [Alkalmazások hozzárendelési ütközéseinek feloldása](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Ha egy szükséges alkalmazás telepítése sikertelen, akkor Ön vagy a segélyszolgálat szinkronizálhatja az eszközt, és újra megkísérelheti az alkalmazás telepítését.

Az alkalmazástelepítési hiba információi ismertetik a problémát. Ezen adatok segítségével meghatározhatja a probléma feloldásához szükséges műveletet. További információ az alkalmazástelepítési problémák elhárításáról: [Alkalmazástelepítési problémák hibakódjai](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> A **Hibaelhárítás** panel a böngészőben a [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) címen is elérhető.

## <a name="app-installation-errors"></a>Alkalmazástelepítési hibák

Az alábbi hibaüzenetek és leírások az Androidos és iOS-es telepítési hibák részleteit mutatják be. 

### <a name="android-errors"></a>Android hibák

|    Hibaüzenet/hibakód    |    Leírás    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Nem sikerült telepíteni az alkalmazást. (0xC7D14FB5)    |    Ez a hibaüzenet akkor jelenik meg, ha az Intune nem tudja megállapítani az Android-alkalmazás telepítési hibájának kiváltó okát. A hiba során az Android nem adott semmilyen információt.       Ez a hiba akkor lép fel, ha az APK letöltése sikeres volt, az alkalmazás telepítése azonban sikertelen. A hibát gyakran egy hibás APK-fájl okozza, amelyet nem lehet telepíteni az eszközre. Egy lehetséges ok, ha a Google Play Protect biztonsági okokból letiltja az alkalmazás telepítését. Egy másik lehetséges ok, ha az eszköz nem támogatja az alkalmazást. Például ha az alkalmazás az API 21-es vagy újabb verzióját igényli, az eszközön pedig az API 19-es verziója van telepítve.         Az Intune ezt a hibát adja vissza a DA és a KNOX eszközökhöz is, és bár előfordulhat, hogy megjelenik egy értesítés, amelyre kattintva a felhasználó újrapróbálkozhat, ha a problémát az APK okozza, akkor a telepítés mindig sikertelen lesz. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.        |
|    Az alkalmazás telepítése megszakadt, mert a telepítő (APK) fájl törölve lett a letöltést követően, de még a telepítés előtt. (0xC7D14FBA)    |    Az APK letöltése sikeres volt, de a fájl el lett távolítva az eszközről, még mielőtt a felhasználó telepítette volna az alkalmazást. Ez akkor fordulhat elő, ha sok idő telt el a letöltés és a telepítés között. Például ha a felhasználó megszakította az eredeti telepítést, várt egy ideig, majd ezután kattintott rá az újrapróbálkozásról szóló értesítésre.         Ez a hibaüzenet csak a DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyvek csendben elvégezhetők. Megjelenítünk egy újrapróbálkozási értesítést, amelyet a felhasználó elfogadhat a megszakítás helyett. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.    |
|    Az alkalmazás telepítése megszakadt, mert a telepítés közben a folyamat újraindult. (0xC7D14FBB)    |    Az eszköz újra lett indítva az APK telepítése során, emiatt a telepítés megszakadt.        Ez a hibaüzenet a DA- és KNOX-eszközök esetén is megjelenik. Az Intune megjelenít egy értesítést, amelyre rákattintva a felhasználó újrapróbálkozhat. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.    |
|    Az alkalmazás nem észlelhető a sikeres telepítést követően. (0x87D1041C)    |    A felhasználó explicit módon eltávolította az alkalmazást. Ezt a hibát nem az ügyfél adja vissza. A hibát az okozza, hogy az alkalmazás valamikor telepítve lett, de aztán a felhasználó eltávolította. Ez a hiba csak a szükséges alkalmazások esetén jelenhet meg. A nem szükséges alkalmazásokat a felhasználó eltávolíthatja. Ez a hiba csak a DA esetén következik be. A KNOX nem engedélyezi a felügyelt alkalmazások eltávolítását.       A következő szinkronizáláskor az eszközön újra megjelenik az értesítés arról, hogy a felhasználó végezze el a telepítést.   A felhasználó figyelmen kívül hagyhatja az értesítést. Az eszköz azonban egészen addig jelenteni fogja a hibát, amíg a felhasználó nem telepíti az alkalmazást.    |
|    A letöltés egy ismeretlen hiba miatt nem sikerült. (0xC7D14FB2)    |    Ez a hiba akkor fordul elő, ha a letöltés sikertelenül végződik. A hibát gyakran a Wi-Fi problémái vagy a lassú kapcsolat okozza.       Ez a hiba csak DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyveknél a felhasználó nem kap értesítést a telepítésről, mert az csendben elvégezhető. Az Intune megjelenít egy értesítést, amelyre rákattintva a felhasználó újrapróbálkozhat. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.    |
|    A letöltés egy ismeretlen hiba miatt nem sikerült. Az eszköz a következő szinkronizáláskor újra megpróbálkozik a szabályzattal. (0xC7D15078)    |    Ez a hiba akkor fordul elő, ha a letöltés sikertelenül végződik. A hibát gyakran a Wi-Fi problémái vagy a lassú kapcsolat okozza.       Ez a hiba csak DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyveknél a felhasználó nem kap értesítést a telepítésről, mert az csendben elvégezhető.    |
|    A végfelhasználó megszakította az alkalmazás telepítését. (0xC7D14FB1)    |    A felhasználó explicit módon eltávolította az alkalmazást. Ez a hiba akkor jelenik meg, ha a felhasználó megszakította az Android operációs rendszer telepítési tevékenységét. Amikor az operációs rendszer telepítésről szóló prompt megjelent, a felhasználó a Mégse gombra vagy a prompton kívülre kattintott.        Ez a hiba csak DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyveknél a felhasználó nem kap értesítést a telepítésről, mert az csendben elvégezhető. Az Intune megjelenít egy értesítést, amelyre rákattintva a felhasználó újrapróbálkozhat. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.    |
|    A fájl letöltésének folyamata váratlanul leállt. (0xC7D15015)    |    Az operációs rendszer leállította a letöltési folyamatot, mielőtt az befejeződött volna. Ez a hiba akkor fordulhat elő, ha az eszköz töltöttségi szintje túl alacsony, vagy a letöltés túl sokáig tart.       Ez a hiba csak DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyveknél a felhasználó nem kap értesítést a telepítésről, mert az csendben elvégezhető. Az Intune megjelenít egy értesítést, amelyre rákattintva a felhasználó újrapróbálkozhat. Ha az alkalmazás egy opcionálisan elérhető alkalmazás, az értesítés elvethető. Azonban ha az alkalmazás szükséges, az értesítés nem vethető el.    |
|    A fájlletöltési szolgáltatás váratlanul leállt. Az eszköz a következő szinkronizáláskor újra megpróbálkozik a szabályzattal. (0xC7D1507C)    |    Az operációs rendszer leállította a letöltési folyamatot, mielőtt az befejeződött volna. Ez a hiba akkor fordulhat elő, ha az eszköz töltöttségi szintje túl alacsony, vagy a letöltés túl sokáig tart.       Ez a hiba csak DA-forgatókönyveknél jelenik meg. A KNOX-forgatókönyveknél a felhasználó nem kap értesítést a telepítésről, mert az csendben elvégezhető.    |

### <a name="ios-errors"></a>iOS hibák

|    Hibaüzenet/hibakód    |    Leírás    |
|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    (0x87D12906)    |    Az Apple MDM-ügynök azt adta vissza, hogy a telepítési parancs sikertelen volt.        |
|    (0x87D1313C)    |    A hálózati kapcsolat megszakadt a frissített letöltési szolgáltatás URL-címének az eszközre való küldése közben. Pontosabban a megadott gazdanévvel rendelkező kiszolgáló nem található.    |
|    Az iOS-eszköz jelenleg elfoglalt. (0x87D11388)    |    Az iOS-eszköz elfoglalt volt, ami hibát eredményezett.    |
|    Az alkalmazás telepítése nem sikerült. (0x87D13B64)    |    Hiba történt az alkalmazás telepítése közben. A hiba okának felderítéséhez szükség van az XCODE-naplókra.    |
|    Az alkalmazás felügyelt alkalmazás, de lejárt, vagy a felhasználó eltávolította. (0x87D13B66)    |    A felhasználó explicit módon eltávolította az alkalmazást. Vagy az alkalmazás lejárt, de nem sikerült letölteni, vagy az alkalmazás észlelésének eredménye nem egyezik meg az eszköz által küldött válasszal.   Emellett a hibát az iOS 9.2.2 platform egyik hibája is okozhatja.    |
|    Az alkalmazás telepítésre van ütemezve, de a tranzakció elvégzéséhez egy érvényesítési kódra van szüksége.   (0x87D13B60)    |    Ez a hiba általában az iOS Store áruház fizetős alkalmazásainál fordul elő.     |
|    Az alkalmazás nem észlelhető a sikeres telepítést követően. (0x87D1041C)    |    Az alkalmazás észlelésének eredménye nem egyezett meg az eszköz által küldött válasszal.    |
|    A felhasználó visszautasította az alkalmazás telepítésére vonatkozó ajánlatot. (0x87D13B62)    |    Az alkalmazás első telepítése közben a felhasználó a megszakítás lehetőségre kattintott.    |
|    A felhasználó visszautasította az alkalmazás frissítésére vonatkozó ajánlatot. (0x87D13B63)    |    A frissítési folyamat során a végfelhasználó a megszakítás lehetőségre kattintott.     |
|    Ismeretlen hiba (0x87D103E8)    |    Ismeretlen alkalmazástelepítési hiba történt. Ez a hiba akkor jelenik meg, ha a másik hiba nem következett be.    |

### <a name="other-installation-errors"></a>Egyéb telepítési hibák

|    Üzenet/hibakód    |    Leírás    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (ügyfélhiba)    |    Az alkalmazás telepítéséhez közvetlen telepítést lehetővé tevő rendszerrel kell rendelkeznie. Győződjön meg arról, hogy az alkalmazáscsomag megbízható aláírással és telepítve van egy tartományhoz csatlakoztatott eszköz, amely rendelkezik a **AllowAllTrustedApps** házirend engedélyezve van, vagy a Windows közvetlen telepítési licenccel rendelkező eszközök esetén a  **AllowAllTrustedApps** házirend engedélyezve van. További információkért lásd: [csomagolási, telepítési és lekérdezési Windows Store Apps hibaelhárítási](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    A csomag nem nyitható meg. Lehetséges okok:<ul><li> A csomag nincs aláírva.</li><li> A közzétevő neve nem egyezik meg az aláíró tanúsítvány tulajdonosával.</li></ul> Ellenőrizze a **AppxPackagingOM** eseménynaplóban talál. További információkért lásd: [csomagolási, telepítési és lekérdezési Windows Store Apps hibaelhárítási](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    A csomag nem sikerült a frissítés, függőségeinek vagy ütközéseinek érvényességét. Lehetséges okok:<ul><li> A bejövő csomag ütközik egy telepített csomaggal.</li><li> Nem található a megadott csomagfüggőség.</li><li> A csomag nem támogatja a megfelelő processzorarchitektúrát.</li></ul> Ellenőrizze a **AppXDeployment-Server** eseménynaplóban talál. További információkért lásd: [csomagolási, telepítési és lekérdezési Windows Store Apps hibaelhárítási](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    A megadott csomag már telepítve van, és a csomag újratelepítése le van tiltva. Ezt a hibaüzenetet kapja, amely nem azonos a csomagot, amely már telepítve van a csomag telepítésekor sikerült. Ellenőrizze, hogy a csomag tartalmaz-e digitális aláírást. Ha újraépít vagy újra aláír egy csomagot, a csomag nem lesz bitenként azonos az előzőleg telepített csomaggal. Ez a hiba kétféleképpen javítható ki:<ul><li> Növelje a verziószámot, az alkalmazás, majd építse és írja alá újra a csomagot.</li><li> Távolítsa el a régi csomagot a rendszer minden felhasználója esetében, az új csomag telepítése előtt.</li></ul> További információkért lásd: [csomagolási, telepítési és lekérdezési Windows Store Apps hibaelhárítási](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Az alkalmazás telepítése sikeres volt, de a rendszer nem ismeri fel az alkalmazást. Az alkalmazás volt Intune sikeresen telepítette, majd később eltávolítja. Az alkalmazás okai a következők:<ul><li> A végfelhasználó eltávolítja az alkalmazást.</li><li> Az azonosító adatokat a csomagban nem egyezik, milyen hibás alkalmazások jelentett.</li><li>Az önfrissítési MSIs a verzió-kezelő nem egyezik az adatokat az alkalmazás, az Intune-on kívül frissítést követően.</li></ul> Kérje meg a felhasználót, hogy telepítse újra az alkalmazást a vállalati portálról. Vegye figyelembe, hogy kötelező alkalmazások újratelepítése automatikusan, amikor az eszköz következő bejelentkezésekor.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>A Microsoft Áruházból származó alkalmazások hibáinak elhárítása

A [Troubleshooting packaging, deployment, and query of Microsoft Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (A Microsoft Áruházbeli alkalmazások csomagolási, telepítési és lekérdezési hibáinak elhárítása) című cikkben foglaltak segítenek elhárítani az alkalmazásoknak a Microsoft Áruházból akár Intune-nal, akár más módon történő telepítésekor tapasztalt gyakori problémákat.

## <a name="next-steps"></a>További lépések

- További információt az Intune hibaelhárításáról a [Segítségnyújtás a céges felhasználóknak a hibaelhárítási portál használatával](help-desk-operators.md) című témakörben talál. 
- Ismertető a Microsoft Intune esetleges ismert problémáiról. További információt [Az Intune ismert problémái](known-issues.md) című témakörben talál.
- További segítségre van szüksége? Ismerje meg, [hogyan kérhet támogatást az Intune-hoz](get-support.md).
