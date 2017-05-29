---
title: "Gyakori kérdések az MAM-ről és az alkalmazásvédelemről"
description: "Ez a cikk az Intune mobilalkalmazás-kezeléssel (MAM) és az Intune alkalmazásvédelemmel kapcsolatos gyakori kérdésekre adott válaszokat ismerteti."
keywords: 
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 32446d9a6f9383b5449dbabf288b0eac0b483ebb
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Gyakori kérdések az MAM-ről és az alkalmazásvédelemről

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a cikk az Intune mobilalkalmazás-kezeléssel (MAM) és az Intune alkalmazásvédelemmel kapcsolatos gyakori kérdésekre adott válaszokat ismerteti.

## <a name="mam-basics"></a>Az MAM alapjai


**Mi az MAM?** Az [Intune mobilalkalmazás-kezelés](../deploy-use/overview-of-app-lifecycle-in-microsoft-intune.md) olyan Intune-beli felügyeleti összetevők csoportja, amelyek lehetővé teszik mobilalkalmazások közzétételét és leküldését a felhasználók részére, valamint azok konfigurálását, védelmét, figyelését és frissítését.

**Milyen előnyöket kínál az MAM-alkalmazásvédelem?** Az MAM védi munkahelye adatait az alkalmazáson belül. Az MAM-WE segítségével a bizalmas adatokat tartalmazó munkahelyi vagy iskolai alkalmazások szinte bármilyen eszközön felügyelhetők, beleértve a személyes tulajdonú eszközöket is saját eszközök használata (BYOD) esetén. Több irodai alkalmazás felügyelhető az Intune MAM-mel, például a Microsoft Office-alkalmazások. Lásd a nyilvánosan elérhető, [Intune-hoz előkészített alkalmazások](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) hivatalos listáját.

**Milyen eszközkonfigurációkat támogat az MAM?** Az Intune MAM két konfigurációt támogat:
  1. **Intune MDM + MAM**: az MAM első indításakor támogatott első konfiguráció. A rendszergazda csak az Intune mobileszköz-kezelésben (MDM) regisztrált eszközökön felügyelheti az MAM- és alkalmazásvédelmi szabályzatokat használó alkalmazásokat. Az MDM + MAM-et használó alkalmazások felügyeletéhez a https://manage.microsoft.com webhelyen elérhető önálló Intune-konzolra van szükség.

  2. **MAM eszközregisztráció nélkül:** az eszközregisztráció nélküli MAM (MAM-WE) révén a rendszergazda felügyelheti az Intune MDM-ben nem regisztrált eszközökön található, MAM- és alkalmazásvédelmi szabályzatot használó alkalmazásokat. Ez azt jelenti, hogy az Intune csak külső EMM-szolgáltatóknál regisztrált eszközökön felügyelheti az alkalmazásokat. Az MAM-WE-t használó alkalmazások felügyeletéhez a http://portal.azure.com webhelyen található Azure-portálon elérhető Intune-konzol használata javasolt.


## <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

**Mik azok az alkalmazásvédelmi szabályzatok?** Az alkalmazásvédelmi szabályzatok olyan szabályok, amelyek biztosítják, hogy a céges adatok biztonságban maradnak, és nem kerülnek ki a felügyelt alkalmazásokból. A szabályzat egyfelől lehet olyan szabály, amely olyankor lép életbe, amikor a felhasználó megpróbál hozzáférni „céges” adatokhoz vagy áthelyezni azokat, másfelől azon műveletek csoportja, amelyeket a rendszer tilt vagy figyel, amikor az felhasználó az alkalmazást használja.

**Milyen példák vannak az alkalmazásvédelmi szabályzatok használatára?** Az alkalmazásvédelmi szabályzat egyes beállításairól részletes információt [Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban ](../deploy-use/android-mam-policy-settings.md) és az [iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása ](../deploy-use/ios-mam-policy-settings.md) című cikkekben talál.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Az alkalmazásvédelmi szabályzatokkal felügyelhető alkalmazások

**Mely alkalmazásokat lehet alkalmazásvédelmi szabályzatokkal felügyelni?** Az [Intune App SDK](../develop/intune-app-sdk.md) által előkészített vagy az [Intune alkalmazásburkoló eszköz](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) által beburkolt, Intune alkalmazásvédelmi szabályzatokat használó alkalmazásokat. Lásd a nyilvánosan elérhető, [Intune-hoz előkészített alkalmazások](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) hivatalos listáját.

