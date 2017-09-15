---
title: "Támogatott eszközök – Microsoft Intune"
description: "Az Intune-eszközkezelés által támogatott eszközplatformok és böngészők listája"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 00fc685062c090b40e20ed3dfa30afbeeb5c9780
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
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
