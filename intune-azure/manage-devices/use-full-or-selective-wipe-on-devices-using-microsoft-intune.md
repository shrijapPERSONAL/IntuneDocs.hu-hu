---
title: "Az eszközök teljes vagy szelektív törlése Intune használatával"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Megtudhatja, hogyan kezdeményezhet szelektív törlést a vállalati adatok eltávolítása érdekében, illetve teljes törlést az eszköz gyári beállításainak visszaállításához."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 22e188e81f2bc278045bb0988642b1b68372d6af
ms.lasthandoff: 02/18/2017


---

# <a name="use-full-or-selective-wipe"></a>Teljes vagy szelektív törlés alkalmazása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune által felügyelt eszközökről törölni tudja az alkalmazásokat és az adatokat, ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. Az Intune ehhez szelektív törlési és teljes törlési funkciókat kínál. Egy távoli törlési parancs kiadásával a felhasználók az Intune Munkahelyi portál segítségével törölhetik az Intune-ban regisztrált saját tulajdonú eszközeik tartalmát.

  > [!NOTE]
  > Ez a témakör kizárólag az Intune mobileszköz-kezelő által felügyelt eszközök tartalmának törlését ismerteti. Az [Azure-portál](https://portal.azure.com) használatával is [törölheti a vállalati adatokat az alkalmazásokból](https://docs.microsoft.com/intune/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). Ezenkívül [kivonhatja az Intune ügyfélszoftver által felügyelt számítógépeket.](https://docs.microsoft.com/intune/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## <a name="full-wipe"></a>Teljes törlés

A **Teljes törlés** visszaállítja az eszközt a gyári beállításokra, és eltávolít minden vállalati is felhasználói adatot és beállítást. Az eszközt a rendszer eltávolítja az Intune-ból. A teljes törlést akkor érdemes használni, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták.  **A teljes törlést óvatosan használja – az eszközről eltávolított adatok nem állíthatók vissza**.


> [!Warning]
> A 4 GB-nál kevesebb memóriával rendelkező Windows 10 RTM rendszerű eszközök (a Windows 10 rendszer 1511-es verziójánál korábbi eszközök) a törlés után használhatatlanná válhatnak. Ha egy Windows 10 rendszerű eszköz nem válaszol, az eszközt egy USB-meghajtó segítségével lehet elindítani.


**Eszköz teljes törlése (gyári beállítások visszaállítása)**:

1.  Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.

2.  Válassza ki a törölni kívánt eszköz nevét.

3.  Az eszköz nevét tartalmazó panelen válassza a **Gyári beállítások visszaállítása** lehetőséget, majd kattintson az **Igen** gombra a törlés megerősítéséhez.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a törlés összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Eszközök törlése az Azure Active Directory portálon

1.  Nyissa meg a [http://aka.ms/accessaad](http://aka.ms/accessaad) weblapot, vagy válassza a **Felügyelet** &gt; **Azure AD** lehetőséget a [https://portal.office.com](https://portal.office.com) portálon.

2.  A lap bal oldalán található hivatkozást használva jelentkezzen be a szervezeti azonosítójával.

3.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (kattintson a **Register your free Azure Active Directory** előfizetési hivatkozásra).

4.  Válassza az **Active Directory** lehetőséget, és jelölje ki a szervezetét.

5.  Válassza a **Felhasználók** fület.

6.  Jelölje ki azokat a felhasználókat, akiknek az eszközeit törölni szeretné.

7.  Válassza az **Eszközök** lehetőséget.

8.  Szükség szerint távolítson el eszközöket, többek között azokat, amelyeket már nem használnak vagy pontatlan definíciókkal rendelkeznek.


## <a name="selective-wipe"></a>Szelektív törlés

A **szelektív törlés** a vállalati adatokat, többek között a beállításokat és az e-mail-profilokat, valamint adott esetben a mobilalkalmazás-felügyeleti (MAM-) adatokat távolítja el az eszközről. Szelektív törlés esetén a felhasználó személyes adatai az eszközön maradnak. Az eszközt a rendszer eltávolítja az Intune-ból. Az alábbi táblázatok ismertetik, hogy milyen adatokat töröl a rendszer, és hogy az eszközön maradó adatokra milyen hatással van a szelektív törlés. (A táblázatok az egyes platformok szerint vannak rendezve)

**iOS**

|Adattípus|iOS|
|-------------|-------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|Törlődnek az alkalmazások. Törlődnek a vállalati alkalmazásadatok.<br /><br />Törlődnek a mobilalkalmazás-felügyeletet használó Microsoft-alkalmazások adatai. Az alkalmazások nem törlődnek.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonásra kerülnek.|
|Felügyeleti ügynök|Törlődik a felügyeleti profil.|
|E-mail|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek. Helyszíni környezetben üzemelő Microsoft Exchange esetén az e-mail-profilok és a gyorsítótárazott e-mailek nem törlődnek.|
|Outlook|Törlődnek az iOS rendszerhez készült Microsoft Outlook alkalmazás által fogadott e-mailek.</br>Kivétel: Helyszíni környezetben üzemelő Exchange esetén az e-mailek nem törlődnek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az AAD-rekord.|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

**Android**

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
|E-mail|Törlődnek az androidos Microsoft Outlook alkalmazás által fogadott e-mailek.|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|
|Outlook|Törlődnek az iOS rendszerhez készült Microsoft Outlook alkalmazás által fogadott e-mailek.</br>Kivétel: Helyszíni környezetben üzemelő Exchange esetén az e-mailek nem törlődnek.|Törlődnek az iOS rendszerhez készült Microsoft Outlook alkalmazás által fogadott e-mailek.</br>Kivétel: Helyszíni környezetben üzemelő Exchange esetén az e-mailek nem törlődnek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az AAD-rekord.|Törlődik az AAD-rekord.|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.|Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

**Windows**

|Adattípus|Windows 8.1 (MDM) és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok|A titkosított fájlrendszerrel (EFS) védett fájlok kulcsát a rendszer visszavonja, és a felhasználó nem fogja tudni megnyitni őket.|Nem törlődnek a vállalati alkalmazások.|Törlődnek az eredetileg a vállalati portálon keresztül telepített alkalmazások. Törlődnek a vállalati alkalmazásadatok.|Az alkalmazások és a közvetlen telepítési kulcsok el lesznek távolítva.|
|Beállítások|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|Az Intune-szabályzat által konfigurált beállítások érvényüket vesztik, és ezután a felhasználók megváltoztathatják ezeket a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva.|Eltávolítva.|Nem támogatott.|Eltávolítva.|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonódnak.|A tanúsítványok törlődnek és visszavonódnak.|Nem támogatott.|A tanúsítványok törlődnek és visszavonódnak.|
|E-mail|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket is.|Nem támogatott.|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket is. A rendszer eltávolítja az Intune által telepített e-mail-fiókokat.</br>**Kivétel**: Helyszíni környezetben üzemelő Exchange esetén az e-mail-fiókok nem törlődnek.|
|Azure Active Directory (AAD) elhagyása|Nem.|Nem.|Törlődik az AAD-rekord.|Nem alkalmazható. A Windows 10 nem támogatja az Azure Active Directoryhoz csatlakoztatott eszközök szelektív törlését.|

**Szelektív törlés**:

1.  Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.

2.  Válassza ki a törölni kívánt eszköz nevét.

3.  Az eszköz nevét tartalmazó panelen válassza a **Céges adatok eltávolítása** lehetőséget, majd kattintson az **Igen** gombra a törlés megerősítéséhez.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a törlés összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

