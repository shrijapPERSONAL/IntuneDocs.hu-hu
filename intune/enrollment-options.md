---
title: "Eszközregisztrációs lehetőségek az Intune-hoz"
description: 
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: dcc97e5bcffb35752b65e8ce275d38b9578da6fa
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2017
---
# <a name="enrollment-options-for-intune"></a>Eszközregisztrációs lehetőségek az Intune-hoz

Intune-rendszergazdaként konfigurálhatja az eszközregisztrációt, hogy segítségére legyen a felhasználóknak, és kihasználja az Intune képességeit.  Az Intune a következő regisztrálási lehetőségeket tartalmazza:

## <a name="terms-and-conditions"></a>használati feltételei

Ön döntheti el, hogy megköveteli-e a felhasználóktól a cég használati feltételeinek elfogadását, mielőtt a Céges portált használnák saját eszközeik beléptetéséhez, valamint az erőforrások (például céges alkalmazások és e-mailek) eléréséhez. A használati feltételek konfigurálása nem kötelező. További információ [a feltételekről és kikötésekről](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Regisztrációs korlátozások

Az eszközregisztrációt az alábbiak szerint korlátozhatja:
- Eszközplatform
- Eszközök száma felhasználónként
- Személyes eszközök letiltása

További információ [a regisztrációs korlátozásokról](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Az Apple-készülékregisztráció engedélyezése

Az iOS- és Mac-eszközökhöz MDM Push-tanúsítványra van szükség. További információ [az MDM Push-tanúsítványokról](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Vállalati azonosítók

Nemzetközi mobilkészülék-azonosító (IMEI) számok és sorozatszámok megadásával azonosíthatja a vállalat által birtokolt eszközök listáját. További információ a [vállalati azonosítókról](corporate-identifiers-add.md).

## <a name="device-enrollment-manager"></a>Készülékregisztráció-kezelő
Felhasználókat tehet meg eszközregisztráció-kezelőnek.  A DEM-felhasználók az Intune használatával nagyszámú mobileszközt regisztrálhatnak egyetlen felhasználói fiókkal. Az eszközregisztráció-kezelői (DEM-) fiók akár ezer eszköz regisztrálására képes. További tudnivalók [az eszközregisztráció-kezelőkről](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Eszközkategóriák

Az eszközkategóriák segítségével automatikusan csoportokba veheti fel az eszközöket az Ön által meghatározott kategóriák alapján. Az eszközök csoportokba való rendszerezése megkönnyíti az eszközök kezelését. További tudnivalók az [eszközkategóriákról](device-group-mapping.md).
