---
title: A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként (hibrid mobileszköz-kezelés)
description: Megtudhatja, hogyan módosíthatja az MDM-szolgáltatót Intune-ról (önálló) Configuration Managerre (hibrid).
keywords: ''
author: dougeby
manager: dougeby
ms.date: 10/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b5494e4b2b6a7983d05ac83d9bc495677ee1a1ab
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="change-the-mdm-authority"></a>Az MDM-szolgáltató módosítása
A Configuration Manager 1610-es verziójától kezdődően anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a már felügyelt eszközök regisztrációjának törlését és az újbóli regisztrációt. Az ebben a témakörben található lépésekkel anélkül módosíthatja egy meglévő Microsoft Intune-bérlő Intune beállítását és az MDM-szolgáltató **Microsoft Intune** (önálló) beállítását **Configuration Manager** (hibrid MDM) értékre, hogy el kellene végeznie a már felügyelt eszközök regisztrációjának törlését és az újbóli regisztrációt.

> [!Note]    
> Ha módosítani szeretné egy meglévő Microsoft Intune-bérlő Configuration Manager-konzol (hibrid) beállítását és az MDM-szolgáltató **Configuration Manager** (hibrid) beállítását **Microsoft Intune** (önálló) értékre, tekintse meg [Az MDM-szolgáltató módosítása Configuration Managerről (hibrid MDM) Intune-ra (önálló)](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority) című cikket. 


## <a name="key-considerations"></a>Fontos szempontok
Az új MDM-szolgáltatóra való váltás után, az eszköz bejelentkezése és a szolgáltatóval való szinkronizálása előtt valószínűleg egy átmeneti időszak következik, amely akár 8 órán át is tarthat. Önnek konfigurálnia kell az új MDM-szolgáltató beállításait, hogy biztosíthassa, hogy a regisztrált eszközök továbbra is felügyelet és védelem alatt álljanak a módosítás után. 
- Az eszközöknek csatlakozniuk kell a szolgáltatáshoz a váltás után annak érdekében, hogy az új MDM-szolgáltató (az Intune önálló verziója) lecserélhesse az eszköz meglévő beállításait.
- Az MDM-szolgáltató módosítása után az előző MDM-szolgáltató (az Intune önálló verziója) egyes alapszintű beállításai (például a profilok) akár 7 napig, vagy az eszköz a szolgáltatáshoz való első csatlakozásáig az eszközön maradhatnak. Javasoljuk, hogy az új, hibrid MDM-szolgáltatóban a lehető leghamarabb konfigurálja az alkalmazásokat és a beállításokat (a szabályzatokat, a profilokat, az alkalmazásokat és egyebeket), és alkalmazza a beállításokat azokra a felhasználói csoportokra, amelyek a meglévő regisztrált eszközökkel rendelkező felhasználókat tartalmazzák. Amint egy eszköz csatlakozik a szolgáltatáshoz az MDM-szolgáltató váltása után, megkapja az új MDM-szolgáltató beállításait, és meggátolja a felügyeleti és a védelmi hiányosságokat.
- Ha ugyanazok az eszközkategóriák megtalálhatóak mind az Intune-ban, mind pedig Configuration Managerben, akkor az új MDM-szolgáltatóra váltás után az eszközökre vonatkozó eszközkategória-hozzárendelések nem lesznek áthozva. Ha továbbra is használni szeretné az eszközkategóriákat, akkor azokat manuálisan kell hozzáadnia a megfelelő gyűjteményekhez azt követően, hogy az új MDM-szolgáltatóra váltás megtörtént, és az eszközök megjelennek a Configuration Manager konzolján.
- Azok az eszközök, amelyek nem rendelkeznek hozzárendelt felhasználókkal (általában az iOS Készülékregisztrációs programja vagy csoportos regisztrálási folyamatok esetén), nem migrálhatók az új MDM-szolgáltatóba. Ezeknek az eszközöknek az új MDM-szolgáltatóba való áthelyezéséhez az ügyfélszolgálat segítségét kell kérnie.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>A hibrid Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként – előkészületek
Ha fel szeretne készülni az új MDM-szolgáltatóra való váltásra, tekintse át az alábbi tudnivalókat:
- Az MDM-szolgáltató váltását lehetővé tevő beállítás eléréséhez a Configuration Manager 1610-es vagy újabb verziójával kell rendelkeznie.
- Az új MDM-szolgáltatóra való váltás után az eszköz a szolgáltatóhoz való csatlakozása akár 8 órát is igénybe vehet.
- Hozzon létre egy olyan felhasználógyűjteményt a Configuration Managerben, amely minden, az Intune önálló verziója által kezelt felhasználót tartalmaz. Ezzel a gyűjteménnyel állíthatja be az Intune-előfizetést a Configuration Manager konzoljában. Ezzel a lépéssel biztosíthatja, hogy a felhasználó és az eszközei Configuration Manager-licencet kapjanak, és a hibrid környezetben kezelhesse őket az új MDM-szolgáltatóra való váltás után.
- Győződjön meg arról, hogy a rendszergazda felhasználó is ebben a felhasználógyűjteményben található.  
- A váltás előtt az MDM-szolgáltató **Beállítás a Microsoft Intune-hoz** (önálló) értékként fog megjelenni az Intune felügyeleti konzolban.
- Az MDM-kiszolgáló a váltás előtt **Beállítás a Microsoft Intune-hoz** (önálló bérlő) értéket kell, hogy mutasson a Microsoft Intune felügyeleti konzolban.
    > [!NOTE]    
    > Ha az MDM-kiszolgáló **Az Intune és az Office 365 által kezelt** értéket jeleníti meg, az Office 365 által kezelt MDM-eszközei nem lesznek kezelve az MDM-szolgáltató **Configuration Managerre** (hibrid) való váltása után. Azt javasoljuk, hogy az érintett felhasználókat az MDM-szolgáltató módosítása előtt licencelje az Intune-hoz vagy az Enterprise Mobility Suite-hez.   

