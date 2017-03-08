---
title: "Androidos eszközök kezelésének beállítása | Microsoft Docs"
description: "Lehetővé teheti az androidos vagy KNOX Standard-eszközöknek a Microsoft Intune-nal történő mobileszköz-felügyeletét (MDM)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6b99854e17e00a0dd0f91fa82fd1b79d1dfe5663
ms.openlocfilehash: 8e2588e2bb0537877f0164bc996fa973f25ea4dd
ms.lasthandoff: 02/18/2017


---

# <a name="set-up-android-device-management"></a>Android-eszközök kezelésének beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune-rendszergazdaként a Munkahelyi portálról engedélyezheti az Android-eszközök (köztük a Samsung Knox Standard eszközök) kezelését. A felhasználók így a Google Play áruházban elérhető Munkahelyi portál alkalmazással regisztrálhatják az eszközeiket.

Alapértelmezés szerint az Android-eszközök regisztrációja engedélyezett az Intune-ban. Az Android-eszközök regisztrációjának letiltásához jelentkezzen be a [Microsoft Intune felügyeleti portálra](http://manage.microsoft.com) a rendszergazdai hitelesítő adataival. Válassza a **Felügyelet** > **Mobileszköz-kezelés** > **Regisztráció szabályai** elemet, majd törölje az **Android-eszközök engedélyezése** jelölőnégyzetet.

1.  **Az Intune beállítása**<br>
    Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#step-2-set-mdm-authority), valamint beállítja a mobileszköz-kezelést.

2.  **Android eszközök regisztrálása**<br>
    Az androidos mobileszközök regisztrációjának engedélyezéséhez nincs szükség további beállítások megadására az Intune-konzolon.

3.  **Mondja el a felhasználóknak, miként regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Android-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-android.md). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

    Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
  - [Információk végfelhasználóknak a Microsoft Intune használatáról](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Végfelhasználói útmutató Android-eszközökhöz](../enduser/using-your-android-device-with-intune.md)

Kínában nem érhető el a Google Play áruház, ezért az Android-eszközöknek kínai alkalmazásáruházakból kell beszerezniük a Vállalati portált. Az androidos Munkahelyi portál alkalmazás a következő áruházakból is letölthető lesz:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

A Munkahelyi portál alkalmazás androidos verziója a Google Play szolgáltatások segítségével kommunikál a Microsoft Intune szolgáltatással. A Google Play szolgáltatások egyelőre nem érhetők el Kínában, ezért a következő műveletek bármelyike akár 8 órát is igénybe vehet. 

|Intune felügyeleti konzol| Intune Munkahelyi portál alkalmazás Androidhoz |Intune Munkahelyi portál webhely|   
|---|---|---|
|Teljes törlés| Távoli eszköz eltávolítása| Eszköz eltávolítása (helyi és távoli)|
|Szelektív törlés| Eszköz alaphelyzetbe állítása| Eszköz alaphelyzetbe állítása|
|Új vagy frissített alkalmazás telepítése| Rendelkezésre álló üzleti alkalmazások telepítése| Eszköz PIN-kódjának alaphelyzetbe állítása|
|Távoli zárolás|||
|PIN-kód alaphelyzetbe állítása|||

### <a name="see-also"></a>További információ
[A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md)

