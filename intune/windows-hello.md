---
title: A Vállalati Windows Hello integrálása a Microsoft Intune-nal
titleSuffix: Microsoft Intune
description: Útmutató szabályzatok létrehozásához a Vállalati Windows Hello felügyelt eszközön való használatához.”
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: beb2043f2e32435d7e4ada3fcb1bb9918908dff9
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898190"
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>A Vállalati Windows Hello integrálása a Microsoft Intune-nal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Vállalati Windows Hello (korábbi nevén Microsoft Passport for Work) integrálható a Microsoft Intune-nal.

 A Vállalati Windows Hello egy alternatív bejelentkezési módszer, amely Active Directoryt vagy egy Azure Active Directory-fiókot használ jelszó, intelligens kártya vagy virtuális intelligens kártya helyett. Ez lehetővé teszi jelszó helyett *felhasználói kézmozdulatok* használatát a bejelentkezéshez. A felhasználói hitelesítési mód lehet egy egyszerű PIN-kód, biometrikus hitelesítés, mint például a Windows Hello, vagy egy külső eszköz, például egy ujjlenyomat-olvasó.

Az Intune kétféleképpen integrálható a Vállalati Hello szolgáltatással:

-   Létrehozható egy Intune-szabályzat az **Eszközregisztráció** alatt. Ez a szabályzat a teljes vállalatra vonatkozik (bérlői szinten). Támogatja a Windows AutoPilot kezdőélményt (OOBE), és az eszköz regisztrációjakor jut érvényre. 
-  Létrehozható egy Identity Protection-szabályzat az **Eszközregisztráció** alatt. Ez a profil a hozzárendelt felhasználókra és eszközökre vonatkozik, és a bejelentkezéskor jut érvényre. 

E cikk segítségével az egész vállalatára vonatkozó alapértelmezett vállalati Windows Hello-szabályzatot hozhat létre. A kiválasztott felhasználó- és eszközcsoportokra vonatkozó Identity Protection-profilt az [Identity Protection-profil konfigurálása](identity-protection-configure.md) című cikk alapján hozhat létre.  

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> Az évfordulós frissítés előtti Windows 10 asztali és mobil verziók esetében két különböző, az erőforrás hitelesítéséhez használható PIN-kódot is beállíthatott:
> - Az **eszköz PIN-kód** segítségével feloldhatta az eszköz zárolását és felhőalapú erőforrásokhoz kapcsolódhatott.
> - A **munkahelyi PIN-kód** segítségével a felhasználó személyes eszközén (BYOD) férhetett hozzá az Azure AD-erőforrásokhoz.
> 
> Az évfordulós frissítés ezt a két különböző PIN-kódot egyetlen eszköz PIN-kódban egyesítette.
> A korábban beállított, az eszköz PIN-kódját felügyelő, bármely Intune-konfigurációs szabályzat, valamint emellett bármely Vállalati Windows Hello-házirend immár kiváltható egyetlen PIN-kóddal.
> Ha mindkét fajta szabályzatot beállította a PIN-kód szabályozására, a Vállalati Windows Hello-szabályzat a Windows 10 rendszerű asztali és mobileszközökön egyaránt alkalmazva lesz.
> A házirendek között felmerülő esetleges ütközések feloldásához és a PIN-házirend megfelelő alkalmazásához frissítse a Vállalati Windows Hellót, hogy megfeleljen a konfigurációs szabályzat beállításainak, és kérje meg felhasználóit, szinkronizálják eszközeiket a Vállalati portál alkalmazásban.



## <a name="create-a-windows-hello-for-business-policy"></a>Vállalati Windows Hello-házirend létrehozása

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** > **Monitoring és felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök beléptetése**, majd a **Windows-alapú regisztráció** > **Vállalati Windows Hello** lehetőséget.

3. A megnyíló panelen válassza az **Alapértelmezett** beállításokat.

4. A **Minden felhasználó** panelen kattintson a **Tulajdonságok** lehetőségre, majd adjon meg egy **Nevet** és **Leírást** a Vállalati Windows Hello beállításai számára.

5. A **Minden felhasználó** panelen kattintson a **Beállítások** lehetőségre, majd a **Vállalati Windows Hello konfigurálása** területen válasszon az alábbi lehetőségek közül:

    - **Letiltva**. Ha nem szeretné használni a Vállalati Windows Hello szolgáltatást, válassza ezt a beállítást. Ezt követően a képernyőn a többi beállítás nem lesz elérhető.
    - **Engedélyezve**. Vállalati Windows Hello beállításainak konfigurálásához válassza ezt a beállítást.
    - **Nincs konfigurálva**. Ha nem szeretné, hogy az Intune vezérelje a Vállalati Windows Hello beállításait, válassza ezt a beállítást. A Windows 10-eszközökön meglévő Vállalati Windows Hello-beállítások nem módosulnak. A panelen a többi beállítás nem elérhető.

