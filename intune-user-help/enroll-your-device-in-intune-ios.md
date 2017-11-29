---
title: "A céges erőforrásokhoz történő hozzáférés beállítása | Microsoft Docs"
description: "Ismerteti az iOS-eszközök Intune-felügyelet alá helyezését"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ee4275ec7b9b455cf6ebf032123127fde97a9a74
ms.sourcegitcommit: 0b96ae18524eb976df01a5340631ef331357e666
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="set-up-access-to-your-company-resources"></a>A céges erőforrásokhoz történő hozzáférés beállítása

Az Ön cége rengeteg védett információt használ, az e-mailektől kezdve többek között a fájlokig és a hálózatokig. A cég a Microsoft Intune segítségével védi ezeket az információkat, amikor Ön az iOS-eszközéről fér hozzájuk. Ennek révén felügyelheti az erőforrásokat és tarthatja biztonságban őket, miközben Ön nyugodtan végezheti a munkáját a kedvenc eszközén.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> Ha céges e-maileket próbál elérni a Mail alkalmazásban, akkor a rendszer már feltehetőleg kérést jelenített meg Önnek, hogy az eszközt felügyeletre regisztrálja a biztonságos használat érdekében. Ahhoz, hogy iOS-eszközén is hozzá tudjon férni a céges e-mailekhez és más erőforrásokhoz, kövesse az alábbi útmutatót.

## <a name="before-you-start"></a>Előkészületek

- Csak akkor kezdje meg a folyamatot, ha egy munkamenetben végre tudja hajtani az egészet. Néhány percnél tovább tartó szünet esetén a folyamat általában megáll, és újra kell kezdeni.
- Ha a folyamat sikertelen, vissza kell térnie a Céges portál alkalmazásba, és ismét meg kell kísérelnie.
- Győződjön meg róla, hogy az eszközén működik a WiFi és a Safari.
- Töltse le az [Intune Céges portál alkalmazás telepítése, majd bejelentkezés a portálra](install-and-sign-in-to-the-intune-company-portal-app-ios.md) fájlt.


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Céges erőforrásokhoz történő hozzáférés beállítása a Céges portál alkalmazás használatával

