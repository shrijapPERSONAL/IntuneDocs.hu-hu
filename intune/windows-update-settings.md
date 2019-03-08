---
title: Windows üzleti frissítési beállításokhoz for Microsoft Intune – Azure |} A Microsoft Docs
description: Windows 10 rendszerű eszközökhöz az Intune használatával üzembe helyezhető beállításokat wufb-t.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef626523898a8873bde9851664b4ade85c2b0a23
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566539"
---
# <a name="windows-update-settings-for-intune"></a>Windows Intune-beállításainak frissítése  

Megtekintheti a Windows 10 frissítési beállításokat is [konfigurálhatja és kezelheti a](windows-update-for-business-configure.md) Microsoft Intune-nal.  

Az Intune-ban Windows 10-es frissítési körök beállításainak konfigurálásakor a Windows Update beállításainak konfigurálása esetén.  Ha a Windows update beállítás maga a Windows 10-es verzió, a függőségi jelenik meg a beállítások részletei.  

## <a name="update-settings"></a>Beállítások frissítése  

Beállításainak frissítése milyen bits eszköz tölti le, és mikor. Tekintse meg a Windows dokumentációjában további információ az egyes beállítások viselkedése.  

### <a name="servicing-channel"></a>Karbantartási csatorna  

- **Alapértelmezett**: Féléves csatorna (célzott)  
- **Windows-referenciák dokumentációiba**: [Frissítési/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Állítsa be a csatorna (ág), amelyen az eszköz megkaphatná a Windows-frissítések. A különböző csatornákon használható különböző késleltetési időszakok előtt a frissítések beszerzését.  

Ha például a *féléves csatorna* egy hat hónapos késleltetési rendelkezik. Ez azt jelenti, hogy nincsenek további halasztási beállításait a szervezet használja ezt a csatornát, ha az eszköz telepíti a frissítési hat hónapban a kiadása után.  

Támogatott frissítési csatornákon:  

- Féléves csatorna  
- Féléves csatorna (célzott)  
- Windows Insider – gyors  
- Windows Insider – lassú  
- A Windows Insider kiadása  

Ha az Insider-csatorna, az Intune automatikusan konfigurálja a Windows update beállítás [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) , hogy az insider-build működjenek.  


> [!IMPORTANT]  
> Kezdve a Windows verzió 1903, használatát a *féléves csatorna (célzott)* SAC-T kivonták. Ezzel a SAC-T a egyesíti a *féléves csatorna*. Ez a változás, és hogyan érinti a Windows Update for Business kapcsolatos további tudnivalókért tekintse meg a Windows IT Pro Blog bejegyzését [és a használatból való kivonást egyaránt SAC-T a Windows Update](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).
 


### <a name="microsoft-product-updates"></a>Microsoft-termékfrissítések  

- **Alapértelmezett**:  Engedélyezés
- **Windows-referenciák dokumentációiba**: [Update/AllowMUUpdateService](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Válasszon *engedélyezése* keresését az alkalmazások frissítése a Microsoft Update webhelyről.    

### <a name="windows-drivers"></a>Windows-illesztőprogramok  

- **Alapértelmezett**:  Engedélyezés
- **Windows-referenciák dokumentációiba**: [Frissítési/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Válasszon *engedélyezése* tartalmazza a Windows Update-illesztőprogramok frissítései során

### <a name="quality-update-deferral-period-days"></a>Minőségi frissítések elhalasztása (nap)  

- **Alapértelmezett**: 0  
- **Windows-referenciák dokumentációiba**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Adja meg a 0 és 30 késleltetni a minőségi frissítések funkciófrissítéseket napok számát. Ebben az időszakban van, kívül semmilyen halasztási időszaka, amely része a szolgáltatási csatorna választja. A késleltetési idő akkor kezdődik, amikor az eszköz megkapta a szabályzatot.  

Minőségi frissítések jellemzően javításai és továbbfejlesztései, meglévő Windows-funkciók.  

### <a name="feature-update-deferral-period-days"></a>Szolgáltatásfrissítések elhalasztása (nap)  

- **Alapértelmezett**: 0  
- **Windows-referenciák dokumentációiba**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Adja meg, hány napig késleltetni a Funkciófrissítések funkciófrissítéseket. Ebben az időszakban van, kívül semmilyen halasztási időszaka, amely része a szolgáltatási csatorna választja. A késleltetési idő akkor kezdődik, amikor az eszköz megkapta a szabályzatot.  
Támogatott késleltetési idő:  

- *1709-es vagy újabb verziójú Windows*: 0 és 365 nap  
- *Windows 1703-as*:  0-180 nap  

A funkciófrissítések általában új Windows-funkciókat tartalmaznak.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Set funkciófrissítés-eltávolítási időszak (2 – 60 nap)  

- **Alapértelmezett**: 10  
- **Windows-referenciák dokumentációiba**:  [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Konfigurálja egy idő után melyik funkciófrissítések nem lehet eltávolítani.  

Ez az időszak lejárta után az előző frissítés bits törlődnek az eszközről, és már nem távolíthatja egy korábbi frissítési verzióra.  

Vegyük példaként egy frissítési kör egyik funkciójával frissítési időszakot 20 napra, távolítsa el. 25 nap elteltével úgy dönt, hogy állítsa vissza a legújabb funkciófrissítést, és használja az Eltávolítás lehetőséget.  Eszközök, amelyek telepítették a funkciófrissítés több mint 20 napja nem távolíthatja el, mivel azok el lett távolítva a szükséges a bits a karbantartási részeként. Eszközök, amelyek csak másolatot telepítették a funkciófrissítés 19 nappal ezelőtt azonban eltávolíthatja a frissítést, ha azok sikeresen be, hogy fogadni az eltávolítási parancs meghaladja az Eltávolítás 20 napos időszak előtt.  


## <a name="user-experience-settings"></a>A felhasználói élmény beállításainak  

A felhasználói élmény beállításainak szabályozása az eszköz újraindítását és emlékeztetők kapcsolatos végfelhasználói élményt. Tekintse meg a Windows dokumentációjában további információ az egyes beállítások viselkedése.  

### <a name="automatic-update-behavior"></a>Automatikus frissítés viselkedése  

- **Alapértelmezett**: Automatikus telepítés és újraindítás ütemezett időpontban  
- **Windows-referenciák dokumentációiba**: [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Válassza ki az automatikus frissítések telepítve vannak, és ha szükséges, ha újraindítja az eszközt.  

A Windows dokumentációjában talál a teljes kiadni a következő támogatott beállítások közül:  

- **Értesítés letöltés** – a felhasználó értesítése, a frissítés letöltése előtt. A frissítések letöltése és telepítése a felhasználók megadhatják.  

- **Automatikus telepítés karbantartási időpontban** – letöltési automatikusan frissül, és majd automatikus karbantartás során telepítse, ha az eszköz nem használatának vagy akkumulátorról üzemel. Ha újraindításra szükség, felhasználók újraindítására legfeljebb 7 napig, és majd meg kell-e az újraindítása.  

  Ez a beállítás is automatikusan újraindul az eszközt, a frissítés telepítése után. Használja a **aktív órák** beállítások megadása egy időszak, amely során az automatikus újraindításokat le vannak tiltva:  

  - **Aktív órák kezdete**: Adja meg a frissítések telepítése miatti újraindítások újrainduljanak kezdési időt.  
    **Windows-referenciák dokumentációiba**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Alapértelmezett**: 8-KOR  
  
  - **Aktív órák vége**: Adja meg a frissítések telepítése miatti újraindítások újrainduljanak befejezési idejét.  
    **Windows-referenciák dokumentációiba**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Alapértelmezett**: 17: 00  

- **Automatikus telepítés és újraindítás karbantartási időpontban** - frissítések automatikus letöltés és majd automatikus karbantartás során telepítse, amikor az eszköz nem szerepel a használatát, illetve akkumulátorról. Ha újraindításra szükség, az eszköz újraindul, amikor nincs használatban. (Ez a nem felügyelt eszközök esetében az alapértelmezett.)  

  Ez a beállítás is automatikusan újraindul az eszközt, a frissítés telepítése után. Használja a **aktív órák** beállításai nem ismertetett Windows Update-beállításokat, de az Intune által meghatározásához használják egy időszak, amely során az automatikus újraindításokat le vannak tiltva:  

  - **Aktív órák kezdete**: Adja meg a frissítések telepítése miatti újraindítások újrainduljanak kezdési időt.  
    **Windows-referenciák dokumentációiba**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Alapértelmezett**: 8-KOR  

  - **Aktív órák vége**: Adja meg a frissítések telepítése miatti újraindítások újrainduljanak befejezési idejét.  
    **Windows-referenciák dokumentációiba**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Alapértelmezett**: 17: 00  

- **Automatikus telepítés és újraindítás ütemezett időpontban** – adjon meg egy telepítési dátumát és időpontját. Ha nincs megadva, telepítési fut naponta 3 órakor 15 perces visszaszámlálást indít el az újraindítást követ. Bejelentkezett használ visszaszámlálás késleltetés, és indítsa újra.  
  
  Ez a lehetőség támogatja a további beállításokat.  
  **Windows-referenciák dokumentációiba**:  [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Automatikus frissítés gyakorisága**: Ezzel a beállítással ütemezheti a frissítésék telepítését, amelyet hét, nap és időpont szerint adhat meg.  
    **Alapértelmezett**: Minden héten

  - **Az ütemezett telepítés napja**:  Adja meg, a hét mely napján frissítések telepítéséhez.  
    **Alapértelmezett**: Minden nap  

  - **Ütemezett telepítés időpontja**:  Adja meg a telepítendő frissítések napi időpontot.  
    **Alapértelmezett**: 3-KOR  

- **Automatikus telepítés és újraindítás végfelhasználói irányítás nélkül** – letöltési automatikusan frissül, és majd automatikus karbantartás során telepítse, amikor az eszköz nem szerepel a használatát, illetve akkumulátorról. Ha újraindításra szükség, az eszköz újraindul, amikor nincs használatban. Ezt a lehetőséget a végfelhasználók vezérlőpanelen csak olvasható állítja be.  

- **Visszaállítás alapértelmezettre** -visszaállítás az eredeti automatikus frissítési beállításokat a Windows 10-es gépen is fut a 2018. október frissítés vagy újabb.  


### <a name="restart-checks"></a>Újraindítási ellenőrzések  

- **Alapértelmezett**: Engedélyezés  
- **Windows-referenciák dokumentációiba**: [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Ez a beállítás a Windows eszköz verziójától függően eltérő eredményt rendelkezik:  

- 1703-as és korábbi verziójú Windows: Egy eszköz újraindításakor a rendszer bizonyos ellenőrzéseket végez, például ellenőrzi az aktív felhasználókat, az akkumulátor szintjét, a futó játékokat és más szempontokat. Ha át szeretné ugrani ezeket az ellenőrzéseket az eszközök újraindításakor, válassza a **Kihagyás** lehetőséget.  
- 1709-es Windows kezdve: Aktív órák során a következő folyamatok nem fut a frissítések: ellenőrzése, letöltése, telepítése és újraindítás. Aktív órák, a folyamatok futtatásához és felébredhet-e alvó állapotba lépni, hogy az eszköz a frissítés vizsgálata, miután letöltése, telepítése és indítsa újra az eszköz mindaddig, amíg az akkumulátor-ellenőrzések és teljesítmény-e az előfeltételeknek. További információkért lásd: [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>A felhasználó felfüggesztése Windows-frissítések  

- **Alapértelmezett**: Engedélyezés  
- **Windows-referenciák dokumentációiba**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Engedélyezheti vagy letilthatja az eszköz felhasználója egy frissítés telepítésének felfüggesztése.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Indítsa újra a munkaidőn kívül felhasználói jóváhagyás szükséges  

- **Alapértelmezett**: Nincs konfigurálva  
- **Windows-referenciák dokumentációiba**: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Válassza ki *szükséges* , hogy a felhasználók jóváhagyása munkaidőn kívül eszköz újraindítása szükséges.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Emlékeztesse a felhasználót előtt kötelező automatikus újraindítás letiltása a mellőzhető emlékeztető (óra)  

- **Alapértelmezett**: *Ez alapértelmezés szerint nem konfigurálja, és nem emlékeztető egyike jelenik meg a felhasználók számára*.  
- **Windows-referenciák dokumentációiba**: [Frissítési/ScheduleRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Adja meg, mennyi ideig szakadjon meg mellőzhető értesítést arról, hogy egy eszköz felhasználója automatikus újraindítást. Az értékek **2**, **4**, **8**, **12**, vagy **24** óra támogatottak.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Emlékeztesse a felhasználót előtt kötelező automatikus újraindítás letiltása a végleges emlékeztető (perc)  

- **Alapértelmezett**: *Ez alapértelmezés szerint nem konfigurálja, és nem emlékeztető egyike jelenik meg a felhasználók számára*.  
- **Windows-referenciák dokumentációiba**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Adja meg, mennyi ideig kíván, arról, hogy egy eszköz felhasználója nem mellőzhető figyelmeztetés megjelenítése automatikus újraindítást. Az értékek **15**, **30** vagy **60** perc támogatottak.  
 
### <a name="allow-user-to-restart-engaged-restart"></a>Lehetővé teszi a felhasználónak újra kell indítania (szerepet játszanak újraindítás)  

- **Alapértelmezett**: Nincs konfigurálva  
- **Windows-referenciák dokumentációiba**: *Nem alkalmazható*  
- **Windows-verzió**: A Windows 10 1803-es és újabb verziók esetében támogatott  

  > [!NOTE]  
  > A Windows 10-es verzió 1809 további szerepet játszanak újraindítási beállításokat, amelyek lehetővé teszik a szolgáltatás- és minőségi frissítések alkalmazandó eltérő beállításokat mutatja be. Azonban az Intune által felügyelt beállításai nem külön-külön vonatkoznak a különböző frissítési típusainak. Ehelyett az Intune ugyanazokat az értékeket a szolgáltatás- és minőségi frissítéseket alkalmazza.  

Ha a beállítása **szükséges**, Windows 10-es szoftverfrissítésekkel szerepet játszanak újraindítási beállításokat használatát engedélyezi. Ezeket a beállításokat a felhasználó-eszköz kezeléséhez, ha az eszköz újraindítása után a számítógép újraindítását igénylő frissítés telepítése léphet.  

Ezzel a beállítással kapcsolatos további információkért lásd: [újraindítását végző](https://docs.microsoft.com/en-us/windows/deployment/update/waas-restart#engaged-restart) a Windows 10 dokumentációjában frissítéseinek telepítéséhez.  

A következő beállítások segítségével szabályozhatja, mikor szerepet játszanak az újraindítási műveletek történnek.  

- **Áttérés a felhasználók számára szerepet játszanak újraindítás az automatikus újraindítás után (napokban)**  
  - **Alapértelmezett**:  Alapértelmezés szerint ez nem történik meg, de támogatja a egy értéke **2** való **30**.  
  - **Windows-referenciák dokumentációiba**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Adja meg, mennyi ideig, amíg az eszköz inkatív a a frissítés telepítését követően a szerepet játszanak viselkedés újraindításához. A beállított napok száma, miután figyelmezteti a felhasználót az eszköz újraindításához.  

- **Késleltetés szerepet játszanak újraindítás emlékeztető (nap)**  
  - **Alapértelmezett**:  Alapértelmezés szerint ez nem történik meg, de támogatja a egy értéke **1** való **3**.  
  - **Windows-referenciák dokumentációiba**: [Frissítési/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Adja meg, mennyi ideig újraindításra vonatkozó kérés is snoozed.  A késleltetés az időtartamnak az elteltével a számítógép újraindítását az újra érhető el. A felhasználó továbbra is az emlékeztető késleltetés, amíg a telepítési határidő elérésekor.  

- **Függőben lévő határidejének beállítása újraindul (nap)**  
  - **Alapértelmezett**:  Alapértelmezés szerint ez nem történik meg, de támogatja a egy értéke **2** való **30**.  
  - **Windows-referenciák dokumentációiba**: [Frissítési/EngagedRestartDeadline](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Adja meg, hogy legfeljebb hány nap után a szerepet játszanak viselkedés újraindításához megkezdése előtt egy eszköz érvényesíti a szükséges újraindítást. Ezt az újraindítást kérni fogja a felhasználótól, hogy mentsék a munkájukat

### <a name="delivery-optimization-download-mode"></a>Kézbesítésoptimalizálásos letöltési mód  

- **Alapértelmezett**:  Nem alkalmazható
- **Windows-referenciák dokumentációiba**: *Nem alkalmazható*

Kézbesítésoptimalizálás a Windows 10 frissítési kör szoftverfrissítések alatt részeként már nincs konfigurálva. Kézbesítésoptimalizálás most keresztül az eszköz konfigurációs van beállítva. Azonban a fenti konfiguráció marad a konzolban. Ezeket a korábbi konfigurációkat eltávolíthatja őket szerkesztésével *nincs konfigurálva*, de ezeket más módon nem módosíthatja. 

Tekintse meg a régi és új-csoportházirend közötti ütközések elkerülése érdekében [helyezheti át meglévő frissítési körök kézbesítésoptimalizálás az](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) és majd helyezze át a beállításokat egy kézbesítési optimalizálás profilhoz.


