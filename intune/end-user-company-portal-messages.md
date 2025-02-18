---
title: Felhasználók által is látható Céges portál-üzenetek az eszközökön
titleSuffix: Microsoft Intune
description: A cikk azokat az üzeneteket ismerteti, amelyeket a végfelhasználók láthatnak a Céges portálon.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/09/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2168c39c80369e16284078df608bdab5f29858c6
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59894965"
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>A Vállalati portál alkalmazás üzeneteinek ismertetése a végfelhasználókkal

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> A következő információk kizárólag Android 6.0-s és újabb rendszerű eszközökre vonatkoznak.

A cikk azokat az alkalmazásüzeneteket ismerteti, amelyeket a végfelhasználók láthatnak a Céges portálon. Az alkalmazásüzenetek általában a regisztrációs folyamat különféle szakaszaiban jelennek meg. A cikk bemutatja, hol jelennek meg az üzenetek, milyen konkrét jelentésük van, és hogy mi történik, ha a felhasználók nem adnak hozzáférést. Ezen kívül megtudhatja, hogyan érdemes az üzeneteket ismertetni a felhasználók számára.

- __Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)__
- __Allow Company Portal to access photos, media, and files on your device? (Engedélyezi a Munkahelyi portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?)__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)

### <a name="where-it-appears"></a>Megjelenési helye
Az **Allow Company Portal to make and manage phone calls?** (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?) üzenet akkor jelenik meg, amikor az eszköz regisztrációja során a felhasználók a **Regisztráció** elemre koppintanak a Vállalati portál alkalmazásban.

### <a name="what-it-means"></a>Jelentés
Megerősítő válasszal a felhasználó engedélyezi, hogy az eszköz telefonszámát és IMEI-számát elküldje a rendszer az Intune szolgáltatásnak. Ezek az információk a felügyeleti konzol __Hardver__ lapján jelennek meg.

> [!NOTE]
> **A Munkahelyi portál alkalmazás soha nem indít telefonhívásokat, és nem is kezeli azokat.** Az üzenet szövegét a Google szabja meg, és nem módosítható.

A **Hardver** lap megnyitásához válassza a **Csoportok** > **Minden mobileszköz** > **Eszközök** lehetőséget. Jelölje ki a felhasználó eszközét, és válassza a **Tulajdonságok megjelenítése** > **Hardver** lehetőséget.

### <a name="what-happens-if-users-deny-access"></a>Mi történik, ha a felhasználók nem engedélyezik a hozzáférést
Ha a felhasználó nem engedélyezi a hozzáférést, attól továbbra is használhatja a Vállalati portál alkalmazást, és regisztrálhatja az eszközeit. Az eszköz telefonszáma és IMEI-száma azonban ebben az esetben nem jelenik meg a felügyeleti konzol __Hardver__ lapján. Amikor a felhasználók a hozzáférés megtagadása után másodszor bejelentkeznek a Vállalati portál alkalmazásba, az üzenetben látható egy **Ne jelenjen meg többé** feliratú jelölőnégyzet, amelynek bejelölésével végleg kikapcsolhatják az üzenet megjelenítését.

Ha a felhasználó engedélyezi a hozzáférést, de később megtagadja azt, az üzenet újból megjelenik, amikor a felhasználó a regisztrálást követően először bejelentkezik a Vállalati portál alkalmazásba.

Amennyiben a felhasználók később ismét engedélyezni szeretnék a hozzáférést, a **Beállítások** > **Alkalmazások** > **Vállalati portál** > **Engedélyek** > **Telefon** lapon tehetik ezt meg.

### <a name="how-to-explain-this-to-your-users"></a>A felhasználók tájékoztatásának módja
További információért ajánlja a felhasználóknak az [Android-eszközök regisztrálása az Intune-ban](/intune-user-help/enroll-device-android-company-portal) című témakört.

## <a name="allow-company-portal-to-access-your-contacts"></a>Engedélyezi, hogy a Vállalati Portál hozzáférjen a névjegyekhez?

