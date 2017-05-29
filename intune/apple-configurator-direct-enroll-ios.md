---
title: "iOS-eszközök regisztrálása az Apple Configurator és közvetlen regisztráció használatával"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató a vállalati tulajdonban lévő iOS-eszközök az Apple Configuratorral való közvetlen regisztrációjához."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5347e2023a9ce19f8e8ab960e2eebf8107530220
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>iOS-eszközök regisztrálása az Apple Configurator és közvetlen regisztráció használatával 

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Az Intune támogatja a vállalat által birtokolt iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) segítségével történő regisztrálását. Ez a folyamat nem állítja vissza az eszköz gyári beállításait, és előre definiált szabályzattal regisztrálja azt. Ez a módszer azokon az eszközökön használható, amelyeken **nincs megadva felhasználói affinitás**. A módszer használatához az iOS-eszközt USB-kapcsolaton egy Mac géphez kell csatlakoztatni a vállalati regisztráció beállítása érdekében.

>[!NOTE]
>Ezt a regisztrációs módszert nem lehet használni az [eszközregisztráció-kezelői](device-enrollment-manager-enroll.md) módszerrel.

Amikor közvetlenül regisztrál iOS-eszközöket, regisztrálhat egy eszközt anélkül, hogy lekérné az eszköz sorozatszámát. Az eszközt el is nevezheti azonosítási célból, mielőtt az Intune rögzítené az eszköz nevét a regisztráció alatt. A Céges portál alkalmazás nem támogatott a közvetlen módon regisztrált eszközökön. Ez az útmutató feltételezi, hogy az Apple Configurator 2.0 verzióját használja egy Mac-gépen.

Az iOS-eszközök regisztrálásának további módjairól [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Az iOS-eszközök regisztrálási módjának kiválasztása) című témakörben olvashat.


## <a name="prerequisites"></a>Előfeltételek

Az iOS-eszközök regisztrációjának beállítása előtt teljesítse az alábbi előfeltételeket:

- [Tartományok beállítása](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Az MDM-szolgáltató beállítása](mdm-authority-set.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [A Céges portál konfigurálása](company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md)
- Az iOS-eszközökhöz való fizikai hozzáférés biztosítása
- Az eszközök sorozatszámának rendelkezésre állása – erről [az iOS-eszközök sorozatszámának megkeresését](https://support.apple.com//HT204308) ismertető cikk nyújt tájékoztatást.
- USB csatlakozókábelek előkészítése
- Egy olyan Mac számítógép rendelkezésre állása, melyen telepítve van az [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Apple Configurator-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt az Apple Configurator eszközzel regisztrált iOS-eszközök számára.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

3. **Az Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **AC-profilok** elemet.

4. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.

5. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.

6. A **Felhasználói affinitás** lehetőségnél válassza a **Regisztráció felhasználói affinitás nélkül** elemet annak biztosítása érdekében, hogy az eszköz ne legyen a felhasználóhoz kapcsolva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

7. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>A profil exportálása iOS-eszközökre .mobileconfig fájlként

1. A **Profil exportálása** panelen töltse le a regisztrációs profilt az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), majd küldje le a profilt közvetlenül felügyeleti profilként egy csatlakoztatott iOS-eszközre. A művelethez nincs szükség a gyári beállítások visszaállítására.

2. Készítse elő az eszközt az Apple Configuratorral az alábbi lépések segítségével.

   a. Egy Mac számítógépen nyissa meg az Apple Configurator 2.0 eszközt.

   b. Csatlakoztassa az iOS-eszközt a Mac számítógéphez egy USB-kábellel. Zárja be a Fotók, az iTunes és más alkalmazásokat, amelyek megnyílnak az eszközhöz annak észlelésekor.

   c. Az Apple Configuratorban válassza ki a csatlakoztatott iOS-eszközt, majd kattintson az **Add** (Hozzáadás) gombra. Az eszközhöz adható lehetőségek a legördülő listában jelennek meg. Válassza a **Profilok** lehetőséget.

   d. A fájlkiválasztóval válassza ki az Intune-ból exportált .mobileconfig fájlt, majd válassza az **Add** (Hozzáadás) gombot. Ezzel a profil hozzá lesz adva az eszközhöz. Ha az eszköz Felügyeletlen, a telepítéshez az eszköz elfogadására van szükség.

3. Az alábbi lépések segítségével telepítse a profilt az iOS-eszközön. Az eszköz elvileg elvégezte a Beállítási asszisztens lépéseit, és készen áll a használatra. Ha a regisztrációba alkalmazástelepítések tartoznak, az eszközhöz be kell állítani egy Apple ID-t, mert az alkalmazástelepítésekhez Apple ID-vel kell bejelentkezni az Apple Store áruházba.

   a. Oldja fel az iOS-eszköz zárolását.

   b. A **Felügyeleti profil** **Profil telepítése** párbeszédpanelén kattintson a **Telepítés** gombra.

   c. Adja meg az Eszköz PIN-kódját vagy az Apple ID-t, ha szükséges.

   d. Fogadja el a **Figyelmeztetést**, és válassza a **Telepítés** gombot.

   e. Fogadja el a **Távoli figyelmeztetést**, és válassza a **Megbízható** gombot.

   f. Amikor a **Profil telepítve** mező megerősíti, hogy a profil Telepítve van, válassza a **Kész** gombot.

4. Az iOS-eszközön nyissa meg a **Beállítások** alkalmazást, majd válassza az **Általános** > **Eszközkezelés** > **Felügyeleti profil** lehetőséget. Ellenőrizze, hogy a profiltelepítés szerepel-e a listán, valamint ellenőrizze az iOS-házirend korlátozásait és a telepített alkalmazásokat. A házirend-korlátozások és alkalmazások megjelenítése az eszközön akár 10 percet is igénybe vehet.

5. Eszközök terjesztése. Az iOS-eszköz most már felügyelt, és regisztrálva van az Intune-nal.

