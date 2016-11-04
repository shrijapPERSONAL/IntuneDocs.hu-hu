---
title: "Bevezetés a Microsoft Intune App SDK használatába | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# Bevezetés a Microsoft Intune App SDK használatába

Ez az első lépéseket bemutató útmutató segítséget nyújt a mobilalkalmazás gyors engedélyezéséhez a Microsoft Intune-beli mobilalkalmazás-felügyelet használatával. Javasoljuk, hogy először tájékozódjon az Intune App SDK előnyeiről, amelyekről [Az Intune App SDK áttekintése](intune-app-sdk.md) című témakörben olvashat bővebben.

Ez az útmutató végigvezeti azokon a fő lépéseken, amelyekkel engedélyezheti az alkalmazás Microsoft Intune mobilalkalmazás-felügyeleten keresztüli felügyeletét. Az Intune App SDK a különböző platformokon hasonló lehetőségeket támogat, és célja, hogy egységes, platformfüggetlen felhasználói élményt teremtsen a rendszergazdáknak. A platformok korlátozásai miatt azonban bizonyos funkciók támogatásában kisebb különbségek vannak.

# Első lépések

## Áruházbeli alkalmazás regisztrálása a Microsoftnál

**Ha az alkalmazás a cég belső alkalmazása, és nem fog megjelenni nyilvános alkalmazás-áruházban**:

**Nem kell** regisztrálnia az alkalmazást. Belső, saját üzleti használatra való alkalmazások esetében a rendszergazda fogja a cégen belül telepíteni az alkalmazást. Az Intune észlelni fogja, hogy az alkalmazást az SDK-val állították össze, és lehetővé teszi a rendszergazda számára, hogy MAM-szabályzatbeállításokat alkalmazzon rá. Lépjen az [iOS vagy Android rendszerhez készült mobilalkalmazás engedélyezése a MAM-hoz az SDK használatával](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) című részre.

**Ha az alkalmazás elérhető lesz nyilvános alkalmazás-áruházban, például az Apple App Store-ban vagy a Google Play áruházban**: 

Először**regisztrálnia kell** az alkalmazást a Microsoft Intune-nál, és el kell fogadnia a regisztrációs feltételeket. A regisztráció után a rendszergazdák Intune MAM szabályzatbeállításokat alkalmazhatnak a felkészített alkalmazásra, amely Intune-alkalmazáspartnerként lesz látható. Az Intune-rendszergazdák nem alkalmazhatják a MAM-szabályzatot az alkalmazás mélyhivatkozására, amíg el nem végezte a regisztrációt, és a Microsoft Intune-csapat meg nem erősítette azt. A Microsoft a [Microsoft Intune-partnerek oldalra](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) is felveszi az alkalmazást. Az oldalon az alkalmazás ikonja jelzi, hogy az alkalmazás támogatja a Microsoft Intune MAM-szabályzatot.

A regisztráció megkezdéséhez töltse ki a **[Microsoft Intune alkalmazás partnerkérdőívét](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)**. 

A Microsoft a kérdőívben megadott e-mail-címek egyikén felveszi Önnel a kapcsolatot, és elindítja a regisztráció folyamatát. Emellett regisztrációs e-mail címén vesszük fel a kapcsolatot Önnel, ha bármilyen kétségeink lennének.

