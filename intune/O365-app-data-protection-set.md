---
title: Office 365-alkalmazások adatkezelése a Microsoft Intune-ban
titlesuffix: ''
description: Tudnivalók az adatok kezelése és védelme Office 365-alkalmazások Microsoft Intune-ban.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c1cf9c7b13f196b8cc962d9d01e6c495cd9f5a5d
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238812"
---
# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps-in-microsoft-intune"></a>Hogyan fogják megtapasztalni a felhasználók az alapszintű védelmet a Microsoft Intune-beli felügyelt Office 365-alkalmazásokban

Az **Office 365-alkalmazások kezelése** varázsló minden eszközplatform esetében létrehoz egy alkalmazásvédelmi szabályzatot.

A varázsló engedélyezi a következő szabályzatokat:

**iOS**
* Alkalmazásadatok titkosítása

**Android**
* Alkalmazásadatok titkosítása
* Egyszerű PIN-kód szükséges a hozzáféréshez

Ezek a szabályzatok biztosítják az Office 365-alkalmazások kezelését, szükség esetén lehetővé téve a munkahelyi adatok törlését az Office-alkalmazásokból. Emellett alapvető védelmet is nyújtanak az eszköz elvesztése vagy ellopása esetén, biztosítva a munkahelyi adatok titkosítását, és azt, hogy az Office 365-alkalmazásokban PIN-kódot kell megadni az adatok megjelenítéséhez.


Ebben a cikkben a OneDrive Vállalati verzióval mutatjuk be a felhasználói élményt az Intune által kezelt alkalmazásokban.


>[!NOTE]
>Személyes eszköz esetén általában a végfelhasználó tölti le az alkalmazást. Ha az eszköz mobileszköz-kezelési megoldással (MDM) felügyelt, az alkalmazást Ön telepítheti az eszközön.

## <a name="user-experience-on-an-ios-device"></a>Az iOS-eszközök felhasználói felülete

1. A OneDrive Vállalati verzió alkalmazást elindítva nyissa meg a bejelentkezési lapot.  
2. Írja be a munkahelyi fiókja felhasználónevét. Ekkor megnyílik az Office 365 hitelesítési lapja, ahol megadhatja a munkahelyi hitelesítő adatait. 
3. Miután az Azure Active Directoryban sikeresen megtörtént az adatok hitelesítése, érvénybe lépnek az alkalmazásvédelmi szabályzatok, és a rendszer arra kéri, hogy indítsa újra a OneDrive Vállalati verziót. 

   > [!NOTE]
   > Az Újraindítás szükséges üzenet csak az Intune-ban nem regisztrált eszközökön jelenik meg.

4. Indítsa újra a OneDrive Vállalati verziót. Az alkalmazás engedélyezett alkalmazásvédelmi szabályzatokkal indul el, és az eszköz PIN-kód megadását kéri (ha nincs még konfigurálva az eszköz PIN-kódja).  

   > [!NOTE]
   > A felhasználók többsége számára nem jelenik meg ez a kérdés. Ezt a kérdést csak azok a felhasználóknak fog megjelenni, akik még nem engedélyezték az iOS-eszközön a PIN-kódot.

5. Miután beállította és megerősítette a PIN-kódot, térjen vissza a OneDrive Vállalati verzió alkalmazáshoz. Ekkor egyszeri értesítés tájékoztatja a felhasználót arról, hogy a rendszergazda már védi a munkahelyi adatokat a OneDrive-on. 
6. A OneDrive Vállalati verzióban tárolt fájljainak eléréséhez kattintással lépjen tovább az értesítésről. 

>[!NOTE]
>A telepített szabályzatok módosításai az alkalmazás következő indításakor lépnek érvénybe.

## <a name="user-experience-on-an-android-device"></a>Az androidos eszközök felhasználói felülete

1. A OneDrive Vállalati verzió alkalmazást elindítva nyissa meg a bejelentkezési lapot.  <br/> ![A OneDrive alkalmazás üdvözlőképernyőjének képe](./media/onedrive-android-welcome.png)
2. Írja be a munkahelyi fiókja felhasználónevét. Ekkor megnyílik az Office 365 hitelesítési lapja, ahol megadhatja a munkahelyi hitelesítő adatait. <br/> ![O365-bejelentkezési lap képe Androidon](./media/o365-sign-in-android.png)
3. Miután az Azure Active Directoryban sikeresen megtörtént az adatok hitelesítése, megjelenik egy üzenet, amely tartalmazza a Céges portál alkalmazás telepítésére vonatkozó utasításokat, ha az még nincs telepítve az eszközön. Koppintson a **Ugrás az Áruházba** elemre a folytatáshoz. <br/> ![A Céges portál alkalmazás beszerzésére kérő üzenet képe](./media/get-company-portal-android.png) <br/>Ha a Céges portál alkalmazás már telepítve van a telefonján, a OneDrive Vállalati verzió alkalmazás automatikusan elindul, és a befejező megjegyzésre ugorhat.   

   > [!IMPORTANT]
   > Androidon, miután beállította az Office-alkalmazások alkalmazásvédelmi szabályzat általi kezelését, az eszköz felhasználójának telepítenie **kell** a Céges portál alkalmazást annak ellenére, hogy a végfelhasználónak nem kell megnyitnia azt, és nem kell bejelentkeznie az alkalmazásba az e-mailek vagy dokumentumok elolvasásához.

