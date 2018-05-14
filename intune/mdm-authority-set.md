---
title: Mobileszköz-felügyeleti szolgáltató megadása
titlesuffix: Microsoft Intune
description: Mobileszköz-felügyeleti szolgáltató beállítása az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f903e9dfe5fb30f45806aac5694171814492f2e
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2018
---
# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Ahhoz, hogy a felhasználók felügyeletre tudják regisztrálni eszközeiket, a rendszergazdának be kell állítania egy MDM-szolgáltatót.

A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll. [MDM-szolgáltató beállítása az Intune-konzolon](#set-mdm-authority-to-intune).

- **Hibrid Intune** – az Intune felhőalapú megoldásainak integrációja a System Center Configuration Manager alkalmazásba. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja. [MDM-szolgáltató beállítása a Configuration Managerben](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune-t az Office 365 Felügyeleti központ segítségével konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza. MDM-szolgáltató beállítása az Office 365 felügyeleti központjában.

> [!IMPORTANT]
> A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információt a [Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) című szakaszban talál.

## <a name="set-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. A **Mobileszköz-kezelő szolgáltató** beállítás megnyitásához válassza a narancssárga szalagcímet.
4. A **Mobileszköz-kezelő szolgáltató** szakaszban válassza ki az alábbiak közül a kívánt MDM-szolgáltatót:
   - **Intune MDM-szolgáltató**
   - **Configuration Manager MDM-szolgáltató**.
   - **Nincsenek**

   ![Képernyőkép az Intune mobileszköz-kezelő szolgáltató beállítására szolgáló képernyőjéről](media/set-mdm-auth.png)

   Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.

## <a name="enable-device-enrollment"></a>Eszközök regisztrálásának lehetővé tétele

Ha az Intune-t állítja be MDM-szolgáltatóként, a felhasználók regisztrálhatják saját tulajdonú eszközeiket, és az alábbi módokon férhetnek hozzá olyan erőforrásokhoz, mint a levelezés, ha telepítik a Céges portál alkalmazást (iOS, macOS és Android), beállítják munkahelyi hitelesítő adataikat (Windows), vagy felkeresik a Céges portál webhelyet (iOS, Android, macOS).

Az egyes platformokon a következők a regisztrálás engedélyezésének, illetve leegyszerűsítésének követelményei:
- **iOS** – (kötelező) [Apple MDM Push-tanúsítvány beszerzése,](apple-mdm-push-certificate-get.md) majd pedig [a céges iOS-eszközök regisztrálásának engedélyezése](ios-enroll.md) (nem kötelező).
- **Android** – (nem kötelező) [Az androidos munkahelyi profilok engedélyezése](android-enroll.md)
- **Windows** – (nem kötelező) Az [automatikus regisztráció](windows-enroll.md) vagy a [csoportos regisztráció](windows-bulk-enroll.md) engedélyezése.
- **macOS** – (kötelező) [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md).

### <a name="workflow-of-intune-administration-ui"></a>Az Intune-felügyelet felhasználói felületének munkafolyamata
Engedélyezett Android- vagy Apple-eszközkezelés esetén az Intune eszköz- és felhasználóadatok küldésével végzi el az eszközök kezeléséhez szükséges integrációt a külső szolgáltatásokkal.

Néhány új helyzet, amelyben az adatok megosztásához a rendszer jóváhagyást kér:
- Android for Work engedélyezése.
- Apple MDM leküldéses tanúsítványok engedélyezése és feltöltése.
- Olyan Apple-szolgáltatások engedélyezése, mint a Készülékregisztrációs program, a School Manager és a mennyiségi vásárlási program (VPP).

A jóváhagyás minden esetben szigorúan csak egy mobileszköz-felügyeleti szolgáltatás futtatására vonatkozik. Ilyen például annak megerősítése, hogy egy rendszergazda engedélyezte Google- vagy Apple-eszközök regisztrálását. Az új munkafolyamatok indulásakor megosztott adatokról szóló dokumentáció az alábbi helyeken érhető el:
- [Az Intune által a Google-nek küldött adatok](https://aka.ms/Data-intune-sends-to-google)
- [Az Intune által az Apple-nek küldött adatok](https://aka.ms/data-intune-sends-to-apple)

További információ a Microsoft GDPR-megfelelőségéről: [Adatvédelmi központ – GDPR-megfelelőség értékelése](https://aka.ms/trust_center_info).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
