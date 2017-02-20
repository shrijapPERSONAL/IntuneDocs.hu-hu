---
title: "Androidos eszközök regisztrálása az Intune-ban |Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan lehet regisztrálni az androidos eszközöket az Azure-os Intune előzetes verziójában."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune-rendszergazdaként a Munkahelyi portálról engedélyezheti az Android-eszközök (köztük a Samsung Knox Standard eszközök) kezelését. A felhasználók így a Google Play áruházban elérhető Munkahelyi portál alkalmazással regisztrálhatják az eszközeiket.

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani MDM-szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](set-mdm-authority.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni; előfordulhat tehát, hogy már megadta. 

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune az Android és a Samsung Knox Standard rendszerű eszközök regisztrálásának engedélyezésére van beállítva. 

Az androidos eszközök regisztrációját engedélyező vagy letiltó beállítást az Azure Portal Intune paneljéről, a **Beléptetés** > **Regisztrációs korlátozások** elem kiválasztásával jelenítheti meg. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Android-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


