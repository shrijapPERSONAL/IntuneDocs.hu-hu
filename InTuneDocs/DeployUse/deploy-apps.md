---
# required metadata

title: Alkalmazások telepítése | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Alkalmazások telepítése a Microsoft Intune-ban

Ez a témakör megmagyarázza azokat a fogalmakat, amelyeknek a megértésére feltétlenül szüksége lesz ahhoz, hogy alkalmazásokat telepítsen a Microsoft Intune-ban.

## Az Intune Software Publisher
Ha alkalmazásokat vesz fel vagy módosít a Microsoft Intune felügyeleti konzol használatával, elindul a **Microsoft Intune Software Publisher**. Ebben a közzétételi eszközben meg kell adnia és konfigurálnia kell egy szoftvertelepítő-típust, amely feltölti az Intune felhőtárhelyén tárolni kívánt számítógép- vagy mobileszköz-alkalmazásokat, illetve kapcsolódik egy online áruházhoz vagy webalkalmazáshoz.

### Követelmények
Mielőtt megkezdené a Microsoft Intune Software Publisher használatát, telepítenie kell a [Microsoft .NET-keretrendszer 4.0](https://www.microsoft.com/download/details.aspx?id=17851) teljes verzióját. Előfordulhat, hogy a Software Publisher csak akkor nyílik meg megfelelően, ha a telepítést követően újraindítja a számítógépet.

## Felhőtárhely
A szoftvertelepítő típusú telepítéssel telepített alkalmazásokat be kell csomagolni, és fel kell tölteni a Microsoft Intune felhőtárhelyébe. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A fizetett előfizetés 20 gigabájtot (GB) biztosít, illetve lehetőséget kínál további tárhely vásárlására.

A **Felügyelet** munkaterület **Tárhely kihasználtsága** csomópontjában megtekintheti, hogy mennyi helyet használ jelenleg, illetve további tárhelyet is vásárolhat.

A további felhőalapú Intune-tárhely vásárlására az alábbi szabályok vonatkoznak:

-   További tárterületet csak akkor vásárolhat, ha a szolgáltatás fizetős verzióját használja, és aktív az előfizetése.

-   Csak a Microsoft Online Service számlázási vagy globális rendszergazdái vásárolhatnak további tárterületet az Intune fiókportálján. Ilyen rendszergazdák hozzáadásához, törléséhez vagy kezeléséhez globális rendszergazdának kell lennie, és be kell jelentkeznie az Intune fiókportáljára.

-   Ha Ön mennyiségi licenccel rendelkező ügyfelünk, és a Nagyvállalati Szerződés keretében fizetett elő az Intune-ra vagy a Microsoft Intune-bővítményre, az árakról és a tárterület-vásárlási lehetőségekről a Microsoft helyi ügyfélmenedzserénél érdeklődhet.

#### A felhőtárhelyre vonatkozó követelmények

-   Az azonos alkalmazáshoz tartozó fájloknak azonos helyen kell lenniük, és az Intune-nak el kell tudnia érni ezeket a fájlokat.

-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.

-   A fájlok feltöltéséhez legalább 768 kB/s sebességű internet-hozzáféréssel kell rendelkeznie.

## Alkalmazástelepítési műveletek
Az alkalmazások telepítésekor a következő telepítési műveletek közül választhat:

-   **Szükséges telepítés** – az alkalmazás végfelhasználói beavatkozás nélkül települ az eszközön.

    > [!TIP] Nem felügyelt üzemmódban működő iOS-eszközök és az összes Android-eszköz esetében az alkalmazás csak akkor települ, ha a felhasználó elfogadja az alkalmazásajánlatot.
    >
    > Az iOS 7.1-es verziójánál régebbi rendszerű iOS-eszközökhöz már nem készíthetők új alkalmazáspéldányok. Az iOS 7.1-es verziójánál korábbi rendszerű eszközökhöz készült meglévő alkalmazáspéldányok azonban továbbra is működnek az Intune-ban, és az Intune felügyeli őket.
    > 
    >  Ha egy végfelhasználó törl egy Ön által kötelezőnek jelölt alkalmazást, az Intune a következő leltározási ciklus során (amely általában 7 naponta következik be) automatikusan újratelepíti az alkalmazást.

-   **Elérhető telepítés** – az alkalmazás megjelenik a vállalati portálon, és a végfelhasználók igény szerint telepíthetik.

-   **Eltávolítás** – a rendszer eltávolítja az alkalmazást az eszközről.

-   **Nem alkalmazható** – az alkalmazás nem jelenik meg a vállalati portálon, és nem települ egyik eszközön sem.

#### Az egyes telepítőtípusokhoz elérhető telepítési műveletek

|Telepítő típusa|Szükséges telepítés|Elérhető telepítés|Eltávolítás|Nem alkalmazható|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows-alkalmazáscsomag (felhasználói csoport számára telepített)|Igen|Igen|Igen|Igen|
|Windows-alkalmazáscsomag (eszközcsoport számára telepített)|Igen|Nem|Igen|Igen|
|Mobileszközökhöz készült alkalmazáscsomag (felhasználói csoport számára telepített)|Igen|Igen|Igen|Igen|
|Mobileszközökhöz készült alkalmazáscsomag (eszközcsoport számára telepített)|Igen|Nem|Igen|Igen|
|Windows Installer (felhasználói csoport számára telepített)|Nem|Igen|Nem|Igen|
|Windows Installer (eszközcsoport számára telepített)|Igen|Nem|Igen|Igen|
|Külső hivatkozás (felhasználói csoport számára telepített)|Nem|Igen|Nem|Igen|
|Külső hivatkozás (eszközcsoport számára telepített)|Nem|Nem|Nem|Nem|
|Felügyelt iOS-alkalmazás az App Store-ból (felhasználói csoport számára telepített)|Igen|Igen|Igen|Igen|
|Felügyelt iOS-alkalmazás az App Store-ból (eszközcsoport számára telepített)|Igen|Nem|Igen|Igen|
> [!TIP] Ha az alkalmazás telepítése során felhasználói és eszközcsoportokat egyaránt megad, az alkalmazást csak **Elérhető telepítés módban** telepítheti.

## A telepítés során fellépő ütközések
Arra az esetre, ha ugyanazon telepítési művelettel két telepítés érkezik egy eszközre, az alábbi szabályok vonatkoznak:

-   Az eszközcsoport számára végrehajtott telepítések elsőbbséget élveznek a felhasználói csoport számára végrehajtott telepítésekkel szemben. Ha azonban egy alkalmazást az **Elérhető** telepítési művelettel telepít egy felhasználói csoport számára, és ugyanazt az alkalmazást egy eszközcsoport számára is telepíti a **Nem alkalmazható**telepítési művelettel, a a felhasználók elérhetik az alkalmazást a vállalati portálon, és telepíthetik.

-   A rendszergazda szándéka elsőbbséget élvez a felhasználó szándékával szemben.

-   A telepítési műveletek elsőbbséget élveznek az eltávolítási műveletekkel szemben.

-   Ha egy eszköz egyszerre kap szükséges és elérhető telepítést, a rendszer kombinálja a műveleteket (az alkalmazás telepítése egyaránt lesz szükséges és elérhető).


## További lépések

Ismerje meg, hogyan [telepíthet alkalmazásokat a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md).

<!--HONumber=Jun16_HO1-->


