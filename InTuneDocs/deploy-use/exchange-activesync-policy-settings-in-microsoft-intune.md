---
title: "Exchange ActiveSync szabályzatbeállításai | Microsoft Docs"
description: "Az Intune Exchange ActiveSync-szabályzatának használatával megadhatók azok a beállítások, amelyekkel az Exchange ActiveSync által kezelt eszközök szolgáltatásai és funkciói vezérelhetővé válnak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: c4023007f993436e0d7628cce52f78a1127c88f8
ms.lasthandoff: 04/24/2017


---

# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a>Exchange ActiveSync házirend-beállítások a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune **Exchange ActiveSync**-házirendjének használatával megadhatók azok a beállítások, amelyekkel az Exchange ActiveSync által kezelt eszközök szolgáltatásai és funkciói széles körben vezérelhetővé válnak.


## <a name="password-settings"></a>Jelszóbeállítások

|Beállítás neve|Részletek
|----------------|---|
|**Jelszó szükséges a mobileszközök feloldásához**|Meghatározza, hogy az eszközöket jelszóval kell-e zárolni.<br>(a Windows RT rendszerű eszközökre nem vonatkozik).|
|**Kötelező jelszótípus**|A megkövetelt jelszótípust határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.|
|**Jelszó minimális hossza**|Az eszközhöz használt jelszóban használandó karakterek minimális számát határozza meg.|
|**Egyszerű jelszavak engedélyezése**|Meghatározza, hogy használható-e egyszerű jelszó, például „0000” vagy „1234”.|
|**Ennyi ismétlődő sikertelen bejelentkezés után törlődnek végleg az adatok az eszközről**|Azt a számot adja meg, ahányszor a felhasználó helytelen jelszót adhat meg, mielőtt a rendszer törölné az eszközt.|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.
|**Jelszóelőzmények megjegyzése**|Megadja, hogy használhatók-e a korábban már használt jelszavak.|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Meghatározza, hogy hány jelszóra visszamenőleg nem használható egy már korábban használt jelszó.|
|**Jelszó kérése ennyi perc inaktivitás után**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.

## <a name="encryption-settings"></a>Titkosítási beállítások

|Beállítás neve|Részletek|
|----------------|---|
|**Titkosítás megkövetelése mobileszközön**<sup>1</sup>|Ha az eszköz támogatja a titkosítást, titkosítani kell a rajta lévő adatokat.<br><br>A Windows Phone 8-telefonokon ezt **Igen**értékre kell állítani.<br /><br />Az iOS-eszközök titkosításának engedélyezéséhez **A mobileszközök zárolásának feloldásához jelszó szükséges**beállítást engedélyezni kell.|
|**Titkosítás megkövetelése tárolókártyákon**|A külső tárhelyen, például egy SD-kártyán tárolt adatok titkosítása szükséges (a támogatott eszközökön).
<sup>1</sup> További információ a Windows 8.1 rendszerű eszközökhöz

-   A Windows 8.1 rendszerű eszközökön a titkosítás kényszerítéséhez minden egyes eszközön telepíteni kell a következőt: [2014. decemberi MDM-ügyfélfrissítés Windows rendszerre](https://support.microsoft.com/kb/3013816) .

-   Ha engedélyezi ezt a beállítást a Windows 8.1 rendszerű eszközökön, az eszköz valamennyi felhasználójának rendelkeznie kell Microsoft-fiókkal.

-   Windows 8.1 rendszerű eszközökön a titkosítás működéséhez az eszköznek teljesítenie kell a Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardvertanúsítvány követelményeit.

-   Amikor Windows 8.1 rendszerű eszközön kényszeríti a titkosítást, a helyreállítási kulcs csak a felhasználók Microsoft-fiókjaiból érhető el, amelyet a felhasználó OneDrive-fiókjaiból lehet elérni. Ez a kulcs nem állítható vissza egy felhasználó nevében.

## <a name="email-settings"></a>E-mail beállítások

|Beállítás neve|Részletek
|----------------|---|
|**Az e-mail-mellékletek letöltésének engedélyezése a felhasználók számára**|Megadja, hogy le lehet-e tölteni az e-mail mellékleteket az eszközre.|
|**E-mail-szinkronizálási időszak**|Meghatározza, hogy hány napnyi beérkezett e-mail szinkronizálódjon az eszközzel.
|**Engedélyezze az Exchange ActiveSync-beállításokat nem teljes mértékben támogató eszközök szinkronizálását az Exchange kiszolgálóval**|A beállítással megadható, hogy engedélyezi-e az Exchange kiszolgálóhoz a hozzáférést az Exchange ActiveSync-beállításokat csak részben vagy egyáltalán nem támogató eszközök számára.

## <a name="browser-settings"></a>Webböngésző beállításai

|Beállítás neve|Részletek
|----------------|---|
|**Webböngésző engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a webböngésző.<br>(Windows RT vagy Windows Phone esetén nem érhető el.).

## <a name="hardware-settings"></a>Hardverbeállítások

|Beállítás neve|Részletek
|----------------|---|
|**Kamera engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a kamera.<br>(Windows RT vagy Windows Phone esetén nem érhető el.).



### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

