---
title: "Windows 8.1- vagy Windows RT 8.1-eszköz regisztrálása | Microsoft Intune"
description: "Egy Windows 8.1-eszköz vagy Windows RT 8.1-eszköz regisztrálását mutatja be az Intune-ban"
keywords: 
author: barlanmsft
ms.author: barlanmsft
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28984f26-1070-4f7a-877c-669a59375c0c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7eefcefa5e1cd0f789c77bf020c256e449099273
ms.openlocfilehash: 53e9313bc85c149960fa985b655a22065b55b8a0


---


# <a name="enroll-your-windows-8.1-or-windows-rt-8.1-device-in-intune"></a>Windows 8.1- vagy Windows RT 8.1-eszköz regisztrálása az Intune-ban

Ha munkahelye vagy iskolája a Microsoft Intune-t használja, eszközének regisztrálásával hozzáférhet a vállalati levelezéséhez, fájljaihoz és egyéb vállalati erőforrásaihoz. Ha regisztrálja az eszközöket, azzal a szervezete megóvhatja a vállalati adatokat. További információk a regisztrációval kapcsolatban: [Mi történik a Vállalati portál alkalmazás telepítésekor és az eszköz Intune-beli regisztrálásakor?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md), illetve [Mit láthat a rendszergazda az eszközén, és mit nem?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) témakörben.


Windows 8.1- vagy Windows RT 8.1-eszköz regisztrálása az Intune-ban:

1.  Nyissa meg az eszközön a **Beállítások** &gt; **Gépház** &gt; **Hálózat** &gt; **Munkahely** lapot.

    ![nav-to-workplace](./media/W81-1-workplacejoin.png)

2.  Írja be a felhasználói azonosítójához tartozó munkahelyi vagy iskolai e-mail címét, és koppintson a **Csatlakozás** elemre.

    Ha az alkalmazás nem kéri a felhasználói azonosítót, akkor automatikusan azt az e-mail-címet használja, amelyikkel bejelentkezett az eszközre.

3.  Adja meg a munkahelyi vagy az iskolai e-mail-címéhez tartozó jelszót.

    ![type-password](./media/W81-2-workplacesettings_signin.png)

4.  Koppintson az **Eszközkezelés bekapcsolása** terület **Bekapcsolás** elemére.

    ![turn-on-device-management](./media/W81-3-dev-mgt-turn-on.png)

5.  Jelölje be az **Alkalmazások és szolgáltatások engedélyezése az IT rendszergazdai felületről** párbeszédpanel **Elfogadom** négyzetét, majd koppintson a **Bekapcsolás** elemre.

    ![turn-on-allow-apps-services](./media/W81-4-agree-allow-apps-services.png)

    A sikeres regisztrálás után megjelenik a következő képernyő.

    ![enrollment-complete](./media/W81-5-enrolled-done.png)

Azt javasoljuk, hogy telepítse a Vállalati portál alkalmazást, mert azzal egyszerűen megismerheti és letöltheti az Ön és munkaköre szempontjából fontos vállalati alkalmazásokat. Attól függően, hogy a vállalat hogyan állította be az Intune-t, előfordulhat, hogy a Vállalati portál alkalmazás már a regisztrációs folyamat részeként települt. Ha az alkalmazáslistában szerepel a **Vállalati portál**, akkor már megvan Önnek az alkalmazás. Ha a vállalati portál nem jelenik meg az alkalmazáslistán, akkor a következő lépésekkel telepítheti.

1.  Koppintson a **Start** &gt; **Áruház** parancsra.

2.  Koppintson a **Keresés** elemre, majd írja be a **vállalati portál** kifejezést.

3.  Az eredmények listájában koppintson a **Vállalati portál** elemre.

4.  Koppintson a **Telepítés** vagy az **Ingyenes** lehetőségre. Az, hogy melyik beállítás jelenik meg, attól függ, hogy a vállalat hogyan állította be az alkalmazást.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO2-->


