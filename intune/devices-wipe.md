---
title: "A céges adatok eltávolítása és a gyári beállítások visszaállítása az Intune-ban felügyelt eszközökön"
titlesuffix: Azure portal
description: "Ez a cikk tájékoztatást nyújt egy eszközön található céges adatok eltávolításáról, valamit az eszköz gyári beállításainak visszaállításáról."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4ee4e9b4abb99e280bf2529f9f60d295096426c0
ms.sourcegitcommit: 4e0ed4087a1e596831fa215135824ca5d38e33f7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2017
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Eszközök eltávolítása a gyári beállítások visszaállításával vagy a céges adatok eltávolításával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Eltávolíthatja az eszközt az Intune-ból, ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. Ez a **céges adatok eltávolítása** vagy a **gyári beállítások visszaállítása** parancsok kiadásával tehető meg. A saját tulajdonban lévő, Intune-ban regisztrált eszközeikre a felhasználók is kiadhatnak egy távoli parancsot az Intune céges portálon keresztül.

> [!NOTE]
> Mielőtt eltávolítana egy felhasználót az Azure Active Directoryból, adjon ki egy **Gyári beállítások visszaállítása** vagy egy **Céges adatok eltávolítása** parancsot az adott felhasználóhoz rendelt összes eszközre. Ha egy felügyelt eszközzel rendelkező felhasználót távolít el az Azure Active Directoryból, akkor az Intune már nem fogja tudni visszaállítani az eszközén a gyári beállításokat vagy törölni a céges adatokat.

## <a name="factory-reset"></a>Gyári beállítások visszaállítása

A **Gyári beállítások visszaállítása** visszaállítja az eszközt a gyári beállításokra, és eltávolít minden vállalati és felhasználói adatot és beállítást. Az eszközt a rendszer eltávolítja az Intune-ból. A gyári beállítások visszaállítását akkor érdemes használni, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták. A gyári beállítások visszaállítását óvatosan használja. Az eszközön tárolt adatok a művelet után nem állíthatók vissza.

### <a name="to-factory-reset-a-device"></a>Az eszköz gyári beállításainak visszaállítása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
4. Válassza ki az eszköz nevét, amelyen vissza szeretné állítani a gyári beállításokat.
5. Az eszköz nevét tartalmazó panelen válassza a **Gyári beállítások visszaállítása** lehetőséget.
6. A Windows 10 rendszer 1709-es és újabb verzióihoz egy további lehetőség is rendelkezésre áll a regisztrációállapot és a felhasználói fiók megőrzéséhez. 
    
    |Megőrződik a gyári beállítások visszaállításakor|Nem őrződik meg|
    | -------------|------------|
    |Az eszközhöz társított felhasználói fiókok|Felhasználói fájlok|
    |A gép állapota \(tartományhoz való csatlakozás, Azure Active Directory-csatlakozás)| A felhasználók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)|
    |MDM-regisztráció|Nem alapértelmezett eszközbeállítások|
    |Az eredeti berendezésgyártók által telepített alkalmazások \(áruházbeli és Win32-alkalmazások)||
    |Felhasználói profil||
    |A felhasználói profilon kívüli felhasználói adatok||
    |Felhasználói automatikus bejelentkezés|| 
    
         
7. A gyári beállítások visszaállításának megerősítéséhez válassza az **Igen** lehetőséget.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a gyári beállítások visszaállításának az összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

## <a name="remove-company-data"></a>Céges adatok eltávolítása

A **céges adatok eltávolítása** a felügyelt alkalmazásadatokat (ha vannak ilyenek), a beállításokat és az eszközhöz az Intune használatával hozzárendelt e-mail-profilokat távolítja el. A céges adatok eltávolítása esetén a felhasználó személyes adatai az eszközön maradnak. Az eszközt a rendszer eltávolítja az Intune-ból. Az alábbi táblázatok ismertetik, hogy milyen adatokat távolít el a rendszer, és hogy az eszközön maradó adatokra milyen hatással van a céges adatok eltávolítsa.

### <a name="ios"></a>iOS

|Adattípus|iOS|
|-------------|-------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|Törlődnek az alkalmazások. Törlődnek a vállalati alkalmazásadatok.<br /><br />Törlődnek a mobilalkalmazás-felügyeletet használó Microsoft-alkalmazások adatai. Az alkalmazások nem törlődnek.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Felügyeleti ügynök|Törlődik a felügyeleti profil.|
|E-mail|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|
|Outlook|Törlődnek az iOS rendszerhez készült Microsoft Outlook alkalmazás által fogadott e-mailek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az Azure AD rekord.|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

### <a name="android"></a>Android