- A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) távolítsa el az Eszközregisztráció-kezelő szerepkört. Részletes információ: [Eszközregisztráció-kezelő törlése az Intune-ból](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Kapcsolja ki a konfigurált eszközcsoport-leképezéseket. Részletes információ: [Eszközök kategorizálása eszközcsoport-leképezéssel a Microsoft Intune-ban](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- Az MDM-szolgáltató módosítása során a végfelhasználók várhatóan nem tapasztalnak észrevehető változást. A módosítást azonban célszerű előre tudatnia a felhasználókkal, hogy gondoskodni tudjanak róla, hogy az eszközeik be legyenek kapcsolva, és hogy a váltás után minél hamarabb csatlakozzanak a szolgáltatáshoz. Ezzel biztosíthatja, hogy a lehető legtöbb eszköz a lehető leghamarabb csatlakozzon és regisztráljon a szolgáltatásban az új szolgáltató hatásköre alatt.
- Ha az új MDM-szolgáltatóra való váltást megelőzően az Intune önálló verziójával kezeli az iOS-eszközöket, akkor meg kell újítania az Intune által korábban használt Apple Push Notification Service (APNs) tanúsítványát, és annak segítségével kell újra beállítania a bérlőt a hibrid Configuration Managerben.    

    > [!IMPORTANT]  
    > Ha a hibrid szolgáltatóhoz más APNs-tanúsítványt használ, az ÖSSZES korábban regisztrált iOS-eszköz regisztrációja megszűnik, és újból végre kell hajtania a regisztrációs folyamatot. Az MDM-szolgáltató módosítása előtt győződjön meg róla, hogy tisztában van az Intune-ban az iOS-eszközök kezeléséhez használt APNs-tanúsítvány típusával. Keresse meg ugyanazt a tanúsítványt az Apple Push Certificates portálon (https://identity.apple.com), majd ellenőrizze, hogy az eredeti APNs-tanúsítvány létrehozásához használt felhasználói Apple ID-t azonosította és elérhetőként észlelte a program, így megújíthatja vele a megegyező APNs-tanúsítványt az új MDM-szolgáltatóra való váltás részeként.  

## <a name="change-the-mdm-authority-to-configuration-manager"></a>A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként
A hibrid Configuration Manager beállítása MDM-szolgáltatóként az alábbi magas szintű lépésekkel jár:  
- A Configuration Manager konzolban adja hozzá a Microsoft Intune-előfizetést.
- Konfigurálja az Apple APNs-tanúsítványt a megújított APNs-tanúsítvánnyal.
- A Configuration Manager konzolban konfigurálja és alkalmazza az új MDM-szolgáltató (hibrid) beállításait és alkalmazásait.
- Amikor az eszközök legközelebb csatlakoznak a szolgáltatáshoz, az szinkronizálja a beállításokat az új MDM-szolgáltatóval.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként
1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Áttekintés** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd kijelöléssel adjon hozzá egy Intune-előfizetést.
2. Jelentkezzen be az MDM-szolgáltató eredeti beállításakor használt Intune-bérlőbe, majd kattintson a **Tovább** gombra.
3. Válassza **A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként** lehetőséget, majd kattintson a **Tovább** gombra.
4. Állítsa be, hogy a felhasználógyűjtemény az összes olyan felhasználót tartalmazza, akik továbbra is az új hibrid MDM-szolgáltató által lesznek kezelve.
5. Kattintson a **Tovább** gombra, és fejezze be a varázslót. Az MDM-szolgáltató mostantól a **Configuration Manager**.
6. Jelentkezzen be a [Microsoft Intune felügyeleti konzolba](http://manage.microsoft.com) ugyanazzal az Intune-bérlővel, majd erősítse meg, hogy az MDM-szolgáltatót módosította **A Configuration Manager szolgáltatáshoz beállítva** értékre.


## <a name="enable-ios-enrollment"></a>iOS-eszközök regisztrációjának engedélyezése
iOS-eszközök esetében konfigurálnia kell az APNs-tanúsítványt a Configuration Managerben.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>iOS-regisztráció engedélyezése és az APNs-tanúsítvány konfigurálása

1. **Tanúsítvány-aláírási kérés letöltése**

    1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetések** területre, és válassza az **APN szolgáltatás tanúsítványkérésének létrehozása** lehetőséget az **Apple Push Notification Service tanúsítványkérésének beszerzése** párbeszédpanel megnyitásához.  
    2. A**Tallózás** gombra válassza ki a helyet, ahová menteni szeretné az új tanúsítvány-aláírási kérés (.csr) fájlját. Mentse helyileg a tanúsítvány-aláírási kérelem (.csr) fájlját.  
    3. Kattintson a **Letöltés**lehetőségre. A rendszer letölti az új Microsoft Intune .csr fájlt, és a Configuration Manager menti azt.   

    > [!IMPORTANT]
    > Ekkor le kell töltenie egy új tanúsítvány-aláírási kérelmet. Ne használjon egy meglévő fájlt, mert a művelet sikertelen lesz.  

2.  Nyissa meg az [Apple Push Certificates portált](http://go.microsoft.com/fwlink/?LinkId=269844), majd jelentkezzen be **ugyanazzal** az Apple ID-vel, mint amit korábban az Intune önálló verziójában az APNs-tanúsítvány létrehozásához és megújításához használt.

    ![Az Apple Push Certificates portál bejelentkezési oldala](../media/mdm-change-apns-portal.png)

3. Válassza ki az Intune önálló verziójában használt APNs-tanúsítványt, majd kattintson a **Megújítás**lehetőségre.

    ![Az APNs megújítása párbeszédpanel](../media/mdm-change-renew-apns.png)

4. Válassza ki a helyi számítógépre letöltött APNs-tanúsítvány aláírási kérelmét (egy .csr fájlt), majd kattintson a **Feltöltés** lehetőségre.

    ![Az Apple Push Certificates portál bejelentkezési oldala](../media/mdm-change-renew-apns-upload.png)
 
5. Válassza ki ugyanazt azt APNs-t, majd kattintson a **Letöltés** lehetőségre. Töltse le az APNs-tanúsítványt (.pem), és mentse helyileg a fájlt.  

    ![Az Apple Push Certificates portál bejelentkezési oldala](../media/mdm-change-renew-apns-download.png)

6. Töltse fel a megújított APNs-tanúsítványt a hibrid bérlőbe a korábban használt Apple ID-vel.

    1.  A Configuration Manager konzolban lépjen az **Felügyelet** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd válassza a **Platformok konfigurálása** &gt; **iOS** lehetőséget.  
    2.  A **Microsoft Intune-előfizetés tulajdonságai** párbeszédpanelen válassza az **APNs-tanúsítvány** lapot, majd jelölje be az **iOS- és Mac OS X- (MDM-) igénylés engedélyezése** jelölőnégyzetet.  
    3.  Kattintson a **Tallózás**gombra, majd keresse meg az Apple-től letöltött APNs-tanúsítvány (.cer) fájlját. A Configuration Manager megjeleníti az APNs-tanúsítvány adatait. Az **OK** gombra kattintva mentse az APN szolgáltatás tanúsítványát az Intune-ba.  

        ![Intune-előfizetés tulajdonságai lap – iOS](../media/mdm-change-subscription-properties-ios.png)

## <a name="enable-android-enrollment"></a>Android-igénylés engedélyezése
1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd válassza a **Platformok konfigurálása** &gt; **Android** lehetőséget.  
2. Válassza az **Android-eszközök regisztrációjának engedélyezése** lehetőséget, majd kattintson az **OK** gombra.

### <a name="enable-windows-enrollment"></a>Windows-igénylés engedélyezése
1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd válassza a **Platformok konfigurálása** &gt; **Windows** lehetőséget.  
2. Válassza a **Windows-eszközök regisztrációjának engedélyezése** lehetőséget, majd kattintson az **OK** gombra.

### <a name="enable-windows-phone-enrollment"></a>Windows Phone-regisztráció engedélyezése
1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd válassza a **Platformok konfigurálása** &gt; **Windows Phone** lehetőséget.  
2. Válassza ki az engedélyezni kívánt platformot, majd kattintson az **OK** gombra.


## <a name="next-steps"></a>További lépések
Az MDM-szolgáltató váltása után tekintse át az alábbi lépéseket:
- Amikor az Intune szolgáltatás észleli, hogy egy bérlő MDM-szolgáltatója módosult, értesítést küld az összes regisztrált eszköznek, amelyben bejelentkezést és a szolgáltatással való szinkronizást kér (ez a rendszeresen ütemezett bejelentkezéstől eltérően értendő). Emiatt miután az Intune önálló verziójáról hibridre módosítja a bérlő MDM-szolgáltatóját, az összes bekapcsolt és online eszköz csatlakozik a szolgáltatáshoz, az új MDM-szolgáltató hatásköre alá kerül, és a továbbiakban a hibrid szolgáltatás kezelése alá tartozik. Az eszközök kezelése és védelme megszakítás nélkül fennmarad.
- Az MDM-szolgáltató módosítása során (vagy röviddel utána) bekapcsolt és online állapotban lévő eszközök esetében akár 8 órás késés várható (a következő ütemezett rendszeres bejelentkezés idejétől függően), mielőtt az eszközök regisztrációja befejeződne az új MDM-szolgáltató szolgáltatása alatt.    

  > [!IMPORTANT]    
  > Az MDM-szolgáltató módosítása és a megújított APNs-tanúsítvány az új szolgáltatóra való feltöltése között az iOS-eszközök új eszközregisztrációi és -bejelentkezései sikertelenek lesznek. Emiatt fontos, hogy az MDM-szolgáltató módosítása után a lehető leghamarabb tekintse át és töltse fel az APNs-tanúsítványt az új szolgáltatóba.

- A felhasználók gyorsan átválthatnak az új MDM-szolgáltatóra, ha manuálisan bejelentkeznek az eszközről a szolgáltatásba. Ezt könnyen megtehetik a Céges portál alkalmazásból, egy eszközmegfelelőségi ellenőrzés elindításával.
- Ha ellenőrizni szeretné, hogy az MDM-szolgáltató módosítása után megfelelően működik-e minden a bejelentkezett és a szolgáltatással szinkronizált eszközök esetében, keresse meg az eszközöket a Configuration Manager konzolban. A korábban az Intune által kezelt eszközök mostantól kezelt eszközökként jelennek meg a Configuration Manager konzolban.    
- Az MDM-szolgáltató váltásakor, valamint az eszköz szolgáltatásba való bejelentkezésekor az eszköz ideiglenesen offline állapotba kerül. Annak érdekében, hogy az eszköz az ideiglenes időszak alatt is védelem alatt álljon és megfelelően működjön, az alábbi profilok az eszközön maradnak legfeljebb 7 napig (vagy addig, amíg az eszköz nem csatlakozik az új MDM-szolgáltatóhoz és kapja meg a meglévő beállításokat felülíró új beállításokat):
    - E-mail-profil
    - VPN-profil
    - Tanúsítványprofil
    - Wi-Fi profil
    - Konfigurációs profilok
- Az új MDM-szolgáltatóra való váltás után a Microsoft Intune felügyeleti konzol megfelelőségi adatainak akár egy hétre is szükségük lehet, hogy pontosan jelenjenek meg. Az Azure Active Directory és az eszköz megfelelőségi állapotai azonban pontosak maradnak, az eszköz így továbbra is védelem alatt áll.
- Ügyeljen rá, hogy a meglévő beállításokat felülírandó új beállítások ugyanazzal a névvel rendelkezzenek, mint a korábbiak. Így az új beállítások biztosan felülírják a korábbiakat. Ellenkező esetben előfordulhat, hogy az eszközökön felesleges profilok és szabályzatok maradnak.    

  > [!TIP]    
  > Ajánlott eljárásként érdemes létrehozni minden kezelési beállítást, konfigurációt és példányt nem sokkal az MDM-szolgáltató módosítása után. Ezzel biztosíthatja, hogy az eszközök az ideiglenes időszak alatt is védelem és kezelés alatt álljanak.

-  Az MDM-szolgáltató módosítása után végezze el az alábbi lépéseket az új eszközök sikeres regisztrációjának ellenőrzéséhez:   
    - Új eszköz regisztrációja
    - Ellenőrizze, hogy az újonnan regisztrált eszköz megjelenik-e a Configuration Manager konzolban.
    - Végezzen el egy, az eszközre vonatkozó műveletet (például távoli zárolást) a felügyeleti konzolban. Ha a művelet sikeres, az eszköz már az új MDM-szolgáltató által van kezelve.
- Ha problémába ütközik bizonyos eszközökkel, szüntesse meg azok regisztrációját, majd regisztrálja őket újra, így azok csatlakozni tudnak az új szolgáltatóhoz, és a lehető leggyorsabban újra kezelés alatt állhatnak.