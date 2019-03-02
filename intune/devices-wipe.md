---
title: Eszközök kivonása vagy összes adatuk törlése a Microsoft Intune használatával – Azure | Microsoft Docs
description: A Windows Intune-nal kivonhat Android rendszerű, androidos munkahelyi profilt használó, iOS, macOS vagy Windows rendszerű eszközöket, vagy törölheti azok összes adatát. Törölheti is az eszközt az Azure Active Directoryból.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bf4d63ed680b589dd6743daa491c5eaddb74352e
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230992"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Eszközök eltávolítása összes adatuk törlésével, az eszköz kivonásával vagy regisztrációja manuális törlésével

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A **Kivonás** vagy az **Összes adat törlése** művelettel eltávolíthatja az eszközt az Intune-ból, ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. A saját tulajdonban lévő, Intune-ban regisztrált eszközeikre a felhasználók is kiadhatnak egy távoli parancsot az Intune céges portálon keresztül.

> [!NOTE]
> Mielőtt eltávolítana egy felhasználót az Azure Active Directoryból (Azure AD), adjon ki egy **Kivonás** vagy egy **Összes adat törlése** parancsot az adott felhasználóhoz rendelt összes eszközre. Ha felügyelt eszközzel rendelkező felhasználókat távolít el az Azure AD-ból, akkor az Intune már nem fogja tudni törölni ezeknek az eszközöknek az összes adatát, vagy kivonni az eszközöket.

## <a name="wipe"></a>Törlés

Az **Összes adat törlése** művelet visszaállítja az eszközön az alapértelmezett gyári beállításokat. A felhasználói adatok attól függően maradnak meg, hogy bejelölte-e a **Regisztrációs állapot és felhasználói fiók megtartása** jelölőnégyzetet. Ellenkező esetben megtörténik a meghajtó biztonságos törölése.

|Az Összes adat törlése művelet|**Regisztrációs állapot és felhasználói fiók megtartása**|Eltávolítva az Intune kezelése alól|Leírás|
|:-------------:|:------------:|:------------:|------------|
|**Törlés**| Nincs bejelölve | Igen | Törli az összes felhasználói fiókot, adatot, MDM-szabályzatot és beállítást. Visszaállítja az operációs rendszert az alapértelmezett állapotra és beállításokra.|
|**Törlés**| Bejelölve | Nem | Törli az összes MDM-szabályzatot. Megtartja a felhasználói fiókokat és az adatokat. Visszaállítja a felhasználói beállításokat az alapértelmezett értékre. Visszaállítja az operációs rendszert az alapértelmezett állapotra és beállításokra.|

A **Regisztrációs állapot és felhasználói fiók megtartása** lehetőség csak a Windows 10 1709-es vagy újabb verziók esetében érhető el.

A rendszer újra alkalmazza az MDM-szabályzatokat az eszköz következő Intune-csatlakozásakor.

Az összes adat törlését akkor érdemes használni, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták. Az **Összes adat törlése** műveletet körültekintően használja. Az eszközön tárolt adatok a művelet után nem állíthatók vissza.

### <a name="wiping-a-device"></a>Eszköz összes adatának törlése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget.
4. Válassza ki az eszköz nevét, amelyen az összes adatot törölni szeretné.
5. Az eszköz nevét megjelenítő panelen válassza az **Összes adat törlése** lehetőséget.
6. A Windows 10 1709-es vagy újabb verziója esetén rendelkezésre áll a **Regisztrációs állapot és felhasználói fiók megtartása** lehetőség is. 
    
    |Meg lesz őrizve az összes adat törlése során |Nem őrződik meg|
    | -------------|------------|
    |Az eszközhöz társított felhasználói fiókok|Felhasználói fájlok|
    |A gép állapota \(tartományhoz való csatlakozás, Azure AD-csatlakoztatás)| A felhasználók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)|
    |Mobileszköz-felügyeleti (MDM-) regisztráció|Nem alapértelmezett eszközbeállítások|
    |Az eredeti berendezésgyártók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)||
    |Felhasználói profil||
    |A felhasználói profilon kívüli felhasználói adatok||
    |Felhasználói automatikus bejelentkezés|| 
    
         
