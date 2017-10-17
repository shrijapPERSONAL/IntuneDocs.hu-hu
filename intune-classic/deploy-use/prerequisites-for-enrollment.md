---
title: "A mobileszközök regisztrációjára vonatkozó előfeltételek"
description: "Beállíthat mobileszköz-felügyeleti (MDM) előfeltételeket, és felkészülhet a különböző operációs rendszerek beléptetésére."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d02a822dc9a403806657f36ae0ac4bfad8246d0
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Mobileszköz-kezelés előfeltételei az Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A következő lépésekkel teheti lehetővé az alkalmazottak számára, hogy regisztrálják a mobileszközüket az Intune-ban. Ugyanezek a lépések szükségesek a vállalat tulajdonában lévő eszközök esetében is.

|Lépések|Részletek|  
|-----------|-------------|  
|**1. lépés:** [Kapcsolatok engedélyezése](#step-1-enable-connections)|Gondoskodjon róla, hogy az egyéni tartománynév konfigurálva legyen, és a hálózati kommunikáció készen álljon.|  
|**2. lépés:** [MDM-szolgáltató beállítása](#step-2-set-mdm-authority)|A mobileszköz-kezelő szolgáltató határozza meg az eszközökhöz hozzárendelt szolgáltatást.|
|**3. lépés:** [Csoportok létrehozása](#step-3-create-groups)|Konfigurálja a Vállalati portál alkalmazás felhasználókat érintő beállításait.|  
|**4. lépés:** [A Munkahelyi portál konfigurálása](#step-4-configure-company-portal)|Konfigurálja a Vállalati portál alkalmazás felhasználókat érintő beállításait.|  
|**5. lépés:** [Felhasználói licencek hozzárendelése](#step-5-assign-user-licenses)|Rendeljen Intune-licencet a felhasználókhoz, hogy regisztrálhassák az eszközöket.|
|**6. lépés:** [A regisztráció engedélyezése](#step-6-enable-enrollment)|Engedélyezze az iOS- és Windows-felügyelet platformspecifikus beállításait. Az Android-eszközökhöz nincs szükség további konfigurálásra.|
|**7. lépés:** [További lépések](#step-7-next-steps)|Engedélyezze az iOS- és Windows-felügyelet platformspecifikus beállításait. Az Android-eszközökhöz nincs szükség további konfigurálásra.|

A Microsoft Intune-nal bővített Configuration Manager-t keresi?
> [!div class="button"]
[Az SCCM dokumentációjának megtekintése >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>1. lépés: Kapcsolatok engedélyezése

A mobileszközök regisztrációjának engedélyezése előtt feltétlenül végezze el a következőket:
- [Ellenőrizze a szükséges hálózati URL-címeket és -portokat.](/intune/network-bandwidth-use)
- [Vegye fel és ellenőrizze a tartományevet.](/intune/custom-domain-name-configure)

## <a name="step-2-set-mdm-authority"></a>2. lépés: MDM-szolgáltató beállítása
Az MDM-szolgáltató határozza meg azt a felügyeleti szolgáltatást, amely az eszközök kezelésére jogosult. MDM-szolgáltató lehet például maga az Intune, illetve a Configuration Managerbe és az Intune. Ha a Configuration Manager van beállítva felügyeleti szolgáltatóként, nem használhat más szolgáltatást a mobileszközök felügyeletére.

>[!IMPORTANT]
> A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információért tekintse meg a [Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) című részt.

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** lehetőséget.

2.  A **Feladatok** listában kattintson a **Mobileszköz-kezelő szolgáltatás beállítása**elemre. Megnyílik az **MDM szolgáltatás beállítása** párbeszédpanel.

    ![Az MDM-szolgáltató megadása párbeszédpanel](../media/intune-mdm-authority.png)

3.  Az Intune annak megerősítését kéri, hogy be szeretné állítani MDM-szolgáltatóként. Jelölje be a jelölőnégyzetet, majd válassza az **Igen** lehetőséget a Microsoft Intune mobileszközök kezelésére történő használatához.

## <a name="step-3-create-groups"></a>3. lépés: Csoportok létrehozása

Felhasználó- és eszközcsoportok létrehozásával leegyszerűsítheti a felügyeletet, és javíthatja a telepített alkalmazások, a szabályzatok és a vállalati erőforrások felügyeletét. [Ez a cikk ismerteti a csoportok létrehozását](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>4. lépés: A Munkahelyi portál konfigurálása

A felhasználók az Intune Vállalati portálon érhetik el a vállalati adatokat, és olyan gyakori feladatokat hajthatnak végre, mint például az eszközök regisztrálása, az alkalmazások telepítése és az informatikai támogatási információk megtekintése.

> [!TIP]
> A vállalati portál testreszabása a vállalati portál webhelyére és a vállalati portál alkalmazásaira egyaránt hatással van.

A vállalati portál testreszabásával ismerős és könnyen használható környezetet teremthet felhasználóinak. Ehhez regisztráljon a [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) bérlői vagy szolgáltatás-rendszergazdaként, válassza a **Felügyelet** &gt; **Vállalati portál** lehetőséget, és konfigurálja a Vállalati portál beállításait.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Vállalat kapcsolattartási adatai és adatvédelmi nyilatkozata

A vállalat neve a Vállalati portál címeként jelenik meg. A kapcsolattartási adatokat és részleteket a felhasználók a Vállalati portál IT-csoport elérhetősége képernyőjén tekinthetik meg. Az adatvédelmi nyilatkozat az Adatvédelem hivatkozásra kattintva jeleníthető meg.

|Mező neve|Maximális hossz|További információ|
    |----------|------------------------|----------------|
    |A cég neve|40|Ez a név a Vállalati portál címeként jelenik meg. **Megjegyzés:**: Csak alfanumerikus karaktereket tartalmazhat. Ez a mező nem támogatja a speciális karaktereket.|
    |IT-részleg kapcsolattartójának a neve|40|Ez a név az **IT-csoport elérhetősége** lapon jelenik meg.|
    |IT-részleg telefonszáma|20|Ez a telefonszám az **IT-csoport elérhetősége** lapon jelenik meg.|
    |IT-részleg e-mail címe|40|Ez a cím az **IT-csoport elérhetősége** lapon jelenik meg. Meg kell adnia egy érvényes e-mail címet a következő formátumban: **alias@domainname.com**.|
    |További információ|120|Ez az információ az **IT-csoport elérhetősége** lapon jelenik meg.|
    |Vállalat adatvédelmi nyilatkozatának URL-címe:|79|Itt adhatja meg vállalatának adatvédelmi nyilatkozatát, amely akkor jelenik meg, ha a felhasználó a Vállalati portál adatvédelmi hivatkozásaira kattint. Érvényes URL-címet kell megadnia, a következő formátumban: https://www.contoso.com.|

### <a name="support-contacts"></a>Támogatási kapcsolattartók
A támogatási webhely a Vállalati portálon jelenik meg, és lehetővé teszi a felhasználók számára az online támogatás elérését.

|Mező neve|Maximális hossz|További információ|
    |----------|------------------------|----------------|
    |Támogatási webhely URL-címe|150|Ha rendelkezik saját felhasználóinak szánt támogatási webhellyel, ide írja be az URL-címét. Az URL-címet a https://www.contoso.com formátumban kell megadni. Ha nem ad meg URL-címet, semmi sem jelenik meg a támogatási webhelyről a Vállalati portál **IT-csoport elérhetősége** lapján.|
    |Webhely neve|40|Ez a név a támogatási webhely URL-címének rövid neveként jelenik meg. Ha a támogatási webhelyhez csak URL-címet ad meg, de egyszerű nevet nem, akkor **Az IT-csoport weboldalának megnyitása** felirat jelenik meg a Vállalati portál **IT-csoport elérhetősége** lapján.|


### <a name="company-branding-customization"></a>Vállalati arculat szerinti testreszabás

A Vállalati portál testre szabható a vállalat emblémájának és nevének, valamint a téma színének és a háttérnek a megadásával.

|Mező neve|További információ|
    |----------|----------------|
    |Téma színe|A Vállalati portálra alkalmazni kívánt témaszín kiválasztása.|
    |Cég emblémájának megjelenítése|Ha engedélyezi ezt a beállítást, feltöltheti a Vállalati portálon megjeleníteni kívánt vállalati emblémát. Két emblémát tölthet fel: az egyik akkor jelenik meg, ha a Vállalati portál háttérszíne fehér, a másik pedig akkor, ha a Vállalati portál a témának megfelelő háttérszínnel jelenik meg. Mindkét emblémának egy .png vagy .jpg formátumú fájlnak kell lennie, melyek felbontása legfeljebb 400 x 100 képpont, mérete pedig legfeljebb 750 KB lehet.|
    |Háttér választása a Vállalati portál alkalmazás számára|Ez a beállítás csak a Vállalati portál alkalmazás hátterére van hatással.|


A módosítások mentése után a felügyeleti konzol **Vállalati portál** lapjának alján található hivatkozásokra kattintva megtekintheti a Vállalati portál webhelyét. Ezek a hivatkozások nem módosíthatók. A felhasználók bejelentkezésekor ezek a hivatkozások a Vállalati portálon megjelenítik az Ön előfizetéseit.

## <a name="step-5-assign-user-licenses"></a>5. lépés: Felhasználói licencek hozzárendelése

Az **Office 365 felügyeleti portál** használatával a felhőalapú felhasználók és licencek manuálisan hozzáadhatók, illetve hozzárendelhetők a felhőalapú felhasználói fiókokhoz és a helyszíni Active Directoryból az Azure Active Directoryba (Azure AD) szinkronizált fiókokhoz is. [Szinkronizálhatja a helyszíni felhasználókat az Azure AD-be](/intune/users-permissions-add#how-to-sync-on-premises-users-with-azure-ad).

1.  Jelentkezzen be az [Office 365 felügyeleti portálján](https://portal.office.com/Admin/Default.aspx) bérlői rendszergazdai hitelesítő adataival.

2.  Válassza ki azt a felhasználói fiókot, amelyhez Intune felhasználói licencet kíván hozzárendelni, majd jelölje be a **Microsoft Intune** jelölőnégyzetet a felhasználói fiók tulajdonságai között.

3.  A felhasználói fiók ezzel bekerül a Microsoft Intune felhasználói csoportba, amely engedélyt ad a felhasználónak a szolgáltatás használatára és eszközeinek felügyeletre való regisztrálására.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Helyszíni felhasználók szinkronizálása az Azure AD szolgáltatással

1. [Adja hozzá az egyszerű felhasználónévi utótagot](https://technet.microsoft.com/library/cc772007.aspx) az egyéni tartományhoz a helyszíni Active Directoryban.
2. Állítsa be az egyszerű felhasználónévi utótagot az importálni kívánt helyszíni felhasználóknak.
3. Futtassa [az Azure AD Connect szinkronizálási szolgáltatást](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) a helyszíni felhasználók az Azure AD-val való integrálásához.
4. Miután a felhasználói fiókok adatait sikeresen szinkronizálta, az [Office 365 felügyeleti portállal](https://portal.office.com/Admin/Default.aspx) hozzájuk rendelheti a Microsoft Intune-licenceket.

## <a name="step-6-enable-enrollment"></a>6. lépés: Regisztráció engedélyezése
A mobileszköz-kezelő szolgáltató beállítása után meg kell adnia az eszközkezelési beállításokat a szervezet által támogatni kívánt operációs rendszerekhez. Az eszközkezelés beállításához szükséges lépések operációs rendszertől függően eltérhetnek. Android operációs rendszer esetén például semmit sem kell megadnia az Intune felügyeleti konzolon. Windows- és iOS-eszközökön azonban a felügyelet engedélyezéséhez megbízhatósági kapcsolatot kell beállítani az eszközök és az Intune között.

Az eszközkezelés beállítása a következő platformokhoz:
- [iOS és Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile és Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [Windowsos PC-k és laptopok](manage-windows-pcs-with-microsoft-intune.md) (Intune ügyfélszoftver)

A [vállalati tulajdonban lévő eszközök is regisztrálását](manage-corporate-owned-devices.md) is engedélyezheti.

## <a name="step-7-next-steps"></a>7. lépés: További lépések

A regisztráció engedélyezését követően hozzáláthat ahhoz, hogy a kialakítsa az üzleti szükségleteknek megfelelő felügyeletet. Például a következő felügyeleti lehetőségek állnak rendelkezésére:

- [Az eszközök beállításait és funkcióit kezelő szabályzatok életbe léptetése](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [A vállalati erőforrások (e-mail, Wi-FI és VPN) elérésének engedélyezése](enable-access-to-company-resources-with-microsoft-intune.md)
- [Alkalmazások felvétele](add-apps.md) és [alkalmazás telepítése](deploy-apps.md) a felügyelt eszközökre
- [Eszközmegfelelőségi szabályzatok létrehozása](introduction-to-device-compliance-policies-in-microsoft-intune.md) és a [hozzáférés korlátozása a megfelelőség alapján](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## <a name="what-to-do-if-you-choose-the-wrong-mdm-authority-setting"></a>Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?

Ha nem a megfelelő MDM-szolgáltatót állította be, és szeretné azt megváltoztatni, a következő lehetőségek állnak rendelkezésére:

### <a name="change-the-mdm-authority-yourself"></a>A mobileszköz-kezelési szolgáltató saját kezű módosítása
A Configuration Manager 1610-es és a Microsoft Intune 1705-ös verziójával kezdődően anélkül módosíthatja az MDM-szolgáltatót Microsoft Intune-ról Configuration Manager (hibrid) szolgáltatásra vagy vissza, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. Részletekért lásd az [MDM-szolgáltató módosítása]( /sccm/mdm/deploy-use/change-mdm-authority) szakaszt.

### <a name="contact-microsoft-support"></a>Kapcsolatfelvétel a Microsoft ügyfélszolgálatával
Ha az 1610-es verziónál régebbi Configuration Managerrel rendelkezik, vegye fel a kapcsolatot a Microsoft ügyfélszolgálatával. A beállítást egyedül nem fogja tudni megváltoztatni. Mielőtt kapcsolatba lépne a Microsoft ügyfélszolgálatával, kérjük, tekintse át a következő információkat, amelyekből megtudhatja, hogy a Microsoft ügyfélszolgálatának milyen adatokra lesz szüksége a beállítás megváltoztatásához.

Az MDM-szolgáltató beállítását 3 módon lehet alaphelyzetbe állítani. Ezek közül a támogatási kérelmében azt a módot kell kiválasztania, amelyik a helyzetére vonatkozik. Ha az adott körülményt nem találja a felsorolásban, tájékoztassa a Microsoft ügyfélszolgálatát.

A Microsoft ügyfélszolgálata a következő információk megerősítésére fogja megkérni:

- Bérlőazonosító: a szolgáltatásba való belépéshez használt tartomány (például intune.onmicrosoft.com)
- Az MDM-szolgáltató neve, amelyre a beállítást változtatni szeretné
- Továbbá meg kell erősítenie, hogy az alábbi előfeltételek közül melyeket teljesítette már

Ha az Intune-t és az Office 365-öt szinkronizált módban használja, mind a két szolgáltatás ellenőrzőlistáját figyelembe kell vennie.

#### <a name="reset-mdm-authority-from-intune-to-configuration-manager"></a>Mobileszköz-felügyeleti szolgáltató módosítása az Intune-ról a Configuration Managerre

Mielőtt kapcsolatba lépne a Microsoft ügyfélszolgálatával, az alábbi lépéseket használva állítsa alaphelyzetbe az MDM-szolgáltatót.

- Vonja ki az összes eszközt az Intune felügyeleti konzolja segítségével. Az eszköz kivonását ne próbálja meg az adott eszközön végrehajtani. 
- Törölje a szolgáltatások közötti összekötőt (a **Felügyelet** > **Mobileszköz-kezelés** > **Microsoft Exchange** oldalon), vagy állítsa le az Exchange-összekötőt, ha korábban azt állította be.
- Távolítsa el a Készülékregisztráció-kezelő szerepkört a **Felügyelet** > **Készülékregisztráció-kezelő** oldalon.
- Kapcsolja ki az Eszközcsoport-leképezést a **Felügyelet** > **Mobileszköz-kezelés** > **Eszközcsoport-leképezés** oldalon.
- Törölje a tesztcélú telepítési kulcsokat a **Felügyelet** > **Mobileszköz-kezelés** > **Windows** > **Tesztcélú telepítés kulcsai** oldalon.
- Törölje az iOS APNs-tanúsítványt a **Felügyelet** > **Mobileszköz-kezelés** > **iOS** oldalon.
- Törölje az iOS DEP-tokent a **Felügyelet** > **Mobileszköz-kezelés** > **iOS** oldalon.
- Törölje az összes MDM-eszközre vonatkozó szabályzatot a **Szabályzat** > **Konfigurációs szabályzatok** oldalon.
- Törölje az összes MDM-eszköz számára közzétett alkalmazást az **Alkalmazások** > **Felügyelt szoftver** oldalon.

#### <a name="reset-mdm-authority-from-configuration-manager-to-intune"></a>Mobileszköz-felügyeleti szolgáltató módosítása a Configuration Managerről az Intune-ra

Mielőtt kapcsolatba lépne a Microsoft ügyfélszolgálatával, az alábbi lépéseket használva állítsa alaphelyzetbe az MDM-szolgáltatót.

- Vonja ki az összes mobileszközként felügyelt eszközt a Configuration Manager konzoljáról. Az eszköz kivonását ne próbálja meg az adott eszközön végrehajtani. 
- Távolítsa el az összes felhasználót az Intune felhasználói csoportból. Jelöljön ki egy üres felhasználógyűjteményt az Intune-előfizetés számára, vagy távolítsa el az összes felhasználót a jelenleg megadott felhasználógyűjteményből.  Ellenőrizze a Cloudusersync.log naplófájlban, hogy az összes felhasználó el lett távolítva. 
- Törölje a jelölést az iOS platform mellől az APNs-tanúsítvány eltávolításához.
- Törölje az összes MDM-eszköz számára közzétett alkalmazást.
- Törölje az összes MDM-eszközre vonatkozó szabályzatot.
- Távolítsa el a Windows Intune-összekötőt a Configuration Manager konzoljáról (csak az R2 SP1 és korábbi verziók esetén érvényes).
Távolítsa el az Intune-előfizetést úgy, hogy jobb gombbal az előfizetésre kattint, majd a **Törlést** választja.
- Indítsa újra az SMS Executive szolgáltatást.
- Biztosítson számunkra néhány fiktív felhasználói fiókot, amelyek segítségével a folyamat vége után ellenőrizhetjük, hogy a Configuration Manager-licencek eltávolítása megtörtént.

#### <a name="reset-mdm-authority-from-office-365-to-configuration-manager"></a>Mobileszköz-felügyeleti szolgáltató módosítása az Office 365-ről a Configuration Managerre

1. Lépjen a [https://protection.office.com](https://protection.office.com) oldalra.
2. Válassza a **Biztonsági házirendek** fület, majd az **Eszközkezelés** lehetőséget.
3. A **Szelektív törlés** segítségével vonja ki az összes eszközt. Az eszköz kivonását ne próbálja meg az adott eszközön végrehajtani. Ha a szelektív törlés nincsen engedélyezve, nincs szükség további műveletre.
4. Válassza a **Biztonsági házirendek** fület, majd az **Eszközbiztonsági házirendek** lehetőséget.
5. Válassza a **Törlést** mindegyik házirend esetében. Ha a házirendek függő állapotban vannak nincs szükség további műveletre.

>[!NOTE]
>Az iOS APNs-tanúsítványt nem lehet törölni, így az továbbra is a fiókhoz rendelve marad.

#### <a name="next-steps-for-mdm-authority-resets"></a>Az MDM-szolgáltató alaphelyzetbe állításának további lépései

Miután a Microsoft ügyfélszolgálata ellenőrizte a vonatkozó ellenőrzőlista állapotát, az MDM-szolgáltató alaphelyzetbe állítása legfeljebb három munkanapot vehet igénybe, de általában egy napon belül megtörténik.

>[!IMPORTANT]
>Előfizetését ne próbálja meg módosítani addig, amíg a Microsoft ügyfélszolgálata meg nem erősíti, hogy az alaphelyzetbe állítás sikeresen megtörtént! Az idő előtti konfigurációs változtatások adatsérülést okozhatnak és azt eredményezhetik, hogy nem fogja tudni használni az Intune szolgáltatást.
