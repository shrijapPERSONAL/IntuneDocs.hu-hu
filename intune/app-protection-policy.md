---
title: "Mik azok az alkalmazásvédelmi szabályzatok?"
titleSuffix: Azure portal
description: "Ez a témakör azt ismerteti, hogyan védhetők a céges adatok a Microsoft Intune alkalmazásvédelmi szabályzataival.”"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/19/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6645261e2a90ea3890dc22b42fe65d6af4af6e5
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-app-protection-policies"></a>Mik azok az alkalmazásvédelmi szabályzatok?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazásvédelmi szabályzatai segítik a céges adatok védelmét és az adatvesztés megelőzését.

## <a name="how-you-can-protect-app-data"></a>Az alkalmazásadatok védelme
Az alkalmazottak mobileszközöket használnak a személyes és munkahelyi feladatokhoz.  A produktív munkavégzést elősegítő környezet megteremtése mellett a véletlen vagy szándékos adatveszteség megelőzése is fontos szempont egy vállalatban.  Fontos továbbá, hogy az eszközhasználattal elért vállalati adatok védelme akkor is megvalósulhasson, ha az adott eszközöket nem felügyeli.

Az Intune alkalmazásvédelmi szabályzataival védheti a céges adatokat. Mivel az Intune alkalmazásvédelmi szabályzatai **függetlenek a mobileszköz-kezelési (MDM) megoldásoktól**, a vállalati adatok védelme az eszközök regisztrációja nélkül is biztosítható, így eszközkezelő megoldásra sincs feltétlenül szükség. Az **alkalmazásszintű házirendek** érvénybe léptetésével korlátozhatja a vállalati erőforrásokhoz való hozzáférést, és az informatikai részleg adatainak is nagyobb védelmet nyújthat.

Az alkalmazásvédelmi szabályzatok olyan eszközökön futó alkalmazáshoz konfigurálhatók, amelyek:

- **Regisztrálva vannak a Microsoft Intune-ban:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

-   **Regisztrálva vannak egy harmadik fél mobileszköz-felügyeleti (MDM) megoldásában:** A kategóriába tartozó eszközök általában vállalati tulajdonú eszközök.

  > [!NOTE]
  > A mobilalkalmazás-felügyeleti szabályzatokat nem ajánlott harmadik fél mobileszköz-kezelőjével vagy biztonságos tároló-megoldásokkal együtt használni.

-   **Nincsenek regisztrálva mobileszköz-felügyeleti (MDM) megoldásban:** A kategóriába tartozó eszközök általában olyan, alkalmazottak által tulajdonolt eszközök, amelyek nincsenek az Intune-ban vagy más MDM-megoldásban kezelve vagy regisztrálva.

> [!IMPORTANT]
> Mobilalkalmazás-kezelési házirendeket hozhat létre az Office 365-szolgáltatásokhoz kapcsolódó Office-mobilalkalmazások számára. Az alkalmazásvédelmi szabályzatok a helyszíni Exchange-hez vagy a SharePoint-szolgáltatásokhoz kapcsolódó alkalmazások esetében nincsenek támogatva.

**Az alkalmazásvédelmi szabályzatok fontos előnyei a következők:**

-   Alkalmazásszinten biztosítja a vállalati adatok védelmét.  Mivel a mobilalkalmazás-felügyelet nem igényel eszközkezelést, a felügyelt és a nem felügyelt eszközökön is biztosíthatja a vállalati adatok védelmét. A felügyelet a felhasználói azonosítón alapul, így nincs szükség az eszközkezelőre.

-   A végfelhasználói termelékenység nem változik, és a szabályzatok sem lépnek érvénybe, ha személyes környezetben használják az alkalmazásokat.  Ha a szabályzatokat kizárólag munkahelyi környezetben alkalmazza, a személyes adatok érintése nélkül biztosíthatja a vállalati adatok védelmét.

Az MDM-megoldásoknak az alkalmazásvédelmi szabályzatokkal együttes használata további előnyökkel is jár, a vállalatoknál az alkalmazásvédelmi szabályzatok MDM-megoldásokkal és azok nélkül is használhatók. Egy alkalmazott például egyaránt használhat munkahelyi telefont és saját táblagépet.  Ebben az esetben a munkahelyi telefon MDM-ben regisztrált és alkalmazásvédelmi szabályzatokkal védett, míg a személyes eszközt csak az alkalmazásvédelmi szabályzatok védik.

- **Az MDM biztosítja az eszköz védettségét**.  Segítségével például PIN-kódot kérhet az eszköz eléréséhez, vagy felügyelt alkalmazásokat telepíthet az eszközre. Az MDM-megoldáson keresztül is telepíthet alkalmazásokat, így jobban szabályozhatja az alkalmazáskezelést.

- **Az alkalmazásvédelmi szabályzatok biztosítják az alkalmazásrétegek védelmét**. PIN-kódot kérhet például egy vállalati alkalmazás megnyitásához, az alkalmazások közötti adatmegosztáshoz, vagy az alkalmazásadatok személyes tárolóra való mentésének megakadályozásához.


