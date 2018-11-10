---
title: Mik azok az alkalmazásvédelmi szabályzatok?
titleSuffix: Microsoft Intune
description: Hogyan segítik a Microsoft Intune alkalmazásvédelmi szabályzatai a céges adatok védelmét és az adatvesztés megelőzését.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: fea87d72e8d8485c1cde3038d357b8d6bc7f1c71
ms.sourcegitcommit: ab08dd841f16ae11f958c43b6262a9f6a0cabdd4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49102001"
---
# <a name="what-are-app-protection-policies"></a>Mik azok az alkalmazásvédelmi szabályzatok?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazásvédelmi szabályzatai segítik a céges adatok védelmét és az adatvesztés megelőzését.

## <a name="how-you-can-protect-app-data"></a>Az alkalmazásadatok védelme
Az alkalmazottak mobileszközöket használnak a személyes és munkahelyi feladatokhoz. A produktív munkavégzést elősegítő környezet megteremtése mellett a véletlen vagy szándékos adatveszteség megelőzése is fontos szempont egy vállalatban. Azoknak a vállalati adatoknak a védelme is fontos, amelyeket nem az Ön felügyelete alatt álló eszközökről érnek el.

Az Intune alkalmazásvédelmi szabályzatai **a mobileszköz-felügyeleti (MDM) megoldásoktól függetlenül** használhatók. Ennek köszönhetően a vállalati adatokat attól függetlenül védheti, hogy regisztrálta-e az eszközöket egy eszközfelügyeleti megoldásba. Az **alkalmazásszintű házirendek** érvénybe léptetésével korlátozhatja a vállalati erőforrásokhoz való hozzáférést, és az informatikai részleg adatainak is nagyobb védelmet nyújthat.

Az alkalmazásvédelmi szabályzatok olyan eszközökön futó alkalmazásokhoz konfigurálhatók, amelyek:

- **Regisztrálva vannak a Microsoft Intune-ban:** Ezek általában vállalati tulajdonú eszközök.

- **Regisztrálva vannak egy harmadik fél mobileszköz-felügyeleti (MDM) megoldásában:** Ezek általában vállalati tulajdonú eszközök.

  > [!NOTE]
  > A mobilalkalmazás-felügyeleti szabályzatokat nem ajánlott külső mobileszköz-felügyeleti biztonságos tárolómegoldásokkal együtt használni.

- **Nincsenek regisztrálva mobileszköz-felügyeleti (MDM) megoldásban:** Ezek általában alkalmazottak tulajdonában álló eszközök, amelyek nincsenek az Intune-ban vagy más MDM-megoldásban kezelve vagy regisztrálva.

