---
title: Mobileszköz-felügyeleti szolgáltató megadása
titlesuffix: Microsoft Intune
description: Mobileszköz-felügyeleti szolgáltató beállítása az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 41573eb05039dceeef45ba3cf04e890603a90362
ms.sourcegitcommit: c4258bb5824daf3f7e0ac3bb8afc539bde4d95da
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/16/2019
ms.locfileid: "57991151"
---
# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Ahhoz, hogy a felhasználók felügyeletre tudják regisztrálni eszközeiket, a rendszergazdának be kell állítania egy MDM-szolgáltatót.

A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll. [MDM-szolgáltató beállítása az Intune-konzolon](#set-mdm-authority-to-intune).

- **Megosztott kezelés Intune** -integrációja az Intune felhőalapú megoldás a System Center Configuration Managerrel Windows 10 rendszerű eszközökhöz. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja. [Eszközök automatikus regisztrációjának beállítása az Intune-ban](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >Új hibrid MDM-ügyfelek bevezetésének elavult. További információkért lásd: a [válthatnak a hibrid mobileszköz-kezelés az Intune-bA az Azure-ban](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) blogbejegyzést.

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune a Microsoft 365 felügyeleti központban konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza. Az MDM-szolgáltató beállítása a Microsoft 365 felügyeleti központban.

> [!IMPORTANT]
> A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, vagy hogy el kellene végeznie a már felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információkért lásd: [előkészítése az MDM-szolgáltató módosítása a Configuration Manager](mdm-authority-set.md#prepare-to-change-the-mdm-authority-to-configuration-manager).

## <a name="set-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

Ha még nem állította be az MDM-szolgáltatót, kövesse az alábbi lépéseket. Az MDM-szolgáltatók váltásához lásd az alábbi [Mobileszköz-felügyeleti szolgáltató módosítása](#prepare-to-change-the-mdm-authority-to-configuration-manager) szakaszt.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. A **Mobileszköz-kezelő szolgáltató** beállítás megnyitásához válassza a narancssárga szalagcímet. A narancssárga szalagcím csak akkor jelenik meg, ha még nem állított be az MDM-szolgáltatót.
4. A **Mobileszköz-kezelő szolgáltató** szakaszban válassza ki az alábbiak közül a kívánt MDM-szolgáltatót:
   - **Intune MDM-szolgáltató**
   - **Configuration Manager MDM-szolgáltató**.
   - **Nincsenek**

   ![Képernyőkép az Intune mobileszköz-kezelő szolgáltató beállítására szolgáló képernyőjéről](media/set-mdm-auth.png)

   Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.

### <a name="workflow-of-intune-administration-ui"></a>Az Intune-felügyelet felhasználói felületének munkafolyamata
Engedélyezett Android- vagy Apple-eszközkezelés esetén az Intune eszköz- és felhasználóadatok küldésével végzi el az eszközök kezeléséhez szükséges integrációt a külső szolgáltatásokkal.

Néhány új helyzet, amelyben az adatok megosztásához a rendszer jóváhagyást kér:
- Az androidos munkahelyi profilok engedélyezése.
- Apple MDM leküldéses tanúsítványok engedélyezése és feltöltése.
- Olyan Apple-szolgáltatások engedélyezése, mint a Készülékregisztrációs program, a School Manager és a mennyiségi vásárlási program (VPP).

Ezekben az esetekben a jóváhagyás szigorúan csak egy mobileszköz-felügyeleti szolgáltatás futtatásához kapcsolódik, például annak megerősítéséhez, hogy egy rendszergazda engedélyezte a Google- vagy Apple-eszközök regisztrálását. Az új munkafolyamatok indulásakor megosztott adatokról szóló dokumentáció az alábbi helyeken érhető el:
- [Az Intune által a Google-nek küldött adatok](https://aka.ms/Data-intune-sends-to-google)
- [Az Intune által az Apple-nek küldött adatok](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Fontos szempontok
Az új MDM-szolgáltatóra való váltás után, az eszköz bejelentkezése és a szolgáltatóval való szinkronizálása előtt valószínűleg egy átmeneti időszak következik, amely akár 8 órán át is tarthat. Konfigurálnia kell az új (hibrid) MDM-szolgáltató beállításait, hogy továbbra is gondoskodhasson a regisztrált eszközök felügyeletéről és védelméről a módosítás után. 
- Az eszközöknek csatlakozniuk kell a szolgáltatáshoz a váltás után annak érdekében, hogy az új MDM-szolgáltató (az Intune önálló verziója) lecserélhesse az eszköz meglévő beállításait.
- Az MDM-szolgáltató módosítása után az előző MDM-szolgáltató (az Intune önálló verziója) egyes alapszintű beállításai (például a profilok) akár 7 napig, vagy az eszköz a szolgáltatáshoz való első csatlakozásáig az eszközön maradhatnak. Javasoljuk, hogy az új hibrid MDM-szolgáltatóban a lehető leghamarabb konfigurálja az alkalmazásokat és a beállításokat (a szabályzatokat, a profilokat, az alkalmazásokat és egyebeket), és alkalmazza a beállításokat azokra a felhasználói csoportokra, amelyek a meglévő regisztrált eszközökkel rendelkező felhasználókat tartalmazzák. Amint egy eszköz csatlakozik a szolgáltatáshoz az MDM-szolgáltató váltása után, megkapja az új MDM-szolgáltató beállításait, és meggátolja a felügyeleti és a védelmi hiányosságokat.
- Ha ugyanazok az eszközkategóriák megtalálhatóak mind az Intune-ban, mind pedig Configuration Managerben, akkor az új MDM-szolgáltatóra váltás után az eszközökre vonatkozó eszközkategória-hozzárendelések nem lesznek áthozva. Ha továbbra is használni szeretné az eszközkategóriákat, akkor azokat manuálisan kell hozzáadnia a megfelelő gyűjteményekhez azt követően, hogy az új MDM-szolgáltatóra váltás megtörtént, és az eszközök megjelennek a Configuration Manager konzolján.
- Azok az eszközök, amelyek nem rendelkeznek hozzárendelt felhasználókkal (általában az iOS Készülékregisztrációs programja vagy csoportos regisztrálási folyamatok esetén), nem migrálhatók az új MDM-szolgáltatóba. Ezeknek az eszközöknek az új MDM-szolgáltatóba való áthelyezéséhez az ügyfélszolgálat segítségét kell kérnie.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként – előkészületek

Ha fel szeretne készülni az új MDM-szolgáltatóra való váltásra, tekintse át az alábbi tudnivalókat:
- Az MDM-szolgáltató váltását lehetővé tevő beállítás eléréséhez a Configuration Manager 1610-es vagy újabb verziójával kell rendelkeznie.
- Az új MDM-szolgáltatóra való váltás után az eszköz a szolgáltatóhoz való csatlakozása akár 8 órát is igénybe vehet.
- Hozzon létre egy olyan felhasználógyűjteményt a Configuration Managerben, amely minden, az Intune önálló verziója által kezelt felhasználót tartalmaz. Ezzel a gyűjteménnyel állíthatja be az Intune-előfizetést a Configuration Manager konzoljában. Ezzel a lépéssel gondoskodhat róla, hogy a felhasználó és az eszközei Configuration Manager-licencet kapjanak, és a hibrid környezetben is kezelhesse őket az új MDM-szolgáltatóra való váltás után.
- Győződjön meg arról, hogy a rendszergazda felhasználó is ebben a felhasználógyűjteményben található.  
- A váltás előtt az MDM-szolgáltató **Beállítás a Microsoft Intune-hoz** (önálló) értékként fog megjelenni az Intune felügyeleti konzolban.
- Az MDM-kiszolgáló a váltás előtt **Beállítás a Microsoft Intune-hoz** (önálló bérlő) értéket kell, hogy mutasson a Microsoft Intune felügyeleti konzolban.
    > [!NOTE]    
    > Ha az MDM-kiszolgáló **Az Intune és az Office 365 által kezelt** értéket jeleníti meg, az Office 365 által kezelt MDM-eszközei nem lesznek kezelve az MDM-szolgáltató **Configuration Managerre** (hibrid) való váltása után. Azt javasoljuk, hogy az érintett felhasználókat az MDM-szolgáltató módosítása előtt licencelje az Intune-hoz vagy az Enterprise Mobility Suite-hez.   

- A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) távolítsa el az Eszközregisztráció-kezelő szerepkört. Részletes információ: [Eszközregisztráció-kezelő törlése az Intune-ból](device-enrollment-manager-enroll.md#remove-device-enrollment-manager-permissions).
- Kapcsolja ki a konfigurált eszközcsoport-leképezéseket. Részletes információ: [Eszközök kategorizálása eszközcsoport-leképezéssel a Microsoft Intune-ban](device-group-mapping.md).
- Az MDM-szolgáltató módosítása során a végfelhasználók várhatóan nem tapasztalnak észrevehető változást. A módosítást azonban célszerű előre tudatnia a felhasználókkal, hogy gondoskodni tudjanak róla, hogy az eszközeik be legyenek kapcsolva, és hogy a váltás után minél hamarabb csatlakozzanak a szolgáltatáshoz. Ezzel gondoskodhat róka, hogy a lehető legtöbb eszköz a lehető leghamarabb csatlakozzon és regisztráljon a szolgáltatásba az új szolgáltatón keresztül.
- Ha az új MDM-szolgáltatóra való váltást megelőzően az Intune önálló verziójával kezeli az iOS-eszközöket, akkor meg kell újítania az Intune által korábban használt Apple Push Notification Service (APNs) tanúsítványát, és annak segítségével kell újra beállítania a bérlőt a hibrid Configuration Managerben.    

    > [!IMPORTANT]  
    > Ha a hibrid szolgáltatóhoz más APNs-tanúsítványt használ, az ÖSSZES korábban regisztrált iOS-eszköz regisztrációja megszűnik, és újból végre kell hajtania a regisztrációs folyamatot. Az MDM-szolgáltató módosítása előtt győződjön meg róla, hogy tisztában van az Intune-ban az iOS-eszközök kezeléséhez használt APNs-tanúsítvány típusával. Keresse meg ugyanazt a tanúsítványt az Apple Push Certificates portálon (https://identity.apple.com), majd ellenőrizze, hogy az eredeti APNs-tanúsítvány létrehozásához használt felhasználói Apple ID-t azonosította és elérhetőként észlelte a program, így megújíthatja vele a megegyező APNs-tanúsítványt az új MDM-szolgáltatóra való váltás részeként.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként

1. A Configuration Manager konzolban lépjen a **Felügyelet** &gt; **Áttekintés** &gt; **Felhőszolgáltatások** &gt; **Microsoft Intune-előfizetés** területre, majd kijelöléssel adjon hozzá egy Intune-előfizetést.
2. Jelentkezzen be az MDM-szolgáltató eredeti beállításakor használt Intune-bérlőbe, majd kattintson a **Tovább** gombra.
3. Válassza **A Configuration Manager beállítása mobileszköz-felügyeleti szolgáltatóként** lehetőséget, majd kattintson a **Tovább** gombra.
4. Állítsa be, hogy a felhasználógyűjtemény az összes olyan felhasználót tartalmazza, akik továbbra is az új hibrid MDM-szolgáltató által lesznek kezelve.
5. Kattintson a **tovább** fejezze be a varázslót. Az MDM-szolgáltató mostantól a **Configuration Manager**.
6. Jelentkezzen be a [Microsoft Intune felügyeleti konzolba](http://manage.microsoft.com) ugyanazzal az Intune-bérlővel, majd erősítse meg, hogy az MDM-szolgáltatót módosította **a Configuration Manager szolgáltatáshoz beállított** értékre.
7. Miután beállította a Configuration Managert mobileszköz-felügyeleti szolgáltatóként, beállíthatja az [iOS-regisztrációt](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) és az [Android-regisztrációt](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-android).
8. A Configuration Manager konzolban konfigurálja és alkalmazza az új MDM-szolgáltató (hibrid) beállításait és alkalmazásait.

Amikor az eszközök legközelebb csatlakoznak a szolgáltatáshoz, az szinkronizálja a beállításokat az új MDM-szolgáltatóval.

## <a name="change-mdm-authority-to-office-365"></a>Az Office 365 beállítása mobileszköz-felügyeleti szolgáltatóként

A meglévő Intune szolgáltatásban az Office 365 mobileszköz-felügyeleti szolgáltatásként való beállításához nyissa meg a [https://protection.office.com](https://protection.office.com) oldalt, majd válassza az **Adatveszteség-megelőzés** > **Eszközbiztonsági szabályzatok** > **Felügyelt eszközök listájának megtekintése** > **Első lépések** lehetőséget.

További információ: [Mobileszköz-felügyelet (MDM) beállítása az Office 365-ben](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Ha azt szeretné, hogy a végfelhasználókat egyedül az Office 365 MDM felügyelje, akkor az Office 365 MDM aktiválása után távolítson el minden hozzárendelt Intune- és/vagy EMS-licencet.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.

## <a name="remove-mdm-authority"></a>Mobileszköz-felügyeleti szolgáltató eltávolítása

A mobileszköz-felügyeleti szolgáltató nem állítható vissza Ismeretlenre. A Microsoft-kiszolgálók a mobileszköz-felügyeleti szolgáltató használatával állapítják meg, hogy melyik portálnak jelentenek a regisztrált eszközök (ConfigMGR, Azure Intune, Office 365 MDM).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Amire a mobileszköz-felügyeleti szolgáltató módosítása után számítani kell

- Amikor az Intune észleli, hogy egy bérlő MDM-szolgáltatója módosult, értesítést küld az összes regisztrált eszköznek, hogy jelentkezzenek be és szinkronizáljanak a szolgáltatással (ez az értesítés nem tartozik a rendszeresen ütemezett bejelentkezések közé). Emiatt miután az Intune önálló verziójáról hibridre módosítja a bérlő MDM-szolgáltatóját, az összes bekapcsolt és online eszköz csatlakozik a szolgáltatáshoz, az új MDM-szolgáltató hatásköre alá kerül, és a továbbiakban a hibrid szolgáltatás kezelése alá tartozik. Az eszközök kezelése és védelme megszakítás nélkül fennmarad.
- Az MDM-szolgáltató módosítása során (vagy röviddel utána) bekapcsolt és online állapotban lévő eszközök esetében akár 8 órás késés várható (a következő ütemezett rendszeres bejelentkezés idejétől függően), mielőtt az eszközök regisztrációja befejeződne az új MDM-szolgáltató szolgáltatása alatt.    

  > [!IMPORTANT]    
  > Az MDM-szolgáltató módosítása és a megújított APNs-tanúsítvány az új szolgáltatóra való feltöltése között az iOS-eszközök új eszközregisztrációi és -bejelentkezései sikertelenek lesznek. Ezért különösen fontos, hogy az MDM-szolgáltató módosítása után a lehető leghamarabb tekintse át és töltse fel az APNs-tanúsítványt az új szolgáltatóba.

- A felhasználók gyorsan átválthatnak az új MDM-szolgáltatóra, ha manuálisan bejelentkeznek az eszközről a szolgáltatásba. Ezt könnyen megtehetik a Céges portál alkalmazásból, ha elindítanak egy eszközmegfelelőségi ellenőrzést.
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
    - Végezzen el egy, az eszközre vonatkozó műveletet (például távoli zárolást) a felügyeleti konzolban. Ha a művelet sikeres, az eszközt már az új MDM-szolgáltató kezeli.
- Ha problémába ütközik bizonyos eszközökkel, szüntesse meg azok regisztrációját, majd regisztrálja őket újra, így azok csatlakozni tudnak az új szolgáltatóhoz, és a lehető leggyorsabban újra kezelés alatt állhatnak.

## <a name="next-steps"></a>További lépések

A mobileszköz-felügyeleti szolgáltató beállítása után megkezdheti az [eszközök regisztrálását](device-enrollment.md).