### <a name="supported-platforms-for-app-protection-polices"></a>Az alkalmazásvédelmi szabályzatok által támogatott platformok
-   iOS 9-es vagy újabb verzió
-   Android 4.4-es vagy újabb verzió

A Windows-eszközök jelenleg nem támogatottak. A Windows 10-eszközöket azonban regisztrálhatja az Intune-ba, amelyben lehetőség van a hasonló funkciókat biztosító Windows Információvédelem használatára. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
##  <a name="how-app-protection-policies-protect-app-data"></a>Az alkalmazásvédelmi szabályzatok és az alkalmazásadatok védelme

####  <a name="apps-without-app-protection-policies"></a>Alkalmazásvédelmi szabályzat nélküli alkalmazások

![A kép azt ábrázolja, hogy alkalmazásvédelmi szabályzatok nélkül az adatok szabadon mozoghatnak az alkalmazások között](./media/apps-without-protection-policies.png)

A korlátozások nélkül használt alkalmazások miatt összekeveredhetnek a vállalati és személyes adatok.  Adatvesztéssel járhat, ha a vállalati adatok személyes tárolókra vagy a vállalaton kívüli alkalmazásokra kerülnek. Az ábrán a nyilak a korlátozások nélküli adatátvitelt jelölik a (vállalati és személyes) alkalmazások között és a tárolási helyekre.

### <a name="data-protection-with-app-protection-policies"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal

![A céges adatok alkalmazásvédelmi szabályzatokkal való védelmét ismertető kép ](./media/apps-with-protection-policies.png)


Az alkalmazásvédelmi szabályzatok révén megakadályozható a vállalati adatoknak az eszköz helyi tárolójára történő mentése, illetve korlátozható a más, alkalmazásvédelmi szabályzatokkal nem védett alkalmazásokba irányuló adatmozgás. Íme néhány az alkalmazásvédelmi szabályzatok beállításai közül:
- Adatáthelyezési szabályzatok, például **A Mentés másként művelet letiltása**,  **A kivágás, másolás és beillesztés korlátozása**.
- Hozzáférési szabályzati beállítások, például **A hozzáféréshez egyszerű PIN-kód szükséges**, **Felügyelt alkalmazások függetlenített vagy feltört eszközökön való futtatásának letiltása**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal az MDM-megoldásokkal felügyelt eszközökön

![Az alkalmazásvédelmi szabályzatok BYOD-eszközökön való működését bemutató kép](./media/app-protection-policies-with-mdm.png)

**Az MDM-megoldásban regisztrált eszközökhöz**-

A fenti ábra az MDM és az alkalmazásvédelmi szabályzatok által közösen biztosított védelmi réteget mutatja be.

Az MDM-megoldás:

-   Regisztrálja az eszközt

-   Telepíti az alkalmazásokat az eszközön

-   Folyamatosan ellenőrzi az eszköz megfelelőségét és felügyeletét

**Az alkalmazásvédelmi szabályzatok hasznos vonásai:**

-   A vállalati adatok a fogyasztói alkalmazásokba és szolgáltatásokba való kiszivárgásának megelőzése

-   Korlátozások alkalmazása (mentés másként, vágólap, PIN stb.) a mobilalkalmazásokra

-   Céges adatok eltávolítása az alkalmazásokból a szóban forgó alkalmazások törlése nélkül


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal a nem regisztrált eszközökön

![Az alkalmazásvédelmi szabályzatok felügyelt eszközökön való működését bemutató kép](./media/app-protection-policies-without-mdm.png)

A fenti ábra az alkalmazásszintű, MDM nélküli adatvédelmi szabályzatokat mutatja be.

Mivel az MDM-megoldás nem regisztrálja a BYOD-eszközöket, az alkalmazásvédelmi szabályzatok segítségével alkalmazásszinten biztosíthatja a vállalati adatok védelmét.
Mindazonáltal néhány korlátozást érdemes figyelembe vennie, például:

-   Nem telepíthet alkalmazásokat az eszközre.  A végfelhasználónak az áruházból kell letölteniük az alkalmazásokat.

-   Az eszközön nem használhatók a tanúsítványprofilok.

-   Az eszközön nem használhatók a Wi-Fi- és VPN-beállítások.


## <a name="multi-identity"></a>Többszörös identitás

A több identitást támogató alkalmazások esetében az alkalmazás különböző (munkahelyi és személyes) fiókokkal is elérhető, ilyenkor az alkalmazásvédelmi szabályzatokat csak az alkalmazások munkahelyi környezetben való használata esetén alkalmazza a rendszer.

Például, ha egy felhasználó a munkahelyi fiókjával nyitja meg a OneDrive alkalmazást, akkor nem tudja áthelyezni a fájlokat egy személyes tárolóhelyre. Ha azonban a felhasználó a OneDrive alkalmazást a személyes fiókjával használja, akkor korlátozás nélkül másolhat és helyezhet át adatokat a személyes OneDrive-jából.

- További információ azon alkalmazásokról, amelyek támogatják az [MAM-et és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

##  <a name="next-steps"></a>További lépések

[Alkalmazásvédelmi szabályzatok létrehozása és telepítése Microsoft Intune-ban](app-protection-policies.md)
