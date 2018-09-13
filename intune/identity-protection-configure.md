---
title: Identitásvédelmi beállítások konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Eszközprofil hozzáadása a Vállalati Windows Hello beállításainak megadásához a Windows 10 rendszerű eszközökön a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7012479023ece83ef475431c5cefe150ab2ef342
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43317942"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Identitásvédelmi beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az identitásvédelmi profilok vezérlik, hogyan történjen a Vállalati Windows Hello kiépítése és konfigurálása a felügyelt Windows 10 rendszerű eszközökön. Hozza létre ezt a profilt konfiguráláshoz:  
* A Vállalati Windows Hello rendelkezésre állása eszközökhöz és felhasználók számára.
* Az eszköz PIN-kóddal kapcsolatos követelményei.
* Kézmozdulatok, amelyekkel a felhasználók bejelentkezhetnek az eszközükre, és amelyekkel nem.  

 Ezt a profilt hozzárendelheti kiválasztott felhasználókhoz vagy eszközcsoportokhoz, vagy minden felhasználóhoz és minden eszközhöz. A csoportok az Intune-ba történő bejelentkezéskor kapják meg az identitásvédelmi profiljukat.    

A cikkben található információk alapján létrehozhat egy identitásvédelmi profilt. Ezután [rendelje hozzá a profilt](device-profile-assign.md) a felhasználói és eszközcsoportokhoz.

Ez a funkció a következő rendszerű eszközökre vonatkozik:  
- Windows 10 és újabb
- Windows Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Eszközprofil létrehozása identitásvédelmi beállításokkal

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
4. Adja meg az identitásvédelmi profil **nevét** és **leírását**.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget. A Vállalati Windows Hello csak a Windows 10 vagy újabb rendszerű eszközökön támogatott.
6. A **Profil típusa** legördülő listából válassza az **Identitásvédelem** lehetőséget.
7. A Vállalati Windows Hello konfigurálásához a Vállalati Windows Hello ablaktáblán válasszon az alábbi lehetőségek közül:
    * Letiltva. Ha nem szeretné használni a Vállalati Windows Hello szolgáltatást, válassza ezt a beállítást. Ezt követően a képernyőn a többi beállítás nem lesz elérhető.
    * Engedélyezve. Vállalati Windows Hello beállításainak konfigurálásához válassza ezt a beállítást.  

8. Ha az előző lépésben az **Engedélyezve** lehetőséget választotta, akkor konfigurálja a szükséges beállításokat, amelyeket a rendszer a megcélzott és regisztrált Windows 10 és Windows 10 Mobile rendszerű eszközre és felhasználóra fog alkalmazni.