|Megjelenő kép|Magyarázat|
|---|---|
|![A Céges portál bejelentkezési képernyője, alul a „Bejelentkezés” gombbal.](./media/ios-0-cp-enroll-1711.png)|Nyissa meg a Céges portál alkalmazást, és koppintson a **Bejelentkezés** gombra.|
|![Azure AD-bejelentkezés kérése.](./media/ios-0a-cp-enroll-1711.png)|Adja meg a céges e-mail-címét, majd koppintson a **Következő** elemre.|
|![Azure AD-jelszó kérése.](./media/ios-0b-cp-enroll-1711.png)|Adja meg a jelszót, majd koppintson a **Bejelentkezés** elemre.|
|![Céges erőforrások betöltése kezdőképernyő.](./media/ios-1-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![Feltételek és kikötések.](./media/ios-2-cp-enroll-1711.png)|Olvassa el, majd koppintson az **Összes elfogadása** elemre a feltételek és kikötések elfogadásához.|
|![Céges hozzáférés beállítása képernyő. Az eszköz felügyeletét és beállításait most kell kialakítani.](./media/ios-3-cp-enroll-1711.png)|Az **Eszköz felügyelet alá helyezése** elemre koppintva kezdje meg az eszköz alkalmassá tételét a céges erőforrásokhoz történő hozzáféréshez. Ha jelenleg nem tudja megtenni ezt, választhatja az **Elhalasztás** műveletet, de ebben az esetben nem férhet hozzá az e-mailjeihez, dokumentumaihoz, stb.|
|![Mit láthat a cégem képernyő.](./media/ios-4-cp-enroll-1711.png)|Az alul látható hivatkozásra kattintva **További információkat** kaphat arról, ami a cég számára látható. Ha nem kívánja megtekinteni, koppintson a **Folytatás** elemre.|
|![Következő lépések képernyő.](./media/ios-5-cp-enroll-1711.png)|Ez képernyő végigvezeti a beállítás folyamatának lépésein. A folyamat végrehajtása során a Safari, a Beállítások, és a Céges portál alkalmazásokat fogja használni. Koppintson a **Következő** elemre.|
|![Képernyő betöltése, miután a „Következő lépések” képernyőn a Következő elemre koppintott.](./media/ios-6-cp-enroll-1711.png)||
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-7-cp-enroll-1711.png)|A rendszer átirányítja Önt a Safarira, hogy felügyeleti információkat szerezzen az eszközről.|
|![A rendszer arra kéri, hogy nyissa meg a Beállítások alkalmazást.](./media/ios-8-cp-enroll-1711.png)|Az **Engedélyezés** elemre koppintva nyissa meg a Beállítások alkalmazást a konfigurációs profil letöltéséhez. Ezt kell telepíteni ahhoz, hogy a cége kezelhesse a vállalati információkat az eszközén.|
|![A profil megnyílik a beállításokban.](./media/ios-9-cp-enroll-1711.png)|Koppintson a **Telepítés** elemre.|
|![A profil modális párbeszédpaneljének telepítése a képernyő aljáról.](./media/ios-10-cp-enroll-1711.png)|Koppintson a **Telepítés** elemre.|
|![A profil telepítése folyamatban betöltési képernyő.](./media/ios-11-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![Profilkezelés figyelmeztetési képernyő.](./media/ios-12-cp-enroll-1711.png)|Ez az Apple által írt figyelmeztetés további információt nyújt arról, hogy milyen műveleteket lehet végrehajtani a felügyelt eszközökön. Részletesebb tudnivalók a [Milyen adatok láthatók a cég számára](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) című oldalon.|
|![A rendszer arra kéri, hogy adjon megbízást a távoli felügyeletre.](./media/ios-13-cp-enroll-1711.png)|A **Megbízom** elemre koppintással engedélyezze cégének, hogy a vállalati információkat és beállításokat felügyelje az eszközén.|
|![Profil telepítésének befejezése képernyő.](./media/ios-14-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![A profil telepítése megtörtént képernyő.](./media/ios-15-cp-enroll-1711.png)|A profilja telepítve van, hamarosan megkezdődhet az eszközén található vállalati információk és beállítások felügyelete.|
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-16-cp-enroll-1711.png)|A rendszer ismét átirányítja a Safarira, hogy lezárulhasson az eszköz felügyeleti információinak bekérése. |
|![A rendszer arra kéri, hogy nyissa meg a Céges portált.](./media/ios-17-cp-enroll-1711.png)|Koppintson a **Megnyitás** gombra.|
|![Vállalati erőforrások betöltése képernyő.](./media/ios-18-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![Válasszon eszközkategóriát a Céges portál alkalmazásban.](./media/ios-19-cp-enroll-1711.png)|Válassza ki az eszköznek leginkább megfelelő kategóriát. Ez általában attól függ, hogy ki az eszköz tulajdonosa, és hogy hol található az eszköz az idő legnagyobb részében.|
|![Kategória kiválasztva.](./media/ios-20-cp-enroll-1711.png)||
|![Eszközfelügyelet sikeres; most frissítenie kell a beállításokat.](./media/ios-21-cp-enroll-1711.png)|Sikeresen felügyelet alá helyezte az eszközt. Lehet, hogy még hátravan néhány beállítás, mint például a jelszó hossza, amelyet valószínűleg frissítenie kell a cég számára. A végrehajtáshoz koppintson az **Eszközbeállítások frissítése** lehetőségre.|
|![Eszközbeállítások megerősítése.](./media/ios-22-cp-enroll-1711.png)|A Céges portál ellenőrzi, hogy szükség van-e valamelyik beállítás frissítésére.|
|![A beállítások ellenőrzése lezárult, az operációs rendszer verziója nem megfelelő](./media/ios-23-cp-enroll-1711.png)|A Céges Portál javaslatokat ad a beállításokkal kapcsolatos problémák megoldására. A problémák megoldását követően koppintson a **Beállítások ellenőrzése** elemre.|
|![Eszközbeállítások megerősítése képernyő](./media/ios-24-cp-enroll-1711.png)|Az eszköz ellenőrzi, hogy a beállítások elég biztonságosak-e a céges erőforrások eléréséhez.|
|![Sikeresen regisztrált és frissítette beállításait](./media/ios-25-cp-enroll-1711.png)|Gratulálunk! Ezzel megtörtént az eszköz Intune-beli regisztrálása.|

> [!Note]
> Már csak néhány lépést kell megtennie, hogy az eszköz teljes felügyelet alá kerüljön. További információ a [távközlésiköltség-kezelőben való regisztrációról](enroll-your-device-with-telecom-expense-management-ios.md). Ha a cége az Apple Készülékregisztrációs programját használja, további információt [itt](enroll-your-device-dep-ios.md) találhat.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com).
