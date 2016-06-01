---
# required metadata

title: Felkészülés az eszközök regisztrálására a Microsoft Intune-ban | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Felkészülés az eszközök regisztrálására a Microsoft Intune-ban
Ha lehetővé szeretné tenni, hogy alkalmazottai regisztrálni tudják mobileszközeiket (például Android, iOS és Windows Phone rendszerű eszközeiket, illetve Windows rendszerű számítógépeiket), engedélyeznie kell az eszközregisztrációt. A regisztráció engedélyezéséhez először be kell állítania egy mobileszköz-kezelő szolgáltatót, konfigurálnia kell az Intune Vállalati portált, ki kell osztania licenceket, és engedélyeznie kell a regisztrációt az adott eszközplatform számára.

## <a name="BKMK_Set_MDM_Authority"></a>A mobileszköz-kezelő szolgáltató beállítása
A mobileszköz-felügyeleti szolgáltató határozza meg azt a felügyeleti szolgáltatást, amely az eszközök kezelésére jogosult. MDM-szolgáltató lehet például az Intune önmagában, illetve az Intune-nal bővített Configuration Manager. Ha a Configuration Manager van beállítva felügyeleti szolgáltatóként, nem használhat más szolgáltatást a mobileszközök felügyeletére.

>[!IMPORTANT]
> Alaposan fontolja meg, hogy a mobileszközöket csak az Intune használatával (online szolgáltatás), vagy a System Center Configuration Managerbe integrált Intune-nal szeretné-e kezelni (helyszíni szoftveres megoldás online szolgáltatással együtt). A mobileszköz-kezelő szolgáltató beállítása után a szolgáltató nem módosítható.



1.  A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** elemre..

2.  A **Feladatok** listában kattintson a **Mobileszköz-kezelő szolgáltatás beállítása**elemre. Megnyílik az **MDM szolgáltatás beállítása** párbeszédpanel.

    ![Az MDM-szolgáltató megadása párbeszédpanel](../media/intune-mdm-authority.png)

3.  Az Intune annak megerősítését kéri, hogy be szeretné állítani MDM-szolgáltatóként. Ha az Intune-t szeretné használni a mobileszközök kezeléséhez, jelölje be a jelölőnégyzetet, és kattintson az **Igen** lehetőségre.

## Az Intune Vállalati portál konfigurálása és licencek hozzárendelése
Az Intune Vállalati portál segítségével a felhasználók hozzáférhetnek a vállalat erőforrásaihoz, például az alkalmazásokhoz, információt kérhetnek a segélyszolgálattól, illetve elvégezhetik az eszközök regisztrálását és regisztrációjuk törlését. Az eszközök regisztrálása előtt el kell végeznie a [Vállalati portál konfigurálását](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Ezenkívül [ki kell osztania felhasználói licenceket](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) az Intune elérésének engedélyezéséhez.

## Eszközkezelés beállítása
A mobileszköz-kezelő szolgáltató beállítása után meg kell adnia az eszközkezelési beállításokat a szervezet által támogatni kívánt operációs rendszerekhez. Az eszközkezelés beállításához szükséges lépések az operációs rendszertől függően változhatnak. Android operációs rendszer esetén például semmit sem kell megadnia az Intune felügyeleti konzolon. Windows- és iOS-eszközökön azonban a felügyelet engedélyezéséhez megbízhatósági kapcsolatot kell beállítani az eszközök és az Intune között.

> [!div class="op_single_selector"]
- [Androidos eszközök Microsoft Intune-beli kezelésének beállítása](set-up-android-management-with-microsoft-intune.md)
- [Az iOS kezelésének beállítása a Microsoft Intune-nal](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-phone-management-with-microsoft-intune.md)
- [Windowsos eszközök Microsoft Intune-beli kezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md)

További lehetőségek:
 - Több eszköz regisztrálásához használja a [készülékregisztráció-kezelői fiókot](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - A [Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) című témakör az eszközök regisztrálásához, illetve a szabályzatok célzásához nyújt segítséget.


<!--HONumber=May16_HO1-->