> [!NOTE]
> A Microsoft a fenti űrlapról és az Intune csapatával váltott e-mailekből gyűjtött összes adat esetében betartja a [Microsoft adatvédelmi nyilatkozatát](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Mire számítson a regisztrációs folyamat során**: 

1. Miután elküldte a kérdőívet, a Microsoft a megadott regisztrációs e-mail-címen felveszi Önnel a kapcsolatot, hogy ellenőrizze, eléri-e Önt ezen a címen, vagy további információkat kérjen a regisztráció befejezéséhez. 
2. Ha minden szükséges információ beérkezett, elküldjük aláírásra a Microsoft Intune alkalmazás partnerszerződését. Ez a szerződés tartalmazza azokat a feltételeket, amelyeket vállalatának el kell fogadnia ahhoz, hogy Microsoft Intune-alkalmazáspartner lehessen. 
3. Akkor is értesítjük, ha megtörtént az alkalmazás regisztrációja a Microsoft Intune rendszerében, és az alkalmazás megjelent a [Microsoft Intune-partnerek](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) webhelyén. 
4. Ezenfelül az alkalmazás mélyhivatkozását felvesszük a következő havi Intune-szolgáltatásfrissítésbe is. Ha például a regisztrációs adatokat júliusban töltötte ki, az alkalmazás mélyhivatkozása augusztus közepétől támogatott. 

Ha a jövőben változik az áruházbeli alkalmazás mélyhivatkozása, újra kell regisztrálnia az alkalmazást. Ezenfelül akkor is értesítsen minket, ha az alkalmazást az Intune App SDK új verziójával frissíti.



## Az SDK-fájlok letöltése

A natív iOS-hez, illetve Androidhoz készült Intune App SDK-k egy Microsoft GitHub-fiókban találhatók. Az alábbi két nyilvános adattár tartalmazza az iOS-hez, illetve az Androidhoz készült SDK-fájlokat:

* [Intune App SDK iOS rendszerhez](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK Android rendszerhez](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Ha Xamarin- vagy Cordova-alkalmazást kíván felvenni, használja az alábbi fejlesztői eszközöket**:

* [Intune App SDK Xamarin összetevő](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK Cordova beépülő modul](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Javasoljuk, hogy regisztráljon GitHub-fiókot, hogy leágazhasson az adattárakból, és lehúzhassa a változásokat. A GitHub révén a fejlesztők kommunikálni tudnak a termékcsapattal, hibákat jelenthetnek, és gyors válaszokat kaphatnak, elolvashatják a kibocsátási megjegyzéseket, valamint visszajelzést adhatnak a Microsoftnak. A GitHub-fiókkal és -adattárakkal kapcsolatos kérdéseit a msintuneappsdk@microsoft.com címen várjuk.





## iOS vagy Android rendszerhez készült mobilalkalmazás engedélyezése a MAM-hoz az SDK használatával

Az alábbiakra lesz szüksége az Intune App SDK-nak egy natív iOS-alkalmazásba történő integrálásához: 

* **[iOS-hez készült Microsoft Intune App SDK – fejlesztői útmutató](intune-app-sdk-ios.md)**: Ez a dokumentum részletesen ismerteti a mobil iOS-alkalmazásnak az Intune App SDK-val való engedélyezésének lépéseit. 


Az alábbiakra lesz szüksége az Intune App SDK-nak egy natív Android-alkalmazásba történő integrálásához:

* **[Androidhoz készült Microsoft Intune App SDK – fejlesztői útmutató](intune-app-sdk-android.md)**: Ez a dokumentum részletesen ismerteti az androidos mobilalkalmazásnak az Intune App SDK-val való engedélyezésének lépéseit. 

Az Intune App SDK Xamarin összetevő és az Intune App SDK Cordova beépülő modul dokumentációját a vonatkozó GitHub-tárakban találja. 


## Telemetria konfigurálása az alkalmazásra vonatkozóan

A Microsoft Intune statisztikát gyűjt az alkalmazás használatáról.

* **iOS-hez készült Intune App SDK**: Az SDK alapértelmezés szerint naplózza a használati események SDK-telemetriai adatait. Az adatokat az SDK a Microsoft Intune-nak küldi el.

    * Ha úgy dönt, hogy nem kíván SDK-ból származó telemetriai adatokat küldeni a Microsoft Intune-nak az alkalmazásából, le kell tiltania az SDK-ban a telemetria-átvitelt az IntuneMAMSetting könyvtárban található `MAMTelemetryDisabled` tulajdonság „YES” értékre való állításával.

* **Androidhoz készült Intune App SDK**: A telemetriai adatokat a program nem naplózza az SDK használatával.

## A MAM használatát támogató alkalmazás tesztelése a Microsoft Intune-nal

Miután végrehajtotta az iOS vagy Android alkalmazásnak az Intune App SDK-való integrálásához szükséges lépéseket, meg kell győződnie arról, hogy a végfelhasználóknál és a rendszergazdánál engedélyezve vannak és működnek az alkalmazásfelügyeleti szabályzatok. Az integrált alkalmazás teszteléséhez a következőkre lesz szüksége:

<!--TODO-->

* **A MAM használatát támogató Microsoft Intune-alkalmazás tesztelése**: A jelen dokumentum részletesen ismerteti a MAM használatát támogató iOS- vagy androidos alkalmazások Microsoft Intune-nal való tesztelésének lépéseit. Ezt a dokumentumot megtalálhatja az SDK-k GitHub-adattárában.

* **Microsoft Intune-fiók**: A MAM használatát támogató alkalmazásoknak a Microsoft Intune-nal való teszteléséhez szüksége lesz egy Microsoft Intune-fiókra. 
    * Ha egy független szoftverszállítóként engedélyezi az Intune MAM-hoz az iOS vagy Android rendszerhez készült áruházbeli alkalmazásait, a regisztráció (az ezt ismertető lépésben leírt módon történő) befejezése után kapni fog egy promóciós kódot. A promóciós kód lehetővé teszi, hogy feliratkozzon a Microsoft Intune próbaverziójának 1 évig meghosszabbított használatára. 
    * Az áruházban nem közzéteendő üzleti alkalmazások fejlesztői az adott szervezeten keresztül kaphatnak hozzáférést a Microsoft Intune-hoz. Emellett feliratkozhat a [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) 1 hónapos ingyenes próbaidőszakára is.




<!--HONumber=Oct16_HO3-->


