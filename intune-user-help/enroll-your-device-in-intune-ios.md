---
title: A céges erőforrásokhoz történő hozzáférés beállítása | Microsoft Docs
description: Ismerteti az iOS-eszközök Intune-felügyelet alá helyezését
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c29c01169483b408528db71b1e9bb2b718220ddc
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/04/2018
ms.locfileid: "30755249"
---
# <a name="set-up-access-to-your-company-resources"></a>A céges erőforrásokhoz történő hozzáférés beállítása

Az Ön cége rengeteg védett információt használ, az e-mailektől kezdve többek között a fájlokig és a hálózatokig. A cég a Microsoft Intune segítségével védi ezeket az információkat, amikor Ön az iOS-eszközéről fér hozzájuk. Ennek révén felügyelheti az erőforrásokat és tarthatja biztonságban őket, miközben Ön nyugodtan végezheti a munkáját a kedvenc eszközén.

> [!NOTE]
> Ha céges e-maileket próbál elérni a Mail alkalmazásban, akkor a rendszer már feltehetőleg kérést jelenített meg Önnek, hogy az eszközt felügyeletre regisztrálja a biztonságos használat érdekében. Ahhoz, hogy iOS-eszközén is hozzá tudjon férni a céges e-mailekhez és más erőforrásokhoz, kövesse az alábbi útmutatót.

## <a name="before-you-start"></a>Előkészületek

