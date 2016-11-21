---
title: "Az adatok védelme távoli törléssel | Microsoft Intune"
description: "Az Intune a szelektív és a teljes törlési funkcióval is eltávolíthatja a bizalmas vállalati adatokat, valamint a vállalati erőforrásokhoz való hozzáférést."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 5900894ded0518f731ac76c3eac0332e5a3f6c4b


---

# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Adatok védelme teljes vagy szelektív törléssel a Microsoft Intune használatával
Az Intune által felügyelt eszközökről törölni tudja az alkalmazásokat és az adatokat, ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. Az Intune ehhez szelektív törlési és teljes törlési funkciókat kínál. Egy távoli törlési parancs kiadásával a felhasználók az Intune Munkahelyi portál segítségével törölhetik az Intune-ban regisztrált saját tulajdonú eszközeik tartalmát.

  > [!NOTE]
  > Ez a témakör kizárólag az Intune mobileszköz-kezelő által felügyelt eszközök tartalmának törlését ismerteti. Az [Azure-portál](https://portal.azure.com) használatával is [törölheti a vállalati adatokat az alkalmazásokból](wipe-managed-company-app-data-with-microsoft-intune.md). Ezenkívül [kivonhatja az Intune ügyfélszoftver által felügyelt számítógépeket.](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## <a name="full-wipe"></a>Teljes törlés

A **Teljes törlés** visszaállítja az eszközt a gyári beállításokra, és eltávolít minden vállalati is felhasználói adatot és beállítást. Az eszközt a rendszer eltávolítja az Intune-ból. A teljes törlést akkor érdemes használni, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták.  **A teljes törlést óvatosan használja – az eszközről eltávolított adatok nem állíthatók vissza**.


> [!Warning]
> A 4 GB-nál kevesebb memóriával rendelkező Windows 10 RTM rendszerű eszközök (a Windows 10 rendszer 1511-es verziójánál korábbi eszközök) a törlés után használhatatlanná válhatnak. Ha egy Windows 10 rendszerű eszköz nem válaszol, az eszközt egy USB-meghajtó segítségével lehet elindítani.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Eszköz tartalmának távoli törlése az Intune felügyeleti konzoljáról

1.  Válassza ki a törlendő eszközöket. Az eszközök felhasználónként vagy eszközönként választhatók ki.

    -   **Felhasználó alapján:**

        1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) kattintson a **Csoportok** &gt; **Minden felhasználó** elemre.

        2.  Kattintson annak a felhasználónak a nevére, akinek a mobileszközét törölni szeretné. Kattintson a **Tulajdonságok megtekintése** elemre.

        3.  A felhasználó **Tulajdonságok** lapján kattintson az **Eszközök** elemre, majd a törölni kívánt mobileszköz nevére. Több eszköz kijelöléséhez nyomja le a Ctrl billentyűt és kattintson az egérrel.

    -   **Eszköz alapján:**

        1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Csoportok** &gt; **Minden mobileszköz** lehetőséget.

         ![Kivonási vagy törlési művelet indítása](../media/dev-sa-wipe.png)

        2.  Kattintson az **Eszközök** elemre, majd a törölni kívánt mobileszköz nevére. Több eszköz kijelöléséhez nyomja le a Ctrl billentyűt és kattintson az egérrel.

2.  Válassza a **Kivonás/Összes adat törlése** lehetőséget.

3.  Ekkor a rendszer kérni fogja az eszköz kivonásának megerősítését.

    -   Ha **szelektív törlést** szeretne végrehajtani, amely csak a vállalati alkalmazásokat és adatokat távolítja el, kattintson az **Igen** gombra.

    -   Minden alkalmazást és adatot törlő és az eszközt a gyári alapértelmezett beállításokra visszaállító **Teljes törlés** végrehajtásához válassza az **Adatok törlése az eszközről annak kivonása előtt** lehetőséget. Ez a művelet minden platformra érvényes, kivéve a Windows 8.1-et. **A teljes törlési funkcióval törölt adatok nem állíthatók vissza**.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a törlés összes eszköztípusra való propagálása kevesebb, mint 15 percet vesz igénybe.

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
|E-mail|Törlődnek az androidos Microsoft Outlook alkalmazás által fogadott e-mailek.|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek. Helyszíni környezetben üzemelő Microsoft Exchange esetén az e-mail-profilok és a gyorsítótárazott e-mailek nem törlődnek.|
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

## <a name="wipe-encryption-file-system-efsenabled-content"></a>Titkosítási fájlrendszer (EFS) által védett tartalom törlése
A Windows 8.1 és a Windows RT 8.1 rendszer támogatja az EFS által védett tartalom szelektív törlését. Az EFS által védett tartalom szelektív törlése az alábbiak szerint működik:

-   A szelektív törlés során csak azok az EFS által védett alkalmazások és adatok törlődnek, amelyek az Intune-fiókkal megegyező internetes tartományba tartoznak. További információ: [Eszközadatok törlése a Windows szelektív törlési funkciójával](http://technet.microsoft.com/library/dn486874.aspx).

-   Ha az EFS-hez társított tartomány bármilyen módon megváltozik, akár 48 órára is szükség lehet ahhoz, hogy az új tartományt használó alkalmazások és adatok szelektív törlése lehetséges legyen.

-   A rendszer az Intune-ban regisztrált valamennyi tartományt törli.

Szelektív törléssel jelenleg a következő EFS által védett adatok és alkalmazások törölhetők:

-   A Posta alkalmazás a Windowsban

-   Munkahelyi mappák

-   Az EFS által titkosított fájlok és mappák. További információ: [Gyakorlati tanácsok a titkosított fájlrendszerhez](http://support.microsoft.com/kb/223316).

-   Ha a szervezet Active Directoryt használ identitáskezelőként, akkor ahhoz, hogy az EFS által védett adatok szelektív törlése megfelelően működjön, szinkronizálnia kell az adatokat az AAD-be a Címtár-szinkronizálás (DirSync) eszközzel.  A DirSyncről az Azure Active Directory dokumentációjának következő cikkében találhat további információt: [Címtár-szinkronizálási forgatókönyv](http://technet.microsoft.com/library/dn441212.aspx).

## <a name="monitor-retire-wipe-and-delete-actions"></a>A kivonási és törlési műveletek figyelése
A kivont, megtisztított és törölt eszközök listáját tartalmazó jelentés megtekintése:

1.  Az [Intune felügyeleti konzoljában](https://manage.microsoft.com/) kattintson a **Jelentések** &gt; **Korábbi eszközökről készült jelentések** elemre.

2.  Adja meg a jelentés kezdő és záró dátumát, majd kattintson a **Jelentés megjelenítése** elemre.

A jelentésben az is szerepel, hogy ki végezte az adott műveletet.

### <a name="see-also"></a>További információ
[Eszközök kivonása](retire-devices-from-microsoft-intune-management.md)

[Eszközadatok törlése a Windows szelektív törlési funkciójával](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Nov16_HO2-->


