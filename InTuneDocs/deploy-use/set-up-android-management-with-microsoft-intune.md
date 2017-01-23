---
title: "Androidos eszközök kezelésének beállítása | Microsoft Docs"
description: "Lehetővé teheti az androidos vagy KNOX Standard-eszközöknek a Microsoft Intune-nal történő mobileszköz-felügyeletét (MDM)."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ddc03985ab8a4959a1d2c9a47e77f042ab9310
ms.openlocfilehash: 6b74c09c37970429d3eaa571db655854d592a2fe


---

# <a name="set-up-android-device-management"></a>Android-eszközök kezelésének beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune-rendszergazdaként a Munkahelyi portálról engedélyezheti az Android-eszközök (köztük a Samsung Knox Standard eszközök) kezelését. A felhasználók így a Google Play áruházban elérhető Munkahelyi portál alkalmazással regisztrálhatják az eszközeiket.

1.  **Az Intune beállítása**<br>
    Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#step-2-set-mdm-authority), valamint beállítja a mobileszköz-kezelést.

2.  **Android eszközök regisztrálása**<br>
    Az androidos mobileszközök regisztrációjának engedélyezéséhez nincs szükség további beállítások megadására az Intune-konzolon.

3.  **Mondja el a felhasználóknak, miként regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Android-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-android.md). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

    Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
  - [Információk végfelhasználóknak a Microsoft Intune használatáról](what-to-tell-your-end-users-about-using-microsoft-intune.md)
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



<!--HONumber=Jan17_HO1-->