7. Az összes adat törlésének megerősítéséhez válassza az **Igen** lehetőséget.

Ha az eszköz be van kapcsolva és csatlakoztatva van, az **Összes adat törlése** műveletnek az összes eszköztípusra való propagálása kevesebb mint 15 percet vesz igénybe.

## <a name="retire"></a>Kivonás

A **Kivonás** művelet eltávolítja a felügyelt alkalmazásadatokat (ha vannak ilyenek), a beállításokat és az eszközhöz az Intune használatával hozzárendelt e-mail-profilokat. Az eszközt a rendszer eltávolítja az Intune-ból. Ez akkor történik meg, amikor az eszköz legközelebb bejelentkezik és megkapja a távoli **Kivonás** műveletet.

A **Kivonás** meghagyja az eszközön a felhasználó személyes adatait.  

Az alábbi táblázatok ismertetik, hogy milyen adatokat távolít el a rendszer, és hogy az eszközön maradó adatokra milyen hatással van a **Kivonás** művelet a céges adatok eltávolítása után.

### <a name="ios"></a>iOS

|Adattípus|iOS|
|-------------|-------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|**Vállalati portálon keresztül telepített alkalmazások:** A felügyeleti profil rögzített alkalmazások esetében minden alkalmazásadat és az alkalmazások törlődnek. Az alkalmazások tartalmazzák az App Store telepített és később felügyelt vállalati alkalmazások alkalmazások. <br /><br /> **Microsoft-alkalmazások mobilalkalmazás-felügyeletet használó, és megtörtént-e az App Store:** A céges portál által nem kezelt alkalmazások esetében az alkalmazás helyi Storage mobilalkalmazás-felügyeleti (MAM)-titkosítás által védett vállalati alkalmazásadatok törlődnek. Az alkalmazáson kívüli MAM titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de nem törlődnek. Személyes adatokat, és az alkalmazások nem lesznek eltávolítva.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Kezelőügynök|Törlődik a felügyeleti profil.|
|E-mail|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|
|Az Azure AD elhagyása|Törlődik az Azure AD rekord.|

### <a name="android"></a>Android

|Adattípus|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webhivatkozások|Eltávolítva.|Eltávolítva.|
|Nem felügyelt Google Play-alkalmazások|A telepített alkalmazások és azok adatai megmaradnak. <br /> <br />Az alkalmazás helyi Storage mobilalkalmazás-felügyeleti (MAM)-titkosítás által védett vállalati alkalmazásadatok törlődnek. Az alkalmazáson kívüli MAM titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de nem törlődnek. |A telepített alkalmazások és azok adatai megmaradnak. <br /> <br />Az alkalmazás helyi Storage mobilalkalmazás-felügyeleti (MAM)-titkosítás által védett vállalati alkalmazásadatok törlődnek. Az alkalmazáson kívüli MAM titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de nem törlődnek.|
|Nem felügyelt üzletági alkalmazások|A telepített alkalmazások és azok adatai megmaradnak.|Az alkalmazások el lesznek távolítva, és az alkalmazás helyi adatai is törlődnek. Az alkalmazáson kívüli adatok (például amelyek az SD-kártyán vannak) nem fognak törlődni.|
|Felügyelt Google Play-alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívüli (például az SD-kártyán lévő), Mobile Application Management- (MAM)-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, de a rendszer nem távolítja el azokat.|
|Felügyelt üzletági alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, és használhatatlanok lesznek, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, és használhatatlanok lesznek, de a rendszer nem távolítja el azokat.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok visszavonódnak, de nem törlődnek.|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Kezelőügynök|Visszavonódik az eszköz-rendszergazdai jogosultság.|Visszavonódik az eszköz-rendszergazdai jogosultság.|
|E-mail|Nem alkalmazható (az androidos eszközök nem támogatják az e-mail-profilokat)|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|
|Az Azure AD elhagyása|Törlődik az Azure AD rekord.|Törlődik az Azure AD rekord.|

