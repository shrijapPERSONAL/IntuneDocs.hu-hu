---
title: "Mobileszköz-felügyeleti szolgáltató megadása"
titlesuffix: Azure portal
description: "A cikk azt ismerteti, hogyan állítható be a mobileszköz-felügyeleti szolgáltató az Intune-ban. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cee02cf20416f719771705079beae7bc986f1069
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Ahhoz, hogy a felhasználók felügyeletre tudják regisztrálni eszközeiket, a rendszergazdának be kell állítania egy MDM-szolgáltatót.

A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll. [MDM-szolgáltató beállítása az Intune-konzolon](#set-mdm-authority-to-intune).

- **Hibrid Intune** – az Intune felhőalapú megoldásainak integrációja a System Center Configuration Manager alkalmazásba. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja. [MDM-szolgáltató beállítása a Configuration Managerben](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune-t az Office 365 Felügyeleti központ segítségével konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza. MDM-szolgáltató beállítása az Office 365 felügyeleti központjában.

>[!IMPORTANT]    
A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információért tekintse meg a [Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) című részt.

## <a name="set-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

1. Az [Azure Portalon](https://portal.azure.com) válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. A **Mobileszköz-kezelő szolgáltató** beállítás megnyitásához válassza a narancssárga szalagcímet.
3. A **Mobileszköz-kezelő szolgáltató** szakaszban válassza ki az alábbiak közül a kívánt MDM-szolgáltatót:
  - **Intune MDM-szolgáltató**
  - **Configuration Manager MDM-szolgáltató**.
  - **Nincsenek**

  ![Képernyőkép az Intune mobileszköz-kezelő szolgáltató beállítására szolgáló képernyőjéről](media/set-mdm-auth.png)

  Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.

## <a name="enable-device-enrollment"></a>Eszközök regisztrálásának lehetővé tétele

Ha az Intune-t állítja be MDM-szolgáltatóként, a felhasználók regisztrálhatják saját tulajdonú eszközeiket, és az alábbi módokon férhetnek hozzá olyan erőforrásokhoz, mint a levelezés, ha telepítik a Céges portál alkalmazást (iOS és Android), beállítják munkahelyi hitelesítő adataikat (Windows), vagy felkeresik a Céges portál webhelyet (iOS, Android, macOS).

Az egyes platformokon a következők a regisztrálás engedélyezésének, illetve leegyszerűsítésének követelményei:
- **iOS** – (kötelező) [Apple MDM Push-tanúsítvány beszerzése,](apple-mdm-push-certificate-get.md) majd pedig [a céges iOS-eszközök regisztrálásának engedélyezése](ios-enroll.md) (nem kötelező).
- **Android** – (nem kötelező) [Az androidos munkahelyi profilok engedélyezése](android-enroll.md)
- **Windows** – (nem kötelező) Az [automatikus regisztráció](windows-enroll.md) vagy a [csoportos regisztráció](windows-bulk-enroll.md) engedélyezése.
- **macOS** – Nincsenek követelmények.


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