6. Ha az előző lépésben az **Engedélyezve** lehetőséget választotta, akkor konfigurálja a szükséges beállításokat. A rendszer az összes regisztrált Windows 10 és Windows 10 Mobile rendszerű eszközre alkalmazni fogja őket.

   - **Platformmegbízhatósági modul (TPM) használata**. A TPM lapka használata további adatbiztonsági réteget biztosít.<br>Válasszon egyet az alábbi lehetőségek közül:

     - **Kötelező** (alapértelmezett). A Vállalati Windows Hello csak az elérhető TPM modullal rendelkező eszközökön építhető ki.
     - **Elsődleges**. Az eszközök először a TPM használatára tesznek kísérletet. Ha az nem érhető el, használhatnak szoftveralapú titkosítást.

   - **PIN-kód minimális hossza**/**PIN-kód minimális hossza**. Beállítja az eszközöket a megadott minimális és maximális hosszúságú PIN-kód használatára, a biztonságos bejelentkezés érdekében. A PIN-kód alapértelmezett hossza 6 karakter, de előírható, hogy legalább 4 karakterből kell állnia. A PIN-kód legfeljebb 127 karakter hosszú lehet.

   - **Kisbetűk használata a PIN-kódban**/**Nagybetűk használata a PIN-kódban**/**Speciális karakterek a PIN-kódban**. Erősebb PIN-kód használata is előírható kis- és nagybetűk, illetve speciális karakterek PIN-kódon belüli használatának együttes megkövetelésével. A következő lehetőségek közül választhat:

     - **Engedélyezett**. A felhasználók használhatják a karaktertípust a PIN-kódban, de ez nem kötelező.

     - **Kötelező**. A felhasználóknak a karaktertípusból legalább egyet használniuk kell a PIN-kódjukban. Például általános gyakorlat legalább egy nagybetű és egy speciális karakter megkövetelése.

     - **Nem engedélyezett** (alapértelmezés). A felhasználók nem használhatják ezeket a karaktertípusokat a PIN-kódjukban. (Ugyanez a viselkedés jellemző, ha a beállítás nincs konfigurálva.)<br>A speciális karakterek a következők: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN lejárata (nap)**. A PIN-kódhoz célszerű lejárati időt megadni, amelynek eltelte után a felhasználóknak módosítaniuk kell a PIN-kódot. Az alapértelmezett érték 41 nap.

   - **PIN-előzmények megjegyzése**. Korlátozza a korábban használt PIN-kódok ismételt használatát. Alapértelmezés szerint az 5 legutóbb használt PIN-kód nem használható újra.

   - **Biometrikus hitelesítés engedélyezése**. Lehetővé teszi a biometrikus hitelesítést, például az arcfelismerést vagy az ujjlenyomat használatát a PIN-kód alternatívájaként a Vállalati Windows Hello szolgáltatásban. A felhasználóknak ekkor is be kell állítaniuk egy PIN-kódot arra az esetre, ha a biometrikus hitelesítés nem sikerül. A következő lehetőségek közül választhat:

     - **Igen**. A Vállalati Windows Hello lehetővé teszi a biometrikus hitelesítést.
     - **Nem**. A Vállalati Windows Hello meggátolja a biometrikus hitelesítést (minden fióktípus esetében).

   - **Kibővített hamisításszűrés használata, ha elérhető**. Konfigurálható, hogy a Windows Hello hamisításszűrési funkcióit használják-e az azt támogató eszközök (például egy valós arc helyett egy arcról készült fénykép észlelése).<br>Ha **Igen** értékre van állítva, a Windows minden felhasználótól megköveteli a kibővített hamisításszűrés alkalmazását arcfelismerés esetén, ha az támogatott.

   - **Telefonos bejelentkezés engedélyezése**. Ha a beállítás az **Igen** értékre van beállítva, a felhasználók egy Remote Passport eszközt használhatnak hordozható társeszközként az asztali hitelesítéshez. Az asztali gépnek csatlakoztatva kell lennie az Azure Active Directoryhoz, és a társeszköznek rendelkeznie kell a Vállalati Windows Hello PIN-kódjával.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business-támogatás

A Windows Holographic for Business az alábbi Vállalati Windows Hello-beállításokat támogatja:

- Platformmegbízhatósági modul (TPM) használata
- PIN-kód minimális hossza
- PIN-kód minimális hossza
- Kisbetűk használata a PIN kódban
- Nagybetűk használata a PIN kódban
- Speciális karakterek a PIN-kódban
- PIN lejárata (nap)
- PIN-előzmények megjegyzése

## <a name="further-information"></a>További információ
A Microsoft Passporttal kapcsolatos további információkért olvassa el a Windows 10 dokumentációjában található [útmutatót](https://technet.microsoft.com/library/mt589441.aspx).
