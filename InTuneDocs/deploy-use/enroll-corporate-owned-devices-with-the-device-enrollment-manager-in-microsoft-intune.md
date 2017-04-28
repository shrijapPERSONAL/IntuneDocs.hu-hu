---
title: "Eszközök regisztrálása az eszközregisztráció-kezelővel | Microsoft Docs"
description: "Az eszközregisztráció-kezelői (DEM-) fiók segítségével nagy számú megosztott, vállalati tulajdonban lévő, egy felhasználói fiókkal rendelkező mobileszköz kezelhető."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: ea57a51f2855dea416ad4a76e657e1846ffe41f1
ms.lasthandoff: 04/24/2017


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az *eszközregisztráció-kezelői* (DEM-) fiók egy speciális felhasználói fiók, mely akár ezer eszköz regisztrálására képes. A meglévő felhasználók a DEM-fiókba való felvételével különleges DEM-képességeket biztosíthat számukra. Minden regisztrált eszköz felhasznál egyetlen licencet. Az ezzel a fiókkal regisztrált eszközöket célszerű nem személyes („BYOD”), hanem megosztott (konkrét felhasználóhoz nem társított) eszközökként használni.  

A felhasználóknak szerepelniük kell az Azure Portal webhelyen ahhoz, hogy fel lehessen venni őket eszközregisztráció-kezelőként. Az optimális biztonság biztosítása érdekében a DEM-felhasználó nem lehet egyben Intune-rendszergazda is.

