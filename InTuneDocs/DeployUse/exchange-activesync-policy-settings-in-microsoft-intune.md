---
title: "Exchange ActiveSync házirend-beállítások | Microsoft Intune"
description: "Az Intune Exchange ActiveSync-szabályzatának használatával megadhatók azok a beállítások, amelyekkel az Exchange ActiveSync által kezelt eszközök szolgáltatásai és funkciói vezérelhetővé válnak."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72e6bcd3fd480c1ed8558fefd3958b4bbf3184c2
ms.openlocfilehash: 39a844db56edf18f25996c1aaf52223ac80f8071


---

# Exchange ActiveSync házirend-beállítások a Microsoft Intune-ban
A Microsoft Intune **Exchange ActiveSync**-házirendjének használatával megadhatók azok a beállítások, amelyekkel az Exchange ActiveSync által kezelt eszközök szolgáltatásai és funkciói széles körben vezérelhetővé válnak.


## Jelszóbeállítások

|Beállítás neve|Részletek
|----------------|
|**Jelszó szükséges a mobileszközök feloldásához**|Meghatározza, hogy az eszközöket jelszóval kell-e zárolni.<br>(a Windows RT rendszerű eszközökre nem vonatkozik).|
|**Kötelező jelszótípus**|A megkövetelt jelszótípust határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.|
|**Jelszó minimális hossza**|Az eszközhöz használt jelszóban használandó karakterek minimális számát határozza meg.|
|**Egyszerű jelszavak engedélyezése**|Meghatározza, hogy használható-e egyszerű jelszó, például „0000” vagy „1234”.|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|Azt a számot adja meg, ahányszor a felhasználó helytelen jelszót adhat meg, mielőtt a rendszer törölné az eszközt.|
|**Jelszó lejárta (napokban)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.
|**Jelszóelőzmények megjegyzése**|Megadja, hogy használhatók-e a korábban már használt jelszavak.|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Meghatározza, hogy hány jelszóra visszamenőleg nem használható egy már korábban használt jelszó.|
|**Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.

## Titkosítási beállítások

|Beállítás neve|Részletek|
|----------------|
|**Titkosítás megkövetelése mobileszközön**<sup>1</sup>|Ha az eszköz támogatja a titkosítást, titkosítani kell a rajta lévő adatokat.<br><br>A Windows Phone 8-telefonokon ezt **Igen**értékre kell állítani.<br /><br />Az iOS-eszközök titkosításának engedélyezéséhez **A mobileszközök zárolásának feloldásához jelszó szükséges**beállítást engedélyezni kell.|
|**Titkosítás megkövetelése tárolókártyákon**|A külső tárhelyen, például egy SD-kártyán tárolt adatok titkosítása szükséges (a támogatott eszközökön).
<sup>1</sup> További információ a Windows 8.1 rendszerű eszközökhöz

-   A Windows 8.1 rendszerű eszközökön a titkosítás kényszerítéséhez minden egyes eszközön telepíteni kell a következőt: [2014. decemberi MDM-ügyfélfrissítés Windows rendszerre](http://support.microsoft.com/kb/3013816) .

-   Ha engedélyezi ezt a beállítást a Windows 8.1 rendszerű eszközökön, az eszköz valamennyi felhasználójának rendelkeznie kell Microsoft-fiókkal.

-   Windows 8.1 rendszerű eszközökön a titkosítás működéséhez az eszköznek teljesítenie kell a Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardvertanúsítvány követelményeit.

-   Amikor Windows 8.1 rendszerű eszközön kényszeríti a titkosítást, a helyreállítási kulcs csak a felhasználók Microsoft-fiókjaiból érhető el, amelyet a felhasználó OneDrive-fiókjaiból lehet elérni. Ez a kulcs nem állítható vissza egy felhasználó nevében.

## E-mail beállítások

|Beállítás neve|Részletek
|----------------|
|**Az e-mail mellékletek letöltésének engedélyezése a felhasználók számára**|Megadja, hogy le lehet-e tölteni az e-mail mellékleteket az eszközre.|
|**E-mail szinkronizálási időszak**|Meghatározza, hogy hány napnyi beérkezett e-mail szinkronizálódjon az eszközzel.
|**Engedélyezze az Exchange ActiveSync-beállításokat nem teljes mértékben támogató eszközök szinkronizálását az Exchange kiszolgálóval**|A beállítással megadható, hogy engedélyezi-e az Exchange kiszolgálóhoz a hozzáférést az Exchange ActiveSync-beállításokat csak részben vagy egyáltalán nem támogató eszközök számára.

## Webböngésző beállításai

|Beállítás neve|Részletek
|----------------|-
|**Webböngésző használatának engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a webböngésző.<br>(Windows RT vagy Windows Phone esetén nem érhető el.).

## Hardverbeállítások

|Beállítás neve|Részletek
|----------------|
|**Kamera használatának engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a kamera.<br>(Windows RT vagy Windows Phone esetén nem érhető el.).



### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO5-->


