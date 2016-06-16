---
# required metadata

title: Gyakori kérdések a Microsoft Intune-ról | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gyakori kérdések a Microsoft Intune-ról
Ebben a cikkben megválaszolunk néhány, a Microsoft Intune-nal kapcsolatban gyakran felmerülő kérdést. Ha itt nem talál választ a kérdésére, feltétlenül [tudassa velünk](https://microsoftintune.uservoice.com/).

## Általános problémák

-   **Hogyan szerezhetek tudomást arról, hogy frissült az Intune szolgáltatás?**

    Jelentkezzen be fiókjába a manage.microsoft.com webhelyen. Az Adminisztráció – áttekintés résznél válassza a **Szolgáltatás állapotának megjelenítése** elemet. Itt megtalálja a bérlő helyét és a karbantartási ütemtervet. Olvassa el a szolgáltatással kapcsolatos híreket az [Újdonságok](/intune/deploy-use/whats-new-in-microsoft-intune) című cikkben.

-   **Ha egy felhasználó átnevez egy eszközt a Vállalati portál alkalmazásban, a név az Intune-ban, illetve a Configuration Managerben is megváltozik?**

    Nem, a névváltozás csak a felhasználó kényelmét szolgálja.

-   **Van távoli segítségnyújtási funkció a mobileszközökhöz készült Intune-ban?**

    Nincs. Hasznosak lehetnek bizonyos külső alkalmazások, például a [Bomgar](http://www.bomgar.com/) <!---and [TeamViewer](https://www.teamviewer.com/)---> alkalmazás.

## Fiókok

-   **Ha megkezdtem az Intune kipróbálását, és létrehozok egy új bérlőt a próbaverzióhoz, felvehetem az Office 365-öt a próbaverzióba ugyanannak a bérlőnek a használatával?**

    Igen. Csak jelentkezzen be egy globális rendszergazdai fiókkal (például *globalisrendszergazda@&lt;vallalat&gt;.onmicrosoft.com*) meglévő Intune-bérlőjéből/-előfizetéséből.

-   **Ha hozzárendelek egy MDM-szolgáltatót az Intune-hoz egy próbaverziós előfizetés során, akkor nehezebben fogok tudni váltani egy másik vállalat szolgáltatására, amennyiben meggondolnám magamat az Intune-nal kapcsolatban?**

    Habár nehezen képzelhető el, hogy váltani szeretne az Intune-ról, az MDM-szolgáltató kiválasztása nincs hatással arra a képességére, hogy másik szolgáltatóra térjen át. Választhatja az Intune-t vagy az Intune-t System Center Configuration Managerrel.

-   **Használhatom meglévő Office 365-ös tartománynevemet következő Intune-fiókom létrehozásához?**

    Igen, ha azzal a szervezeti azonosítóval jelentkezik be, amely meglévő Office 365-ös bérlőjéhez és ellenőrzött tartományához van társítva, amikor létrehozza az Intune-próbaverziót vagy aktiválja a licenceit.

    Az Intune ez esetben ugyanazt a tartományt, ugyanazokat a felhasználókat stb. fogja használni, mint az Office 365-ös fiókja. Ne feledje, hogy minden egyes Office 365-felhasználót engedélyezni kell Intune-felhasználóként egy Intune-licenc használatával. Ezt annak a globális rendszergazdának kell elvégeznie, aki a bérlőt kezeli.

## Beléptetés

-   **Hol tudhatják meg felhasználóim, hogy hogyan regisztrálhatják eszközeiket?**

    Ehhez az [End-user Intune enrollment instructions for IT administrators](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) (Végfelhasználók Intune-regisztrálására vonatkozó utasítások rendszergazdák számára) oldalon található, igény szerint testre szabható információkat használja.

-   **Hogyan háríthatom el az eszközök beléptetésével kapcsolatos hibákat?**

    A regisztráció általános problémáinak megoldásai az [Eszközök regisztrálásával kapcsolatos problémák elhárítása az Intune-ban](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune) című szakaszban találhatók.

-   **Hogyan gyűjthetem be a beléptetési naplókat, ha egy felhasználó beléptetési problémát tapasztal?**

    Kövesse a [megjelenő útmutatást](http://www.microsoft.com/en-us/download/46391).

## Mobil eszközök felügyelete

-   **Általános kérdések a mobileszköz-kezelésről**

    -   **Az Intune észleli, ha az eszközt feltörik?**

        Igen, bizonyos operációs rendszerek esetén. A feltört eszközök felügyeletének módjával kapcsolatos információkért lásd: [Eszközmegfelelőségi szabályzat létrehozása](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md).

    -   **Törölhetem külön csak a vállalati adatokat egy eszközről?**

        Igen. A szelektív törléssel kapcsolatos információkért lásd: [Az adatok védelme távoli törléssel, távoli zárolással vagy új PIN kód létrehozásával](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

    -   **Van mód bizonyos webhelyek letiltására a mobileszköz böngészőjében az Intune-on keresztül?**

        A különböző platformok natív böngészőjében nincs erre lehetőség. Ha azonban telepíti az Intune által kezelt webböngészőt iOS- vagy Android-eszközére, lehetősége van engedélyezni vagy blokkolni az egyes URL-címeket. További információkért lásd: [Az internet-hozzáférés kezelése felügyelt böngészőszabályzatokkal](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).

    -   **Korlátozható, hogy egy felhasználó mely alkalmazásokat távolíthatja el?**

        Általában nem. A felügyelt iOS-eszközökön azonban megakadályozható, hogy egy felhasználó eltávolítson egy olyan alkalmazást, amelynek terjesztése az Apple Configurator használatával történt. 

    -   **Van mód a mobiladat-felhasználás kezelésére?**

        Nem közvetlenül ugyan, de a Wi-Fi-profilok eszközökre küldésével gondoskodhat arról, hogy a Wi-Fi legyen a kapcsolódás előnyben részesített módszere [A felhasználók vállalati hálózatokhoz való kapcsolódásának megkönnyítése Wi-Fi profilokkal](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md) című szakaszban leírtaknak megfelelően. Ezenkívül néhány platformon (például iOS és Android KNOX) lehetőség van a beállítások, például a hang és az adatroaming szabályozására is.

    -   **Meg lehet akadályozni, hogy egy felhasználó beléptessen egy eszközt? Mi a helyzet akkor, ha a vállalat tulajdonában álló eszközről van szó?**

        Általában nem. Egyéni Windows Phone-beállítások használatával azonban megakadályozhatja a felhasználók regisztrációját a Windows Phone 8.1 rendszerű eszközökön. A felügyelt és az Apple Eszközfelíratási programjába beléptetett iOS-eszközök esetében pedig szintén megelőzhető, hogy egy felhasználó beléptessen egy eszközt.

    -   **Megváltoztathatom az általam kiválasztott MDM-szolgáltatót?**

        Bizonyos esetekben megváltoztathatja az MDM-szolgáltatót. Ehhez lépjen kapcsolatba a Terméktámogatással a [Hogyan kérhet támogatást az Intune-hoz](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md) című szakaszban leírtak szerint. Az alábbi táblázat összefoglalja, hogy milyen változtatások lehetségesek. Az MDM-szolgáltató módosításához újra be kell léptetni az eszközöket.

        ||**Ide:** Intune!**Ide:** O365|**Ide:** Intune-nal bővített Configuration Manager| |**Innen:** Intune| |Igen&#42;|Igen| |**Innen:** O365||Igen&#42;||Igen| |**Innen:** Intune-nal bővített Configuration Manager|Igen|Igen| |
        
        &#42;Az Office 365 és az Intune MDM-szolgáltatója egyszerre is használható, így nem kell ismét beléptetnie az eszközöket.



-   **Windows**

    -   **Telepíthetek közvetlenül Windows Áruházbeli alkalmazást?**

        A nyilvánosan elérhető alkalmazások nem telepíthetők közvetlenül. Még ha le is tudja tölteni az XAP-fájlt, nem tudja feltölteni az Intune-ba, mert ez egy nyilvános XAP-fájl, amelyet titkosítottak és a fejlesztő kódaláíró tanúsítványával írtak alá. Csak az Ön által fejlesztett és saját kódaláíró tanúsítványával aláírt alkalmazások telepíthetők közvetlenül.

    -   **A vállalati portálon keresztül terjesztett Windows Phone Áruházbeli alkalmazásokhoz szükségük van a végfelhasználóknak Microsoft-fiókra?**

        Igen, a végfelhasználó csak Microsoft-fiókkal szerezhet be alkalmazásokat. Ez alól azok a közvetlenül telepített, magánjellegű LOB-alkalmazások képeznek kivételt, amelyek Microsoft-fiók nélkül telepíthetők az eszközökre.

    -   **Szükség van Microsoft-fiókra egy Windows Phone 8.1-eszközön ahhoz, hogy az Intune kezelje az eszközt?**

        Nem. A legtöbb alkalmazást azonban a nyilvános áruházból kell telepíteni.

        **Miért szükséges a Windows Phone-telefonok kezeléséhez Symantec-tanúsítvány?**
        A Windows Phone szabályozza, hogyan telepíthet alkalmazásokat. Minden Microsoft-fiókkal rendelkező felhasználó telepíthet alkalmazásokat a Windows Phone Áruházból, a vállalatok pedig telepíthetik vagy közvetlenül telepíthetik belső fejlesztésű üzletági (LOB) alkalmazásaikat a Windows Phone dokumentációjában leírt speciális eljárással. Üzletági alkalmazások telepítése esetén a Windows Phone-telefonok csak egyetlen, a Symantec által kibocsátott, különleges típusú tanúsítványt tekintenek megbízhatónak. Semmilyen más, kereskedelmi vagy egyénileg létrehozott tanúsítvány nem használható. Ez a követelmény nem csak az Intune szolgáltatásra, hanem minden mobileszköz-kezelési megoldásra igaz.

        A Symantec-tanúsítvány egy alkalmazásregisztrációs adatblokkot (AET) hoz létre. Az AET telepíthető eszközökre azok mobileszköz-kezelésre való regisztrálásakor, vagy telepíthető sávon kívül egy biztonságos webhelyről vagy egy e-mail mellékletéből. A rendszergazdáknak a [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439)-ban biztosított eszközökkel minden LOB-alkalmazást alá kell írniuk a Symantec-tanúsítvánnyal. Amikor a felhasználók LOB-alkalmazásokat próbálnak telepíteni, a Windows Phone operációs rendszer összeveti az AET-ben lévő aláírást az alkalmazás aláírásával. Ha az aláírások egyeznek, a telepítés folytatható. Ha az AET nem ellenőrizhető, a telepítés sikertelen lesz. Több okból is előfordulhat, hogy az AET-t nem lehet ellenőrizni:

        -   Az AET nem is lett telepítve az eszközön

        -   Az AET érvényessége lejárt

        -   Az AET nem az alkalmazás aláírására használt Symantec-tanúsítvánnyal lett létrehozva

        A Windows Phone nem követeli meg, hogy az AET jelen legyen a mobileszköz-kezelésre való regisztráció során, de az Intune 2014. november előtti kiadásaiban szükséges az AET és egy aláírt ssp.xap fájl, mivel más módon nem lehetett telepíteni az AET-t és az ssp.xap fájlt, csak a regisztráció során.

    **Hogyan hozza létre a rendszer az alkalmazásregisztrációs adatblokkot Intune-felhasználók számára?**
  Amikor a rendszergazdák feltöltik a Symantec-tanúsítványuk .pfx-fájlját, az Intune automatikusan létrehozza az AET-t, és telepíti a regisztrált Windows Phone-telefonokra. Az Intune-rendszergazdáknak nem szükséges a Windows Phone SDK AET Generator eszközét használniuk.

      > [!IMPORTANT] Az Intune nem támogatja az AET manuális létrehozását és sávon kívüli telepítését.

    **Milyen módosítások történtek, melyeknek köszönhetően csökkentek a Symantec-tanúsítvánnyal kapcsolatos követelmények?**
       Az Intune 2014. novemberi kiadásában olyan módosítások történtek, melyek lehetővé tesznek olyan forgatókönyveket, amelyekben a vállalatok nem rendelkeznek Symantec-tanúsítvánnyal.

       -   A Windows Phone 8.1 rendszerhez készült Vállalati portál az Áruházból telepíthető, így nem szükséges aláírni a Symantec-tanúsítvánnyal és összevetni az AET-vel. Ehelyett az alkalmazás az áruházbeli közzétételi folyamat részeként van hitelesítve.

        -   Windows Phone 8.1 rendszerű eszközöket anélkül is lehet regisztrálni, hogy AET lenne a telefonon. Ha van elérhető AET, azt a rendszer az eszköz az Intune szolgáltatással való első szinkronizálásakor telepíti. Az eszközt továbbra is az Intune fogja kezelni akkor is, ha nincs AET, a felhasználók pedig az Áruházból telepíthetik a Vállalati portált, és annak legtöbb szolgáltatását használhatják az alkalmazások aláírásához használt Symantec-tanúsítvány nélkül is.

        A Windows Phone 8 rendszerű eszközökre vonatkozó Symantec-követelmények nem módosultak. A Windows Phone 8 rendszerű eszközöknek rendelkezniük kell az aláírt ssp.xap fájllal és az AET-vel a regisztráció során, különben azok regisztrációja le lesz tiltva.

        **Mely szolgáltatásokat támogatja a rendszer, ha egy Windows Phone 8.1 rendszerű eszköz regisztrálva van, de nincs Symantec-tanúsítvány?**
        Ha egy Windows Phone 8.1 rendszerű eszköz regisztrálva van, de nincs Symantec-tanúsítvány, akkor a következőket végezheti el:

        -   Házirendek létrehozása és azok leküldése az eszközre

        -   Az IT részleg a Vállalati portálon megjelenő kapcsolattartási adatainak beállítása

        -   Az Áruházra mutató mélyhivatkozások létrehozása és azok elhelyezése a Vállalati portálon

        -   Weblapokra mutató hivatkozások létrehozása és azok elhelyezése a Vállalati portálon

        -   Használati feltételek létrehozása, melyeket a felhasználóknak el kell fogadnia, hogy használhassák a Vállalati portált

        Symantec-tanúsítvány nélkül egyetlen művelet, a LOB-alkalmazások telepítése nem hajtható végre.

        > [!IMPORTANT]
        > Az Intune Software Publisher eszköz az alkalmazások feltöltésekor nem ellenőrzi, hogy azok alá vannak-e írva. Ha aláíratlan alkalmazásokat terjeszt, és a felhasználók megpróbálják telepíteni őket, az sikertelen lesz.

        **Milyen műveleteket végezhetnek el a felhasználók, ha rendelkeznek a Vállalati portállal, de nincs Symantec-tanúsítvány?**
        A Windows Phone 8.1 rendszerű eszközöket azelőtt kell regisztrálni, hogy a felhasználók telepítenék a Vállalati portál alkalmazást az Áruházból. Ha egy eszköz nincs regisztrálva, a rendszer kéri a felhasználókat, hogy regisztrálják. A Vállalati portálon megjelenő kérdésre koppintva a felhasználók közvetlenül a **Beállítások / Munkahelyi fiók** területre juthatnak, ahol regisztrálhatják az eszközeiket.

        A felhasználók a következő műveleteket még akkor is elvégezhetik az Áruházból telepített Vállalati Portál alkalmazással, ha az eszköz nincs regisztrálva:

        -   A rendszergazda által esetlegesen beállított használati feltételek elfogadása vagy elutasítása. Ha egy felhasználó elutasítja a használati feltételeket, a Vállalati portál alkalmazás bezáródik.

        -   Az IT részleg kapcsolattartási adatainak megtekintése

        -   Bármely regisztrált eszköz megtekintése, beleértve az iOS, Android és Windows rendszerű eszközöket

        -   Áruházbeli alkalmazásokra mutató mélyhivatkozások használata

        -   Weblapok megnyitása webes hivatkozásokkal

        Ha az eszköz regisztrálva van, a felhasználók megtekinthetik az eszközt az **Eszközök** listában. A regisztrálása után az eszközre minden az Intune szolgáltatásban alkalmazott házirend érvényes. Az eszközöket az AET beszerzéséhez és a LOB-alkalmazások telepítéséhez regisztrálni kell. A LOB-alkalmazások telepítését megkísérlő, de nem regisztrált eszközöket a regisztrációhoz irányítja a rendszer.

        A felhasználók egyedül a rendszergazda által terjesztett LOB-alkalmazások telepítését nem végezhetik el, ha a vállalat nem rendelkezik Symantec-tanúsítvánnyal.

        **A vállalat már rendelkezik tanúsítvánnyal, és már folyik a Windows Phone 8.1 rendszerű eszközök regisztrálása. Van bármilyen teendő most, hogy a Vállalati portál elérhető az Áruházban?**
        A letöltőközpontban aktuálisan elérhető ssp.xap fájl továbbra is működik Windows Phone 8.1 rendszerű eszközökön. Továbbra is utasíthatók arra a felhasználók, hogy regisztráljanak, és a telepítés során szerezzék be a vállalati portál alkalmazást.

        **Mik az előnyei és a hátrányai annak, ha a felhasználók az Áruházból szerzik be a Vállalati portál alkalmazást?**
        Előnyök:

        -   A felhasználók megkaphatják a mély- és webes hivatkozásokat akkor is, ha az adott Windows Phone 8.1 rendszerű eszköz nincs regisztrálva

        -   Amikor a Microsoft frissíti a Vállalati portált, az áruházbeli alkalmazás automatikusan frissül, letöltés, aláírás és az ssp.xap fájl újbóli terjesztése nélkül

        -   A Windows Phone 8.1, az iOS, az Android és a Windows rendszerű eszközök használóinak az Áruházból kell letölteniük és telepíteniük a vállalati portált

        -   A felhasználók láthatják az alkalmazás telepítését, és a megnyílásakor útmutatást kapnap a regisztrációhoz

        Hátrányok:

        -   A felhasználók láthatnak egy „**vállalati központ**” telepítésére vonatkozó jelölőnégyzetet, de semmi nem vezeti őket a Vállalati portálhoz az eszköz alkalmazáslistájában

        -   A felhasználóknak a Vállalati portál megnyitásáig nem szükséges elfogadniuk az egyéni használati feltételeket

        A következő esetekben továbbra is arra utasíthatja a felhasználókat, hogy regisztráljanak, és a regisztráció során telepítsék az ssp.xap fájlt:

        -   Ha a vállalat blokkolja az Áruházhoz való hozzáférést a Windows Phone-telefonokon, a felhasználóknak a regisztráció során kell telepítenie az ssp.xap fájlt.

        -   Ha a felhasználók nem rendelkeznek Windows Phone-telefonjaikon beállított Microsoft-fiókokkal, nem fogják tudni telepíteni a Vállalati portált az Áruházból.

        -   Ha a Windows Phone rendszeren való regisztrációra vonatkozó meglévő dokumentáció alapján először a Beállítások, Munkahelyi fiók részre lépnek, eltarthat egy darabig a dokumentumok frissítése és a felhasználók az Áruházba irányítása.

        **Mi a különbség a letöltőközpontban lévő ssp.xap fájl és az áruházbeli alkalmazás között?**

        -   Az áruházbeli Vállalati portált nem szükséges Symantec-tanúsítvánnyal aláírni a telepítéshez

        -   Az áruházbeli Vállalati portál alkalmazás megjeleníti a használati feltételeket a felhasználó számára, a letöltőközpontban található ssp.xap fájl viszont sem

        -   Az áruházbeli Vállalati portál alkalmazás .appx, nem pedig .xap kiterjesztésű

        **Le tudom tölteni a vállalati portál fájlját, hogy leküldhessem a felhasználók eszközeire ahelyett, hogy az Áruházba irányítanám a felhasználókat?**
        Igen. A Vállalati portál alkalmazás a következő operációs rendszerekre tölthető le a letöltőközpontból:

        -   Windows Phone 8-as.1-es: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **A vállalatok továbbra is használhatják a Windows Phone rendszer Windows Intune-próbaverzióval való felügyeletéhez készült támogatási eszközt, ha nem rendelkeznek Symantec-tanúsítvánnyal, és továbbra is az Áruházból telepíttetik az Vállalati portált a felhasználókkal?**
        Igen. Ha olyan technológiai próbát kell elvégeznie, melyben LOB-alkalmazásokat is telepít, a próbakezelési eszköz együttműködik a vállalati portál áruházbeli verziójával. Mivel azonban a Windows Phone 8.1 rendszerű eszközök regisztrálásához már nem szükséges a Symantec-tanúsítványból létrehozott AET, a vállalatok tesztelhetik az alkalmazások telepítését áruházbeli alkalmazásokra mutató mélyhivatkozásokkal.

        A a Windows Phone rendszer Windows Intune-próbaverzióval való felügyeletéhez készült támogatási eszköz csak az Intune próba-előfizetéseiben érhető el.

        > [!IMPORTANT]
        > A próbakezelési eszköz csak tesztelési célra használható. A próbakezelési eszköz AET-jével regisztrált eszközök regisztrációját meg kell szüntetni, majd újra regisztrálni kell azokat a Symantec-tanúsítvánnyal, amikor a próbafelügyeleti eszköz már nem érhető el, vagy ha a vállalat beszerzi saját Symantec-tanúsítványát az alkalmazások aláírásához.

        **A vállalatok megkezdhetik a kezelést Symantec-tanúsítvány nélkül, és hozzáadhatnak egyet később, akkor is, ha már vannak regisztrálva Windows Phone 8.1 rendszerű eszközök?**
        Igen. Akkor is beszerezhető egy Symantec-tanúsítvány, aláírható az ssp.xap fájl, és feltölthető a pfx-fájl, ha már vannak regisztrálva Windows Phone 8.1 rendszerű eszközök. Az Intune ekkor létrehozza az alkalmazásregisztrációs adatblokkot. A Windows Phone 8.1 rendszerű eszközök a következő szinkronizáláskor, legfeljebb nyolc óra múlva megkapják az alkalmazásregisztrációs adatblokkot. A xap- és a pfx-fájl feltöltése után legalább nyolc órát kell várni az üzletági alkalmazások telepítése előtt.


-   **Android**

    -   **Mennyi ideig tart egy Android-eszköz titkosítása?**

        Ez elsősorban az eszköz processzorának sebességétől, valamint az összes és a felhasznált memória mennyiségétől függ, és nem az Intune-tól.

-   **iOS**

    -   **Az iOS-alkalmazások Intune-nal való telepítésekor, ha az alkalmazás IPA- és jegyzékfájlja fel lett töltve, szükség van AppleID azonosító megadására ahhoz, hogy folytatódjon a telepítés?**

        Nem. Ha az IPA-fájl fel lett töltve az Intune-ba, az alkalmazások közvetlenül települnek, és nincs szükség hozzájuk Apple ID azonosítóra.

    -   **Engedélyezhető iOS rendszerben az alkalmazások telepítése anélkül, hogy engedélyezném a hozzáférést az Apple Store áruházhoz?**

        Nem, de engedélyezheti az App Store áruház használatát, majd az engedélyezett és a tiltott iOS-alkalmazásokon keresztül nyomon követheti a felhasználók tevékenységeit. A közvetlenül telepített LOB-alkalmazásokhoz nincs szükség hozzáférésre az Apple App Store áruházához.

    -   **Szükségük van a végfelhasználóknak iTunes-fiókra a vállalati portálon keresztül terjesztett Apple Store-beli alkalmazásokhoz?**

        Igen, a végfelhasználók csak iTunes-fiókkal szerezhetik be az alkalmazásokat.

    -   **Letilthatom az App Store áruházat?**

        Igen, de ezzel az App Store áruházból származó minden alkalmazástelepítést és -frissítést is letilt, nem csak azokat, amelyeket a végfelhasználó kezdeményezett. Ez azt jelenti, hogy a nyilvános App Store áruházból származó, az Intune-ból telepített alkalmazások sem fognak működni.

## Alkalmazástelepítés

-   **Hogyan vehetek fel egy ajánlott alkalmazást?**

    Az Intune-ban ezek „kiemelt alkalmazások”, és az [Alkalmazások telepítése a Microsoft Intune-ban](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md) című szakaszban szerepelnek.

-   **Kaphatok további felhőalapú tárhelyet a telepíteni kívánt alkalmazásokhoz?**

    Igen. Erről az [Alkalmazások telepítése](/Intune/Deploy-Use/deploy-apps.md) témakör *A felhőbeli tárhellyel kapcsolatos követelmények* című szakaszában olvashat.

## Biztonság

-   **Az Intune kényszerítheti a BitLockert?**

    Az OMA-DM ügynök a Windows 8.1/RT rendszerben lehetővé teszi a titkosítási állapot elolvasását (beolvasását). Ön nem állíthatja ezt be. Ez az Intune-ra és más mobileszköz-kezelő szolgáltatásokra egyaránt érvényes.

-   **Ha a BitLocker használatával titkosítok egy Windows 8-as táblagépet, kényszeríthetem az eszköz összes adatának törlését, ha egy felhasználónak egymás után több alkalommal nem sikerül bejelentkeznie?**

    Az összes adat törlésére nincs külön beállítás a Windows 8.1/RT rendszerű eszközökön egyik mobileszköz-kezelő szolgáltatás, így az Intune esetében sem. Az Intune az ilyen eszközökön a szelektív törlés lehetőségét biztosítja. Az Intune törlés/szelektív törlés funkciójával kapcsolatban lásd: [Az alkalmazások és az adatok védelme a Microsoft Intune-nal](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

## Vállalati portál

-   **Testre szabható a vállalati portál?**

    Igen. A szükséges beállítások eléréséhez az Intune felügyeleti konzoljában válassza a **Felügyelet&gt;Vállalati portál** lehetőséget.

## Microsoft Intune-nal bővített Configuration Manager

-   **Hol kezelhetem az eszközeimet az Intune-nal bővített Configuration Managerben?**

    Minden eszköz a Configuration Manager konzolján kezelhető, noha az Intune-ügynököt futtató eszközök az Intune konzolján jelennek meg. A mobileszközök nem látszanak az Intune konzolján.

-   **Végezhetek szelektív törlést az eszközökön?**

    Ha az Intune-nal bővített System Center 2012 R2 Configuration Managert vagy annak egy újabb verzióját használja, szelektív törléssel végleg eltávolíthatja eszközeiről a munkahelyi adatokat. További információ: [Az alkalmazások és az adatok védelme a Microsoft Intune-nal](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

-   **Ha a Configuration Managert és az Intune-t egyaránt használom, akkor is használhatom az Intune felügyeleti portálját?**

    Igen, de a portálról csak azok a gépek kezelhetők, amelyekre telepítve van az Intune-ügynök. A portálon szerepel továbbá néhány hasznos információ a szolgáltatásról szóló figyelmeztetésekkel, a szolgáltatás állapotával stb. kapcsolatban, de az ott szereplő eszközfelügyeleti beállítások nem vonatkoznak a beléptetett eszközökre.



<!--HONumber=Jun16_HO2-->


