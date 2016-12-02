---
title: "Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz | Microsoft Intune"
description: "A helyszíni felhasználók szinkronizálása az Azure AD-vel és rendszergazdai jogosultság megadása az Intune-előfizetésnek"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz
A címtár-szinkronizálás konfigurálásával importálhatja a helyi Active Directoryban lévő felhasználói fiókokat a Microsoft Azure Active Directory (Azure AD) szolgáltatásba. A helyi Active Directory szolgáltatás Azure Active Directory-alapú szolgáltatásokkal való összekapcsolásával jóval egyszerűbbé válik az identitásfelügyelet. Az egyszeri bejelentkezési funkciók konfigurálásával ismerőssé és könnyebbé teheti a felhasználók számára a hitelesítést.

Hogy ez még egyszerűbb legyen, több szolgáltatás ugyanazon [Azure AD-bérlővel](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) való használata esetén a korábban szinkronizált felhasználói fiókok minden olyan felhőalapú szolgáltatás számára elérhetők lesznek, amelyek ugyanahhoz az Azure AD-bérlői előfizetéshez tartoznak.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Helyi felhasználók szinkronizálása az Azure AD szolgáltatással
A felhasználói fiókoknak az Azure AD-val való szinkronizálásához kizárólag az [Azure AD Connect varázslóra](https://www.microsoft.com/download/details.aspx?id=47594) van szüksége. Az Azure AD Connect varázsló egyszerűsített és irányított kezelőfelülettel segíti a helyszíni identitási infrastruktúrának a felhőhöz történő csatlakoztatását.  Válassza ki a topológiát és a vonatkozó igényeket (egyetlen vagy többszörös címtárak, jelszavak szinkronizálása vagy összevonása), a varázsló pedig a kapcsolat létrehozásához és működéséhez szükséges valamennyi összetevő telepítését és konfigurálását elvégzi. Ilyen összetevők többek között: a szinkronizálási szolgáltatások, az Active Directory összevonási szolgáltatások (AD FS) és az Azure AD PowerShell modul.

> [!TIP]
> Az Azure AD Connect a korábban Dirsync és Azure AD Sync néven kibocsátott eszközök valamennyi funkcióját tartalmazza. További tájékoztatás a [Címtár-integrációra](http://technet.microsoft.com/library/jj573653.aspx) vonatkozóan. További tudnivalók a helyi címtárban lévő felhasználói fiókok Azure AD-vel való szinkronizálásának előnyeiről: [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx) (Az Active Directory és az Azure AD közötti hasonlóságok).

## <a name="grant-administrator-permissions"></a>Rendszergazdai jogosultságok engedélyezése

Az Intune felügyeletéhez a következőket fogja használni:
- Két különböző típusú rendszergazdai fiók
- További jogosultságokkal rendelkező felhasználói fiókok
- Két webalapú felügyeleti konzol/portál, amelyek hozzáférést biztosítanak a rendszergazdák számára azokhoz az elemekhez, amelyeket felügyelniük kell.

Azt javasoljuk, hogy a felhasználók Intune előfizetéshez történő hozzáadása után néhány felhasználói fiók számára biztosítson rendszergazdai jogosultságokat. A rendszergazdai jogosultságok hozzárendelésére szolgáló konzol a hozzárendelni kívánt rendszergazda típusától függ:

-   **Bérlői rendszergazda**: Ezt a rendszergazdatípust a **Microsoft Intune-fiók portáljával** rendelheti hozzá az előfizetés kezelése céljából, beleértve a számlázást, a felhőalapú tárolást és azon felhasználók felügyeletét, akik számára engedélyezte az Intune használatát.

-   **Szolgáltatás-rendszergazda**: Ezt a rendszergazdatípust a **Microsoft Intune rendszergazdai konzoljával** rendelheti hozzá a napi rutinfeladatok elvégzése céljából, beleértve a mobileszközök és számítógépek felügyeletét, a szabályzatok érvénybe léptetését, a szoftverek telepítését és a jelentéskészítést.

Az alábbiakban ezen fiókokról és portálokról esik szó.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Az Intune rendszergazdai fiókjai és speciális engedélyekkel rendelkező felhasználói fiókjai

A következő fiókokat és engedélyeket kell használnia az Intune-ban.

### <a name="tenant-administrator"></a>Bérlői rendszergazda
|Jogosultsági szintek|További információ|
|--------------------------|-------------------------|
|A bérlői rendszergazdák egy rendszergazdai szerepkörrel rendelkeznek, amely meghatározza az adott felhasználó felügyeleti hatókörét és az általa kezelhető feladatokat.<br /><br />A Microsoft különböző felhőszolgáltatásai ugyanazokat a rendszergazdai szerepköröket használják, azonban előfordulhat, hogy egyes szolgáltatások nem támogatnak bizonyos szerepköröket.<br /><br /> A Microsoft Intune a következő szerepköröket használja:<br /><br />- Globális rendszergazda<br />- Számlázási rendszergazda<br />- Jelszókezelő<br />- Szolgáltatás-rendszergazda<br />- Felhasználókezelő rendszergazda|A Microsoft Intune-előfizetés létrehozásához használt fiók alapértelmezés szerint egy bérlői rendszergazda, aki megkapja a globális rendszergazdai szerepkört.<br /></br>  Bérlői rendszergazdaként a [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] segítségével kezelheti Intune-előfizetését, valamint kijelölheti a bérlő rendszergazdákat az [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] felületén.<br /><br />A globális rendszergazdai szerepkörrel rendelkező bérlői rendszergazdákkal hozzáférhet a [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]hoz, és kijelölheti az első szolgáltatás-rendszergazdát. A napi felügyeleti feladatok elvégzéséhez nem ajánlott bérlői rendszergazdát alkalmazni. A bérlői rendszergazdának nincs szüksége Intune-licencre az [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]hoz való hozzáféréshez.<br /><br />A bérlői rendszergazda a Microsoft felhőszolgáltatásaiban általánosan használt fogalom. Az Intune-ra való előfizetéskor a szolgáltatás a Microsoft Azure AD bérlője lesz. Lásd az Azure AD-bérlőről szóló részt a következő cikkben: [Mi az az Azure AD címtár?](http://technet.microsoft.com/library/jj573650.aspx)|


### <a name="service-administrator"></a>Szolgáltatás-rendszergazda
|Jogosultsági szintek|További információ|
|--------------------------|-------------------------|
|A szolgáltatás-rendszergazdák a következő jogosultságok egyikével rendelkeznek:<br /><br />**Teljes hozzáférés**: A [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] minden területéhez korlátlan hozzáférést biztosít. Más szolgáltatás-rendszergazdákat is hozzáadhat és kezelhet.<br /><br />**Olvasási hozzáférés**: A [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] minden területéhez olvasási engedélyt biztosít. A csak olvasási hozzáféréssel rendelkező szolgáltatás-rendszergazdák nem módosíthatják az adatokat, de futtathatnak jelentéseket.<br /><br />**Segélyszolgálat – Csoportok csomópont**: csak a segélyszolgálati forgatókönyvekhez gyakran kapcsolódó feladatokhoz biztosít engedélyeket a szolgáltatás rendszergazdája számára. Az engedélyeknek ezzel a halmazával kapcsolatos további információkért lásd: [Az Intune-konzolnézetek testreszabása a rendszergazdai szerepköröknek megfelelően](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Az Intune alapértelmezés szerint nem jelöl ki szolgáltatás-rendszergazdát. Ehelyett egy globális rendszergazdai szerepkörrel rendelkező bérlői rendszergazda használatával kell kijelölnie az első szolgáltatás-rendszergazdát az előfizetéshez. </br></br> Szolgáltatás-rendszergazdaként az [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]on végezheti el az Intune napi feladatait.<br /><br />A szolgáltatás-rendszergazdákat a felügyeleti konzolon lehet kijelölni. A szolgáltatás-rendszergazdáknak rendelkezniük kell Intune-licenccel ahhoz, hogy a fiók hozzáférhessen a felügyeleti konzolhoz.|



### <a name="device-enrollment-managers"></a>Eszközregisztráció-kezelők
|Jogosultsági szintek|További információ|
|--------------------------|-------------------------|
|Az eszközregisztráció-kezelők normál felhasználói fiókok, melyek rendelkeznek az ötnél több eszköz regisztrálásához szükséges további engedélyekkel.|Alapértelmezés szerint minden [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-felhasználó legfeljebb öt eszközt regisztrálhat. Megadhatja azonban az eszközregisztráció-kezelői engedélyt egy felhasználói fióknak, majd ezzel a fiókkal regisztrálhat nagy mennyiségű vállalati eszközt. Ez akkor hasznos, ha előfordulhat, hogy az eszközöket csak ideiglenesen rendelik hozzá a felhasználókhoz, vagy kioszkmódban működnek, amelyben a felhasználók eszközökhöz való társítása nem szükséges.|




>[!div class="step-by-step"]

>[&larr; **Tartományi beállítások**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune-licencek kezelése** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


