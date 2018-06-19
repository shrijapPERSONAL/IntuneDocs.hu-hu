---
title: Regisztráció beállítása macOS-eszközökhöz
titlesuffix: Microsoft Intune
description: Útmutató macOS-eszközök Intune-ban való regisztrációjának beállításához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f8cddb69ac85e45acde8a846df3b5413c3b75bf
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32046247"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Regisztráció beállítása macOS-eszközökhöz az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-nal macOS-eszközöket is lehet felügyelni. Az eszközfelügyelethez a felhasználóknak a [Céges portál webhely](http://portal.manage.microsoft.com) útmutatása alapján regisztrálniuk kell eszközeiket. Ha bekerültek a felügyelet alá, [egyéni beállításokat hozhat létre a macOS-eszközökhöz](custom-settings-macos.md). Hamarosan további képességek lesznek elérhetők.

## <a name="prerequisites"></a>Előfeltételek

macOS-eszközök regisztrációjának indítása előtt végezze el az alábbiakat:

- [Tartományok beállítása](custom-domain-name-configure.md)
- [Az MDM-szolgáltató beállítása](mdm-authority-set.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [A Céges portál konfigurálása](company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md)

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Azt is engedélyezheti, hogy a felhasználók saját személyes eszközeiket regisztrálják az Intune-felügyelethez. Ezt „saját eszköz használata” vagy BYOD (Bring Your Own Device) néven ismerjük. Az előfeltételek teljesítése és a felhasználói licencek hozzárendelése után a felhasználók letölthetik az macOS-es Céges portál alkalmazást az App Store-ból, és az alkalmazástól kapott utasításokat követve elvégezhetik a regisztrációt.

## <a name="company-owned-ios-devices"></a>Vállalati tulajdonban lévő iOS-eszközök
A felhasználóknak eszközöket vásárló szervezetek számára az Intune [eszközregisztrációs-kezelő](device-enrollment-manager-enroll.md) fiókkal támogatja a vállalati tulajdonban lévő macOS-eszközök regisztrálását.

## <a name="set-up-macos-enrollment"></a>macOS-regisztráció beállítása

Az Intune alapértelmezés szerint lehetővé teszi macOS-eszközök regisztrálását.

A macOS-eszközök regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

Kérje a végfelhasználókat, hogy a [Céges portál webhelyen](https://portal.manage.microsoft.com) található útmutatás alapján regisztrálják eszközeiket. Hivatkozást is küldhet nekik az online regisztrációhoz: [macOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [macOS-eszköz használata az Intune-nal](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Virtuális macOS-gépek regisztrálása teszteléshez

> [!NOTE]
> A virtuális macOS-gépekhez csak teszteléshez jár támogatás. A virtuális macOS-gépeket ne használja végfelhasználói termelési eszközökként. 

A virtuális macOS-gépeket a Parallels Desktop vagy a VMWare Fusion segítségével regisztrálhatja tesztelésre. 

A Parallels Desktophoz meg kell adnia a virtuális gépek hardvertípusát és sorozatszámát, hogy az Intune felismerje őket. A Parallels útmutatójával [megadhatja a hardvertípust](http://kb.parallels.com/123594) és a [sorozatszámot](http://kb.parallels.com/123455), valamint a teszteléshez szükséges beállításokat. Azt javasoljuk, hogy a virtuális gépeket futtató eszközök hardvertípusa egyezzen meg a létrehozandó virtuális gépek hardvertípusával. A hardvertípust az **Apple menü** > **A Mac névjegye** > **Rendszerjelentés** > **Modellazonosító** területen találhatja meg. 

A VMware Fusion esetében [szerkesztenie kell a .vmx-fájlt](https://kb.vmware.com/s/article/1014782) a virtuális gép hardvermodelljének és sorozatszámának megadásához. Azt javasoljuk, hogy a virtuális gépeket futtató eszközök hardvertípusa egyezzen meg a létrehozandó virtuális gépek hardvertípusával. A hardvertípust az **Apple menü** > **A Mac névjegye** > **Rendszerjelentés** > **Modellazonosító** területen találhatja meg. 

## <a name="user-approved-enrollment"></a>Felhasználó által jóváhagyott regisztráció

A felhasználói jóváhagyott MDM-regisztráció egy olyan macOS-regisztrációs típus, amellyel bizonyos biztonsági szempontból kényes beállításokat kezelhet. További információt az [Apple támogatási dokumentumában találhat](https://support.apple.com/HT208019).

A felhasználó általi jóváhagyáshoz a végfelhasználónak manuális jóváhagyást kell adnia a rendszerbeállítások használatával a macOS Céges portállal való regisztráció után. Ehhez útmutatást a macOS 10.13.2 vagy újabb rendszert használó felhasználók a macOS Céges portálon találhatnak.

Annak megállapításához, hogy az eszköz jóvá van-e hagyva a felhasználó által, lépjen az Intune-portálra, majd válassza az **Eszközök** > **Minden eszköz**> kívánt eszköz > **Hardver** lehetőséget. Jelölje be a **Felhasználó által jóváhagyott** mezőt.