> [!NOTE]
> Ha csak felhasználókhoz rendel hozzá identitásvédelmi profilokat, az eszközkörnyezet alapértelmezett beállítása a **Nem konfigurált** lesz.  

   - **PIN-kód minimális hossza**/**PIN-kód minimális hossza**. Beállítja az eszközöket a megadott minimális és maximális hosszúságú PIN-kód használatára, a biztonságos bejelentkezés érdekében. A PIN-kód alapértelmezett hossza 6 karakter, de előírható, hogy legalább 4 karakterből kell állnia. A PIN-kód legfeljebb 127 karakter hosszú lehet.  

   - **Kisbetűk használata a PIN-kódban**/**Nagybetűk használata a PIN-kódban**/**Speciális karakterek a PIN-kódban**. Erősebb PIN-kód használata is előírható kis- és nagybetűk, illetve speciális karakterek PIN-kódon belüli használatának együttes megkövetelésével. A következő lehetőségek közül választhat:

     - **Engedélyezett**. A felhasználók használhatják a karaktertípust a PIN-kódban, de ez nem kötelező.

     - **Kötelező**. A felhasználóknak a karaktertípusból legalább egyet használniuk kell a PIN-kódjukban. Például általános gyakorlat legalább egy nagybetű és egy speciális karakter megkövetelése.

     - **Nem engedélyezett** (alapértelmezés). A felhasználók nem használhatják ezeket a karaktertípusokat a PIN-kódjukban. (Ugyanez történik, ha a beállítás nincs konfigurálva.)<br>A speciális karakterek a következők: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN lejárata (nap)**. A PIN-kódhoz célszerű lejárati időt megadni, amelynek eltelte után a felhasználóknak módosítaniuk kell a PIN-kódot. Az alapértelmezett érték 41 nap.

   - **PIN-előzmények megjegyzése**. Korlátozza a korábban használt PIN-kódok ismételt használatát. Alapértelmezés szerint az 5 legutóbb használt PIN-kód nem használható újra.  
   - **PIN-kód helyreállításának engedélyezése:** Lehetővé teszi, hogy a felhasználó megváltoztassa a PIN-kódját a Vállalat Windows Hello PIN-helyreállítási szolgáltatásával. 
       - **Engedélyezés**. A felhőszolgáltatásban létrejön egy titkos kód a PIN-kód helyreállításához, amelynek a tárolása az eszközön történik. A felhasználó szükség esetén megváltoztathatja a PIN-kódját.  
       - **Nincs konfigurálva** (alapértelmezett). Nem jött létre vagy nincs tárolva a PIN-kód helyreállításához titkos kód. Ha elfelejti a felhasználó a PIN-kódját, csak úgy lehet új PIN-kódot kérni, ha törli a meglévő PIN-kódot, és létrehoz egy újat. A felhasználó minden szolgáltatásban újból el kell végeznie a regisztrációt, amelyhez a régi PIN-kóddal fért hozzá.  
   
   - **Platformmegbízhatósági modul (TPM) használata**. A TPM lapka használata további adatbiztonsági réteget biztosít. Válasszon egyet az alábbi lehetőségek közül:  
     - **Engedélyezés**. A Vállalati Windows Hello csak az elérhető TPM modullal rendelkező eszközökön építhető ki.
     - **Nincs konfigurálva**. A Vállalati Windows Hello minden eszközön telepíthető, még akkor is, ha nincs használható TPM. Az eszközök először megpróbálják a TPM-et használni, de ha nem áll rendelkezésre, akkor szoftveres titkosítást alkalmaznak.  

   - **Biometrikus hitelesítés engedélyezése**. Lehetővé teszi a biometrikus hitelesítést, például az arcfelismerést vagy az ujjlenyomat használatát a PIN-kód alternatívájaként a Vállalati Windows Hello szolgáltatásban. A felhasználóknak ekkor is be kell állítaniuk egy PIN-kódot arra az esetre, ha a biometrikus hitelesítés nem sikerül. A következő lehetőségek közül választhat:

     - **Engedélyezés**. A Vállalati Windows Hello lehetővé teszi a biometrikus hitelesítést.
     - **Nincs konfigurálva** (alapértelmezett). A Vállalati Windows Hello meggátolja a biometrikus hitelesítést (minden fióktípus esetében).

   - **Kibővített hamisításszűrés használata, ha elérhető**. Konfigurálható, hogy a Windows Hello hamisításszűrési funkcióit használják-e az azt támogató eszközök (például egy valós arc helyett egy arcról készült fénykép észlelése).
       - **Engedélyezés**. A Windows minden felhasználótól megköveteli a kibővített hamisításszűrés alkalmazását arcfelismerés esetén, ha az támogatott.  
       - **Nincs konfigurálva** (alapértelmezett). A Windows figyelembe veszi a hamisításszűrési konfigurációkat az eszközön.

   - **Tanúsítvány helyi erőforrásokhoz**. 
       - **Engedélyezés**. Engedélyezi a Vállalati Windows Hello számára, hogy tanúsítványokkal végezzen hitelesítést a helyszíni erőforrásokban.
       - **Nincs konfigurálva** (alapértelmezett). Megakadályozz, hogy a Vállalati Windows Hello tanúsítványokkal végezzen hitelesítést a helyszíni erőforrásokban.  
9. Kattintson az **OK** gombra a profil mentéséhez.  

A profil létrejött, és megjelenik az **Eszközkonfiguráció – profilok** listában. Az eszközprofil csoportokhoz való hozzárendeléséhez az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
