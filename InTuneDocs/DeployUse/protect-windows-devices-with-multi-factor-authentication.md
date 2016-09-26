---
title: "Multi-Factor Authentication hitelesítés Windows rendszeren | Microsoft Intune"
description: "Az Intune többtényezős hitelesítés (MFA) alkalmazásával segíti elő a vállalati erőforrások védelmét."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: 00d63fa55cd29c938dd082e2eff240f08319e01a


---

# Protect Windows devices with multi-factor authentication
A Microsoft Intune többtényezős hitelesítés (MFA) alkalmazásával segíti elő a vállalati erőforrások védelmét. Az MFA a felhasználónevek és jelszavak mellett olyan hitelesítési tényezőket is igényel, mint például a szöveges hitelesítés. Az Intune a többtényezős hitelesítés használatát a Windows 8.1 vagy későbbi verziójú, a Windows Phone 8.1, illetve a Windows 10 rendszerű asztali és mobileszközök regisztrálása során támogatja.

## Az ADFS Multi-Factor Authentication helyszíni infrastruktúra-követelményei
A többtényezős hitelesítés beállításához az alábbiakra van szükség:

-   Automatikus regisztráció a [Windows eszközkezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md) című részben leírtak szerint.
-   **Egy Active Directory-tartomány, amelyhez az ADFS-kiszolgáló csatlakozik.**

-   **A Multi-Factor Authentication szolgáltatáshoz beállított ADFS-kiszolgáló.** ADFS-kiszolgálóként beállított, Windows Server 2012 R2 rendszerű kiszolgáló. További információkért lásd: [Secure cloud and on-premises resources using Azure Multi-Factor Authentication Server with Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/) (A felhőalapú és helyszíni erőforrások védelme a Windows Server 2012 R2 Active Directory összevonási szolgáltatásokkal használt Azure Multi-Factor Authentication alkalmazásával)

A kiszolgálóknak meg kell felelniük a [Rendszerkövetelmények és telepítési információk a Windows Server 2012 R2-höz](http://technet.microsoft.com/library/dn303418.aspx) című cikkben megadott rendszerkövetelményeknek.

 


#### Többtényezős hitelesítés az Intune-ban
Ha vállalata helyszíni informatikai infrastruktúrát használ, amelynek az Active Directory-tartományában be van állítva az Active Directory összevonási szolgáltatások (ADFS), beállíthatja a Multi-Factor Authentication szolgáltatást az összevonási kiszolgálón, majd engedélyezheti azt az Intune-ban történő regisztráláshoz. Az MFA szolgáltatásnak az Intune-beli konfigurálásával engedélyezi, hogy a felhasználók egyszer, a regisztráció során hitelesítsék magukat, majd ezt követően úgy használhassák a vállalati erőforrásokat, hogy az MFA hitelesítési folyamatot nem kell minden alkalommal megismételniük.

>[!NOTE]
>Az MFA hitelesítés felhasználói vagy csoportszinten követelhető meg az ADFS-kiszolgálón.  

#### Többtényezős hitelesítés az Intune nélkül
Ha beállítja az MFA használatát az összevonási kiszolgálón, de nem engedélyezi az MFA használatát az Intune-beléptetéshez, a felhasználóknak minden olyan alkalommal használniuk kell a többtényezős hitelesítést, amikor vállalati erőforrásokhoz férnek hozzá (nem csak a regisztrációnál).

Az Azure Active Directory (Azure AD) MFA használható arra is, hogy a többtényezős hitelesítés minden alkalommal, felhasználónkénti alapon kötelező legyen, amikor a felhasználók vállalati erőforrásokhoz férnek hozzá. Az Azure AD MFA egy olyan felhőalapú szolgáltatás, amelyhez nincs szükség helyszíni informatikai infrastruktúrára. Az Azure AD MFA beállításáról a [Getting started with Azure Multi-Factor Authentication in the cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/) (Bevezetés a felhőalapú Azure Multi-Factor Authentication használatába) című témakörben tájékozódhat.

## Többtényezős hitelesítés megkövetelése az Active Directory összevonási szolgáltatásokban windowsos eszközök regisztrálásakor
A Multi-Factor Authentication engedélyezéséről az ADFS-ben a [Kockázatkezelés további többtényezős hitelesítéssel érzékeny alkalmazások esetén](http://technet.microsoft.com/library/dn280949.aspx)című bemutatóban tájékozódhat.

## Többtényezős hitelesítésű eszközregisztráció beállítása az Intune-ban
>[!Important]  
>Mielőtt kötelezővé tenné a többtényezős hitelesítés használatát a windowsos eszközök Intune-beli regisztrálásához, engedélyezze ezt a hitelesítési módot az Azure AD-bérlőn vagy a helyszíni környezetben. Ellenkező esetben a felhasználók hibaüzenetet kapnak, amikor Windows rendszerű eszközüket próbálják regisztrálni, illetve amikor megpróbálják csatlakoztatni eszközüket az Azure Active Directoryhoz, amennyiben az Azure AD-hoz való csatlakozáskori automatikus regisztráció be van állítva.

1.  Az Intune felügyeleti konzolon válassza a **Rendszergazda** &gt; **Mobileszköz-kezelés** &gt; **Többtényezős hitelesítés** elemet.

2.  Válassza **A többtényezős hitelesítés konfigurálása**, majd a **Többtényezős hitelesítés engedélyezése** elemet.



<!--HONumber=Sep16_HO3-->


