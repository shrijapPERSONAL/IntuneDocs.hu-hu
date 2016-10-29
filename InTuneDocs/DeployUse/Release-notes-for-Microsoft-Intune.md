---
title: "A Microsoft Intune kibocsátási megjegyzései | Microsoft Intune"
description: "Az Intune kibocsátási megjegyzései"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f1147e5fe766bc4642439c4ad23b2fdfbf74bb03
ms.openlocfilehash: da476088435d6ef8bd58ecad1b221254a30858cc


---

# A Microsoft Intune kibocsátási megjegyzései
A Microsoft Intune egy integrált, felhőalapú ügyfél-felügyeleti megoldás, amely az eszközöket, jelentéseket és a Windows a legújabb verziójára történő frissítést lehetővé tevő licenceket biztosít. Emellett elősegíti a számítógépek naprakészen tartását és védelmét. Ezenkívül az Intune lehetővé teszi a hálózathoz csatlakoztatott mobileszközök kezelését az Exchange ActiveSync szolgáltatással vagy közvetlenül az Intune-ban. Az alábbi kibocsátási megjegyzések a Microsoft Intune-nal kapcsolatos fontos információkat és ismert problémákat ismertetik.


## Az Android-felhasználók nem tudnak e-mailt küldeni, ha az Exchange Online-hoz feltételes hozzáférést megvalósították

**Probléma:** Az eszközükön Samsung Android 5.1.1-es vagy újabb rendszert futtató felhasználók nem tudnak e-mailt küldeni, ha az Exchange Online-hoz feltételes hozzáférés van beállítva. A Samsung elismerte, hogy a hiba az Android 5.1.1-es és újabb rendszerek beépített e-mail-ügyfélprogramjában van, és vizsgálja a javítás lehetőségét.

**1. megkerülő megoldás:** Javasolja a végfelhasználóknak, hogy használják az Androidhoz készült Outlook alkalmazást.

**2. megkerülő megoldás:** Ahhoz, hogy az érintett felhasználók e-mail-üzeneteket küldhessenek, hajtsa végre a következő lépéseket:

1. Minden egyes érintett felhasználót vegye fel egy olyan biztonsági csoportba, amely az Exchange Online feltételes hozzáférési szabályzatának „kivétel alá eső csoportok” részébe tartozik.
2. Engedélyezze a felhasználó számára, hogy szinkronizálja az e-mailjeit a beépített e-mail-ügyfélprogrammal.
3. Távolítsa el az érintett felhasználót a kivétel alá eső csoportból, majd győződjön meg arról, hogy a felhasználó már tud e-mailt küldeni.

A Microsoft továbbra is szorosan együttműködik a Samsunggal a javítás vagy a további megkerülő megoldások kidolgozásában.



## Az iOS és az Android rendszer esetében előfordulhat, hogy csoportváltás alkalmával sikertelen lesz az erőforrás-hozzáférési profilok módosítása
**Probléma:** Ha csoportváltás hatására másik e-mail-profil vagy SCEP-erőforrás-hozzáférési profil lép életbe, akkor előfordulhat, hogy a profilok ütköznek, és működésük hibás lesz. Tegyük fel például, hogy van egy e-mail-profilja, amely a helyszíni Exchange-kiszolgálóra mutat, és az „A” csoportot célozza. Ezután létrehoz egy új e-mail-profilt, amely az Exchange Online-ra mutat, és a „B” csoportot célozza. Ha az „A” csoportból a „B” csoportba helyez át felhasználókat, akkor az eszközök megőrzik a helyszíni Exchange e-mail profilt, és megkísérlik a „B” csoportot célzó Exchange Online e-mail-profil telepítését.

Ezen a ponton a következők egyike történik: 
* Ha az „A” és a „B” profil azonos, akkor az eszköz elutasítja a „B” e-mail-profilt, mert a „B” e-mail-profil már tartalmazza az „A” e-mail-profilt.
* Ha az „A” e-mail-profil eltér a „B” e-mail-profiltól, akkor, amint azt a fenti példa is említi, az eszköznek két e-mail-profilja lesz.

> [!NOTE]
> Az e-mail-profilok egymástól való megkülönböztetéséhez a rendszer ellenőrzi a felhasználónévhez használt állomásnevet és attribútumot.

Az erőforrás-hozzáférési profilt (az e-mail-profilt) a rendszer egyik esetben sem távolítja el az eszközről, nehogy véletlenül megszűnjön a felhasználó hozzáférése az e-mailhez, vagy törlődjön az ügyfél SCEP-tanúsítványa.

**Megkerülő megoldás:** Nincs.

