---
title: "Alkalmazásadatok védelme MAM-szabályzatokkal | Microsoft Docs"
description: "Ez a témakör azt ismerteti, hogyan segítenek a mobilalkalmazás-kezelési szabályzatok a vállalati adatok védelmében, az adatveszteség megakadályozásában és a személyes és munkahelyi adatok különválasztásában."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 40298ae2de5f3bc8090e19882e039c5ec6471820
ms.openlocfilehash: 3d3c3e0b5fa68f838b8cf1d72346d7abb140073a


---

# <a name="protect-app-data-using-mobile-application-management-policies-with-microsoft-intune"></a>Alkalmazásadatok védelme mobilalkalmazás-kezelési szabályzatokkal a Microsoft Intune segítségével

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Az alkalmazásadatok védelme
Az alkalmazottak mobileszközöket használnak a személyes és munkahelyi feladatokhoz. A produktív munkavégzést elősegítő környezet megteremtése mellett a véletlen vagy szándékos adatveszteség megelőzése is fontos szempont egy vállalatban.  Továbbá fontos szempont az is, hogy azon vállalati adatok védelmét is tudja biztosítani, melyekhez az alkalmazottak nem felügyelt eszközök használatával férnek hozzá.

Az Intune mobilalkalmazás-felügyeleti (MAM) szabályzatai segítségével gondoskodhat a vállalati adatok védelméről. Mivel az Intune MAM-szabályzatok **függetlenek a mobileszköz-kezelési (MDM) megoldásoktól**, a vállalati adatok védelmét az eszközök regisztrációjával és anélkül is biztosíthatja, így eszközkezelő megoldásra sincs feltétlenül szüksége. Az **alkalmazásszintű házirendek** érvénybe léptetésével korlátozhatja a vállalati erőforrásokhoz való hozzáférést, és az informatikai részleg adatainak is nagyobb védelmet nyújthat.

A MAM-szabályzatok olyan eszközökön futó alkalmazásokhoz konfigurálhatók, amelyek:

-   **Regisztrálva vannak a Microsoft Intune-ban:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

-   **Egy külső mobileszköz-kezelési (MDM) megoldásban vannak regisztrálva:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

  > [!NOTE]
  > A MAM házirendek használata nem ajánlott harmadik féltől származó mobilalkalmazás-kezelési és biztonságos tárolómegoldások használata esetén.

-   **Nincsenek regisztrálva mobileszköz-kezelési (MDM) megoldásban:** A kategóriába tartozó eszközök általában olyan, az alkalmazottak tulajdonában lévő eszközök, amelyek nincsenek az Intune-ban vagy más MDM-megoldásban kezelve vagy regisztrálva.

> [!IMPORTANT]
> Az Office 365-szolgáltatásokhoz kapcsolódó Office-mobilalkalmazások számára mobilalkalmazás-kezelési házirendeket hozhat létre. A MAM-szabályzatok nem támogatottak helyszíni Exchange-hez, Skype Vállalati verzióhoz vagy a SharePoint-szolgáltatásokhoz kapcsolódó alkalmazások esetében.

## <a name="benefits-of-using-mam-policies"></a>A MAM-szabályzatok használatának előnyei

-   **A vállalati adatok védelmét alkalmazási szinten biztosítják.** Mivel a mobilalkalmazás-felügyelet nem igényel eszközkezelést, a felügyelt és a nem felügyelt eszközökön is biztosíthatja a vállalati adatok védelmét. A felügyelet a felhasználói azonosítón alapul, így nincs szükség az eszközkezelőre.

-   **A felhasználói termelékenység változatlan marad, és a szabályzatok sem lépnek érvénybe, ha az alkalmazásokat személyes környezetben használja.** A szabályzatok kizárólag munkahelyi környezetben vannak alkalmazva, így a vállalati adatok védelmét a személyes adatok érintése nélkül biztosíthatja.

Az MDM-megoldások és MAM-szabályzatok együttes használata további előnyökkel is jár, valamint a vállalatok a MAM-szabályzatokat MDM-megoldásokkal és azok nélkül is használhatják. Előfordulhat például, hogy egy alkalmazott egyszerre használja munkahelyi telefonját és személyes táblagépét. Ebben az esetben a munkahelyi telefon MDM-ben regisztrált és MAM-szabályzatok által védett, míg a személyes eszközt csak a MAM-szabályzatok védik.

- **Az MDM biztosítja az eszköz védettségét.** Segítségével például PIN-kódot kérhet az eszköz eléréséhez, vagy felügyelt alkalmazásokat telepíthet az eszközre. Az MDM-megoldáson keresztül is telepíthet alkalmazásokat eszközökre, így jobban szabályozhatja az alkalmazáskezelést.

- **A MAM-szabályzatok biztosítják az alkalmazási rétegek védelmét.** Például egy szabályzat segítségével PIN-kódot kérhet egy alkalmazás munkahelyi környezetben való megnyitásához, meggátolhatja az alkalmazások közötti adatmegosztást, illetve megakadályozhatja a vállalati alkalmazások adatainak személyes tárolóhelyre való mentését.

## <a name="devices-that-support-mam"></a>A mobilalkalmazás-felügyeletet támogató eszközök
A MAM-szabályzatok jelenleg a következő rendszereken támogatottak:
-   iOS 8.1-es vagy újabb verzió
-   Android 4 vagy újabb verzió

