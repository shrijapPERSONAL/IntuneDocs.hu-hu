---
title: "Androidos eszközök kezelésének beállítása | Microsoft Docs"
description: "Lehetővé teheti az androidos vagy KNOX Standard-eszközöknek a Microsoft Intune-nal történő mobileszköz-felügyeletét (MDM)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: a5a4f11ae341480b2e674ca55a514b62831bdd60
ms.lasthandoff: 03/21/2017


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

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Android-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

    Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
  - [Információk végfelhasználóknak a Microsoft Intune használatáról](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Végfelhasználói útmutató Android-eszközökhöz](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

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