### <a name="android-work-profile"></a>Androidos munkahelyi profil

Az androidos munkahelyi profillal rendelkező eszközökről a céges adatok eltávolítása a munkahelyi profilban lévő összes adatot, alkalmazást és beállítást eltávolítja. Az eszköz kikerült az Intune felügyeletéből. Az androidos munkahelyi profilok esetében a kivonás nem támogatott.

### <a name="android-enterprise-kiosk-devices"></a>Vállalati androidos kioszkeszközök

Az összes adat törlése csak kioszkeszközökön lehetséges. Androidos kioszkeszközöket nem lehet kivonni.


### <a name="macos"></a>macOS

|Adattípus|macOS|
|-------------|-------|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|
|Tanúsítvány profilbeállításai|A rendszer az MDM-mel telepített tanúsítványokat eltávolítja és visszavonja.|
|Kezelőügynök|Törlődik a felügyeleti profil.|
|Outlook|Ha a feltételes hozzáférés engedélyezve van, az eszközre nem fog új e-mail érkezni.|
|Az Azure AD elhagyása|Törlődik az Azure AD rekord.|

### <a name="windows"></a>Windows

|Adattípus|Windows 8.1 (MDM) és Windows RT 8.1|Windows RT|Windows Phone 8.1 és Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|Az EFS által védett fájloknál a kulcsok visszavonódnak. A felhasználó nem tudja megnyitni a fájlokat.|A vállalati alkalmazásokat a rendszer nem távolítja el.|Törlődnek az eredetileg a Céges portálon keresztül telepített alkalmazások. Törlődnek a vállalati alkalmazásadatok.|Törlődnek az alkalmazások. A közvetlen telepítési kulcsokat a rendszer eltávolítja.<br>A Windows 10 1703-as (alkotói frissítés) és újabb verzióinál a rendszer az Office 365 ProPlus alkalmazásokat nem távolítja el. Az Intune felügyeleti bővítmény Win32-alkalmazások nem lesz eltávolítva a nem regisztrált eszközökön telepítve van.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|Nem támogatott.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|A tanúsítványok törlődnek és visszavonásra kerülnek.|Nem támogatott.|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|E-mail|Eltávolítja az EFS-kompatibilis e-maileket. Ez magában foglalja a Windows Posta alkalmazásában található e-maileket és mellékleteket.|Nem támogatott.|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|Eltávolítja az EFS-kompatibilis e-maileket. Ez magában foglalja a Windows Posta alkalmazásában található e-maileket és mellékleteket. A rendszer eltávolítja az Intune által telepített e-mail-fiókokat.|
|Az Azure AD elhagyása|Nem.|Nem.|Törlődik az Azure AD rekord.|Nem alkalmazható. A Windows 10-ben nem lehet kivonni az Azure AD-hez csatlakoztatott eszközöket.|

### <a name="retire"></a>Kivonás

1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
3. Válassza ki a kivonni kívánt eszköz nevét.
4. Az eszköz nevét megjelenítő panelen válassza a **Kivonás** lehetőséget. Válassza az **Igen** lehetőséget a megerősítéshez.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a **Kivonás** műveletnek az összes eszköztípusra való propagálása kevesebb mint 15 percet vesz igénybe.

## <a name="delete-devices-from-the-intune-portal"></a>Eszközök törlése az Intune-portálról

Ha el szeretne távolítani eszközöket az Intune-portálról, ezt megteheti az adott eszközpanelen. Az eszköz következő bejelentkezésekor minden céges adat el lesz távolítva.

