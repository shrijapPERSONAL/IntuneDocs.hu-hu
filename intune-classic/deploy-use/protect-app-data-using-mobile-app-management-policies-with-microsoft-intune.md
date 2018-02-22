---
title: "Alkalmazásadatok védelme MAM-szabályzatok használatával"
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e5f9eb33ca877fba0d59cfd9ddbc23f5eb2cd05c
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2018
---
# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a>Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal a Microsoft Intune segítségével

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Az alkalmazásadatok védelme
Az alkalmazottak mobileszközöket használnak a személyes és munkahelyi feladatokhoz. A produktív munkavégzést elősegítő környezet megteremtése mellett a véletlen vagy szándékos adatveszteség megelőzése is fontos szempont egy vállalatban.  Továbbá fontos szempont az is, hogy azon vállalati adatok védelmét is tudja biztosítani, melyekhez az alkalmazottak nem felügyelt eszközök használatával férnek hozzá.

Az Intune alkalmazásvédelmi szabályzataival védheti a céges adatokat. Mivel az Intune alkalmazásvédelmi szabályzatai **függetlenek a mobileszköz-kezelési (MDM) megoldásoktól**, a mobilalkalmazás-felügyelettel (MAM) az eszközök regisztrációja nélkül is biztosítható a vállalati adatok védelme, így eszközkezelő megoldásra sincs feltétlenül szükség. Az **alkalmazásszintű házirendek** érvénybe léptetésével korlátozhatja a vállalati erőforrásokhoz való hozzáférést, és az informatikai részleg adatainak is nagyobb védelmet nyújthat.

Az alkalmazásvédelmi szabályzatok olyan eszközökön futó alkalmazásokhoz konfigurálhatók, amelyek:

-   **Regisztrálva vannak a Microsoft Intune-ban:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

-   **Egy külső mobileszköz-kezelési (MDM) megoldásban vannak regisztrálva:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

    > [!NOTE]
    > Az alkalmazásvédelmi szabályzatok használata nem ajánlott harmadik féltől származó mobilalkalmazás-kezelési és biztonságos tárolómegoldások használata esetén.

-   **Nincsenek regisztrálva mobileszköz-kezelési (MDM) megoldásban:** A kategóriába tartozó eszközök általában olyan, az alkalmazottak tulajdonában lévő eszközök, amelyek nincsenek az Intune-ban vagy más MDM-megoldásban kezelve vagy regisztrálva.

> [!IMPORTANT]
> Az Office 365 szolgáltatásaihoz csatlakozó Office-mobilalkalmazások számára létrehozhat alkalmazásvédelmi szabályzatokat. Az alkalmazásvédelmi szabályzatok nem támogatottak helyszíni Exchange-hez, Skype Vállalati verzióhoz vagy a SharePoint Serviceshez csatlakozó alkalmazások esetében.

## <a name="benefits-of-using-app-protection-policies"></a>Az alkalmazásvédelmi szabályzatok használatának előnyei

-   **A vállalati adatok védelmét alkalmazási szinten biztosítják.** Mivel a mobilalkalmazás-felügyelet nem igényel eszközkezelést, a felügyelt és a nem felügyelt eszközökön is biztosíthatja a vállalati adatok védelmét. A felügyelet a felhasználói azonosítón alapul, így nincs szükség az eszközkezelőre.

-   **A felhasználói termelékenység változatlan marad, és a szabályzatok sem lépnek érvénybe, ha az alkalmazásokat személyes környezetben használja.** A szabályzatok kizárólag munkahelyi környezetben vannak alkalmazva, így a vállalati adatok védelmét a személyes adatok érintése nélkül biztosíthatja.

Az MDM-megoldások és az alkalmazásvédelmi szabályzatok együttes használata további előnyökkel is jár, valamint a vállalatok MDM-megoldásokkal és azok nélkül is használhatják az alkalmazásvédelmi szabályzatokat. Előfordulhat például, hogy egy alkalmazott egyszerre használja munkahelyi telefonját és személyes táblagépét. Ebben az esetben a munkahelyi telefon regisztrálva van az MDM-ben, és alkalmazásvédelmi szabályzatok védik, míg a személyes eszközt csak az alkalmazásvédelmi szabályzatok védik.

- **Az MDM biztosítja az eszköz védettségét.** Segítségével például PIN-kódot kérhet az eszköz eléréséhez, vagy felügyelt alkalmazásokat telepíthet az eszközre. Az MDM-megoldáson keresztül is telepíthet alkalmazásokat eszközökre, így jobban szabályozhatja az alkalmazáskezelést.

- **Az alkalmazásvédelmi szabályzatok gondoskodnak az alkalmazási rétegbeli védelemről**. Például egy szabályzat segítségével PIN-kódot kérhet egy alkalmazás munkahelyi környezetben való megnyitásához, meggátolhatja az alkalmazások közötti adatmegosztást, illetve megakadályozhatja a vállalati alkalmazások adatainak személyes tárolóhelyre való mentését.

