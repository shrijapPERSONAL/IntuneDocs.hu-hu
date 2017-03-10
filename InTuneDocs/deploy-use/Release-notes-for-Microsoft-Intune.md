---
title: "A Microsoft Intune kibocsátási megjegyzései | Microsoft Docs"
description: "Az Intune kibocsátási megjegyzései"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0e027d1c63435084c434c591fed7bb71b5c07f2
ms.openlocfilehash: 8369cc039ac1c4c24b29927a96360cd872f8e9bc
ms.lasthandoff: 03/08/2017


---

# <a name="release-notes-for-microsoft-intune"></a>A Microsoft Intune kibocsátási megjegyzései

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune egy integrált, felhőalapú ügyfél-felügyeleti megoldás, amely az eszközöket, jelentéseket és a Windows a legújabb verziójára történő frissítést lehetővé tevő licenceket biztosít. Emellett elősegíti a számítógépek naprakészen tartását és védelmét. Ezenkívül az Intune lehetővé teszi a hálózathoz csatlakoztatott mobileszközök kezelését az Exchange ActiveSync szolgáltatással vagy közvetlenül az Intune-ban. Az alábbi kibocsátási megjegyzések a Microsoft Intune-nal kapcsolatos fontos információkat és ismert problémákat ismertetik.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>Az iOS és az Android rendszer esetében előfordulhat, hogy csoportváltás alkalmával sikertelen lesz az erőforrás-hozzáférési profilok módosítása
**Probléma:** Ha csoportváltás hatására másik e-mail-profil vagy SCEP-erőforrás-hozzáférési profil lép életbe, akkor előfordulhat, hogy a profilok ütköznek, és működésük hibás lesz. Tegyük fel például, hogy van egy e-mail-profilja, amely a helyszíni Exchange-kiszolgálóra mutat, és az „A” csoportot célozza. Ezután létrehoz egy új e-mail-profilt, amely az Exchange Online-ra mutat, és a „B” csoportot célozza. Ha az „A” csoportból a „B” csoportba helyez át felhasználókat, akkor az eszközök megőrzik a helyszíni Exchange e-mail profilt, és megkísérlik a „B” csoportot célzó Exchange Online e-mail-profil telepítését.

Ezen a ponton a következők egyike történik: 
* Ha az „A” és a „B” profil azonos, akkor az eszköz elutasítja a „B” e-mail-profilt, mert a „B” e-mail-profil már tartalmazza az „A” e-mail-profilt.
* Ha az „A” e-mail-profil eltér a „B” e-mail-profiltól, akkor, amint azt a fenti példa is említi, az eszköznek két e-mail-profilja lesz.

> [!NOTE]
> Az e-mail-profilok egymástól való megkülönböztetéséhez a rendszer ellenőrzi a felhasználónévhez használt állomásnevet és attribútumot.

Az erőforrás-hozzáférési profilt (az e-mail-profilt) a rendszer egyik esetben sem távolítja el az eszközről, nehogy véletlenül megszűnjön a felhasználó hozzáférése az e-mailhez, vagy törlődjön az ügyfél SCEP-tanúsítványa.

**Megkerülő megoldás:** Nincs.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Ha olyan Windows 8.1 rendszerű eszközt regisztrál, amelyet proxykiszolgálónak kell hitelesítenie, a regisztrálási folyamat látható ok nélkül sikertelen lesz
**Probléma:** Ha Windows 8.1 rendszerű eszközt regisztrál, és az eszközt proxykiszolgálónak kell hitelesítenie a regisztráció során, a regisztráció sikertelen lesz, ha az eszközön nincsenek gyorsítótárazva a proxykiszolgáló hitelesítő adatait. Ha a proxykiszolgáló hitelesítő adatai nincsenek gyorsítótárazva az eszközön, a regisztrálási folyamatnak meg kell várnia, hogy a felhasználó megadja a hitelesítő adatokat. A proxykiszolgáló hitelesítő adatait kérő felület azonban nem jelenik meg a regisztrálás során. Ennek eredményeképpen a regisztrálási folyamatot a proxykiszolgáló nem tudja hitelesíteni. A felhasználó számára a hiba láthatatlan marad.

**Megkerülő megoldás:** Ha az a hálózat, amelyen regisztrálni kíván egy Windows 8.1 rendszerű eszközt, hitelesített proxykiszolgáló használatát igényli, akkor a proxykiszolgáló hitelesítő adatait az eszköz regisztrálása előtt be kell állítani és menteni. Hitelesítő adatok beállítása és mentése a Windows 8.1 rendszerű eszközökön:

1.  A Windows 8.1 rendszerű eszközön nyissa meg az Internet Explorert.
2.  Amikor a rendszer kéri, adja meg a proxykiszolgáló hitelesítő adatait, majd válassza a **Jegyezze meg a hitelesítő adataimat**lehetőséget.
3.  Regisztrálja az eszközt.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>A Windows Phone 8.1 rendszerű eszközök nem regisztrálhatók a Microsoft Intune-ban, ha az eszközhitelesítés engedélyezve van az AD FS-ben
**Probléma:** A Windows Phone 8.1-eszközök regisztrálása sikertelen lesz, ha az opcionális eszközhitelesítési beállítás engedélyezve van a globális hitelesítési házirend részeként az Active Directory összevonási szolgáltatásokban (AD FS).

**Megkerülő megoldás:** Tiltsa le az eszközhitelesítést az AD FS-kiszolgálón az **Enable device authentication** (Eszközhitelesítés engedélyezése) lehetőség kiválasztásával az **Edit Global Authentication Policy**(Globális hitelesítési házirend szerkesztése) beállításban. További információ: [Hitelesítési házirendek konfigurálása](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>A Microsoft Intune App Wrapping Tool for Android nem rendelkezik beépített eltávolítási funkcióval
**Probléma:** A **Microsoft Andorid rendszerhez készült alkalmazásburkoló eszköze** nem tartalmaz olyan beépített funkciót, amellyel eltávolítható.

**Megkerülő megoldás:** Keresse meg az eszköz telepítési helyét, és törölje a könyvtárat. Az alapértelmezett telepítési hely a következő: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. További információk az alkalmazásburkoló eszközről: [Android-alkalmazások előkészítése az alkalmazásburkoló eszközzel való kezeléshez](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>A Távsegítség nem érhető el a Windows 8 vagy Windows 8.1 rendszerű számítógépeken
**Probléma:** Ebben a kiadásban a Távsegítség funkció nem érhető el a Windows 8 vagy Windows 8.1 rendszert futtató számítógépeken.

**Megkerülő megoldás:** Nincs.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Előfordulhat, hogy az automatikusan hozzáadott címzettek nem kapják meg a riasztási értesítéseket
**Probléma:** A riasztási értesítéshez automatikusan hozzáadott címzettek nem mindig kapják meg az értesítést.

**Megkerülő megoldás:** Annak érdekében, hogy a címzettek megkapják az értesítési üzeneteket, manuálisan adja hozzá a címzetteket a riasztási értesítésekhez.

## <a name="language-support-in-the-azure-portal"></a>Nyelvi támogatás az Azure-portálon
Az Azure-portál a következő nyelveket támogatja: angol, cseh, francia, holland, japán, kínai (egyszerűsített), kínai (hagyományos), koreai, lengyel, magyar, német, olasz, orosz, portugál (brazíliai), portugál (portugáliai), spanyol, svéd, török.

Az Intune felügyeleti konzol és a felhasználói mobilélmények az Azure-portál által támogatott nyelveken kívül a következő nyelveket támogatják: dán, finn, görög, norvég és román.

