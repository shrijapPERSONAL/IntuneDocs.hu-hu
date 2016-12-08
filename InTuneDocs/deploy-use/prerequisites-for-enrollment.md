---
title: "Mobileszközök regisztrálásának előfeltételei | Microsoft Intune"
description: "Beállíthat mobileszköz-felügyeleti (MDM) előfeltételeket, és felkészülhet a különböző operációs rendszerek beléptetésére."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 391612c35a7665073ca8a5c629169e5be967ab59


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Mobileszköz-kezelés előfeltételei az Intune-ban
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
- [Ellenőrizze a szükséges hálózati URL-címeket és -portokat.](../get-started/network-infrastructure-requirements-for-microsoft-intune)
- [Vegye fel és ellenőrizze a tartományevet.](../get-started/domain-names-for-microsoft-intune)

## <a name="step-2-set-mdm-authority"></a>2. lépés: MDM-szolgáltató beállítása
Az MDM-szolgáltató határozza meg azt a felügyeleti szolgáltatást, amely az eszközök kezelésére jogosult. MDM-szolgáltató lehet például maga az Intune, illetve a Configuration Managerbe és az Intune. Ha a Configuration Manager van beállítva felügyeleti szolgáltatóként, nem használhat más szolgáltatást a mobileszközök felügyeletére.

>[!IMPORTANT]
> Alaposan fontolja meg, hogy a mobileszközöket csak az Intune használatával (online szolgáltatás), vagy a System Center Configuration Managerbe integrált Intune-nal szeretné-e kezelni (helyszíni szoftveres megoldás online szolgáltatással együtt). Miután beállította az MDM-szolgáltatót, ez már nem módosítható.



1.  A [Microsoft Intune felügyeleti konzoljában](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** lehetőséget.

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

Az **Office 365 felügyeleti portál** használatával a felhőalapú felhasználók és licencek manuálisan hozzáadhatók, illetve hozzárendelhetők a felhőalapú felhasználói fiókokhoz és a helyszíni Active Directoryból az Azure Active Directoryba (Azure AD) szinkronizált fiókokhoz is. [Szinkronizálhatja a helyszíni felhasználókat az Azure AD-be](../get-started/domain-names-for-microsoft-intune#to-synchronize-on-premises-users-with-azure-ad.md).

1.  Jelentkezzen be az [Office 365 felügyeleti portálján](https://portal.office.com/Admin/Default.aspx) bérlői rendszergazdai hitelesítő adataival.

2.  Válassza ki azt a felhasználói fiókot, amelyhez Intune felhasználói licencet kíván hozzárendelni, majd jelölje be a **Microsoft Intune** jelölőnégyzetet a felhasználói fiók tulajdonságai között.

3.  A felhasználói fiók ezzel bekerül a Microsoft Intune felhasználói csoportba, amely engedélyt ad a felhasználónak a szolgáltatás használatára és eszközeinek felügyeletre való regisztrálására.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Helyszíni felhasználók szinkronizálása az Azure AD szolgáltatással

1. [Adja hozzá az egyszerű felhasználónévi utótagot](https://technet.microsoft.com/en-us/library/cc772007.aspx) az egyéni tartományhoz a helyszíni Active Directoryban.
2. Állítsa be az egyszerű felhasználónévi utótagot az importálni kívánt helyszíni felhasználóknak.
3. Futtassa [az Azure AD Connect szinkronizálási szolgáltatást](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) a helyszíni felhasználók az Azure AD-val való integrálásához.
4. Miután a felhasználói fiókok adatait sikeresen szinkronizálta, az [Office 365 felügyeleti portállal](https://portal.office.com/Admin/Default.aspx) hozzájuk rendelheti a Microsoft Intune-licenceket.

## <a name="step-6-enable-enrollment"></a>6. lépés: Regisztráció engedélyezése
A mobileszköz-kezelő szolgáltató beállítása után meg kell adnia az eszközkezelési beállításokat a szervezet által támogatni kívánt operációs rendszerekhez. Az eszközkezelés beállításához szükséges lépések operációs rendszertől függően eltérhetnek. Android operációs rendszer esetén például semmit sem kell megadnia az Intune felügyeleti konzolon. Windows- és iOS-eszközökön azonban a felügyelet engedélyezéséhez megbízhatósági kapcsolatot kell beállítani az eszközök és az Intune között.

Az eszközkezelés beállítása a következő platformokhoz:
- [iOS és Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows rendszerű számítógépek és laptopok](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile és Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

A [vállalati tulajdonban lévő eszközök is regisztrálását](manage-corporate-owned-devices) is engedélyezheti.

## <a name="step-7-next-steps"></a>7. lépés: További lépések

A regisztráció engedélyezését követően hozzáláthat ahhoz, hogy a kialakítsa az üzleti szükségleteknek megfelelő felügyeletet. Például a következő felügyeleti lehetőségek állnak rendelkezésére:

- [Az eszközök beállításait és funkcióit kezelő szabályzatok életbe léptetése](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [A vállalati erőforrások (e-mail, Wi-FI és VPN) elérésének engedélyezése](enable-access-to-company-resources-with-microsoft-intune.md)
- [Alkalmazások felvétele](add-apps.md) és [alkalmazás telepítése](deploy-apps.md) a felügyelt eszközökre
- [Eszközmegfelelőségi szabályzatok létrehozása](introduction-to-device-compliance-policies-in-microsoft-intune.md) és a [hozzáférés korlátozása a megfelelőség alapján](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