1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Válassza az **Eszközök** > **Minden eszköz** > a törölni kívánt eszközök > **Törlés** lehetőséget.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Eszközök automatikus törlése törlési szabályok alkalmazásával
Az Intune konfigurálható úgy, hogy automatikusan törölje az inaktívnak, elavultnak vagy nem válaszolónak látszó eszközöket. Ezek a törlési szabályok folyamatosan figyelik az eszközleltárt, hogy az eszközrekordok naprakészek maradjanak. Az így törölt eszközök törlődnek az Intune-felügyeletből.
1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Válassza az **Eszközök** > **Eszköztörlési szabályok** > **Igen** lehetőséget.
3. Az **Azon eszközök törlése, amelyek a megadott számú napig nem jelentkeztek be** mezőben adjon meg egy 90 és 270 közötti értéket.
4. Válassza a **Mentés** elemet.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Eszközök törlése az Azure Active Directory portálról

Előfordulhat, hogy eszközöket kell törölnie az Azure AD-ből kommunikációs problémák vagy hiányzó eszközök miatt. A **Törlés** művelettel eltávolíthatók az Azure Portalról az olyan eszköz rekordjai, amelyekről tudja, hogy nem érhetők el, és nem valószínű, hogy újra kommunikálni fognak az Azure-ral. A **Törlés** művelet nem távolítja el az eszközt a felügyelet alól.

1.  Jelentkezzen be az [Azure Active Directoryba az Azure Portalon](http://aka.ms/accessaad) a rendszergazdai hitelesítő adataival. Az [Office 365-portálra](https://portal.office.com) is bejelentkezhet. Válassza a menüben a **Felügyeleti központok** > **Azure AD** menüpontot.
2.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (válassza a **Register your free Azure Active Directory** előfizetési hivatkozást).
3.  Válassza az **Azure Active Directory** lehetőséget, majd válassza ki a vállalatot.
4.  Válassza a **Felhasználók** fület.
5. Válassza ki azt a felhasználót, aki a törölni kívánt eszközhöz van társítva.
6.  Válassza az **Eszközök** lehetőséget.
7.  Szükség szerint távolítsa el az eszközöket. Eltávolíthat például olyan eszközöket, amelyeket már nem használnak vagy pontatlan definíciókkal rendelkeznek.

## <a name="retire-an-apple-dep-device-from-intune"></a>Apple DEP-eszközök kivonása az Intune-ból

Ha szeretne teljesen kivonni egy Apple DEP-eszközt az Intune általi felügyeletből, kövesse az alábbi lépéseket:

1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Válassza az **Eszközök** > **Minden eszköz** > a törölni kívánt eszköz > **Kivonás** lehetőséget.
![Kivonás képernyőképe](./media/devices-wipe/retire.png)
3. Válassza az **Eszközök regisztrálása** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > token kiválasztása > **Eszközök** > jelölőnégyzet bejelölése az eszközhöz > **Törlés** > **Igen** lehetőséget.
![Képernyőkép az eszköz törléséről](./media/devices-wipe/delete-device.png)
4. Látogasson el a [deploy.apple.com](http://deploy.apple.com) webhelyre, és keressen rá az eszközre a sorozatszáma alapján.
5. A **Hozzárendelve** menüben válassza a **Nincs hozzárendelés** elemet.

6. Válassza az **Újbóli hozzárendelés** lehetőséget.

    ![Képernyőkép az újbóli hozzárendelésről az Apple esetében](./media/devices-wipe/apple-reassign.png)

## <a name="fresh-start"></a>Újrakezdés

A Windows 10-eszközökre alkalmazható. Tudjon meg többet [újrakezdés](https://docs.microsoft.com/intune/device-fresh-start).

## <a name="next-steps"></a>További lépések

Ha szeretne egy törölt eszközt újból regisztrálni, olvassa el a [Regisztrációs lehetőségek](enrollment-options.md) szakaszt.