### <a name="where-it-appears"></a>Megjelenési helye
Az **Allow Company Portal to access your contacts?** (Engedélyezi, hogy a Munkahelyi portál alkalmazás hozzáférjen a névjegyekhez?) üzenet akkor jelenik meg, amikor az eszköz regisztrációja során a felhasználók a **Regisztráció** elemre koppintanak a Vállalati portál alkalmazásban.

### <a name="what-it-means"></a>Jelentés
Megerősítő válasszal a felhasználó engedélyezi az Intune számára, hogy létrehozza munkahelyi fiókjukat és kezelje az eszköz felhasználójához regisztrált Active Directory-identitást.

> [!NOTE]
> **A Microsoft soha nem fér hozzá a névjegyeihez!** Az üzenet szövegét a Google szabja meg, és nem módosítható.

### <a name="what-happens-if-users-deny-access"></a>Mi történik, ha a felhasználók nem engedélyezik a hozzáférést
Ha a felhasználó tiltja a hozzáférést, az eszköz nem regisztrál az Intune-ban és nem felügyelhető. Amikor a felhasználók a hozzáférés megtagadása után másodszor bejelentkeznek a Vállalati portál alkalmazásba, az üzenetben látható egy **Ne jelenjen meg többé** feliratú jelölőnégyzet, amelynek bejelölésével végleg kikapcsolhatják az üzenet megjelenítését.

Ha a felhasználó engedélyezi a hozzáférést, de később megtagadja azt, az üzenet újból megjelenik, amikor a felhasználó a regisztrálást követően először bejelentkezik a Vállalati portál alkalmazásba.

Amennyiben a felhasználók később ismét engedélyezni szeretnék a hozzáférést, a **Beállítások** > **Alkalmazások** > **Vállalati portál** > **Engedélyek** > **Telefon** lapon tehetik ezt meg.

### <a name="how-to-explain-this-to-your-users"></a>A felhasználók tájékoztatásának módja
További információért ajánlja a felhasználóknak az [Android-eszközök regisztrálása az Intune-ban](/intune-user-help/enroll-device-android-company-portal) című témakört.  

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Allow Company Portal to access photos, media, and files on your device? (Engedélyezi a Munkahelyi portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?)

### <a name="where-it-appears"></a>Megjelenési helye
Az **Allow Company Portal to access photos, media, and files on your device?** (Engedélyezi a Vállalati portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?) üzenet akkor jelenik meg, ha a felhasználó az **Adatok elküldése** elemre koppintva naplókat küld a rendszergazdának.

### <a name="what-it-means"></a>Jelentés
Megerősítő válasszal a felhasználó engedélyezi, hogy eszköze adatnaplókat írjon az eszköz SD-kártyájára.Megerősítő válasszal a felhasználó engedélyezi, hogy eszköze adatnaplókat írjon az eszköz SD-kártyájára. Azt is engedélyezi továbbá, hogy a rendszer ezeket a naplókat USB-kábel segítségével más helyre másolja.   

> [!NOTE]
> **A Munkahelyi portál alkalmazás sohasem próbál hozzáférni a felhasználó fényképeihez, médiatartalmaihoz és fájljaihoz.** Az üzenet szövegét a Google szabja meg, és nem módosítható.

### <a name="what-happens-if-users-deny-access"></a>Mi történik, ha a felhasználók nem engedélyezik a hozzáférést
Ha a felhasználó nem engedélyezi a hozzáférést, e-mailben akkor is elküldheti az adatnaplókat, ám azok nem másolhatók az SD-kártyára.

Amikor a felhasználók a hozzáférés megtagadása után másodszor bejelentkeznek a Vállalati portál alkalmazásba, az üzenetben látható egy **Ne jelenjen meg többé** feliratú jelölőnégyzet, amelynek bejelölésével végleg kikapcsolhatják az üzenet megjelenítését. Ha a felhasználó engedélyezi a hozzáférést, de később megtagadja, az üzenet újból megjelenik, amikor a felhasználó a legközelebb megpróbálja elküldeni a naplókat. Amennyiben azonban a felhasználók később ismét engedélyezni szeretnék a hozzáférést, a **Beállítások** > **Alkalmazások** > **Vállalati portál** > **Engedélyek** > **Tárterület** lapon tehetik ezt meg.