> [!IMPORTANT]
> Mobilalkalmazás-kezelési házirendeket hozhat létre az Office 365-szolgáltatásokhoz kapcsolódó Office-mobilalkalmazások számára. Emellett a helyszíni Exchange-postafiókok hozzáférését is védheti, az iOS és Android rendszerű Outlookhoz készült Intune alkalmazásvédelmi szabályzatok létrehozásával és a hibrid modern hitelesítés engedélyezésével. A funkció használata előtt győződjön meg arról, hogy megfelel az [iOS-es és Androidos Outlook követelményeinek](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Az alkalmazásvédelmi szabályzatok a helyszíni Exchange-hez vagy a SharePoint-szolgáltatásokhoz kapcsolódó egyéb alkalmazások esetében nem támogatottak.

**Az alkalmazásvédelmi szabályzatok fontos előnyei a következők:**

-   Alkalmazásszinten biztosítja a vállalati adatok védelmét. Mivel a mobilalkalmazás-felügyelet nem igényel eszközkezelést, a felügyelt és a nem felügyelt eszközökön is biztosíthatja a vállalati adatok védelmét. A felügyelet a felhasználói azonosítón alapul, így nincs szükség az eszközkezelőre.

-   A végfelhasználói termelékenység nem változik, és a szabályzatok sem érvényesek, ha az alkalmazásokat személyes környezetben használják. A szabályzatok kizárólag munkahelyi környezetben vannak alkalmazva, így a vállalati adatok védelmét a személyes adatok érintése nélkül biztosíthatja.

Az MDM-megoldások és alkalmazásvédelmi szabályzatok együttes használata további előnyökkel is jár, és a vállalatoknál az alkalmazásvédelmi szabályzatok MDM-megoldásokkal és azok nélkül is használhatók. Vegyünk például egy alkalmazottat, aki egy munkahelyi telefont és egy saját táblagépet használ. A munkahelyi telefon regisztrálva van az MDM-ben, és érvényesek rá az alkalmazásvédelmi szabályzatok, míg a személyes eszközt csak az alkalmazásvédelmi szabályzatok védik.

- **Az MDM biztosítja az eszköz védettségét**. Segítségével például PIN-kódot kérhet az eszköz eléréséhez, vagy felügyelt alkalmazásokat telepíthet az eszközre. Az MDM-megoldáson keresztül is telepíthet alkalmazásokat, így jobban szabályozhatja az alkalmazáskezelést.

- **Az alkalmazásvédelmi szabályzatok biztosítják az alkalmazásrétegek védelmét**. Lehetőség van például a következőkre:
  - PIN-kódot kérhet egy alkalmazás vállalati környezetben való megnyitásához 
  - Szabályozhatja az adatok megosztását az alkalmazások között 
  - Megakadályozhatja az alkalmazásadatok személyes tárhelyre való mentését


### <a name="supported-platforms-for-app-protection-policies"></a>Az alkalmazásvédelmi szabályzatok által támogatott platformok
Az Intune alkalmazásvédelmi szabályzatok platformtámogatása az Office-mobilalkalmazások platformtámogatásához igazodik. További információt az [Office rendszerkövetelményeit](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg) ismertető témakör **mobilalkalmazásokkal** foglalkozó szakaszában talál.

A Windows-eszközök jelenleg nem támogatottak. A Windows 10-eszközöket azonban regisztrálhatja az Intune-ba, amelyben lehetőség van a hasonló funkciókat biztosító Windows Információvédelem használatára. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


## <a name="how-app-protection-policies-protect-app-data"></a>Az alkalmazásvédelmi szabályzatok és az alkalmazásadatok védelme

#### <a name="apps-without-app-protection-policies"></a>Alkalmazásvédelmi szabályzat nélküli alkalmazások

![A kép azt ábrázolja, hogy alkalmazásvédelmi szabályzatok nélkül az adatok szabadon mozoghatnak az alkalmazások között](./media/apps-without-protection-policies.png)

A korlátozások nélkül használt alkalmazások miatt összekeveredhetnek a vállalati és személyes adatok. Adatvesztéssel járhat, ha a vállalati adatok személyes tárolókra vagy az Ön hatáskörén kívüli alkalmazásokba kerülnek. Az előző ábrán a nyilak a korlátozások nélküli adatátvitelt jelölik a vállalati és személyes alkalmazások között, valamint a tárolási helyekre.


### <a name="data-protection-with-app-protection-policies"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal

![A vállalati adatok alkalmazásvédelmi szabályzatokkal való védelmét ábrázoló kép ](./media/apps-with-protection-policies.png)


Az alkalmazásvédelmi szabályzatokkal megakadályozható a vállalati adatoknak az eszköz helyi tárolójára való mentése. Emellett korlátozható a más, alkalmazásvédelmi szabályzatokkal nem védett alkalmazásokba irányuló adattovábbítás. Íme néhány az alkalmazásvédelmi szabályzatok beállításai közül:
- Adatáthelyezési szabályzatok, például **A Mentés másként művelet letiltása** és **A kivágás, másolás és beillesztés korlátozása**.
- A hozzáférési szabályzat beállításai, például **Egyszerű PIN-kód megkövetelése a hozzáféréshez** és **A felügyelt alkalmazások futásának letiltása a függetlenített vagy feltört eszközökön**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal a mobileszköz-felügyeleti megoldásokkal felügyelt eszközökön

![Az alkalmazásvédelmi szabályzatok BYOD-eszközökön való működését bemutató kép](./media/app-protection-policies-with-mdm.png)

**Az MDM-megoldásban regisztrált eszközökhöz**-

Az előző ábra az MDM és az alkalmazásvédelmi szabályzatok által közösen biztosított védelmi réteget mutatja be.

Az MDM-megoldás:

-   Regisztrálja az eszközt

-   Telepíti az alkalmazásokat az eszközön

-   Folyamatosan ellenőrzi az eszköz megfelelőségét és felügyeletét

**Az alkalmazásvédelmi szabályzatok hasznos vonásai:**

-   A vállalati adatok fogyasztói alkalmazásokba és szolgáltatásokba való kiszivárgásának megelőzése

-   Korlátozások (például *mentés másként*, *vágólap* vagy *PIN-kód*) alkalmazása az ügyfélalkalmazásokra

-   Céges adatok eltávolítása az alkalmazásokból a szóban forgó alkalmazások törlése nélkül


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Adatvédelem alkalmazásvédelmi szabályzatokkal a nem regisztrált eszközökön

![Az alkalmazásvédelmi szabályzatok felügyelt eszközökön való működését bemutató kép](./media/app-protection-policies-without-mdm.png)

Az előző ábra az alkalmazásszintű, MDM nélküli adatvédelmi szabályzatokat mutatja be.

Mivel az MDM-megoldás nem regisztrálja a BYOD-eszközöket, az alkalmazásvédelmi szabályzatok segítségével alkalmazásszinten biztosíthatja a vállalati adatok védelmét.
Mindazonáltal néhány korlátozást érdemes figyelembe vennie, például:

-   Nem telepíthet alkalmazásokat az eszközre. A végfelhasználónak az áruházból kell letölteniük az alkalmazásokat.

-   Az ilyen eszközökön nem építhetők ki tanúsítványprofilok.

-   Az eszközön nem használhatók a Wi-Fi- és VPN-beállítások.

## <a name="app-protection-global-policy"></a>Alkalmazásvédelmi globális szabályzat

A OneDrive-rendszergazdák az **admin.office.com** webhelyen az **Eszköz** hozzáférést választva konfigurálhatják a OneDrive- és SharePoint-ügyfélalkalmazások **mobilalkalmazás-kezelési** vezérlőit. 

A OneDrive felügyeleti konzolján elérhető beállításokkal konfigurálható a **Globális** szabályzat nevű speciális Intune alkalmazásvédelmi szabályzat. Ez a globális szabályzat a bérlőn belül az összes felhasználóra vonatkozik, és nincs lehetőség a szabályzat célzására. 

A szabályzat az engedélyezése után alapértelmezés szerint a választott beállításoknak megfelelően védi az iOS és Android rendszerre készült OneDrive és SharePoint alkalmazást. Az informatikai szakemberek az Intune-konzolon szerkeszthetik ezt a szabályzatot, ahol további célalkalmazásokat adhatnak hozzá, és bármely beállítását módosíthatják. 

Alapértelmezés szerint bérlőnként csak egy **Globális** szabályzat létezhet. Az [Intune Graph API-k](intune-graph-apis.md) használatával további globális szabályzatok is létrehozhatók bérlőnként, azonban ezt nem javasoljuk. A további globális szabályzatok létrehozása azért nem ajánlott, mert az ilyen szabályzatok megvalósításának hibaelhárítása igen bonyolult lehet.

A **Globális** szabályzat a bérlőn belül az összes felhasználóra vonatkozik, azonban ezeket a beállításokat bármely normál Intune alkalmazásvédelmi szabályzat felülbírálja.


## <a name="multi-identity"></a>Többszörös identitás

A több identitást támogató alkalmazások különböző (munkahelyi és személyes) fiókokkal is elérhetők. Ilyenkor az alkalmazásvédelmi szabályzatok csak az alkalmazások munkahelyi környezetben való használatára vonatkoznak.

Tekintsünk például egy felhasználót, aki a munkahelyi fiókjával nyitja meg a OneDrive alkalmazást. A felhasználó ebben a vállalati környezetben nem tudja áthelyezni a fájlokat a személyes tárolóhelyére. Ha később a személyes fiókjával használja a OneDrive-ot, akkor korlátozás nélkül másolhat és helyezhet át adatokat a személyes OneDrive-jából.

- További információ azon alkalmazásokról, amelyek támogatják az [MAM-et és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

## <a name="next-steps"></a>További lépések

[Alkalmazásvédelmi szabályzatok létrehozása és telepítése Microsoft Intune-ban](app-protection-policies.md)

## <a name="see-also"></a>Lásd még:
A harmadik féltől származó alkalmazások, például a Salesforce mobilalkalmazás, speciális módon működnek együtt az Intune-nal a vállalati adatok védelme érdekében. Ha szeretne többet megtudni arról, hogy a Salesforce alkalmazás konkrétan hogyan működik együtt az Intune-nal (az MDM alkalmazáskonfigurációs beállításait is beleértve), olvassa el [A Salesforce alkalmazás és a Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf) című témakört.
