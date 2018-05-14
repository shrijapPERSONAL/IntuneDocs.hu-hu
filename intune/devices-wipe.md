---
title: Vállalati adatok eltávolítása az eszközökről a Microsoft Intene használatával – Azure | Microsoft Docs
description: Eltávolíthatja a vállalati adatokat az eszközről, vagy visszaállíthatja a gyári beállításokat Android, Android for Work, iOS, macOS vagy Windows rendszerű eszközön a Windows Intune-nal. Törölheti is az eszközt az Azure Active Directoryból.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f7d3e768e740866d69d675a962dfca6d98c85568
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Eszközök eltávolítása a gyári beállítások visszaállításával vagy a céges adatok eltávolításával

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Eltávolíthatja az eszközt az Intune-ból, ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. Ez a **Céges adatok eltávolítása** vagy a **Gyári beállítások visszaállítása** parancsok kiadásával tehető meg. A saját tulajdonban lévő, Intune-ban regisztrált eszközeikre a felhasználók is kiadhatnak egy távoli parancsot az Intune céges portálon keresztül.

> [!NOTE]
> Mielőtt eltávolítana egy felhasználót az Azure Active Directoryból (Azure AD), adjon ki egy **Gyári beállítások visszaállítása** vagy egy **Céges adatok eltávolítása** parancsot az adott felhasználóhoz rendelt összes eszközre. Ha felügyelt eszközzel rendelkező felhasználókat távolít el az Azure AD-ból, akkor az Intune már nem fogja tudni visszaállítani ezeken az eszközökön a gyári beállításokat vagy eltávolítani a céges adatokat.

## <a name="factory-reset"></a>Gyári beállítások visszaállítása

A **Gyári beállítások visszaállítása** művelet visszaállítja az eszközön az alapértelmezett gyári beállításokat. A gyári beállítások visszaállítása eltávolítja az összes vállalati és felhasználói adatot, illetve beállítást. Az eszközt a rendszer eltávolítja az Intune-ból. A gyári beállítások visszaállítását akkor érdemes használni, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták. A **Gyári beállítások visszaállítása** funkciót óvatosan használja. Az eszközön tárolt adatok a művelet után nem állíthatók vissza.

### <a name="factory-reset-a-device"></a>Az eszköz gyári beállításainak visszaállítása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget.
4. Válassza ki az eszköz nevét, amelyen vissza szeretné állítani a gyári beállításokat.
5. Az eszköz nevét megjelenítő ablaktáblán válassza a **Gyári beállítások visszaállítása** lehetőséget.
6. A Windows 10 1709-es vagy újabb verziója esetén rendelkezésre áll a **Regisztrációs állapot és felhasználói fiók megtartása** lehetőség is. 
    
    |Megőrződik a gyári beállítások visszaállításakor|Nem őrződik meg|
    | -------------|------------|
    |Az eszközhöz társított felhasználói fiókok|Felhasználói fájlok|
    |A gép állapota \(tartományhoz való csatlakozás, Azure AD-csatlakoztatás)| A felhasználók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)|
    |Mobileszköz-felügyeleti (MDM-) regisztráció|Nem alapértelmezett eszközbeállítások|
    |Az eredeti berendezésgyártók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)||
    |Felhasználói profil||
    |A felhasználói profilon kívüli felhasználói adatok||
    |Felhasználói automatikus bejelentkezés|| 
    
         
7. A gyári beállítások visszaállításának megerősítéséhez válassza az **Igen** lehetőséget.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a **Gyári beállítások visszaállítása** műveletnek az összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

## <a name="remove-company-data"></a>Céges adatok eltávolítása

A **Céges adatok eltávolítása** művelet eltávolítja a felügyelt alkalmazásadatokat (ha vannak ilyenek), a beállításokat és az eszközhöz az Intune használatával hozzárendelt e-mail-profilokat. Az eszközt a rendszer eltávolítja az Intune-ból. Ez akkor történik meg, amikor az eszköz legközelebb bejelentkezik és megkapja a távoli **Céges adatok eltávolítása** műveletet.

A **Céges adatok eltávolítása** a felhasználó személyes adatai az eszközön hagyja.  

Az alábbi táblázatok ismertetik, hogy milyen adatokat távolít el a rendszer, és hogy az eszközön maradó adatokra milyen hatással van a **Céges adatok eltávolítsa** művelet a céges adatok eltávolítása után.

### <a name="ios"></a>iOS

|Adattípus|iOS|
|-------------|-------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|Törlődnek az alkalmazások. Törlődnek a vállalati alkalmazásadatok.<br /><br />Törlődnek a mobilalkalmazás-felügyeletet használó Microsoft-alkalmazások adatai. Az alkalmazások nem törlődnek.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Kezelőügynök|Törlődik a felügyeleti profil.|
|E-mail|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|
|Outlook|Törlődnek az iOS rendszerhez készült Microsoft Outlook alkalmazás által fogadott e-mailek. Ennek előfeltétele, hogy az Outlook mobilalkalmazás kötelező alkalmazásként telepítve legyen az iOS-felhasználóknál.|
|Az Azure AD elhagyása|Törlődik az Azure AD rekord.|
|Névjegyek |Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

### <a name="android"></a>Android

