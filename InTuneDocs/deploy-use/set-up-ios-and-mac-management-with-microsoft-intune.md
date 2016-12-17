---
title: "iOS- és Mac-eszközök kezelésének beállítása | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése a Microsoft Intune-nal iOS-eszközök (iPadek és iPhone-ok), illetve Mac OS X-eszközök esetén."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 641d2db2bfb49ce6c4f88d823188a714e61f683c


---

# <a name="set-up-ios-and-mac-device-management"></a>iOS- és Mac-eszközök kezelésének beállítása
Az Intune lehetőséget nyújt az iPadek, iPhone-ok és Mac OS X-eszközök mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz. Az iOS- és Mac-eszközök Intune-felügyeletéhez szüksége lesz egy Apple Push Notification- (APN-) tanúsítványra. Miután hozzáadta a tanúsítványt az Intune-hoz, a felhasználók telepíthetik a Vállalati portál alkalmazást az eszközeik regisztrálásához, vagy a rendszergazda beállíthatja [a vállalati tulajdonú iOS-eszközök felügyeletét](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Az Intune beállítása**<br>
    Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#step-2-set-mdm-authority), valamint beállítja a mobileszköz-kezelést.

2.  **Tanúsítvány-aláírási kérelem beszerzése**<br>
    Rendszergazda felhasználóként nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS és Mac OS X** &gt; **APNs-tanúsítvány feltöltése** menüpontra, majd kattintson **Az APNs-tanúsítvány feltöltése** elemre. Mentse helyileg a tanúsítvány-aláírási kérelem (.csr) fájlját. A .csr fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

    ![APNs-tanúsítvány feltöltése párbeszédpanel](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Az APNs-tanúsítvány beszerzése**<br>
    Keresse fel az [Apple Push Certificates portált](http://go.microsoft.com/fwlink/?LinkId=269844), és jelentkezzen be vállalati Apple-azonosítójával az APNs-tanúsítvány létrehozásához a .csr kiterjesztésű fájllal. Az Apple Push Certificates portál **Upload** (Feltöltés) gombjára való kattintás után egy .json kiterjesztésű fájlt fog kapni, amely nem használható az APN szolgáltatáshoz. Fejezze be a letöltést, térjen vissza az Apple Push Certificates portálra a **Certificates for Third-Party Servers** (Tanúsítványok külső kiszolgálóknak) lapra, majd kattintson a **Download** (Letöltés) elemre.

    Töltse le az APNs-tanúsítványt (.pem), és mentse helyileg a fájlt.

    > [!NOTE]
    > Ezt az APNs-tanúsítványt minden évben meg kell újítani (nem lecserélni). Ugyanezen Apple ID használatával jelentkezzen be az Apple Push Certificate portáljára a tanúsítvány megújításához, majd kövesse a jelen témakörben szereplő ugyanezen utasításokat a tanúsítvány letöltéséhez, majd az Intune-ba való feltöltéséhez.

4.  **Az APNs-tanúsítvány hozzáadása az Intune-hoz**<br>
    A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS és Mac OS X** &gt; **APNs-tanúsítvány feltöltése** menüpontra, majd kattintson **Az APNs-tanúsítvány feltöltése** elemre. Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és adja meg az **Apple ID** azonosítóját. Az APNs-tanúsítvány lehetővé teszi, hogy az Intune iOS-eszközöket regisztráljon a szabályzatok regisztrált mobileszközökre való leküldésével.

5.  **Mondja el a felhasználóknak, miként regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [iOS-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-ios.md), illetve [Mac OS X-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-macos.md). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

    Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
    - [Információk végfelhasználóknak a Microsoft Intune használatáról](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Végfelhasználói útmutató iOS és Mac rendszerű eszközökhöz](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Ha az iOS-eszközöket vállalata vagy szervezete vásárolja meg a felhasználóknak, az eszközöket [vállalat által birtokolt iOS-eszközökként](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) is regisztrálhatja a felügyelethez.

### <a name="see-also"></a>Lásd még:
[A Microsoft Intune-beli regisztráció előfeltételei](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO2-->

