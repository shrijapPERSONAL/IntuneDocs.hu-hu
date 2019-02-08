---
title: Regisztráció beállítása macOS-eszközökhöz
titlesuffix: Microsoft Intune
description: Útmutató macOS-eszközök Intune-ban való regisztrációjának beállításához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32055e4370669de15342ab97dc71f91ee57426e4
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850998"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Regisztráció beállítása macOS-eszközökhöz az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune lehetővé teszi a macOS rendszerű eszközök felügyeletét, és hozzáférést biztosít a felhasználók számára a céges levelezéshez és alkalmazásokhoz.

Az Intune rendszergazda beállíthatja a vállalati tulajdonú macOS-eszközök és a személyes tulajdonú macOS-eszközök („saját eszköz használata” vagy BYOD) regisztrációját. 

## <a name="prerequisites"></a>Előfeltételek

macOS-eszközök regisztrációjának indítása előtt végezze el az alábbiakat:

- [Tartományok beállítása](custom-domain-name-configure.md)
- [Az MDM-szolgáltató beállítása](mdm-authority-set.md)
- [Csoportok létrehozása](groups-add.md)
- [A Céges portál konfigurálása](company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>A felhasználó tulajdonában macOS-eszközök (BYOD)

Azt is engedélyezheti, hogy a felhasználók saját személyes eszközeiket regisztrálják az Intune-felügyelethez. Ez a „saját eszköz használata” vagy BYOD (Bring Your Own Device) néven ismert. Miután teljesítette az előfeltételeket, és kiosztotta a felhasználói licenceket, a felhasználók a következőképp regisztrálhatják az eszközeiket:
- a [Céges portál](https://portal.manage.microsoft.com) webhelyre lépve, vagy
- a Céges portál alkalmazás letöltésével.
Meg is küldhet nekik egy hivatkozást az online regisztrációhoz: [Az Intune-ban macOS-eszköz regisztrálása](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [macOS-eszköz használata az Intune-nal](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Vállalati tulajdonban lévő macOS-eszközök
A felhasználóknak eszközöket vásárló szervezetek számára az Intune a következő módszereket támogatja a vállalati tulajdonban lévő macOS-eszközök regisztrálásához:
- [Az Apple Készülékregisztrációs Program (DEP)](device-enrollment-program-enroll-macos.md): MacOS-eszközök az Apple eszköz beléptetési Program (DEP) keresztül is vásárolhatók. A DEP vezeték nélkül képes telepíteni egy regisztrációs profilt, amely felügyelet alá helyezi az eszközöket.
- [Eszközregisztráció-kezelő (DEM-)](device-enrollment-manager-enroll.md): A DEM-fiók használhatja legfeljebb 1000 eszköz regisztrálásához.

## <a name="block-macos-enrollment"></a>macOS-regisztráció letiltása
Alapértelmezés szerint az Intune engedélyezi a macOS-eszközök regisztrálását. A macOS-eszközök regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="enroll-virtual-macos-machines-for-testing"></a>Virtuális macOS-gépek regisztrálása teszteléshez

> [!NOTE]
> A virtuális macOS-gépekhez csak teszteléshez jár támogatás. A virtuális macOS-gépeket ne használja végfelhasználói termelési eszközökként. 

A virtuális macOS-gépeket a Parallels Desktop vagy a VMWare Fusion segítségével regisztrálhatja tesztelésre. 

A Parallels Desktophoz meg kell adnia a virtuális gépek hardvertípusát és sorozatszámát, hogy az Intune felismerje őket. A hardvertípust Parallels utasítások és [sorozatszám](http://kb.parallels.com/123455) a teszteléshez szükséges beállítások megadásához. Azt javasoljuk, hogy a virtuális gépeket futtató eszközök hardvertípusa egyezzen meg a létrehozandó virtuális gépek hardvertípusával. A hardvertípust az **Apple menü** > **A Mac névjegye** > **Rendszerjelentés** > **Modellazonosító** területen találhatja meg. 

A VMware Fusion esetében [szerkesztenie kell a .vmx-fájlt](https://kb.vmware.com/s/article/1014782) a virtuális gép hardvermodelljének és sorozatszámának megadásához. Azt javasoljuk, hogy a virtuális gépeket futtató eszközök hardvertípusa egyezzen meg a létrehozandó virtuális gépek hardvertípusával. A hardvertípust az **Apple menü** > **A Mac névjegye** > **Rendszerjelentés** > **Modellazonosító** területen találhatja meg. 

## <a name="user-approved-enrollment"></a>Felhasználó által jóváhagyott regisztráció

A felhasználói jóváhagyott MDM-regisztráció egy olyan macOS-regisztrációs típus, amellyel bizonyos biztonsági szempontból kényes beállításokat kezelhet. További információt az [Apple támogatási dokumentumában találhat](https://support.apple.com/HT208019).

A felhasználó általi jóváhagyáshoz a végfelhasználónak manuális jóváhagyást kell adnia a rendszerbeállítások használatával a macOS Céges portállal való regisztráció után. Ehhez útmutatást a macOS 10.13.2 vagy újabb rendszert használó felhasználók a macOS Céges portálon találhatnak.

Annak megállapításához, hogy az eszköz jóvá van-e hagyva a felhasználó által, lépjen az Intune-portálra, majd válassza az **Eszközök** > **Minden eszköz**> kívánt eszköz > **Hardver** lehetőséget. Jelölje be a **Felhasználó által jóváhagyott** mezőt.

## <a name="next-steps"></a>További lépések

A macOS-eszközök regisztrációját követően [egyéni beállításokat hozhat létre a macOS-eszközökhöz](custom-settings-macos.md).
