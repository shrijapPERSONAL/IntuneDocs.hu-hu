---
title: Titkosítási jelentés és a Microsoft Intune-ban a BitLocker-kulcsok
titleSuffix: Microsoft Intune
description: Az Eszközállapot-titkosítást az jelentés megtekintéséhez, és hozzáférési a BitLocker helyreállítási kulcsok, a Microsoft Intune-portálon.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 43cef2e5a07795bc4c6dc7cf42b2cfa6be04269f
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292258"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>A figyelő a BitLocker és az eszköz titkosítása  
Az Intune kínál egy központi helyen, azonosíthatja a Windows 10 rendszerű eszközök titkosítási állapotát, és elérhetővé teszi a BitLocker vonatkozó fontos információk az eszközök, az Azure Active Directoryban (Azure AD) formában.  

- A [(nyilvános előzetes verzióban) titkosítása jelentés](encryption-monitor.md#encryption-report-in-public-preview) eszközök titkosítási állapotát és a készültségi részletesen ismerteti. A jelentés-részletek segítségével azonosíthatja a problémákat, amelyek meggátolják a védeni kívánt eszközök sikeres titkosítását.  
- [A BitLocker részleteinek megtekintése (a nyilvános előzetes verzió)](encryption-monitor.md#bitlocker-recovery-keys-in-public-preview) , például a Kulcsazonosító és a helyreállítási kulcsok az eszközök az Intune-portálon belül.  

## <a name="encryption-report-in-public-preview"></a>Titkosítási jelentés (nyilvános előzetes verzió)
A titkosítási jelentést (az összeköttetés előzetes verzió) segítségével a Windows 10 rendszerű eszközök titkosítási állapotát részleteinek a megtekintéséhez.  

A jelentés megkereséséhez jelentkezzen be a [Intune](https://aka.ms/intuneportal) , majd **eszközkonfiguráció**, majd a *figyelő*, jelölje be **titkosítási jelentésben (előzetes verzió)**.  

### <a name="prerequisites"></a>Előfeltételek:
A titkosítási jelentésben jelennek meg, hogy egy eszköz kell futtatnia Windows verzió, 1607-es vagy újabb.  

### <a name="report-details"></a>Jelentés részletei
A jelentés megjeleníti a **eszköznév** a Windows 10-eszközök és a magas szintű részleteit, köztük:  
- **Operációsrendszer-verzió** – a Windows verzió.  
- **TPM-verzió** – a platformmegbízhatósági modul (TPM) nehézségekbe ütközhet az eszközön lévő verziója.  
- **Titkosítási készültségi** – eszközök készen áll-e BitLocker-titkosítást támogató értékelését. Egy eszköz rendelkezhet egy titkosítási állapotát *titkosított* annak ellenére, hogy a titkosítás készültségi *nem áll készen*, mert nem rendelkezik TPM.  
- **Titkosítás állapota** – az operációs rendszer meghajtójának titkosítva van-e.  


### <a name="device-encryption-status"></a>Eszközállapot-titkosítás
Amikor kijelöl egy eszközt, az Intune megjeleníti a **titkosítási Eszközállapot** ablaktáblán.

Ezen a panelen a következő részleteket biztosítja:  
- **Eszköz neve** – az eszköz megjelenített neve.  
- **Titkosítási készültségi** – egy eszközök készen áll-e BitLocker-titkosítást támogató értékelését. Egy eszköz rendelkezhet egy titkosítási állapotát *titkosított* annak ellenére, hogy a titkosítás készültségi *nem áll készen*, mert nem rendelkezik TPM.  
- **Titkosítás állapota** - e az operációs rendszer meghajtójának titkosítva van.  
- **Profilok** – listáját a *eszközkonfiguráció* profilok, amelyek erre az eszközre érvényesek, és a következő típust és a beállítások tartalmazzák:  
    - Profil típusa = *az Endpoint protection*  
    - Beállítások > Windows-titkosítás > eszközök titkosítása = *szükséges*  

  Ez a lista lehet megkereséséhez tekintse át az egyes szabályzatok kell a profil állapotának összegzése kapcsolatos problémát jeleznek.  

- **Állapot összegzése profile** – a profilokat, amelyek a alkalmazni az eszközre összegzését. Az összegzés a legkevésbé kedvező feltétel az összes alkalmazható profilok jelöli. Például ha egy profil hibát eredményez, a profil állapotának összegzése jelennek meg *hiba*.  
- **Állapot részletei** – speciális az eszköz titkosítási állapot részleteit. 
  > [!NOTE]  
  > Az Intune csak jelenít meg *állapot részletei* futtató eszközök esetében a *Windows 2019. április 10. frissítés* vagy újabb.
  
  Ez a mező észlelhető alkalmazható hibák adatait jeleníti meg. Használhatja ezt az információt, hogy miért egy eszköz nem titkosítási készen áll.  

  A következő példák az Intune-ban jelenthetik állapot részletei:  

   - A BitLocker csoportházirend szükséges felhasználói beleegyezés, indítsa el a BitLocker meghajtótitkosítás varázslót az operációs rendszer kötetének titkosításához elindításához, de a felhasználó nem adott hozzájárulás megadása.  
   - Az operációsrendszer-kötet, a titkosítási módszer nem felel meg a BitLocker csoportházirend.  
   - A szabályzat a BitLocker a TPM-védőt, az operációsrendszer-kötet védelmét igényel, de a TPM nem használható.  
   - A BitLocker csoportházirend-csak TPM-védőt igényel az operációsrendszer-kötet, de nem használja a TPM-védelemmel.  
   - A BitLocker csoportházirend TPM + PIN védelmi igényel az operációsrendszer-kötet, de nem használja a rendszer a TPM + PIN védelmi modulra vonatkozó.  
   - A BitLocker házirend megköveteli a TPM + indítási kulcs védelmét az operációsrendszer-kötet, de a TPM + indítási kulcsvédő nem használja a rendszer.  
   - A BitLocker a házirendhez szükséges TPM + PIN + indítási kulcs védelme az operációsrendszer-kötet, azonban egy TPM + PIN + indítási kulcsvédő nem használja a rendszer.  
   - Az operációsrendszer-kötet védtelenné válik.  
   - Helyreállítási kulcs biztonsági mentése nem sikerült.  
   - Rögzített meghajtó védtelenné válik.  
   - A titkosítási módszer a rögzített meghajtó nem felel meg a BitLocker-házirendet.  
   - Meghajtók titkosítását, a BitLocker csoportházirend vagy a felhasználó, hogy jelentkezzen be rendszergazdaként van szükség, vagy ha az eszköz az Azure ad-hez csatlakozik, akkor a AllowStandardUserEncryption szabályzatot 1 értékre kell állítani.  
   - Nincs konfigurálva a Windows helyreállítási környezet (WinRE).  
   - A TPM nem érhető el a Bitlockert, vagy mert nem található, ezt nem tette lehetővé a beállításjegyzékben vagy az operációs rendszer egy cserélhető meghajtón.  
   - A TPM-eszköz nem áll készen a BitLocker.  
   - A hálózat nem érhető el, amelyre szükség a helyreállítási kulcs biztonsági mentése az.  

## <a name="bitlocker-recovery-keys-in-public-preview"></a>A BitLocker helyreállítási kulcsok (nyilvános előzetes verzióban elérhető)
A nyilvános előzetes verzió az Intune hozzáférést biztosít az Azure ad-ben panel a BitLocker hogy meg tudja tekinteni a BitLocker-kulcs azonosítók és a helyreállítási kulcsok a Windows 10 rendszerű eszközökhöz az Intune-portálon belül.  Az eszköz érhető el, a kulcsok az Azure AD szétválasztást kell rendelkeznie. 
1. Jelentkezzen be a [Intune](https://aka.ms/intuneportal), lépjen a **eszközök** , majd a *kezelés*válassza **minden eszköz**.
2. Jelöljön ki egy eszközt a listából, majd a *figyelő*válassza **helyreállítási kulcsok – előzetes verzió**.  
  
Kulcsok az Azure ad-ben érhetők el, amikor érhető el a következő információkat:
- BitLocker-kulcs azonosítója
- A BitLocker helyreállítási kulcs
- Meghajtó típusa  

Kulcsok nem szerepelnek az Azure AD, ha az Intune megjeleníti *nem BitLocker-kulcs az eszközhöz tartozó található*.  

Információk a BitLocker használatával lekérte a [a BitLocker konfigurációs szolgáltató](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). A BitLocker CSP támogatott a Windows 10 1703-as és újabb, valamint a Windows 10 Pro 1809 és újabb verziók. 

## <a name="next-steps"></a>További lépések
Hozzon létre egy [eszközmegfelelőség](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) házirend konfigurálása a BitLocker és a titkosítás a Windows 10 rendszerű eszközökhöz.
