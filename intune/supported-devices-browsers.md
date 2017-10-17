---
title: "Támogatott eszközök – Microsoft Intune"
description: "Az Intune-eszközkezelés által támogatott eszközplatformok és böngészők listája"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6c9cc3a6a84c48da36b0219743012a15b72e6810
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="supported-devices-and-browsers"></a>Támogatott eszközök és böngészők

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ez a cikk a vállalatnál az eszközkezelésért felelős rendszergazdák számára készült. A következő témakörben találhat segítséget az Intune telefonra való telepítéséhez: [Using managed devices to get work done](/intune-user-help/company-portal-frequently-asked-questions) (Feladatok elvégzése kezelt eszközökön).

A Microsoft Intune beállítása előtt tekintse át az alábbi követelményeket:

- [Támogatott eszközök és számítógépek](#intune-supported-devices)
- [Az Intune használatára alkalmas böngészők listája](#intune-supported-web-browsers)

Ismerkedjen meg [az Intune hálózatisávszélesség-felhasználásával](network-bandwidth-use.md) is ([a klasszikus portálon](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Az Intune által támogatott eszközök

Az Intune a következő eszközöket képes felügyelni a mobileszköz-felügyeleti funkciókkal:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Támogatott Samsung KNOX Standard-eszközök

Az MDM-regisztráció során a Céges portál alkalmazás csak akkor kísérli meg a Samsung KNOX-aktiválást, ha az eszköz szerepel a [támogatott KNOX-eszközök listáján](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Így elkerülhetők az MDM-regisztrációt megakadályozó KNOX-aktiválási hibák. Azokat az eszközöket, melyek nem támogatják a Samsung KNOX-aktiválást, szabványos Android-eszközként regisztrálja a rendszer. Előfordulhat, hogy egy Samsung eszköz néhány modellje támogatja a KNOX platformot, míg mások nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse az eszköz viszonteladójával, hogy kompatibilis-e a KNOX-szal.

Az alábbi Samsung eszközök nem támogatják a KNOX platformot, így ezeket az androidos Céges portál alkalmazás natív Android-eszközként fogja regisztrálni:

| **Eszköz neve** | **Eszköz modellszáma** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Az Intune nem használható a Windows Server operációs rendszer felügyeletére.

### <a name="windows-pc-software-client"></a>Windowsos számítógépeken futó szoftveres ügyfél

A windowsos számítógépekre a regisztráció alternatívájaként telepítheti az [Intune szoftveres ügyfelet](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) is. Ez a funkció csak a klasszikus Intune-portálon érhető el. Az Intune szoftveres ügyfele segítségével a Windows 7 és újabb rendszerű számítógépeket felügyelheti (kivéve a Windows 10 Home verziót).

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Az Intune által támogatott webböngészők

A különféle felügyeleti tevékenységek elvégzésére a következő két felügyeleti webhely valamelyikét kell használnia.

- [Office 365 portál](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

Ezeken a portálokon jelenleg a következő böngészők támogatottak:
- Microsoft Edge (legújabb verzió)
- Microsoft Internet Explorer 11
- Safari (csak Mac, legújabb verzió)
- Chrome (legújabb verzió)
- Firefox (legújabb verzió)

### <a name="intune-classic-portal"></a>Klasszikus Intune-portál

A csak a klasszikus Intune-ban szereplő funkciók, például az Intune PC-s szoftverügyfél, vagy a Mobile Threat Defense-partnerekkel való integráció csak a klasszikus Intune-portálon (https://manage.microsoft.com) érhetők el. A klasszikus Intune-portálhoz a böngésző Silverlight-támogatása szükséges.

A klasszikus Intune-portál a következő Silverlight-kompatibilis böngészőkkel használható:
- Internet Explorer 10 vagy újabb
- Google Chrome (42-es vagy korábbi verziók)
- Mozilla Firefox (a Silverlightot engedélyezni kell) – [További információ](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> A Microsoft Edge és a mobilböngészők a klasszikus Intune-portálhoz való használata nem támogatott, mivel nem támogatják a [Microsoft Silverlightot](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

A portálra szolgáltatás-rendszergazdák, valamint globális rendszergazda szerepkörrel rendelkező bérlői rendszergazdák jelentkezhetnek be. A felügyeleti konzol eléréséhez a fióknak az Intune használatához szükséges licenccel, illetve **Engedélyezett** bejelentkezési állapottal kell rendelkeznie.
