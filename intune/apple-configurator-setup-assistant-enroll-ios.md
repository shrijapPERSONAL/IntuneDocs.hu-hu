---
title: "iOS-eszközök regisztrálása – az Apple Configurator és a Beállítási asszisztens"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Ismerje meg, hogyan regisztrálhatja a vállalat által birtokolt iOS-eszközöket az Apple Configurator és a Beállítási asszisztens használatával."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6b0bc51515a2b72c7574a7ca7e29c094f3bdbdb
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Az Intune támogatja a vállalat által birtokolt iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) segítségével történő regisztrálását. Ez a folyamat visszaállítja az eszköz gyári beállításait és felkészíti a Beállítási asszisztens futtatására, amely telepíti a vállalat szabályzatait az eszköz új felhasználója számára.

>[!NOTE]
>Ezt a regisztrációs módszert nem lehet használni az [eszközregisztráció-kezelői](device-enrollment-manager-enroll.md) módszerrel.

Az Apple Configuratorrel visszaállíthatja az iOS-eszközök gyári beállításait, és előkészítheti őket az új felhasználójuk általi használatra. Ehhez a módszerhez az iOS-eszközt egy Mac számítógéphez kell csatlakoztatni USB-kapcsolattal a vállalati regisztráció beállítása érdekében. A módszer emellett feltételezi, hogy Ön az Apple Configurator 2.0 verziót használja. Az iOS-eszközre alkalmazott szabályzatnak általában felhasználói affinitást kell tartalmaznia az Intune Céges portál alkalmazás használatának engedélyezése érdekében.

Az iOS-eszközök regisztrálásának további lehetőségeiről [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md) című témakörben olvashat.

## <a name="prerequisites"></a>Előfeltételek

Az iOS-eszközök regisztrációjának beállítása előtt teljesítse az alábbi előfeltételeket:

- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md)
- Az iOS-eszközökhöz való fizikai hozzáférés biztosítása
- Az eszközök sorozatszámának rendelkezésre állása – erről [az iOS-eszközök sorozatszámának megkeresését](https://support.apple.com//HT204308) ismertető cikk nyújt tájékoztatást.
- USB csatlakozókábelek előkészítése
- Gondoskodjon arról, hogy a Mac PC-n telepítve legyen az [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Configurator-sorozatszámok hozzáadása](apple-configurator-serial-numbers-add.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Apple Configurator-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt az Apple Configurator eszközzel regisztrált iOS-eszközök számára.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

3. **Az Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **AC-profilok** elemet.

4. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.

5. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.

6. A **Felhasználói affinitás** beállítással adja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül lesznek-e regisztrálva.

   - **Regisztrálás felhasználói affinitással** – Az eszközt össze kell kapcsolni egy felhasználóval a kezdeti beállítás során, majd engedélyezhető számára a vállalati adatok és e-mailek elérése. A felhasználói affinitást azoknál a felügyelt eszközöknél kell beállítani, amelyek felhasználók tulajdonában állnak, és a Céges portált kell rajtuk használni (például eszközök telepítéséhez).

   - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

7. A **Létrehozás** elemet választva mentse a profilt.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Sorozatszámok hozzárendelése az Apple Configurator-profilokhoz

A létrehozott Apple Configurator-profilokhoz hozzárendelheti az eszközök sorozatszámait. A sorozatszámokat előzőleg az [Apple Configurator-sorozatszámok hozzáadása](apple-configurator-serial-numbers-add.md) című témakörben leírtak alapján fel kell venni az Intune-ba.

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Sorozatszámok hozzárendelése Apple Configurator-profilokhoz

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az **Apple Configurator-regisztrációs profilok** panelen válassza ki azt a profilt, amelyikhez hozzá szeretné rendelni a sorozatszámokat.

3. A profil nevét viselő panelen válassza a **Sorozatszámok** > **Hozzárendelés** lehetőséget.

4. Jelölje ki a profilhoz rendelni kívánt sorozatszámokat, majd kattintson a **Hozzárendelés** gombra.

## <a name="export-the-profile-to-ios-devices"></a>Profil exportálása iOS-es eszközökre

Miután létrehozta a profilt, és hozzárendelte a sorozatszámokat, ki kell exportálnia a profilt az Intune-ból URL-ként vagy az alább ismertetett formátumban. Ezt követően manuálisan importálhatja egy Mac gépen az Apple Configuratorba, és utána azzal telepítheti az eszközökre.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Profil exportálása Setup Assistant-regisztrációval

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az **Apple Configurator-regisztrációs profilok** panelen válassza ki az exportálandó profilt.

3. A profil panelén válassza a **Profil exportálása** lehetőséget.

4. Csatlakoztassa az iOS-eszközt, és másolja a profil URL-címét az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). A címet később fel kell töltenie az Apple Configurator eszközbe az iOS-eszközök által használt Intune profil meghatározásához.

  Az alábbi eljárás során az Apple Configurator segítségével kell feltöltenie a profil URL-címét az Apple szolgáltatásába, és ezzel meghatározhatja az iOS-eszközök által használandó Intune-profilt.

5. Az Apple Configurator segítségével töltse fel a profil URL-címét az Apple szolgáltatásába, és ezzel meghatározhatja az iOS-eszközök által használandó Intune-profilt.
 1.  A Mac-számítógépen nyissa meg az **Apple Configurator 2** eszközt. A menüsávban válassza az **Apple Configurator 2**, majd a **Beállítások** elemet.
  > [!WARNING]
  > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. Az eszközön az **üdvözlőképernyőnek** kell látszania az eszköz csatlakoztatásakor.

  2. Válassza a **Beállítások** panelen a **Servers** (Kiszolgálók) elemet, majd az MDM-kiszolgálói varázsló elindításához válassza a „+” szimbólumot. Kattintson a **Tovább** gombra.

  3. Írja be a Beállítási asszisztens segítségével a Microsoft Intune-ban történő iOS-eszközregisztrációhoz megadott MDM-kiszolgáló **állomásnevét vagy URL-címét** (Host name or URL) és **regisztrációs URL-címét** (Enrollment URL) a megfelelő mezőkbe. Az Enrollment URL (Regisztrációs URL-cím) mezőnél az Intune-ból exportált regisztrációs profil URL-címét adja meg. Kattintson a **Tovább** gombra.  

    Ha a rendszer figyelmezteti, hogy nincs ellenőrizve a kiszolgáló URL-címe, nyugodtan figyelmen kívül hagyhatja. Kattintson minden megjelenő oldalon a **Next** (Tovább) gombra, amíg be nem fejeződik a varázsló.

  4.  Az iOS-mobileszközöket csatlakoztassa a Mac számítógéphez egy USB-adapterrel.
  > [!WARNING]
  > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. A Beállítási asszisztens indításakor az eszközön az **üdvözlőképernyőnek** kell látszania.

  5.  Válassza a **Prepare** (Előkészítés) lehetőséget. A **Prepare iOS Device** (iOS-eszköz előkészítése) panelen válassza a **Manual** (Manuális) elemet, majd a **Next** (Tovább) gombot.
  6. Az **Enroll in MDM Server** (Regisztrálás MDM-kiszolgálón) panelen válassza ki a létrehozott kiszolgáló nevét, majd válassza a **Next** (Tovább) gombot.
  7. A **Supervise Devices** (Eszközök felügyelete) panelen válassza ki a felügyelet szintjét, majd válassza a **Next** (Tovább) gombot.
  8. A **Create an Organization** (Szervezet létrehozása) panelen válassza ki a szervezetet az **Organization** mezőben, vagy hozzon létre új szervezetet, majd válassza a **Next** gombot.
  9. A **Configure iOS Setup Assistant** (iOS-es Beállítási asszisztens konfigurálása) panelen válassza ki a felhasználó számára megjelenő lépéseket, majd válassza a **Prepare** (Előkészítés) gombot. Ha a rendszer kéri, végezzen hitelesítést a megbízhatósági beállítások frissítése érdekében.  
  10. Az iOS-eszköz előkészítésének befejezésekor válassza le az USB-kábelt.  
6.  **Eszközök terjesztése**:
    Az eszközök most már készen állnak a vállalati regisztrációra. Kapcsolja ki az eszközöket, és ossza ki őket a felhasználóknak. Amikor a felhasználók bekapcsolják az eszközüket, elindul a Beállítási asszisztens.

    Lásd: [A végfelhasználók felkészítése a Microsoft Intune használatára](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Továbbíthatja a végfelhasználóknak a következő cikket is: [iOS vagy macOS rendszerű eszköz használata az Intune-nal](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>A Vállalati portál telepítése és használata a felhasználók által

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, végre kell hajtaniuk az alább ismertetett további lépéseket a Beállítási asszisztens befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.