>[!NOTE]
>A Windows-eszközök az MAM-ben regisztrációs forgatókönyv hiányában nem támogatottak. A Windows 10-eszközöket azonban >regisztrálhatja az Intune-ba, amelyben lehetőség van a hasonló funkciókat biztosító Windows Információvédelem >használatára. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


##  <a name="how-mam-policies-protect-app-data"></a>A MAM-szabályzatok és az alkalmazásadatok védelme

###  <a name="apps-without-mam-policies"></a>MAM-szabályzatok nélküli alkalmazások

![Az adatok az alkalmazások közötti, MAM-szabályzatok hiányában szabad mozgását bemutató kép](../media/Apps_without_MAM_policies.png)

A korlátozások nélkül használt alkalmazások miatt összekeveredhetnek a vállalati és személyes adatok. A vállalati adatok személyes tárolóhelyekre vagy a vállalaton kívüli alkalmazásokba kerülnek át, ami adatvesztéssel is járhat. Az ábrán a nyilak a korlátozások nélküli adatátvitelt jelölik a (vállalati és személyes) alkalmazások között és a tárolási helyekre.

### <a name="data-protection-with-mam-policies"></a>Adatvédelem MAM-szabályzatokkal

![A vállalati adatok MAM-szabályzatok alkalmazása esetén megvalósuló védelmét bemutató kép](../media/Apps_with_mobile_app_policies.png)

A MAM-szabályzatok használatával megakadályozható a vállalati adatok az eszköz helyi tárolójára történő mentése, illetve korlátozható a más, MAM-szabályzatok által nem védett alkalmazásokba irányuló adatmozgás. A MAM-szabályzatok beállításai a következőket tartalmazzák:
- Adatáthelyezési szabályzatok, például **A Mentés másként művelet letiltása** és **A kivágás, másolás és beillesztés korlátozása**.
- A hozzáférési szabályzat beállításai, például **Egyszerű PIN-kód megkövetelése a hozzáféréshez** és **A felügyelt alkalmazások futásának letiltása a függetlenített vagy feltört eszközökön**.

### <a name="data-protection-with-mam-policies-on-devices-that-are-managed-by-a-mdm-solution"></a>Adatvédelem MAM-szabályzatokkal az MDM-megoldások által felügyelt eszközökön

![A MAM-szabályzatok BYOD-eszközökön való működését bemutató kép](../media/MAM_BYOD_November.png)

**MDM-megoldásban regisztrált eszközök esetén**: A fentebbi ábra bemutatja azokat a védelmi rétegeket, amelyeket az MDM- és MAM-szabályzatok együttes használata biztosít.

Az MDM-megoldás:

-   Regisztrálja az eszközt.

-   Telepíti az alkalmazásokat az eszközön.

-   Folyamatosan biztosítja az eszköz megfelelőségét és felügyeletét.

**A MAM-szabályzatok előnyei:**

-   Segítenek megakadályozni a vállalati adatok kiszivárgását a fogyasztói alkalmazásokba és szolgáltatásokba.

-   Korlátozásokat alkalmazhatnak (mentés másként, vágólap, PIN-kód stb.) a mobilalkalmazásokra.

-   Az alkalmazások az eszközről való eltávolítása nélkül törölhetik a vállalati adatokat az alkalmazásokból.


### <a name="data-protection-with-mam-policies-for-devices-without-enrollment"></a>Adatvédelem MAM-szabályzatokkal a nem regisztrált eszközökön

![A MAM-szabályzatok felügyelt eszközökön való működését bemutató kép](../media/MAM_ManagedDevices_November.png)

A fenti ábra az alkalmazási szintű, MDM nélküli adatvédelmi szabályzatok működését mutatja be.

Olyan BYOD-eszközök esetén, amelyek semmilyen MDM-megoldásban nincsenek regisztrálva, a MAM-szabályzatok segítenek alkalmazási szinten biztosítani a vállalati adatok védelmét.

Néhány korlátozást azonban érdemes figyelembe vennie:

-   Nem telepíthet alkalmazásokat az eszközre. A felhasználóknak az áruházból kell letölteniük az alkalmazásokat.

-   Az ilyen eszközökön nem építhetők ki tanúsítványprofilok.

-   Az ilyen eszközökön nem tud vállalati Wi-Fi- és VPN-beállításokat konfigurálni.


## <a name="multi-identity"></a>Többszörös identitás

A többszörös identitást támogató alkalmazások esetén az alkalmazás különböző (munkahelyi és személyes) fiókok használatával is elérhető, ilyenkor a MAM-szabályzatokat csak az alkalmazások munkahelyi környezetben való használata esetén alkalmazza a rendszer.  

Például, ha egy felhasználó a munkahelyi fiókjával nyitja meg a OneDrive alkalmazást, akkor nem tudja áthelyezni a fájlokat egy személyes tárolóhelyre. Ha azonban a felhasználó a OneDrive alkalmazást a személyes fiókjával használja, akkor korlátozás nélkül másolhat és helyezhet át adatokat a személyes OneDrive-jából.  

A többszörös identitásos hozzáférést minden Office-mobilalkalmazás támogatja.

##  <a name="next-steps"></a>További lépések
- [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése a Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO4-->