**Mik az alkalmazásvédelmi szabályzatok Intune használatára előkészített alkalmazáson való használatának alapkövetelményei?**
  1. A végfelhasználónak rendelkeznie kell egy Azure Active Directory- (AAD-) fiókkal. Az Intune-felhasználók Azure Active Directoryban történő létrehozásáról lásd: [Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md).

  2. A végfelhasználónak rendelkeznie kell az Azure Active Directory-fiókjához rendelt Microsoft Intune-licenccel. További információ a végfelhasználókhoz rendelt Intune-licencekről: [Intune-licencek kezelése](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

  3. A végfelhasználónak egy alkalmazásvédelmi szabályzattal társított biztonsági csoporthoz kell tartoznia. Ugyanezen alkalmazásvédelmi szabályzatnak a használt alkalmazással is társítva kell lennie. Alkalmazásvédelmi csoportokat az [Azure-portálon](http://portal.azure.com) található Intune-konzolban lehet létrehozni és telepíteni. Biztonsági csoportot jelenleg az [Office-portálon](http://portal.office.com) lehet létrehozni.

  4. A végfelhasználónak saját AAD-fiókjával be kell jelentkeznie az alkalmazásba.

**Mik az [Outlook mobilalkalmazás](https://www.microsoft.com/outlook-com/mobile/) használatának további feltételei?**

  1. A végfelhasználónak telepítenie kell az Outlook mobilalkalmazást az eszközére.

  2. A végfelhasználónak [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) postaládával és az AAD-fiókjához kapcsolt licenccel kell rendelkeznie.

  >[!NOTE]
  > Az Outlook mobilalkalmazás jelenleg csupán a Microsoft Exchange Online-t támogatja, a helyszíni Exchange-t vagy az Office 365 dedikált verzióban található Exchange-t nem.

**Mik a [Word, Excel és PowerPoint](https://products.office.com/business/office) alkalmazások használatának további feltételei?**

  1. A végfelhasználónak rendelkeznie kell az Azure Active Directory-fiókjához rendelt [Office 365 Vállalati vagy Nagyvállalati](https://products.office.com/business/compare-more-office-365-for-business-plans) licenccel. Az előfizetésnek tartalmaznia kell a mobileszközökön használt Office-alkalmazásokat és egy felhőalapú társzolgáltatás-fiókot a [OneDrive Vállalati verzióban](https://onedrive.live.com/about/business/). Az Office 365 licenc az [Office-portálon](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) történő hozzárendeléséhez kövesse [ezeket az utasításokat](http://portal.office.com).

  2. A végfelhasználónak rendelkeznie kell az eszközére telepített [OneDrive](https://onedrive.live.com/about/) alkalmazással, és be kell jelentkeznie az AAD-fiókjába.

  3. A végfelhasználóra életbe léptetett alkalmazásvédelmi szabályzatnak társítva kell lennie a OneDrive alkalmazással.

  >[!NOTE]
  > Az Office-mobilalkalmazások jelenleg csak a SharePoint Online verziót támogatják, a helyszíni SharePoint rendszert nem.

**Miért szükséges a OneDrive az Office-hoz?** Az Intune az alkalmazásban található összes adatot „cégesként” vagy „személyesként” jelöli meg. „Cégesnek” azok az adatok számítanak, amelyek vállalati forrásból származnak. Az Office-alkalmazásokat illetően az Intune a következőket tekinti vállalati forrásnak: e-mailek (Exchange) vagy felhőbeli tárhely (OneDrive alkalmazás Vállalati OneDrive-fiókkal).

**Mik a Skype Vállalati verzió használatának további feltételei?** A licenckövetelményekért lásd: [Skype Vállalati verzió](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > A Skype Vállalati verzió mobilalkalmazás jelenleg csupán a Skype Vállalati online verziót támogatja.

## <a name="app-protection-features"></a>Alkalmazásvédelmi funkciók

**Mit jelent a többszörös identitás támogatása?** A többszörösidentitás-támogatás az Intune App SDK-nak azt a képességét jelenti, hogy csak az alkalmazásba bejelentkezett munkahelyi vagy iskolai fiókra alkalmazza az alkalmazásvédelmi szabályzatokat. Ha egy személyes fiók van bejelentkezve az alkalmazásba, az adatok érintetlenek maradnak.

**Mi a többszörösidentitás-támogatás célja?** A többszörösidentitás-támogatással a „céges” és fogyasztói célközönséggel egyaránt rendelkező alkalmazásokat (például az Office-alkalmazásokat) a „céges” fiókok Intune alkalmazásvédelmi funkcióval felvértezve lehet kiadni.

**Mikor jelenik meg a PIN-kód megadására szolgáló képernyő?** Az Intune PIN-kód megadására szolgáló képernyő csak akkor jelenik meg, ha a felhasználó „céges” adatokhoz próbál meg hozzáférni az alkalmazásban. Például a Word/Excel/PowerPoint alkalmazásokban akkor jelenik meg, ha a végfelhasználó a OneDrive vállalati verzióból próbál megnyitni egy dokumentumot (feltételezve, hogy már sikeresen életbe léptett egy PIN-kódot kérő alkalmazásvédelmi szabályzatot).

**Mi helyzet az Outlook többszörös identitással való használata esetén?** Mivel az Outlook a személyes és a „céges” e-mailek kombinált nézetét kínálja, az Outlook alkalmazás már az indításkor kéri az Intune PIN-kódját.

**Mire szolgál az Intune az alkalmazáshoz tartozó PIN-kódja?** A személyes azonosítószám (PIN-kód) egy olyan kód, amellyel ellenőrizni lehet, hogy egy alkalmazásban a megfelelő felhasználó fér-e hozzá a céges adatokhoz.

  1. **Mikor kell a felhasználónak megadni a PIN-kódját?** Az Intune csak akkor kéri a felhasználó PIN-kódját az alkalmazáshoz, amikor a felhasználó „céges” adatokhoz szeretne hozzáférni. A többszörös identitást használó alkalmazások, például a Word/Excel/PowerPoint esetében a felhasználónak akkor kell megadnia a PIN-kódját, mikor „céges” dokumentumot vagy fájlt próbál megnyitni. Az egyszeres identitással rendelkező alkalmazások, például az Intune alkalmazásburkoló eszköz használatával előkészített üzletági alkalmazások már indításkor kérik a PIN-kódot, ugyanis az Intune App SDK tudja, hogy a felhasználó tevékenysége az alkalmazásban mindig „céges”.

  2. **Biztonságos-e a PIN-kód?** A PIN-kód arra szolgál, hogy csak a megfelelő felhasználó férhessen hozzá az alkalmazásban a céges adatokhoz. Így az Intune az alkalmazáshoz tartozó PIN-kódjának megváltoztatásához a végfelhasználónak be kell jelentkeznie a munkahelyi vagy iskolai fiókjába. Ezt a hitelesítést az Azure Active Directory biztonságos jogkivonatcsere révén kezeli, ami nem transzparens az Intune App SDK számára. A munkahelyi vagy iskolai adatok védelmére biztonsági szemszögből a titkosítás a legjobb módszer. A titkosítás nem függ össze az alkalmazás PIN-kódjával, csak annak saját alkalmazásvédelmi szabályzatával.

  3. **Hogyan védi a PIN-kódot az Intune a találgatásos támadásoktól?** Az alkalmazás PIN-szabályzatának részeként a rendszergazda beállíthatja, hogy legfeljebb hányszor adhatja meg a felhasználó a PIN-kódját, mielőtt a rendszer zárolná az alkalmazást. Bizonyos számú kísérlet után az Intune App SDK törölheti az összes „céges” adatot az alkalmazásban.

**Mi a helyzet a titkosítással?** A rendszergazdák olyan alkalmazásvédelmi szabályzatokat léptethetnek életbe, amelyek előírják az alkalmazásadatok titkosítását. A szabályzat részeként a rendszergazda azt is megadhatja, hogy mikor kell titkosítani a tartalmat.

  1. **Hogyan titkosítja az adatokat az Intune?** Az alkalmazásvédelmi szabályzat titkosítási beállításáról részletes információt [Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban](../deploy-use/android-mam-policy-settings.md) és az [iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása](../deploy-use/ios-mam-policy-settings.md) című cikkekben talál.

  2. **Mi kerül titkosításra?** Csak a rendszergazda alkalmazásvédelmi szabályzatának értelmében „cégesként” megjelölt adatok. „Cégesnek” azok az adatok számítanak, amelyek vállalati forrásból származnak. Az Office-alkalmazásokat illetően az Intune a következőket tekinti vállalati forrásnak: e-mailek (Exchange) vagy felhőbeli tárhely (OneDrive alkalmazás Vállalati OneDrive-fiókkal). Az Intune alkalmazásburkoló által előkészített üzletági alkalmazások esetében minden alkalmazásadat „cégesnek” minősül.

**Hogyan törli távolról az adatokat az Intune?** Az Intune három különböző módon törölhet adatokat: teljes törlés az eszközről, MDM szelektív törlés és MAM szelektív törlés. A távoli MDM törléssel kapcsolatos további információkat talál az [Adatok védelme teljes vagy szelektív törléssel a Microsoft Intune használatával](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) című cikkben. Az MAM szelektív törléssel kapcsolatos további információkat talál az [A Microsoft Intune-nal felügyelt vállalati alkalmazások adatainak törlése](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) című cikkben.

  1. **Mi a teljes törlés?** A [teljes törlés](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) törli **az eszközről** az összes adatot és beállítást, visszaállítva az alapértelmezett gyári beállításokat. Az eszközt a rendszer eltávolítja az Intune-ból.
  >[!NOTE]
  > Teljes törlés csak az Intune mobileszköz-kezelésben regisztrált eszközökön hajtható végre.

  2. **Mi az MDM szelektív törlés?** A szelektív törlésről lásd: [Adatok védelme teljes vagy szelektív törléssel a Microsoft Intune használatával](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe).

  3. **Mi az MAM szelektív törlés?** A MAM szelektív törlés egyszerűen eltávolítja a vállalati alkalmazásadatokat egy alkalmazásból. A kérelem az Intune Azure-portál használatával küldhető be. A törlési kérelem beküldéséről az [A Microsoft Intune-nal felügyelt vállalati alkalmazások adatainak törlése](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) című cikk nyújt tájékoztatást.

  4. **Milyen gyorsan megy végbe az MAM szelektív törlés?** Ha a felhasználó a szelektív törlés elindítását követően is használja az alkalmazást, az Intune App SDK 30 percenként ellenőrzi, hogy érkezett-e az Intune MAM szolgáltatásból kérés a szelektív törlésre. Akkor is ellenőrzi a szelektív törlést, amikor a felhasználó először indítja el az alkalmazást és lép be a munkahelyi vagy iskolai fiókjába.

**Miért nem működnek a helyszíni szolgáltatások az Intune-nal védett alkalmazásokkal?** Az Intune alkalmazásvédelem megköveteli a felhasználói identitás konzisztenciáját az alkalmazás és az Intune App SDK között. Ez kizárólag modern hitelesítés révén garantálható. Előfordulnak olyan helyzetek, amelyekben az alkalmazások működnek a helyszíni konfigurációval, ám ezek a forgatókönyvek se nem konzisztensek, se nem garantáltak.

**Létezik biztonságos módja a webes hivatkozások megnyitásának a felügyelt alkalmazásokból?** Igen! A rendszergazda életbe léptethet és beállíthat egy alkalmazásvédelmi szabályzatot az [Intune Managed Browser alkalmazáshoz](../deploy-use/manage-internet-access-using-managed-browser-policies.md), amely egy, a Microsoft Intune által fejlesztett, az Intune használatával egyszerűen felügyelhető webböngésző. A rendszergazda előírhatja, hogy az Intune-hoz előkészített alkalmazásokban található összes webhivatkozást csak a Managed Browser alkalmazással lehessen megnyitni.


## <a name="app-experience-on-android"></a>Az alkalmazás felhasználói felülete Androidon

**Miért szükséges ahhoz a Munkahelyi portál alkalmazás, hogy az Intune alkalmazásvédelem működjön Android-eszközökön?** A legtöbb alkalmazásvédelmi funkció be van építve a Munkahelyi portál alkalmazásba. Annak ellenére, hogy a Munkahelyi portál alkalmazás mindig szükséges, eszközregisztrációra _nincs szükség_. Az MAM-WE-hez a végfelhasználónak telepítenie kell a Munkahelyi portál alkalmazást az eszközre.

## <a name="app-experience-on-ios"></a>Az alkalmazás felhasználói felülete iOS-en

**Az iOS megosztási bővítménnyel megnyithatom a munkahelyi vagy az iskolai adatokat a nem felügyelt alkalmazásokban, még akkor is, ha az adatátviteli szabályzat beállítása „csak felügyelt alkalmazások” vagy „nincs alkalmazás”. Nem jár ez adatszivárgással?** Az Intune alkalmazásvédelmi szabályzata nem tudja kezelni az iOS megosztási bővítményt az eszköz felügyelete nélkül. Ezért az _**Intune titkosítja a „céges” adatokat, mielőtt az alkalmazáson kívül megosztaná**_. Ezt úgy ellenőrizheti, hogy megpróbálja megnyitni a „céges” fájlt a felügyelt alkalmazáson kívül. A fájlnak titkosítottnak kell lennie, így a felügyelt alkalmazáson kívül mással nem nyitható meg.

### <a name="see-also"></a>További információ
- [Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban](../deploy-use/android-mam-policy-settings.md)
- [iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása](../deploy-use/ios-mam-policy-settings.md)
- [A mobilalkalmazás-kezelés beállításának ellenőrzése](../deploy-use/validate-mobile-application-management.md)
- [Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Microsoft Intune-támogatás kérése](../troubleshoot/how-to-get-support-for-microsoft-intune.md)

