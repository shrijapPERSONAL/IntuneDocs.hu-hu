---
title: Windows-eszköz törlése az Intune-ból | Microsoft Docs
description: Egy Windows-eszköz Intune-ból való törlését mutatja be
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 89a69f7d5cda31658cc9faf068a2a37698fdd93c
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="remove-your-windows-device-from-intune"></a>Windows-eszköz törlése az Intune-ból

Ha eszköze regisztrálva van az Intune-ban, de már nem szeretné windowsos eszközét, a munkahelyi vagy iskolai e-mailekhez, alkalmazásokhoz és egyéb erőforrásokhoz való hozzáférésre használni, törölnie kell az eszközt a felügyelet alól. Az eszköz Intune-ból való törlése után már nem fog tudni hozzáférni ezekhez az erőforrásokhoz. Az eszköz felügyelet alóli kivonásának további következményeiről további információkért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Windows 10 rendszerű eszköz törlése

1.  Koppintson a **Vállalati portál** alkalmazásra az alkalmazások listájában.

2.  Jelentkezzen be a munkahelyi vagy iskolai fiókjával.

3.  Az **Eszközök**részben válassza ki azt az eszközt, amelynek regisztrációját törölni szeretné.

4.  Koppintson az **Eltávolítás** &gt; **Eltávolítás** lehetőségre.

## <a name="remove-your-windows-81-computer"></a>Windows 8.1-es számítógép törlése

1.  Lépjen a **Gépház** &gt; **Hálózat** &gt; **Munkaterület** menüpontra.

2.  A **Csatlakozás munkahelyhez** területen válassza a **Kilépés** lehetőséget.

3.  Válassza az **Eszközkezelés bekapcsolása** terület **Kikapcsolás** lehetőségét.

4.  A megjelenő előugró ablakban válassza a **Kikapcsolás** lehetőséget.

## <a name="remove-your-windows-phone-81-mobile-device"></a>Windows Phone 8.1 rendszerű mobileszköz törlése

1.  Lépjen a **Beállítások** &gt; **Munkaterület** menüpontra.

2.  Koppintson a törölni kívánt munkahelyi fiókra.

3.  A képernyő alsó részén koppintson a **Törlés** elemre.

4.  A **Fiók törlése** párbeszédpanelen koppintson a **Törlés** gombra.

## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Személyes információk törlése a Céges portál eltávolítása után

A Céges portál kétféle adatot tárol az Ön windowsos eszközén:

-   **Diagnosztikai naplók**: a Microsoft által gyűjtött szabványos alkalmazástevékenység-adatok, például, hogy meddig volt megnyitva az alkalmazás, vagy, hogy összeomlott-e, automatikusan törlődnek a Céges portál alkalmazás eltávolításakor.
-   **Alkalmazás-gyorsítótár**: bizonyos támogató fájlok, például ikonok és beállítások tárolása szükséges az alkalmazás működéséhez.

Ennek az információnak a teljes törléséhez végre kell hajtania néhány lépést.

### <a name="uninstall-the-company-portal"></a>A Céges portál eltávolítása  

[A Céges portál alkalmazás eltávolítása](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) törli az eszközön tárolt alkalmazásadatok egy részét.  

### <a name="reset-the-company-portal"></a>A Céges portál alaphelyzetbe állítása

A Céges portál többi alkalmazásadata az alkalmazást a Beállítások között alaphelyzetbe állítva törölhető. Válassza a **Beállítások** > **Alkalmazások és funkciók** > **Céges portál** > **Speciális beállítások** > **Alaphelyzetbe állítás** lehetőséget.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).
