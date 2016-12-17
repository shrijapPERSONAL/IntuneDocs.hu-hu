---
title: "Hibába ütközik, amikor megpróbálja regisztrálni az iOS-es eszközt az Intune-ban | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 57b6bb6076b24299fb54626aa55850bf8c0c2428
ms.openlocfilehash: df491807386c80dce0f45822fbc64acefda59eb3


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Hibába ütközik, amikor megpróbálja regisztrálni az iOS-es eszközt az Intune-ban

A következő táblázat azon hibákat tartalmazza, amelyeket az iOS-es eszközök Intune-ban történő regisztrálásakor láthat. Küldje el ezt a hivatkozást a rendszergazdának. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).

|Hibaüzenet|Probléma|Miről tájékoztassa a rendszergazdát|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Nincs eszközregisztrációs házirend|Ellenőrizze, hogy az összes regisztrációs előfeltétel, mint például az Apple Push Notification szolgáltatás (APNs) tanúsítványa konfigurálva van-e, illetve azt, hogy az „iOS mint platform” engedélyezve van-e. Útmutatásért tekintse meg a [Set up iOS and Mac device management](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) (iOS- és Mac-eszközök kezelésének beállítása) című cikket.|
|DeviceCapReached|Már túl sok mobileszközt regisztrált.|A felhasználónak el kell távolítania az aktuálisan regisztrált mobileszközeit a Vállalati portálról, mielőtt másikat regisztrálhatna. Kövesse a megfelelő eszköz típusára vonatkozó utasításokat: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Probléma akadt azzal a tanúsítvánnyal, amely lehetővé teszi a mobileszköz és a vállalat hálózata közötti kommunikációt.<br /><br />Lépjen kapcsolatba az informatikai rendszergazdákkal, és mondja el nekik, hogy az **APNSCertificateNotValid** üzenetet kapta a mobileszköz regisztrálása során, és kérje meg őket, hogy nézzék meg a jelen táblázatban lévő megoldást.|Az Apple Push Notification Service (APNs) révén elérhetők a beléptetett iOS-eszközök. Ha nem lettek végrehajtva az APN-tanúsítvány beszerzésének lépései, vagy ha az APN-tanúsítvány lejárt, a beléptetési kísérletek ezzel az üzenettel hiúsulnak meg.<br /><br />A felhasználók konfigurálásához olvassa el [Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) című szakaszt, valamint a [felhasználók és eszközök rendszerezésével](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) kapcsolatos tudnivalókat.|
|AccountNotOnboarded|Probléma akadt azzal a tanúsítvánnyal, amely lehetővé teszi a mobileszköz és a vállalat hálózata közötti kommunikációt.<br /><br />Lépjen kapcsolatba az informatikai rendszergazdákkal, és mondja el nekik, hogy az **APNSNotOnboarded** üzenetet kapta a mobileszköz regisztrálása során, és kérje meg őket, hogy nézzék meg a jelen táblázatban lévő megoldást.|Az Apple Push Notification Service (APNs) révén elérhetők a beléptetett iOS-eszközök. Ha nem lettek végrehajtva az APN-tanúsítvány beszerzésének lépései, vagy ha az APN-tanúsítvány lejárt, a beléptetési kísérletek ezzel az üzenettel hiúsulnak meg.<br /><br />További információ: [Az iOS kezelésének beállítása a Microsoft Intune-nal](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Lehet, hogy nem iOS-eszközzel próbált meg regisztrálni. A regisztrálni próbált mobileszköz nem támogatott.<br /><br />Győződjön meg róla, hogy az eszközön 8.0-ás vagy újabb iOS-verzió fut.<br /><br />Lépjen kapcsolatba az informatikai rendszergazdákkal, és mondja el nekik, hogy a **DeviceTypeNotSupported** üzenetet kapta a mobileszköz regisztrálása során, és kérje meg őket, hogy nézzék meg a jelen táblázatban lévő megoldást.|Győződjön meg róla, hogy a felhasználó eszközén 8.0-ás vagy újabb iOS-verziót fut.|
|UserLicenseTypeInvalid|Nem tudja regisztrálni a mobileszközt, mert a felhasználói fiók még nem tagja egy szükséges felhasználói csoportnak.<br /><br />Lépjen kapcsolatba az informatikai rendszergazdákkal, és mondja el nekik, hogy a **UserLicenseTypeInvalid** üzenetet kapta a mobileszköz regisztrálása során, és kérje meg őket, hogy nézzék meg a jelen táblázatban lévő megoldást.|Mielőtt a felhasználók regisztrálhatnák az eszközeiket, a megfelelő felhasználói csoport tagjának kell lenniük. Ez az üzenet azt jelenti, hogy nem rendelkeznek a megfelelő licenctípussal a meghatározott mobileszköz-kezelő szolgáltatóhoz. Ha például az Intune lett mobileszköz-kezelő szolgáltatóként meghatározva, és System Center 2012 R2 Configuration Manager-licencet használnak, ezt a hibaüzenetet látják.<br /><br />Tekintse meg az alábbiakat a további információkért:<br /><br />Olvassa el [Az iOS és Mac kezelésének beállítása a Microsoft Intune-nal](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) című szakaszt, illetve a felhasználók konfigurálásával kapcsolatban [Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) című szakaszt, valamint a [felhasználók és eszközök rendszerezésével](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) kapcsolatos tudnivalókat.|
|MdmAuthorityNotDefined|Az informatikai rendszergazdának konfigurálnia kell a vállalatban lévő mobileszközök felügyeletének módját.<br /><br />Lépjen kapcsolatba az informatikai rendszergazdákkal, és mondja el nekik, hogy az **MdmAuthorityNotDefined** üzenetet kapta a mobileszköz regisztrálása során, és kérje meg őket, hogy nézzék meg a jelen táblázatban lévő megoldást.|A mobileszköz-kezelő szolgáltató nincs megadva az Intune-ban.<br /><br />Tekintse meg az 1. elemet [Az első lépések a Microsoft Intune 30 napos próbaverziójában](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) „6. lépés: Mobileszközök regisztrálása és alkalmazások telepítése” szakaszában.|



<!--HONumber=Dec16_HO1-->


