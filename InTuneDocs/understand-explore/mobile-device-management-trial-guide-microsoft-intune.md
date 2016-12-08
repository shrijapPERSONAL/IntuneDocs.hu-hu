---
title: "Mobileszköz-kezelés kipróbálása a Microsoft Intune-ban| Microsoft Docs"
description: "Kipróbálhatja a mobileszköz-kezelést az Intune ingyenes próbaverziójában."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Mobileszköz-kezelés kipróbálása a Microsoft Intune-ban
Ez az útmutató a próbaverzióhoz bemutatja a mobileszköz-kezelés működését az Intune-ban. A következőket kell tennie:
- Az eszközök regisztrálása az Intune általi kezeléshez.
- Csoportok létrehozása a felhasználók és eszközök rendszerezéséhez.
- Néhány eszközkezelési szabályzat létrehozása és üzembe helyezése a csoportokban.
- Alkalmazás közzététele, annak érdekébe, hogy a regisztrált eszközökkel rendelkező felhasználók telepíthessék az alkalmazást az eszközeikre.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Előfeltételek
Ez az útmutató feltételezi, hogy a próbaverziót kizárólag kipróbálás céljából használja, és előfizetéskor tiszta környezettel szeretne kezdeni.

Annak érdekébe, hogy megkönnyítsük Önnek a próba első lépéseit, egy nagyon egyszerű környezetet állítunk be, amely csak Intune-t használ, és feltételezi, hogy az Intune lesz az Ön mobileszköz-kezelő szolgáltatója. Az útmutató során a részletesebb technikai tartalomra is felhívjuk figyelmét, ha mélyebbre szeretne ásni.

Az előfizetéses verzió minden funkciója elérhető a próbaverzióban, az egyetlen különbség az, hogy a próbaverzióban legfeljebb 100 felhasználói fiókja lehet.

