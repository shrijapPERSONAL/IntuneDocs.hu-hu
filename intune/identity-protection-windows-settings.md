---
title: Windows Hello for Business beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Megjelenítheti az összes PIN-kód, biometrikus, és az identity protection profilban hamisításszűrés beállítások használata és konfigurálása Windows Hello for Business a Microsoft Intune-ban Windows 10-eszközök listáját.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 1cbf45fc337cbe7d7a45081a3b9e05002ca126d8
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402927"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Windows 10-es eszközbeállítások engedélyezése Windows Hello for Business az Intune-ban

Ez a cikk felsorolja és ismerteti a Windows Hello for Business beállításaival szabályozhatja az Intune-ban Windows 10 rendszerű eszközökön. Intune-rendszergazdák konfigurálni, és ezek a beállítások hozzárendelése Windows 10-eszközök a mobileszköz-felügyelet (MDM) megoldás részeként. 

Ezeket a beállításokat a további információt talál [konfigurálása Windows Hello for Business szabályzatbeállításai](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings), a Windows Hello dokumentációjában.


Tudjon meg többet a Windows Hello-profilok az Intune-ban, tekintse meg [identity protection konfigurálása](identity-protection-configure.md).

## <a name="before-you-begin"></a>Előkészületek

[Hozzon létre egy konfigurációs profil](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Vállalati Windows Hello
- **A vállalati Windows Hello konfigurálása**:
  - **Nincs konfigurálva** – válassza ezt a beállítást, ha nem szeretné az Intune vezérelje Windows Hello for Business beállításai. A Windows 10-eszközökön meglévő Vállalati Windows Hello-beállítások nem módosulnak. A panelen a többi beállítás nem elérhető.

  - **Letiltott** – Ha nem kívánja használni Windows Hello for Business, ezt a beállítást. Ezt követően a képernyőn a többi beállítás nem lesz elérhető.
  - **Engedélyezett** – válassza ezt a beállítást, ha azt szeretné, hogy a Windows Hello for Business beállításainak konfigurálása.  
  
  **Alapértelmezett**: Nincs konfigurálva

  Ha a beállítása *engedélyezve*, a következő beállítások érhetők el:

    - **PIN-kód minimális hossza**  
     Adja meg a PIN kód minimális hosszának eszközök, biztonságos bejelentkezés érdekében. Windows-eszköz alapértelmezett érték 6 karakter, de ezzel a beállítással kényszeríthet egy legalább négy – 127 karakter. 
  
      **Alapértelmezett**: *Nincs konfigurálva*

    - **PIN-kód maximális hossza**  
    Adja meg a PIN-kód maximális hossza az eszközök, biztonságos bejelentkezés érdekében. Windows-eszköz alapértelmezett érték 6 karakter, de ezzel a beállítással kényszeríthet egy legalább négy – 127 karakter.  

      **Alapértelmezett**: *Nincs konfigurálva*  

    - **Kisbetűk használata a PIN-kód**  
      Erősebb PIN-kód kényszerítheti a végfelhasználók által kisbetűket tartalmazza. A választható lehetőségek:

      - **Nem engedélyezett** -meggátolja a felhasználókat a kisbetűk használatát a PIN-kódban. Ez a viselkedés akkor is előfordul, ha a beállítás nincs konfigurálva.
      - **Engedélyezett** – engedélyezése a felhasználóknak a kisbetűk használata a PIN-kódban, de ez nem szükséges.
      - **Szükséges** -felhasználók tartalmaznia kell legalább egy kisbetű a PIN-kódban. Például általános gyakorlat legalább egy nagybetű és egy speciális karakter megkövetelése.

    - **Nagybetűk a PIN-kód**  
    Erősebb PIN-kód kényszerítheti a végfelhasználók által közé tartozik a nagybetűk. A választható lehetőségek:

      - **Nem engedélyezett** -meggátolja a felhasználókat a nagybetűk használatát a PIN-kódban. Ez a viselkedés akkor is előfordul, ha a beállítás nincs konfigurálva.
      - **Engedélyezett** – engedélyezése a felhasználóknak a nagybetűk használata a PIN-kódban, de ez nem szükséges.
      - **Szükséges** -felhasználók tartalmaznia kell legalább egy nagybetű a PIN-kódban. Például általános gyakorlat legalább egy nagybetű és egy speciális karakter megkövetelése.

    - **Speciális karakterek a PIN-kód**  
    Erősebb PIN-kód azzal, hogy a végfelhasználók kényszerítheti a különleges karaktereket. Speciális karakterek a következők: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  
 
      A választható lehetőségek:
      - **Nem engedélyezett** -meggátolja a felhasználókat a speciális karakterek a PIN-kód használatát. Ez a viselkedés akkor is előfordul, ha a beállítás nincs konfigurálva.
      - **Engedélyezett** – engedélyezése a felhasználóknak a nagybetűk használata a PIN-kódban, de ez nem szükséges.
      - **Szükséges** -felhasználók tartalmaznia kell legalább egy nagybetű a PIN-kódban. Például általános gyakorlat legalább egy nagybetű és egy speciális karakter megkövetelése.

      **Alapértelmezett**: Nem engedélyezett

  - **PIN-kód lejárata (nap)**  
      A PIN-kódhoz célszerű lejárati időt megadni, amelynek eltelte után a felhasználóknak módosítaniuk kell a PIN-kódot. Windows-eszköz alapértelmezett érték 41 nap.

    **Alapértelmezett**: Nincs konfigurálva

  - **PIN-előzmények megjegyzése**  
    Korlátozza a korábban használt PIN-kódok ismételt használatát. Windows eszközök alapértelmezés szerint az utolsó öt PIN-kódok újbóli megakadályozása.  

    **Alapértelmezett**: Nincs konfigurálva  

  - **Helyreállítási PIN-kód engedélyezése**   
    Lehetővé teszi, hogy a felhasználó szeretné használni a Windows Hello PIN-KÓDJÁBAN helyreállítási szolgáltatáshoz. 
    
    - **Engedélyezett** – a PIN-kód helyreállítási titkos kulcs az eszközön tárolt, és szükség esetén a felhasználó módosíthatja PIN-kódjukban.  
    - **Letiltott** – a helyreállítási titkos kulcs nem létre vagy tárolja.

    **Alapértelmezett**: Nincs konfigurálva

  - **Platformmegbízhatósági modul (TPM) használata**   
    A TPM lapka használata további adatbiztonsági réteget biztosít.  

    - **Engedélyezett** – csak az elérhető TPM Modullal rendelkező eszközökön építhető ki a Windows Hello for Business.
    - **Nincs konfigurálva** -eszközök először a TPM használatára tesznek kísérletet. Ha az nem érhető el, használhatnak szoftveralapú titkosítást.
    
    **Alapértelmezett**: Nincs konfigurálva

  - **Biometrikus hitelesítés engedélyezése**  
     Lehetővé teszi a biometrikus hitelesítést, például az arcfelismerést vagy az ujjlenyomat használatát a PIN-kód alternatívájaként a Vállalati Windows Hello szolgáltatásban. A felhasználóknak ekkor is be kell állítaniuk egy PIN-kódot arra az esetre, ha a biometrikus hitelesítés nem sikerül. A következő lehetőségek közül választhat:

    - **Engedélyezése** – Windows Hello for Business lehetővé teszi a biometrikus hitelesítést.
    - **Nincs konfigurálva** – Windows Hello for Business meggátolja a biometrikus hitelesítést (minden fióktípus esetében).

    **Alapértelmezett**: Nincs konfigurálva

  - **Használja a hamisítások kibővített szűrését, ha elérhető**  
    Konfigurálható, hogy a Windows Hello hamisításszűrési funkcióit használják-e az azt támogató eszközök (például egy valós arc helyett egy arcról készült fénykép észlelése).  
    - **Engedélyezése** -hamisításszűrés arcfelismerés esetén, ha támogatja, amelyek minden felhasználótól megköveteli a Windows.
    - **Nincs konfigurálva** – Windows figyelembe veszi a hamisításszűrés konfigurációkat az eszközön.

    **Alapértelmezett**: Nincs konfigurálva

  - **A tanúsítvány a helyi erőforrások**  

    - **Engedélyezése** – lehetővé teszi a Windows Hello for Business tanúsítványok segítségével hitelesíti a helyszíni erőforrásokhoz.
    - **Nincs konfigurálva** – megakadályozza, hogy a Windows Hello for Business tanúsítványok segítségével hitelesíti a helyszíni erőforrások. Ehelyett használja az eszközök a alapértelmezett viselkedését *megbízható kulcs a helyszíni hitelesítési*. További információkért lásd: [felhasználói tanúsítvány a helyszíni hitelesítéshez](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) a Windows Hello dokumentációjában.  

  **Alapértelmezett**: Nincs konfigurálva

- **Jelentkezzen be a biztonsági kulcsok használata**  
  Ez a beállítás 1903 vagy újabb verziójú Windows 10 rendszerű eszközökön érhető el. Kezelésére használhatja támogatása a Windows Hello biztonsági kulcsok használata a bejelentkezéshez.  

  - **Engedélyezett** -felhasználók használhatják a Windows Hello biztonsági kulcs, az ezzel a szabályzattal megcélzott számítógépek esetében a bejelentkezési hitelesítő adataihoz. 
  - **Le van tiltva** – biztonsági kulcsok le vannak tiltva, és a felhasználók nem használhatnak azok a számítógépek bejelentkezni.   

  **Alapértelmezett**: Nincs konfigurálva

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