|Adattípus|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Webhivatkozások|Eltávolítva.|Eltávolítva.|
|Nem felügyelt Google Play-alkalmazások|A telepített alkalmazások és azok adatai megmaradnak.|A telepített alkalmazások és azok adatai megmaradnak.|
|Nem felügyelt üzletági alkalmazások|A telepített alkalmazások és azok adatai megmaradnak.|Az alkalmazások el lesznek távolítva, és emiatt az alkalmazás helyi adatai is törlődnek. Az alkalmazáson kívüli adatok (például amelyek az SD-kártyán vannak) nem fognak törlődni.|
|Felügyelt Google Play-alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívüli (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívül (például az SD-kártyán lévő), MAM titkosítás által védett adatok titkosítva maradnak, de a rendszer nem távolítja el azokat.|
|Felügyelt üzletági alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívüli (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívüli (például az SD-kártyán lévő), MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok visszavonódnak, de nem törlődnek.|A tanúsítványok törlődnek és visszavonódnak.|
|Felügyeleti ügynök|Visszavonódik az eszköz-rendszergazdai jogosultság.|Visszavonódik az eszköz-rendszergazdai jogosultság.|
|E-mail|Nem alkalmazható (az androidos eszközök nem támogatják az e-mail-profilokat)|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|
|Outlook|Törlődnek az androidos Microsoft Outlook alkalmazás által fogadott e-mailek.|Törlődnek az androidos Microsoft Outlook alkalmazás által fogadott e-mailek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az Azure AD rekord.|Törlődik az Azure AD rekord.|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.|Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem távolíthatók el. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

### <a name="android-for-work"></a>Android for Work

Az Android for Work-eszközökről a céges adatok eltávolítása a munkahelyi profilban lévő összes adatot, alkalmazást és beállítást eltávolítja. Az eszköz így kikerül az Intune felügyelete alól. Az Android for Work esetében a gyári beállítások visszaállítása nem támogatott.

### <a name="windows"></a>Windows

|Adattípus|Windows 8.1 (MDM) és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|A titkosított fájlrendszerrel (EFS) védett fájlok kulcsát a rendszer visszavonja, és a felhasználó nem fogja tudni megnyitni őket.|Nem törlődnek a vállalati alkalmazások.|Törlődnek az eredetileg a vállalati portálon keresztül telepített alkalmazások. Törlődnek a vállalati alkalmazásadatok.|Az alkalmazások és a közvetlen telepítési kulcsok el lesznek távolítva.<br>A Windows 10 1703-as (Creator Update) és újabb verziója esetén az Office 365 ProPlus-alkalmazások nem lesznek eltávolítva.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|Nem támogatott.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonódnak.|A tanúsítványok törlődnek és visszavonódnak.|Nem támogatott.|A tanúsítványok törlődnek és visszavonódnak.|
|E-mail|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket is.|Nem támogatott.|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket is. A rendszer eltávolítja az Intune által telepített e-mail-fiókokat.|
|Azure Active Directory (AAD) elhagyása|Nem.|Nem.|Törlődik az Azure AD rekord.|Nem alkalmazható. A Windows 10 nem támogatja a céges adatok eltávolítását az Azure Active Directoryhoz csatlakoztatott eszközökön.|

### <a name="to-remove-company-data"></a>A céges adatok eltávolítása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
4. Válassza ki az eszköz nevét, amelyről szeretné eltávolítani a céges adatokat.
5. Az eszköz nevét tartalmazó panelen válassza a **Céges adatok eltávolítása** lehetőséget, majd kattintson az **Igen** gombra az eltávolítás megerősítéséhez.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a céges adatok eltávolításának az összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Eszközök törlése az Azure Active Directory portálról

Kommunikációs problémák vagy elveszett eszközök miatt előfordulhat, hogy el kell távolítania egy eszközt az Azure Active Directoryból (AD-ból). A törlés parancs nem távolítja el az eszközt a felügyeletből, de a **Törlés** opcióval eltávolíthatók az Azure Portalról egy olyan eszköz rekordjai, amelyikről tudja, hogy nem érhető el, és nem valószínű, hogy újra kommunikálni fog az Azure-ral.

1.  Jelentkezzen be az [Azure Portalon az Azure Active Directoryba](http://aka.ms/accessaad) a rendszergazdai hitelesítő adataival. Bejelentkezhet az [Office 365 portálon](https://portal.office.com) is, majd válassza a **Rendszergazda** &gt; **Azure AD** elemet a lap bal oldalán található hivatkozást használva.
3.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (kattintson a **Register your free Azure Active Directory** előfizetési hivatkozásra).
4.  Válassza az **Active Directory** lehetőséget, és jelölje ki a szervezetét.
5.  Válassza a **Felhasználók** fület.
6.  Jelölje ki azokat a felhasználókat, akiknek az eszközeit törölni szeretné.
7.  Válassza az **Eszközök** lehetőséget.
8.  Szükség szerint távolítson el eszközöket, többek között azokat, amelyeket már nem használnak vagy pontatlan definíciókkal rendelkeznek.