## <a name="whats-not-covered"></a>Miről nem esik szó
|Ha érdeklik az alábbiak |Olvassa el ezt |
|------------------------|----------|
|Mobileszköz-kezelés (MDM) nem tesztelési környezetben | [Első lépések](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|Az MDM Intune-nal és a System Center Configuration Managerrel való együttes használata | [Hibrid mobileszköz-kezelés](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

A fenti útmutatók hosszabbak és több döntési ponttal rendelkeznek, mint az útmutató a próbaverzióhoz, mivel azok az Intune munkakörnyezetekben való beállításában segítenek.

Ahhoz, hogy gyorsan megismerkedjen az Intune-nal azt javasoljuk, hogy kezdje a próbaverzióhoz készült útmutatóval, majd folytassa a többi útmutatóval.

## <a name="prerequisites-for-this-evaluation"></a>A kipróbálás előfeltételei
- Internet Explorer 10 vagy újabb
- Egy eszköz, amellyel tesztelheti, hogy az Intune-felhasználók hogyan regisztrálhatják és kezelhetik eszközekeit a Céges portál használatával. Ehhez az útmutatóhoz egy iPadet és egy Android telefont használunk.
- Az iPad vagy más iOS-eszköz kezeléséhez szüksége lesz az [Apple Push Notification szolgáltatás tanúsítványára](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- [Intune próba-előfizetés](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>MDM-szolgáltató beállítása
A mobileszközök Intune-nal való kezeléséhez elsőként be kell állítania a **mobileszköz-kezelési (MDM) szolgáltatót**.

Ha egyedül az Intune-t használja, ahogyan a próbaverzió feltételezi, vagy az Intune-t egy Enterprise Mobility + Security (EMS) előfizetés részeként használja, akkor az Intune-t kell beállítania mobileszköz-kezelési szolgáltatóként. Ez azt jelenti, hogy az Intune-t jelöli meg a mobileszközeinek kezelésére használt szolgatátásként a munkahelyén.

Azok az ügyfelek, akik az Intune-t a System Center Configuration Managerrel együtt szeretnék használni a mobileszközök kezelésére, el kell dönteniük, hogy az Intune-t vagy a Configuration Manager-t szeretnék használni mobileszköz-kezelési szolgáltatóként. A munkakörnyezetben ez egy fontos döntés, mivel jelenleg nagyon nehéz megváltoztatni ezt a beállítást, viszont ez a próbaverzióhoz készült útmutató hatókörén kívül esik. Az Intune vagy a Configuration Manager MDM-szolgáltatóként való beállításának vonzataival kapcsolatban további információért, lásd: [Választás az önálló Intune és a hibrid mobileszköz-kezelés között](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

A próbaverzióban az Intune-t állítjuk be MDM-szolgáltatóként; ez nem lesz hatással a munkakörnyezetére, hacsak nem dönt úgy, hogy a próbaverziót használja a munkakörnyezetéhez.

1. Az [Intune felügyeleti konzolon](https://manage.microsoft.com/) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** elemre.
2. A **Feladatok** listában válassza az **MDM-szolgáltató beállítása** lehetőséget. Megnyílik az **MDM szolgáltatás beállítása** párbeszédpanel. <!---screen shot--->
3. Az Intune annak megerősítését kéri, hogy be szeretné állítani MDM-szolgáltatóként. Jelölje be a jelölőnégyzetet, majd válassza az **Igen** lehetőséget az Intune mobileszközök kezelésére történő használatához.

## <a name="enroll-your-test-devices-into-intune"></a>Teszteszközök regisztrálása az Intune-ban

Ebben az útmutatóban egy Android telefont és egy Apple iPadet regisztrálunk, de a szakasz végén talál hivatkozásokat az [Intune-ba való eszközregisztrációval kapcsolatos további tudnivalókra](#Learn-more-about-device-enrollment) vonatkozóan.
### <a name="android"></a>Android
Telepítse a Microsoft Corporation által kiadott **Intune Céges portál** alkalmazást, melyet a [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) áruházban érhet el, és jelentkezzen be a próbaverzióra való regisztrációkor [létrehozott felhasználó hitelesítő adataival](sign-up-for-30-day-trial-microsoft-intune.md#add-users).

### <a name="ios"></a>iOS
Mielőtt a felhasználók regisztrálnák az iOS-eszközeiket, be kell állítania, hogy az Intune kezelje ezeket az eszközöket.

1. **Tanúsítvány-aláírási kérelem beszerzése**<br/>
Jelentkezzen be a rendszergazda fiókjával, és navigáljon a **Felügyelet** > **Mobileszköz-kezelés** > **iOS és Mac OS X** > **APNs-tanúsítvány feltöltése** lapra, és kattintson az **APNs-tanúsítványkérelem letöltése** elemre. Mentse helyileg a tanúsítvány-aláírási kérelem (.csr) fájlját. A .csr fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál. <!--- screen shot--->
2.  **Az APNs-tanúsítvány beszerzése**<BR/>
Keresse fel az [Apple Push Certificates portált](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2), és jelentkezzen be vállalati Apple-azonosítójával az APNs-tanúsítvány létrehozásához a .csr kiterjesztésű fájllal. Az **Apple Push Certificates portál Upload (Feltöltés)** gombjára való kattintás után egy .json kiterjesztésű fájlt fog kapni, amely nem használható az APN szolgáltatáshoz. Fejezze be a letöltést, térjen vissza az Apple Push Certificates portálra a Certificates for Third-Party Servers (Tanúsítványok külső kiszolgálóknak) lapra, majd kattintson a **Download** (Letöltés) elemre.

 Töltse le az APNs-tanúsítványt (.pem), és mentse helyileg a fájlt. Később ezzel az Apple-azonosítóval újíthatja meg az APNs-tanúsítványt.
3.  **Az APNs-tanúsítvány hozzáadása az Intune-hoz**<BR/>
A Microsoft Intune felügyeleti konzolon lépjen a **Felügyelet** > **Mobileszköz-kezelés** > **iOS és Mac OS X** > **APNs-tanúsítvány feltöltése** menüpontra, majd kattintson **Az APNs-tanúsítvány feltöltése** elemre. Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és adja meg az Apple ID azonosítóját. Az APNs-tanúsítvány lehetővé teszi, hogy az Intune iOS-eszközöket regisztráljon és kezeljen a szabályzatok regisztrált mobileszközökre való leküldésével.
4.  **Mondja el a felhasználóknak, miként regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez.**<br/>
A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [iOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios), illetve [Mac OS X-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). A beléptetési folyamat tájékoztatja a felhasználókat, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.


### <a name="learn-more-about-device-enrollment"></a>További tudnivalók az eszközregisztrációról

Az Intune a következő eszközplatformokat támogatja:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Az eszközkezelés engedélyezésének követelményei a kezelni kívánt platformoktól függnek.
- Az **Android** rendszerű mobileszközök lehetővé teszik, hogy a felhasználók a Google Play áruházban elérhető [Céges portál alkalmazással regisztráljanak](/intune/deploy-use/set-up-android-management-with-microsoft-intune). Így nincs szükség további Intune konfigurációra.
- [Telepítési követelmények **iOS és Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) esetén.
- [Telepítési követelmények **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) esetén.

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>További lépések
[Csoportok létrehozása a felhasználók és eszközök rendszerezéséhez](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Nov16_HO5-->