- Csak akkor kezdje meg a folyamatot, ha egy munkamenetben végre tudja hajtani az egészet. Néhány percnél tovább tartó szünet esetén a folyamat általában megáll, és újra kell kezdeni.
- Ha a folyamat sikertelen, vissza kell térnie a Céges portál alkalmazásba, és ismét meg kell kísérelnie.
- Győződjön meg róla, hogy az eszközén működik a WiFi és a Safari.
- Töltse le és telepítse az [Intune céges portál alkalmazást](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Céges erőforrásokhoz történő hozzáférés beállítása a Céges portál alkalmazás használatával

|Megjelenő kép|Magyarázat|
|---|---|
|![A Céges portál bejelentkezési képernyője, alul a „Bejelentkezés” gombbal.](./media/ios-01-cp-enroll-1802.png)|Nyissa meg a Céges portál alkalmazást, és koppintson a **Bejelentkezés** gombra.|
|![Azure AD-bejelentkezés kérése.](./media/ios-02-cp-enroll-1802.png)|Adja meg a céges e-mail-címét, majd koppintson a **Következő** elemre.|
|![Azure AD-jelszó kérése.](./media/ios-03-cp-enroll-1802.png)|Adja meg a jelszót, majd koppintson a **Bejelentkezés** elemre.|
|![Céges erőforrások betöltése kezdőképernyő.](./media/ios-04-cp-enroll-1802.png)|Várja meg, amíg betöltődik.|
|![A használati feltételek oldala.](./media/ios-05-cp-enroll-1802.png)|Olvassa el, majd koppintson az **Összes elfogadása** elemre a feltételek és kikötések elfogadásához.|
|![Céges hozzáférés beállítása képernyő. Az eszköz felügyeletét és beállításait most kell kialakítani.](./media/ios-06-cp-enroll-1802.png)|Az **Kezdés** elemre koppintva kezdje meg az eszköz alkalmassá tételét a céges erőforrásokhoz történő hozzáféréshez. Ha jelenleg nem tudja megtenni ezt, választhatja az **Elhalasztás** műveletet, de ebben az esetben nem férhet hozzá az e-mailjeihez, dokumentumaihoz, stb.|
|![Mit láthat a cégem képernyő.](./media/ios-07-cp-enroll-1802.png)|Az alul látható hivatkozásra kattintva **További információkat** kaphat arról, ami a cég számára látható. Ha nem kívánja megtekinteni, koppintson a **Folytatás** elemre.|
|![Következő lépések képernyő.](./media/ios-08-cp-enroll-1802.png)|Ez képernyő végigvezeti a beállítás folyamatának lépésein. A folyamat végrehajtása során a Safari, a Beállítások, és a Céges portál alkalmazásokat fogja használni. Koppintson a **Tovább** gombra.|
|![Képernyő betöltése, miután a „Következő lépések” képernyőn a Következő elemre koppintott.](./media/ios-09-cp-enroll-1802.png)|Várja meg, amíg betöltődik.|
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-7-cp-enroll-1711.png)|A rendszer átirányítja Önt a Safarira, hogy felügyeleti információkat szerezzen az eszközről.|
|![A rendszer arra kéri, hogy nyissa meg a Beállítások alkalmazást.](./media/ios-8-cp-enroll-1711.png)|Az **Engedélyezés** elemre koppintva nyissa meg a Beállítások alkalmazást a konfigurációs profil letöltéséhez. Ezt kell telepíteni ahhoz, hogy a cége kezelhesse a vállalati információkat az eszközén.|
|![A profil megnyílik a beállításokban.](./media/ios-9-cp-enroll-1711.png)|Koppintson a **Telepítés** elemre.|
|![A profil modális párbeszédpaneljének telepítése a képernyő aljáról.](./media/ios-10-cp-enroll-1711.png)|Koppintson a **Telepítés** elemre.|
|![A profil telepítése folyamatban betöltési képernyő.](./media/ios-11-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![Profilkezelés figyelmeztetési képernyő.](./media/ios-12-cp-enroll-1711.png)|Ez az Apple által írt figyelmeztetés további információt nyújt arról, hogy milyen műveleteket lehet végrehajtani a felügyelt eszközökön. Részletes tudnivalókért lásd: [Milyen adatok láthatók a cég számára](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![A rendszer arra kéri, hogy adjon megbízást a távoli felügyeletre.](./media/ios-13-cp-enroll-1711.png)|A **Megbízom** elemre koppintással engedélyezze cégének, hogy a vállalati információkat és beállításokat felügyelje az eszközén.|
|![Profil telepítésének befejezése képernyő.](./media/ios-14-cp-enroll-1711.png)|Várja meg, amíg betöltődik.|
|![A profil telepítése megtörtént képernyő.](./media/ios-15-cp-enroll-1711.png)|A profilja telepítve van, hamarosan megkezdődhet az eszközén található vállalati információk és beállítások felügyelete.|
|![Átváltás a Safari böngészőre a regisztrációhoz.](./media/ios-16-cp-enroll-1711.png)|A rendszer ismét átirányítja a Safarira, hogy lezárulhasson az eszköz felügyeleti információinak bekérése. |
|![A rendszer arra kéri, hogy nyissa meg a Céges portált.](./media/ios-17-cp-enroll-1711.png)|Koppintson a **Megnyitás** gombra.|
|![Vállalati erőforrások betöltése képernyő.](./media/ios-21-cp-enroll-1802.png)|Várja meg, amíg betöltődik.|
|![Válasszon eszközkategóriát a Céges portál alkalmazásban.](./media/ios-22-cp-enroll-1802.png)|Válassza ki az eszköznek leginkább megfelelő kategóriát. Ez általában attól függ, hogy ki az eszköz tulajdonosa, és hogy hol található az eszköz az idő legnagyobb részében.|
|![Kategória kiválasztva.](./media/ios-23-cp-enroll-1802.png)||
|![Eszközfelügyelet sikeres; most frissítenie kell a beállításokat.](./media/ios-24-cp-enroll-1802.png)|Sikeresen felügyelet alá helyezte az eszközt. Lehet, hogy még hátravan néhány beállítás, mint például a jelszó hossza, amelyet valószínűleg frissítenie kell a cég számára. A folytatáshoz koppintson a **Folytatás** parancsra.|
|![Eszközbeállítások megerősítése.](./media/ios-25-cp-enroll-1802.png)|A Céges portál ellenőrzi, hogy szükség van-e valamelyik beállítás frissítésére.|
|![A beállítások ellenőrzése lezárult, az operációs rendszer verziója nem megfelelő](./media/ios-26-cp-enroll-1802.png)|A Céges Portál javaslatokat ad a beállításokkal kapcsolatos problémák megoldására. A problémák megoldását követően koppintson a **Beállítások ellenőrzése** elemre.|
|![Eszközbeállítások megerősítése képernyő](./media/ios-27-cp-enroll-1802.png)|Az eszköz ellenőrzi, hogy a beállítások elég biztonságosak-e a céges erőforrások eléréséhez.|
|![Sikeresen regisztrált és frissítette beállításait](./media/ios-28-cp-enroll-1802.png)|Gratulálunk! Ezzel megtörtént az eszköz Intune-beli regisztrálása.|

> [!Note]
> Már csak néhány lépést kell megtennie, hogy az eszköz teljes felügyelet alá kerüljön. További információ a [távközlésiköltség-kezelőben való regisztrációról](enroll-your-device-with-telecom-expense-management-ios.md). Ha a cége az Apple Készülékregisztrációs programját használja, további információt [itt](enroll-your-device-dep-ios.md) találhat.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).
