---
title: "Androidos eszközök regisztrálása az Intune-ban"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan lehet regisztrálni az androidos eszközöket az Azure-os Intune előzetes verziójában."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b7188dd8163334429396e7b7c8687810a6e63bb2
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune-nal felügyelhet androidos eszközöket, többek között Samsung Knox Standard típusúakat is. Az eszközfelügyelethez a felhasználóknak le kell tölteniük a Google Play-ből az Intune Céges portál alkalmazást, majd azt megnyitva az útmutatás alapján regisztrálniuk kell az eszközt. Ha az androidos eszközök bekerültek a felügyelet alá, Ön számos más művelet mellett [megfelelőségi szabályzatokat hozhat létre](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android) vagy [felügyelheti az alkalmazásokat](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management).

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani MDM-szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](set-mdm-authority.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni; előfordulhat tehát, hogy már megadta. 

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune engedélyezi az Android és a Samsung Knox Standard rendszerű eszközök regisztrálását. 

Az androidos eszközök (vagy csak a személyes tulajdonban levők) regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions) című témakörben olvashat. 

Az egy felhasználó által regisztrálható eszközök számának korlátozásáról a [Regisztrált eszközök maximális számának beállítása](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions) című témakörben olvashat.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A felhasználókat meg kell kérnie, hogy a Google Play-ből töltsék le az Intune Céges portál alkalmazást, és annak útmutatása alapján regisztrálják eszközeiket. Az alkalmazás végigvezeti a felhasználókat a beléptetési folyamaton, tájékoztatja őket arról, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

Hivatkozást is küldhet nekik az online regisztrációhoz: [Androidos eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android) 

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