|Adattípus|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webhivatkozások|Eltávolítva.|Eltávolítva.|
|Nem felügyelt Google Play-alkalmazások|A telepített alkalmazások és azok adatai megmaradnak.|A telepített alkalmazások és azok adatai megmaradnak.|
|Nem felügyelt üzletági alkalmazások|A telepített alkalmazások és azok adatai megmaradnak.|Az alkalmazások el lesznek távolítva, és az alkalmazás helyi adatai is törlődnek. Az alkalmazáson kívüli adatok (például amelyek az SD-kártyán vannak) nem fognak törlődni.|
|Felügyelt Google Play-alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívüli (például az SD-kártyán lévő), Mobile Application Management- (MAM)-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, de a rendszer nem távolítja el azokat.|
|Felügyelt üzletági alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, és használhatatlanok lesznek, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazások nem törlődnek. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva maradnak, és használhatatlanok lesznek, de a rendszer nem távolítja el azokat.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok visszavonódnak, de nem törlődnek.|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Kezelőügynök|Visszavonódik az eszköz-rendszergazdai jogosultság.|Visszavonódik az eszköz-rendszergazdai jogosultság.|
|E-mail|Nem alkalmazható (az androidos eszközök nem támogatják az e-mail-profilokat)|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|
|Outlook|Az androidos Outlook alkalmazás által fogadott e-mailek törlődnek, de csak abban az esetben, ha az Outlook MAM-szabályzatokkal védett. Ellenkező esetben az Outlook nem törlődik az eszköz regisztrációjának megszüntetésekor.|Az androidos Outlook alkalmazás által fogadott e-mailek törlődnek, de csak abban az esetben, ha az Outlook MAM-szabályzatokkal védett. Ellenkező esetben az Outlook nem törlődik az eszköz regisztrációjának megszüntetésekor.|
|Az Azure AD elhagyása|Törlődik az Azure AD rekord.|Törlődik az Azure AD rekord.|
|Névjegyek |Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.|Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

### <a name="android-for-work"></a>Android for Work

Az Android for Work-eszközökről a céges adatok eltávolítása a munkahelyi profilban lévő összes adatot, alkalmazást és beállítást eltávolítja. Az eszköz kikerült az Intune felügyeletéből. Az Android for Work esetében a gyári beállítások visszaállítása nem támogatott.


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
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|Az EFS által védett fájloknál a kulcsok visszavonódnak. A felhasználó nem tudja megnyitni a fájlokat.|A vállalati alkalmazásokat a rendszer nem távolítja el.|Törlődnek az eredetileg a Céges portálon keresztül telepített alkalmazások. Törlődnek a vállalati alkalmazásadatok.|Törlődnek az alkalmazások. A közvetlen telepítési kulcsokat a rendszer eltávolítja.<br>A Windows 10 1703-as (alkotói frissítés) és újabb verzióinál a rendszer az Office 365 ProPlus alkalmazásokat nem távolítja el.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik. A felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|Nem támogatott.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|A tanúsítványok törlődnek és visszavonásra kerülnek.|Nem támogatott.|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|E-mail|Eltávolítja az EFS-kompatibilis e-maileket. Ez magában foglalja a Windows Posta alkalmazásában található e-maileket és mellékleteket.|Nem támogatott.|Törlődnek az Intune-on keresztül telepített e-mail-profilok. Törlődnek az eszközön gyorsítótárazott e-mailek.|Eltávolítja az EFS-kompatibilis e-maileket. Ez magában foglalja a Windows Posta alkalmazásában található e-maileket és mellékleteket. A rendszer eltávolítja az Intune által telepített e-mail-fiókokat.|
|Az Azure AD elhagyása|Nem.|Nem.|Törlődik az Azure AD rekord.|Nem alkalmazható. A Windows 10-ben nem lehet eltávolítani a vállalati adatokat az Azure AD-hez csatlakoztatott eszközökről.|

### <a name="remove-company-data"></a>Céges adatok eltávolítása

1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
3. Válassza ki az eszköz nevét, amelyről szeretné eltávolítani a céges adatokat.
4. Az eszköz nevét megjelenítő ablaktáblán válassza a **Céges adatok eltávolítása** lehetőséget. Válassza az **Igen** lehetőséget a megerősítéshez.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a **Céges adatok eltávolítása** műveletnek az összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

## <a name="delete-devices-from-the-intune-portal"></a>Eszközök törlése az Intune-portálról

Ha el szeretne távolítani eszközöket az Intune-portálról, ezt megteheti az adott eszközpanelen. Az eszköz következő bejelentkezésekor minden céges adat el lesz távolítva.

1. Jelentkezzen be az [Intune-ba az Azure Portalon](https://aka.ms/intuneportal).
2. Válassza az **Eszközök** > **Minden eszköz** > a törölni kívánt eszközök > **Törlés** lehetőséget.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Eszközök törlése az Azure Active Directory portálról

Előfordulhat, hogy eszközöket kell törölnie az Azure AD-ből kommunikációs problémák vagy hiányzó eszközök miatt. A **Törlés** művelettel eltávolíthatók az Azure Portalról az olyan eszköz rekordjai, amelyekről tudja, hogy nem érhetők el, és nem valószínű, hogy újra kommunikálni fognak az Azure-ral. A **Törlés** művelet nem távolítja el az eszközt a felügyelet alól.

1.  Jelentkezzen be az [Azure Active Directoryba az Azure Portalon](http://aka.ms/accessaad) a rendszergazdai hitelesítő adataival. Az [Office 365-portálra](https://portal.office.com) is bejelentkezhet. Válassza a menüben a **Felügyeleti központok** > **Azure AD** menüpontot.
2.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (válassza a **Register your free Azure Active Directory** előfizetési hivatkozást).
3.  Válassza az **Azure Active Directory** lehetőséget, majd válassza ki a vállalatot.
4.  Válassza a **Felhasználók** fület.
5. Válassza ki azt a felhasználót, aki a törölni kívánt eszközhöz van társítva.
6.  Válassza az **Eszközök** lehetőséget.
7.  Szükség szerint távolítsa el az eszközöket. Eltávolíthat például olyan eszközöket, amelyeket már nem használnak vagy pontatlan definíciókkal rendelkeznek.
