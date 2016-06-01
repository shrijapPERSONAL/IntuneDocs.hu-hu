---
# required metadata

title: Windowsos eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windowsos eszközök kezelésének beállítása
Az Intune-nal megteremthetők a saját eszközök használatának (BYOD) feltételei a Windows-eszközök regisztrálásával, ezáltal gondoskodva a vállalati levelezés és erőforrások eléréséről. Az Azure Active Directoryval együtt használva ezzel gyorsan, az eszköz megérintése nélkül vonhatja felügyelet alá az új, Windows 10 rendszerű eszközöket, és szerezhet hozzáférést a vállalati erőforrásokhoz anélkül, hogy új lemezképet kellene telepíteni a számítógépre. A regisztráció után a felhasználók bejelentkezhetnek, és az Intune felügyeleti konzol segítségével eszközeiket szabályzatokkal, alkalmazásokkal és beállításokkal célozhatják. Dönthet a [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-phone-management-with-microsoft-intune.md) mellett is, vagy [kezelheti az Intune ügyfélszoftverrel rendelkező gépeit](manage-windows-pcs-with-microsoft-intune.md) az Intune ügyfél használatával.

DNS CNAME rekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

### Windowsos eszközök kezelésének beállítása

  1.  Hozza létre a megfelelő **CNAME** DNS erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 óra|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  Az [Intune felügyeleti konzolján](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows** lehetőséget..
  ![Windowsos eszközök kezelése párbeszédpanel](../media/enroll-intune-winenr.png)
  3.  Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, és kattintson az **Automatikus észlelés tesztelése** elemre..

### További információ
[Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