## Ha olyan Windows 8.1 rendszerű eszközt regisztrál, amelyet proxykiszolgálónak kell hitelesítenie, a regisztrálási folyamat látható ok nélkül sikertelen lesz
**Probléma:** Ha Windows 8.1 rendszerű eszközt regisztrál, és az eszközt proxykiszolgálónak kell hitelesítenie a regisztráció során, a regisztráció sikertelen lesz, ha az eszközön nincsenek gyorsítótárazva a proxykiszolgáló hitelesítő adatait. Ha a proxykiszolgáló hitelesítő adatai nincsenek gyorsítótárazva az eszközön, a regisztrálási folyamatnak meg kell várnia, hogy a felhasználó megadja a hitelesítő adatokat. A proxykiszolgáló hitelesítő adatait kérő felület azonban nem jelenik meg a regisztrálás során. Ennek eredményeképpen a regisztrálási folyamatot a proxykiszolgáló nem tudja hitelesíteni. A felhasználó számára a hiba láthatatlan marad.

**Megkerülő megoldás:** Ha az a hálózat, amelyen regisztrálni kíván egy Windows 8.1 rendszerű eszközt, hitelesített proxykiszolgáló használatát igényli, akkor a proxykiszolgáló hitelesítő adatait az eszköz regisztrálása előtt be kell állítani és menteni. Hitelesítő adatok beállítása és mentése a Windows 8.1 rendszerű eszközökön:

1.  A Windows 8.1 rendszerű eszközön nyissa meg az Internet Explorert.
2.  Amikor a rendszer kéri, adja meg a proxykiszolgáló hitelesítő adatait, majd válassza a **Jegyezze meg a hitelesítő adataimat**lehetőséget.
3.  Regisztrálja az eszközt.

## A Windows Phone 8.1 rendszerű eszközök nem regisztrálhatók a Microsoft Intune-ban, ha az eszközhitelesítés engedélyezve van az AD FS-ben
**Probléma:** A Windows Phone 8.1-eszközök regisztrálása sikertelen lesz, ha az opcionális eszközhitelesítési beállítás engedélyezve van a globális hitelesítési házirend részeként az Active Directory összevonási szolgáltatásokban (AD FS).

**Megkerülő megoldás:** Tiltsa le az eszközhitelesítést az AD FS-kiszolgálón az **Enable device authentication** (Eszközhitelesítés engedélyezése) lehetőség kiválasztásával az **Edit Global Authentication Policy**(Globális hitelesítési házirend szerkesztése) beállításban. További információ: [Hitelesítési házirendek konfigurálása](http://technet.microsoft.com/library/dn486781.aspx).


## A Microsoft Intune App Wrapping Tool for Android nem rendelkezik beépített eltávolítási funkcióval
**Probléma:** A **Microsoft Andorid rendszerhez készült alkalmazásburkoló eszköze** nem tartalmaz olyan beépített funkciót, amellyel eltávolítható.

**Megkerülő megoldás:** Keresse meg az eszköz telepítési helyét, és törölje a könyvtárat. Az alapértelmezett telepítési hely a következő: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. További információk az alkalmazásburkoló eszközről: [Android-alkalmazások előkészítése az alkalmazásburkoló eszközzel való kezeléshez](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## A Távsegítség nem érhető el a Windows 8 vagy Windows 8.1 rendszerű számítógépeken
**Probléma:** Ebben a kiadásban a Távsegítség funkció nem érhető el a Windows 8 vagy Windows 8.1 rendszert futtató számítógépeken.

**Megkerülő megoldás:** Nincs.

## Előfordulhat, hogy az automatikusan hozzáadott címzettek nem kapják meg a riasztási értesítéseket
**Probléma:** A riasztási értesítéshez automatikusan hozzáadott címzettek nem mindig kapják meg az értesítést.

**Megkerülő megoldás:** Annak érdekében, hogy a címzettek megkapják az értesítési üzeneteket, manuálisan adja hozzá a címzetteket a riasztási értesítésekhez.

## Nyelvi támogatás az Azure-portálon
Az Azure-portál a következő nyelveket támogatja: angol, cseh, francia, holland, japán, kínai (egyszerűsített), kínai (hagyományos), koreai, lengyel, magyar, német, olasz, orosz, portugál (brazíliai), portugál (portugáliai), spanyol, svéd, török.

Az Intune felügyeleti konzol és a felhasználói mobilélmények az Azure-portál által támogatott nyelveken kívül a következő nyelveket támogatják: dán, finn, görög, norvég és román.



<!--HONumber=Oct16_HO2-->