### <a name="how-to-explain-this-to-your-users"></a>A felhasználók tájékoztatásának módja
Ajánlja a felhasználóknak a [Naplók elküldése a rendszergazdának e-mailben](/intune-user-help/send-logs-to-your-it-admin-by-email-android) című témakört. 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>A céges ügyfélszolgálatnak hozzáférést kell nyújtania Önnek a céges erőforrásokhoz

### <a name="where-it-appears"></a>Megjelenési helye
Ha nem adta hozzá a Céges portált az **Engedélyezett alkalmazások** vagy a **Mentesített alkalmazások** listájához, és egy felhasználó megpróbál bejelentkezni, a bejelentkezés meghiúsul. Az alábbi üzenet jelenik meg:

> **A céges ügyfélszolgálatnak hozzáférést kell nyújtania Önnek a céges erőforrásokhoz**  
> A cége a Windows Információvédelem szabályzataival védi az eszközt. A céges ügyfélszolgálatnak biztosítania kell, hogy engedélyezze a Céges portálnak a hozzáférést ezekhez az erőforrásokhoz.

### <a name="what-it-means"></a>Mit jelent

Adja hozzá a céges portál a **engedélyezett alkalmazások** vagy **mentesített alkalmazások** a Windows Information Protection (WIP) alkalmazásvédelmi szabályzat listájában. További információ: [A Windows Információvédelem (WIP) alkalmazásvédelmi szabályzatainak létrehozása és bevezetése az Intune használatával](windows-information-protection-policy-create.md).

## <a name="approve-a-ios-company-app-line-of-business-app-on-your-ios-device"></a>Hagyja jóvá az iOS vállalati alkalmazások (üzleti alkalmazás) iOS-eszközön 

### <a name="where-it-appears"></a>Megjelenési helye
iOS-alkalmazásokat a szervezet által fejlesztett, amelyek nem érhető el az App Store nem talál megbízhatónak a eszköz alapértelmezés szerint. Ha ilyen vállalati portállal alkalmazásokat telepíteni, és indítsa el az alkalmazást, a következő üzenet jelenik meg:

![iOS-alkalmazás üzenet - nem megbízható nagyvállalati fejlesztő](./media/end-user-company-portal-messages/end-user-company-portal-messages-01.png)

### <a name="what-it-means"></a>Mit jelent
Ez az üzenet azt jelenti, hogy módosítania kell az iOS-eszközbeállítások jóváhagyása és telepítése az iOS-eszközön a vállalat által fejlesztett alkalmazás.

A vállalati portálon az ilyen alkalmazások telepítésekor, és indítsa el az alkalmazást, az alkalmazás jóváhagyása a letöltés után az alábbi lépésekkel:

1. Után (az üzletági alkalmazásokat) telepített munkahelyi alkalmazás elindítása, látni fogja a "Nem megbízható nagyvállalati fejlesztő" üzenet. <br>
   Nyomja meg **Mégse**.
2. Navigáljon a **beállítások** > **általános** > **Eszközkezelés**.

   ![iOS-eszköz UI - kezelés](./media/end-user-company-portal-messages/end-user-company-portal-messages-02.png)

3. Válassza ki **felügyeleti profil** > **vállalati alkalmazás**.
4. Válassza ki a fejlesztői nevét.
5. Nyomja meg **megbízható _fejlesztő neve_**.
6. Erősítse meg az alkalmazás kiválasztásával **megbízható** az alkalmazás telepítése az előugró üzenet.

   ![iOS-eszköz UI - megbízhatósági alkalmazás üzenet](./media/end-user-company-portal-messages/end-user-company-portal-messages-03.png)

    Indítsa el, és használhassák a vállalati alkalmazás kell lennie.


### <a name="see-also"></a>Lásd még:
[Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](end-user-educate.md)
