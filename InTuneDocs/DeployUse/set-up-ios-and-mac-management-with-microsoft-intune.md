---
# required metadata

title: iOS- és Mac-eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS- és Mac-eszközök kezelésének beállítása
A Microsoft Intune-nal megteremthetők a saját eszközök használatának (BYOD) feltételei iPhone-, iPad- és Mac-felhasználók számára az iOS- és Mac OS X-eszközök regisztrálásával, ezáltal a vállalati levelezés és erőforrások elérésének biztosításával. A regisztráció után a felhasználók telepíthetik az Intune Vállalati portál alkalmazást, és eszközeik célozhatók lesznek a szabályzatokkal az Intune felügyeleti konzolon.

Az iOS-eszközöknek az Intune-beli kezeléséhez az eszközöknek képesnek kell lenniük az Intune-nal való kommunikációra. Az Apple által igényelt, Intune szolgáltatással való megbízhatósági kapcsolat az Apple Push Notification (APN) szolgáltatásból importált tanúsítvánnyal biztosítható.

1.  **Az Intune beállítása**<br>
    Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2.  **Tanúsítvány-aláírási kérelem beszerzése**<br>
    Rendszergazda felhasználóként nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com), navigáljon a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS és Mac OS X** &gt; **APNs-tanúsítvány feltöltése** lapra, és kattintson az **APNs-tanúsítványkérelem letöltése** elemre. Mentse helyileg a tanúsítvány-aláírási kérelem (.csr) fájlját. A .csr fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

    ![APNs-tanúsítvány feltöltése párbeszédpanel](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Tanúsítvány beszerzése az Apple leküldéses értesítési szolgáltatáshoz**<br>
    Keresse fel az [Apple Push Certificates portált](http://go.microsoft.com/fwlink/?LinkId=269844) , és jelentkezzen be vállalati Apple-azonosítójával az APNs-tanúsítvány létrehozásához a .csr kiterjesztésű fájllal. Az Apple Push Certificates portál **Upload** (Feltöltés) gombjára való kattintás után egy .json kiterjesztésű fájlt fog kapni, amely nem használható az APN szolgáltatáshoz. Fejezze be a letöltést, és térjen vissza az Apple Push Certificates portálra a **Certificates for Third-Party Servers** (Tanúsítványok külső kiszolgálóknak) lapra, majd kattintson a **Download** (Letöltés) elemre..

    Töltse le az APNs-tanúsítványt (.pem), és mentse helyileg a fájlt. Később ezzel az Apple-azonosítóval újíthatja meg az APNs-tanúsítványt.

4.  **Az APNs-tanúsítvány hozzáadása az Intune-hoz**<br>
    A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS és Mac OS X** &gt; **APNs-tanúsítvány feltöltése** lapra, majd kattintson **Az APNs-tanúsítvány feltöltése**. **Tallózás** elemre a tanúsítvány megkereséséhez, kattintson a **Megnyitás** elemre, végül adja meg **Apple ID** azonosítóját. Az APNs-tanúsítvány lehetővé teszi, hogy az Intune iOS-eszközöket regisztráljon a szabályzatok regisztrált mobileszközökre való leküldésével.

5.  **A felhasználók tájékoztatása a vállalati erőforrások eléréséről a vállalati portál használatával**<br>
    A felhasználóknak tudniuk kell, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken. [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Ha az iOS-eszközöket vállalata vagy szervezete vásárolja meg a felhasználóknak, az eszközöket [vállalat által birtokolt iOS-eszközökként](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) is regisztrálhatja a felügyelethez..

### Lásd még:
[Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


