---
title: Oktatóanyag – használata az Intune-ban iOS-eszközök regisztrálása a Készülékregisztrációs Program
titleSuffix: Microsoft Intune
description: Ebben az oktatóanyagban, állítsa be az Apple iOS-eszközök regisztrálása DEP.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9cd0eec492f5131e4015aa64eccb4c081c663ee
ms.sourcegitcommit: 8e6f4acb592dbe5de63aa7642ee9487288740714
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58646471"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Oktatóanyag: Az Intune-ban iOS-eszközök regisztrálása a Készülékregisztrációs Program segítségével
Az Apple eszköz beléptetési Program (DEP) egyszerűbbé teszi az eszközök regisztrálását. A Microsoft Intune és a DEP eszközök automatikus regisztrációjának az első alkalommal a felhasználó bekapcsolja az eszközt. Ezért el olyan eszközöket, számos felhasználó számára anélkül, hogy minden egyes eszköz beállításához külön-külön kellene. 

Az oktatóanyag segítségével megtanulhatja a következőket:
> [!div class="checklist"]
> * Apple DEP-token beszerzése
> * AutoPilot-eszközcsoport létrehozása
> * AutoPilot üzembehelyezési profil létrehozása
> * Az AutoPilot üzembehelyezési profil hozzárendelése az eszközcsoporthoz
> * Windows rendszerű eszközök kiosztása a felhasználóknak

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="prerequisites"></a>Előfeltételek
- [Apple készülékregisztrációs program](http://deploy.apple.com) keretében vásárolt eszközök
- Állítsa be a [mobileszköz-felügyeleti szolgáltatóként](mdm-authority-set.md)
- Get- [Apple MDM Push-tanúsítvány](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Apple DEP-token beszerzése
Regisztrálja az iOS-eszközöket, mielőtt kell egy Apple DEP-token (.pem) fájlt. Ez a token (jogkivonat) teszi lehetővé az Intune számára a vállalat által birtokolt DEP-eszközök adatainak szinkronizálását. Azt is engedélyezi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és eszközöket rendeljen ezen profilokhoz.

A DEP-tokent az Apple DEP-portálon hozhatja létre. Szintén a DEP-portál használatával rendelheti hozzá az eszközök felügyeletét az Intune-hoz.

1. Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > **Hozzáadás** elemet.

2. Engedélyezze a Microsoftnak az **Elfogadom** lehetőség választásával a felhasználó- és eszközadatok Apple-nek való elküldését.

   ![Képernyőkép – A Készülékregisztrációs program tokenje panel az Apple tanúsítványok munkaterületen – nyilvános kulcs letöltése.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Kattintson a **Nyilvános kulcs letöltése** elemre a titkosításikulcs-fájl (.pem) letöltéséhez és helyi mentéséhez. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

4. A **Token létrehozása az Apple Készülékregisztrációs programjában** elemre kattintva nyissa meg az Apple Központi Telepítési Program portálját, és jelentkezzen be a cége Apple-azonosítójával. A későbbiekben ezt az Apple ID-t használhatja a DEP-token megújításához.

5.  Az Apple [Központi Telepítési Program portálján ](https://deploy.apple.com) válassza a**Készülékregisztrációs program** **Első lépések** elemét.

4. A **Kiszolgálók kezelése** lapon válassza az **MDM-kiszolgáló hozzáadása** lehetőséget.

5. A **MDM-kiszolgáló nevét**, adja meg *TestMDMServer* majd **tovább**. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, A neve vagy URL-címét a Microsoft Intune-kiszolgáló nem.

6. Megjelenik a **Hozzáadás:&lt;Kiszolgálónév&gt;** párbeszédablak, és kéri **a nyilvános kulcs feltöltését**. Válassza ki **fájl kiválasztása...** a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

6. Lépjen a **központi telepítési program** > **Device Enrollment Program** > **Eszközkezelés**.
7. A **Choose Devices By**, válassza a **sorozatszám**. <!--ask Tiffany about this-->

8. A **Választott tevékenység** területen jelölje ki a **Hozzárendelés kiszolgálóhoz** elemet, válassza Microsoft Intune-hoz megadott &lt;Kiszolgálónevet&gt;, majd kattintson az **OK** gombra. Az Apple-portál az Intune-kiszolgálóhoz rendeli a megadott eszközök kezelését, majd megjeleníti a **Hozzárendelés kész** üzenetet.

   Az Apple-portál **Központi telepítési programok** &gt; **Készülékregisztrációs program** &gt; **Hozzárendelési előzmények** menüpontjában jeleníthető meg az eszközök és a hozzájuk tartozó MDM-kiszolgálók listája.

9. Adja meg a token létrehozásához használt Apple ID Azonosítót későbbi felhasználás céljából, az Intune-ban az Azure Portalon.

    ![Képernyőkép – A DEP-token létrehozásához használt Apple ID megadása és a DEP-token megkeresése.](./media/device-enrollment-program-enroll-ios/image03.png)

10. Az **Apple-token** mezőben keresse meg tallózással a tanúsítványfájlt (.pem), és válassza a **Megnyitás**, majd a **Létrehozás** lehetőséget. 

## <a name="create-an-apple-enrollment-profile"></a>Apple-regisztrációs profil létrehozása
Most, hogy telepítette a jogkivonatot, létrehozhatja a regisztrációs profilt a DEP-eszközökhöz. A regisztrálás során az eszközök csoportjára alkalmazott beállításokat egy készülékregisztrációs profil határozza meg.

1. Az Azure-beli Intune-portálon válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** elemet.

2. Válassza ki az imént telepített jogkivonat, válassza a **profilok** > **profil létrehozása**.

3. A **profil létrehozása**, adja meg *TestDEPProfile* a **neve** és *tesztelés DEP iOS-eszközök* a **leírása** . Ezeket a felhasználók nem fogják látni.

4. A **felhasználói affinitással**, válassza a **felhasználói affinitással való regisztrálást**. Ez a beállítás akkor szolgáltatásokhoz, például alkalmazások telepítéséhez a vállalati portálon használni kívánt felhasználókhoz tartozó eszközökhöz.

5. Válasszon **nem** alatt **hitelesítés az Apple beállítási asszisztens helyett a céges portál**.

6. Válasszon **Eszközfelügyeleti beállítások** válassza **nem** alatt **felügyelt**. A felügyelt eszközök több felügyeleti lehetőséget biztosítanak, de nem használja ezt az oktatóanyag az alkalmazásában.

7. Válassza az **OK** gombot.

8. Válasszon **beállítási asszisztens testreszabása** , és adja meg *oktatóanyag részleg* a **részleg neve**. Ez a karakterlánc mit látnak a felhasználók Ha rákoppintanak **konfigurációjával kapcsolatos** eszköz az aktiválás során.

9. A **részleg telefonszáma**, adjon meg egy telefonszámot. Ez a szám jelenik meg, amikor a felhasználók a **segítségre van szüksége** gomb az aktiválás során.

10. Is **megjelenítése** vagy **elrejtése** különböző képernyőkkel eszköz az aktiválás során. Ez az oktatóanyag az alkalmazásában, állítsa be **PIN-kód** való **megjelenítése** és a többi való **elrejtése**.

11. Válassza az **OK** > **Létrehozás** lehetőségeket.

## <a name="sync-managed-devices"></a>Felügyelt eszközök szinkronizálása

Most láthatja, hogy mely eszközök vannak hozzárendelve ezt a tokent.

1. Az Intune-ban az Azure Portalon, válassza ki a **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > Válasszon egy tokent a a lista > **eszközök** > **szinkronizálási**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>IOS-eszközökre egy regisztrációs profil hozzárendelése

Ahhoz, hogy egy eszközt regisztrálni lehessen, először hozzá kell rendelni egy regisztrációs programprofilt.

1. Az Intune-ban az Azure Portalon, válassza ki a **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > Válassza ki a tokent a listában.
2. Válassza az **Eszközök** lehetőséget, válasszon eszközöket a listából, majd válassza a **Profil hozzárendelése** elemet.
3. A **Profil hozzárendelése** területen válasszon egy profilt az eszközökhöz, majd válassza a **Hozzárendelés** lehetőséget.

## <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Beállított felügyeleti és az Apple és az Intune közötti szinkronizálása és hozzárendelt egy profilt a DEP-eszközök regisztrálása lehetővé teszik. Az eszközök ekkor már kioszthatók a felhasználóknak. Felhasználói affinitással rendelkező eszközök esetén minden felhasználóhoz hozzá kell rendelni egy Intune-licencet.

## <a name="clean-up-resources"></a>Az erőforrások eltávolítása

Ha az Autopilot-eszközök használata már nem szeretné, törölheti őket.

- Ha az eszközök regisztrálva vannak az Intune-ban, akkor először [törölnie kell azokat az Azure Active Directory portálról](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>További lépések

IOS-eszközök regisztrációjával kapcsolatos annak elérhető egyéb beállításokkal kapcsolatos további információkért.

> [!div class="nextstepaction"]
> [Részletes iOS DEP regisztrációs cikk](device-enrollment-program-enroll-ios.md)