>[!NOTE]
>A DEM regisztrációs módszer nem használható az [Apple Configurator beállítási asszisztenssel](ios-setup-assistant-enrollment-in-microsoft-intune.md) végzett, vagy [közvetlen regisztrációhoz](ios-direct-enrollment-in-microsoft-intune.md), illetve a [DEP regisztrációs módszerrel](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Eszközregisztráció-kezelői példaforgatókönyv

Egy étterem 50 pénztári táblagépet szeretne biztosítani a felszolgálóknak és rendelési monitorokat a konyhai személyzetnek. Az alkalmazottaknak nem szükséges hozzáférni a céges adatokhoz, vagy felhasználóként bejelentkezni. Az Intune-rendszergazda létrehoz egy eszközregisztráció-kezelői fiókot, és felveszi az étterem egyik vezetőjét a DEM-fiókba, ezzel gyakorlatilag DEM-képességeket biztosítva az adott vezető számára. A vezető ekkor már regisztrálhatja az 50 táblagépet a DEM-hitelesítőadatok használatával.

Csak az Intune-konzolon szereplő felhasználók lehetnek eszközregisztráció-kezelők. Az eszközregisztráció-kezelő felhasználó nem lehet Intune-rendszergazda.

A DEM-felhasználó a következőket teheti:

-   Legfeljebb 1000 eszköz regisztrálása az Intune-ban
-   Céges alkalmazások beszerzése a Céges portál alkalmazással
-   Szerepkör-specifikus alkalmazások telepítése a táblagépekre a céges adatok elérésének konfigurálásához

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>A DEM-fiókkal regisztrált eszközökre vonatkozó korlátozások

Az eszközregisztráció-kezelői fiókokkal regisztrált eszközökre a következő korlátozások vonatkoznak:

  - Az eszköznek nincs konkrét „felhasználója”. Így nincs e-mail-fiókhoz vagy a céges adatokhoz való hozzáférés. Az adatok például VPN-nel azonban továbbra is hozzáférhetővé tehetők az eszközökön.

  - Nincs feltételes hozzáférés, mivel az a felhasználókon alapul.

  - A DEM-felhasználó magán az eszközön nem törölheti az eszközregisztráció-kezelésre regisztrált eszközök regisztrációját a Vállalati portálon. Az Intune-rendszergazda rendelkezik ezzel a képességgel, a DEM-felhasználó viszont nem.

  - A Vállalati portál alkalmazásban vagy a webhelyén csak a helyi eszköz jelenik meg.

  - A felhasználók nem futtathatnak az Apple Volume Purchase Program (VPP) keretében vásárolt alkalmazásokat az eszközökön, mivel az alkalmazások kezeléséhez felhasználói Apple ID azonosítóra van szükség.

  - (Csak iOS esetén) Ha eszközregisztráció-kezelővel regisztrálja az iOS-eszközöket, nem használhatja az Apple Configuratort vagy az Apple Device Enrollment Programot (DEP) az eszközök regisztrálásához.

> [!NOTE]
> A vállalati alkalmazások eszközregisztráció-kezelővel felügyelt eszközökre történő telepítéséhez telepítse a Vállalati portál alkalmazást **Szükséges telepítésként** az eszközregisztráció-kezelő felhasználói fiókjára.
> A teljesítmény javítása érdekében a DEM-eszközökön a Vállalati portál alkalmazás kizárólag a helyi eszközt jeleníti meg. A többi DEM-eszköz távoli felügyelete kizárólag az Intune felügyeleti konzolból valósítható meg.


## <a name="add-a-device-enrollment-manager"></a>Eszközregisztráció-kezelő hozzáadása

1.  Győződjön meg arról, hogy már létezik a felhasználó, akit fel szeretne venni a DEM-fiókba. Ha hozzá kell adnia a felhasználót, jelentkezzen be az [Office 365 portálra](https://go.microsoft.com/fwlink/p/?LinkId=698854), és kövesse a [Felhasználók felvétele egyenként és tömegesen az Office 365-be – rendszergazdai súgó](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) című témakörben szereplő lépéseket.

2.  Jelentkezzen be rendszergazdai azonosítójával a [Microsoft Intune felügyeleti konzoljába](https://manage.microsoft.com).

3.  A navigációs ablaktáblában kattintson a **Rendszergazda** elemre, lépjen a **Rendszergazdai felügyelet** beállításra, és válassza az **Eszközregisztráció-kezelő** lehetőséget. Ekkor megnyílik az **Eszközregisztráció-kezelő** lap.

4.  Kattintson a **Hozzáadás...** lehetőségre. Megnyílik az **Eszközregisztráció-kezelő hozzáadása** párbeszédpanel.

5.  Adja meg az Intune-fiók **felhasználói azonosítóját**, és kattintson az **OK** gombra.

    Az eszközregisztráció-kezelő most már ugyanazzal az eljárással regisztrálhat mobileszközöket, amelyet a végfelhasználók használnak a Vállalati portálon a saját eszközök használata esetén. A kezelő végfelhasználó telepítheti a céges portál alkalmazást és regisztrálhatja az eszközt a saját DEM hitelesítő adataival, legfeljebb 1000 eszközön. A végfelhasználók regisztrálásának az egyes platformokra vonatkozó lépéseit lásd:

  - [iOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)
  - [macOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos)
  - [Android-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android)
  - [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Eszközregisztráció-kezelő törlése az Intune-ból

1.  Jelentkezzen be a [Microsoft Intune felügyeleti portálra](https://manage.microsoft.com) a rendszergazdai bejelentkezési adataival.

2.  A navigációs ablaktáblában kattintson a **Rendszergazda** elemre, lépjen a **Rendszergazdai felügyelet** beállításra, és válassza az **Eszközregisztráció-kezelő** lehetőséget. Ekkor megnyílik az **Eszközregisztráció-kezelő** lap.

3.  Jelölje ki a törölni kívánt eszközregisztráció-kezelő **felhasználót**, és kattintson a **Törlés** lehetőségre. Ez a felhasználó nem törlődik az Intune-ból, és a felhasználó által felügyelt eszközök regisztrációja megmarad az Intune-ban. Az eszközregisztráció-kezelő törlése megakadályozza, hogy az adott felhasználó további eszközöket regisztráljon az Intune-ban.

4.  Kattintson az **Igen** lehetőségre az eszközregisztráció-kezelő törlésének jóváhagyásához.

Az eszközregisztráció-kezelő törlése nincs hatással a regisztrált eszközökre. Az eszközregisztráció-kezelő törlésekor:

-   A folyamat a regisztrált eszközöket nem érinti.

-   A regisztrált eszközök továbbra is teljes mértékben felügyeltek.

-   A törölt eszközregisztráció-kezelői fiók hitelesítő adatai továbbra is érvényesek a Vállalati portálra való bejelentkezéshez és az alkalmazások eléréséhez.

-   A törölt eszközregisztráció-kezelői fiók hitelesítő adatai nem törölhetik vagy vonhatják vissza az eszközöket.

-   A törölt eszközregisztráció-kezelői fiók kapcsolata megmarad a regisztrált fiókokkal, de további eszközöket nem lehet regisztrálni.