## <a name="devices-that-support-mam"></a>A mobilalkalmazás-felügyeletet támogató eszközök
Az Intune alkalmazásvédelmi szabályzatplatformjainak támogatása az Office alkalmazásplatformok támogatásával van összhangban. További információt az [Office rendszerkövetelményei](https://products.office.com/en-US/office-system-requirements) című témakörben talál.

>[!NOTE]
>A Windows-eszközök az MAM-ben regisztrációs forgatókönyv hiányában nem támogatottak. A Windows 10-eszközöket azonban regisztrálhatja az Intune-ba, amelyben lehetőség van a hasonló funkciókat biztosító Windows Információvédelem használatára. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


##  <a name="how-app-protection-policies-protect-app-data"></a>Az alkalmazásvédelmi szabályzatok és az alkalmazásadatok védelme

###  <a name="apps-without-app-protection-policies"></a>Alkalmazásvédelmi szabályzat nélküli alkalmazások

![A kép azt ábrázolja, hogy alkalmazásvédelmi szabályzatok nélkül az adatok szabadon mozoghatnak az alkalmazások között](../media/Apps_without_MAM_policies.png)

A korlátozások nélkül használt alkalmazások miatt összekeveredhetnek a vállalati és személyes adatok. A vállalati adatok személyes tárolóhelyekre vagy a vállalaton kívüli alkalmazásokba kerülnek át, ami adatvesztéssel is járhat. Az ábrán a nyilak a korlátozások nélküli adatátvitelt jelölik a (vállalati és személyes) alkalmazások között és a tárolási helyekre.

### <a name="data-protection-with-app-protection-policies"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal

![A vállalati adatok alkalmazásvédelmi szabályzatokkal való védelmét ismertető kép](../media/Apps_with_mobile_app_policies.png)

Az alkalmazásvédelmi szabályzatok révén megakadályozható a vállalati adatoknak az eszköz helyi tárolójára történő mentése, illetve korlátozható a más, alkalmazásvédelmi szabályzatokkal nem védett alkalmazásokba irányuló adatmozgás. Íme néhány az alkalmazásvédelmi szabályzatok beállításai közül:
- Adatáthelyezési szabályzatok, például **A Mentés másként művelet letiltása** és **A kivágás, másolás és beillesztés korlátozása**.
- A hozzáférési szabályzat beállításai, például **Egyszerű PIN-kód megkövetelése a hozzáféréshez** és **A felügyelt alkalmazások futásának letiltása a függetlenített vagy feltört eszközökön**.

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a>Alkalmazásvédelemmel történő adatvédelem az MDM-megoldásokkal felügyelt eszközökön

![Az alkalmazásvédelmi szabályzatok BYOD-eszközökön való működését bemutató kép](../media/MAM_BYOD_November.png)

**MDM-megoldásban regisztrált eszközök esetén**: A fentebbi ábra bemutatja azokat a védelmi rétegeket, amelyeket az MDM és az alkalmazásvédelmi-szabályzatok együttes használata biztosít.

Az MDM-megoldás:

-   Regisztrálja az eszközt.

-   Telepíti az alkalmazásokat az eszközön.

-   Folyamatosan biztosítja az eszköz megfelelőségét és felügyeletét.

**Az alkalmazásvédelmi szabályzatok a következő előnyöket nyújtják:**

-   Segítenek megakadályozni a vállalati adatok kiszivárgását a fogyasztói alkalmazásokba és szolgáltatásokba.

-   Korlátozásokat alkalmazhatnak (mentés másként, vágólap, PIN-kód stb.) a mobilalkalmazásokra.

-   Az alkalmazások az eszközről való eltávolítása nélkül törölhetik a vállalati adatokat az alkalmazásokból.


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Alkalmazásvédelmi szabályzatokkal történő adatvédelem a nem regisztrált eszközökön

![Az alkalmazásvédelmi szabályzatok felügyelt eszközökön való működését bemutató kép](../media/MAM_ManagedDevices_November.png)

A fenti ábra az alkalmazási szintű, MDM nélküli adatvédelmi szabályzatok működését mutatja be.

Az MDM-megoldásban nem regisztrált BYOD-eszközök esetében az alkalmazásvédelmi szabályzatok elősegíti a vállalati adatok alkalmazásszintű védelmét.

Néhány korlátozást azonban érdemes figyelembe vennie:

-   Nem telepíthet alkalmazásokat az eszközre. A felhasználóknak az áruházból kell letölteniük az alkalmazásokat.

-   Az ilyen eszközökön nem építhetők ki tanúsítványprofilok.

-   Az ilyen eszközökön nem tud vállalati Wi-Fi- és VPN-beállításokat konfigurálni.


## <a name="multi-identity"></a>Többszörös identitás

A több identitást támogató alkalmazások esetében az alkalmazás különböző (munkahelyi és személyes) fiókokkal is elérhető, ilyenkor az alkalmazásvédelmi szabályzatokat csak az alkalmazások munkahelyi környezetben való használata esetén alkalmazza a rendszer.  

Például, ha egy felhasználó a munkahelyi fiókjával nyitja meg a OneDrive alkalmazást, akkor nem tudja áthelyezni a fájlokat egy személyes tárolóhelyre. Ha azonban a felhasználó a OneDrive alkalmazást a személyes fiókjával használja, akkor korlátozás nélkül másolhat és helyezhet át adatokat a személyes OneDrive-jából.  

- További információ azon alkalmazásokról, amelyek támogatják az [MAM-et és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

##  <a name="next-steps"></a>További lépések
- [Felkészülés az alkalmazásvédelmi szabályzatok konfigurálására](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