4. Ekkor megnyílik a Google Play áruház, ahonnan letöltheti és telepítheti a Céges portál alkalmazást. Az alkalmazás segít az adatok védelmében és biztonságuk megőrzésében. <br/> ![Az alkalmazás képe a Google Play áruházban](./media/google-play-get-app-android.png)
5. Az alkalmazás telepítésének befejezése után az **Elfogadás** gombra kattintva fogadja el a használati feltételeket. A OneDrive Vállalati verzió ekkor automatikusan elindul.


>[!NOTE]
>A OneDrive következő megnyitásakor előfordulhat, hogy a program a PIN-kód beállítására kéri, ha ezt az informatikai részleg megköveteli. Miután beállította és megerősítette a PIN-kódot, visszatérhet a OneDrive Vállalati verzióhoz.

![A beállította és megerősítette a PIN-kód kérésének képe](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a>Milyen szabályzatokat nem állít be a varázsló?

**Név**: Office 365-alkalmazások kezelése<br>
**Description** (Leírás): Az Office 365-alkalmazások kezelése varázsló által létrehozott

| Beállítás neve | iOS-szabályzat értéke | Android-szabályzat értéke |
|------------------------------------------------------------------------|-----------------------|----------------------|
| ITunes- és iCloud-biztonsági mentések tiltása | Nem | – |
| Az androidos biztonsági mentések tiltása | – | Nem |
| Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak | Minden alkalmazás | Minden alkalmazás |
| Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak | Minden alkalmazás | Minden alkalmazás |
| A „Mentés másként” művelet letiltása | Nem | Nem |
| Más alkalmazásokkal végzett kivágás, másolás és beillesztés korlátozása | Bármely alkalmazás | Bármely alkalmazás |
| A vállalat által kezelt böngészőben megjelenő webtartalom korlátozása | Nem | Nem |
| Alkalmazásadatok titkosítása | Amikor az eszköz zárolva van | Igen |
| Névjegy-szinkronizálás letiltása | Nem | Nem |
| Nyomtatás letiltása | Nem | Nem |
| PIN-kód megkövetelése a hozzáféréshez | Nem | Igen |
| Kísérletek száma a PIN-kód alaphelyzetbe állítása előtt | – | 5 |
| Egyszerű PIN-kód engedélyezése | – | Igen |
| PIN-kód hossza | – | 4 |
| Ujjlenyomat használatának engedélyezése PIN-kód helyett | – | Igen |
| Vállalati hitelesítő adatok szükségesek a hozzáféréshez | Nem | Nem |
| A felügyelt alkalmazások futtatásának tiltása jailbreakelt vagy rootolt eszközökön | Nem | Nem |
| A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc) – Időkorlát | 30 | 30 |
| A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc) – Offline türelmi időszak | 720 | 720 |
| Offline időtartam (nap) az alkalmazásadatok törlése előtt | 90 | 90 |
| Képernyőrögzítés letiltása (csak Android-eszközök esetén) | – | Nem |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a>Miért van az alkalmazás PIN-szabályzata csak az Android-eszközökhöz konfigurálva?
A titkosítás eltérően működik az iOS és az Android rendszeren.

iOS rendszeren az Intune valamely alkalmazásvédelmi szabályzatához társított alkalmazások esetében az adatok titkosítása az operációs rendszer által biztosított eszközszintű titkosítással történik. Igen, az alkalmazás-titkosítási szabályzat engedélyezésekor a program automatikusan megköveteli az eszköz PIN-kódjának megadását ahhoz, hogy a felhasználó hozzáférhessen a munkahelyi adatokhoz. Az eszközön már konfigurált PIN-kóddal nem rendelkező eszközzel nem rendelkező felhasználóktól a program kéri, hogy hozzák létre az eszköz PIN-kódját.

Android rendszeren az Intune-os alkalmazásvédelmi szabályzattal társított alkalmazások esetében a program szinkron módon titkosítja az adatokat a fájlok írási és olvasási műveletei során. Az eszköz tárhelyén található tartalom mindig titkosított marad. Nem MDM által felügyelt eszközökön az alkalmazásvédelmi szabályzat nem kényszerítheti ki az eszköz PIN-kódjának megkövetelését. A varázsló engedélyezi az alkalmazás PIN-szabályzatát, hogy felhasználók számára valamilyen PIN-kód legyen szükséges a munkahelyi adatokhoz való hozzáféréshez.

Minden esetben szerkesztheti ezen szabályzat-beállításokat a munkahelye követelményeinek megfelelően.

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a>Hogyan lehet megtekinteni és szerkeszteni a varázsló által létrehozott szabályzatokat?
Ezen szabályzatok, vagy az Azure-beli Intune-portálon létrehozott bármely szabályzat megtekintéséhez vagy frissítéséhez az irányítópulton válassza az **Alkalmazások kezelése** > **Alkalmazásvédelmi szabályzatok** lehetőséget. Ekkor jobb oldalt megnyílik a szabályzatok listája. Válassza ki azt a szabályzatot, amelyet meg szeretne tekinteni, és szerkessze a beállításokat. <br/>
![Felhasználói felület elérési útja szabályzatok megtekintéséhez – kép](./media/image-for-faq.png)

## <a name="next-steps"></a>További lépések
- További információk az [alkalmazásvédelmi szabályzatokról](app-protection-policy.md).
