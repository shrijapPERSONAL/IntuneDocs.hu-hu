---
title: "Újdonságok archívuma | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecf43b38e9593375981770583220d4ce2dfd709f
ms.openlocfilehash: 8b0f393da727b433a926e780d6de42cf7b4c6034


---
## 2015. december
### A Microsoft Munkahelyi portál szolgáltatásának módosításai és frissítései
Ebben a kiadásban a következő módosításokat vezettük be a Munkahelyi portál szolgáltatásban.

**Androidos Munkahelyi portál alkalmazás**

A Google új követelményeinek való megfelelés végett elvégeztük a következőkben ismertetett változtatásokat. Az Android 6.0-s és újabb verziójú eszközökön két új üzenet jelenik meg a felhasználók számára:
* Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)
* Allow Company Portal to access photos, media, and files on your device? (Engedélyezi a Munkahelyi portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?)

További információt e két üzenetről az alábbi táblázatban talál.



Szöveges üzenet  |Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)  
---------|---------
Üzenet jelentése     |  Engedélyezi a felhasználó eszközéhez tartozó telefonszám és IMEI-szám Intune szolgáltatásnak való elküldését, valamint a Hardver lap felügyeleti konzolján való megjelenítésüket.   </br></br>**MEGJEGYZÉS: A Vállalati portál alkalmazás soha nem indít és kezel telefonhívásokat.** Az üzenet szövegét a Google szabja meg, és nem módosítható. </br></br>A **Hardver** lap megnyitásához válassza a **Csoportok** > **Minden mobileszköz** > **Eszközök** lehetőséget. Jelölje ki a felhasználó eszközét, és válassza a **Tulajdonságok megjelenítése** > **Hardver** lehetőséget.    
Hol és mikor jelenik meg az üzenet  | Akkor jelenik meg az üzenet, amikor a felhasználók első alkalommal jelentkeznek be a Munkahelyi portál alkalmazásba, hogy regisztrálják az eszközüket.|         
Mi történik, ha a felhasználók engedélyezik a hozzáférést  |  Az eszköz telefonszáma és IMEI-száma megjelenik a Hardver lap felügyeleti konzolján. |         
Mi történik, ha a felhasználók nem engedélyezik a hozzáférést     | Tovább használhatják a Munkahelyi portál alkalmazást, regisztrálhatják az eszközeiket, de azok telefonszámai és IMEI-számai nem jelennek meg a Hardver lap felügyeleti konzolján.       </br></br> Amikor a felhasználók a hozzáférés megtagadása után másodszor bejelentkeznek a Vállalati portál alkalmazásba, az üzenetben látható egy **Ne jelenjen meg többé** feliratú jelölőnégyzet, amelynek bejelölésével végleg kikapcsolhatják az üzenet megjelenítését.</br></br>Ha a felhasználók engedélyezik a hozzáférést, de később megtagadják azt, az üzenet újból megjelenik majd, amikor a felhasználók a legközelebb bejelentkeznek a Munkahelyi portál alkalmazásba a regisztrálást követően.</br></br>Amennyiben a felhasználók később ismét engedélyezni szeretnék a hozzáférést, a **Beállítások** > **Alkalmazások** > **Vállalati portál** > **Engedélyek** > **Telefon** lapon tehetik ezt meg.
További információ     |  Felhasználóknak: [Bejelentkezés a Munkahelyi portál alkalmazásba](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Rendszergazdáknak: Az ebben a táblázatban szereplő információk megtalálhatók a [Munkahelyi portál alkalmazás üzeneteinek leírásában](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) is.   

Szöveges üzenet  |Allow Company Portal to access photos, media, and files on your device? (Engedélyezi a Munkahelyi portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?)  
---------|---------
Üzenet jelentése     |  Engedélyezi az eszköznek, hogy adatnaplókat írjon az eszköz SD-kártyájára, így USB-kábelen keresztül áthelyezhetővé válnak a naplók.   </br></br>**MEGJEGYZÉS: A Vállalati portál alkalmazás sohasem próbál hozzáférni a felhasználó fényképeihez, médiatartalmaihoz és fájljaihoz.** Az üzenet szövegét a Google szabja meg, és nem módosítható.     
Hol és mikor jelenik meg az üzenet  | Akkor jelenik meg az üzenet, amikor a felhasználók az **Adatküldés** elemre koppintva elküldik az adatnaplókat a rendszergazdának.|         
Mi történik, ha a felhasználók engedélyezik a hozzáférést  |  A naplók másolással az SD-kártyára kerülnek. |         
Mi történik, ha a felhasználók nem engedélyezik a hozzáférést     | Az adatnaplók elküldése ettől függetlenül továbbra is lehetséges, ám a naplók nem másolhatók az SD-kártyára.       </br></br> Amikor a felhasználók a hozzáférés megtagadása után másodszor bejelentkeznek a Vállalati portál alkalmazásba, az üzenetben látható egy **Ne jelenjen meg többé** feliratú jelölőnégyzet, amelynek bejelölésével végleg kikapcsolhatják az üzenet megjelenítését.</br></br>Ha a felhasználók engedélyezik a hozzáférést, de később megtagadják azt, az üzenet újból megjelenik majd, amikor a felhasználók a legközelebb megpróbálják elküldeni a naplókat.</br></br>Amennyiben a felhasználók később ismét engedélyezni szeretnék a hozzáférést, a **Beállítások** > **Alkalmazások** > **Vállalati portál** > **Engedélyek** > **Tárterület** lapon tehetik ezt meg.
További információ     |  Felhasználóknak: [Diagnosztikai adatok naplófájljainak elküldése e-mailben a rendszergazdának](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Rendszergazdáknak: Az ebben a táblázatban szereplő információk megtalálhatók a [Munkahelyi portál alkalmazás üzeneteinek leírásában](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) is.   


**iOS rendszerű Vállalati portál alkalmazás**
* A felhasználók már a Microsoft Outlookkal vagy más levelezőalkalmazásokkal is elküldhetik a rendszergazdának a diagnosztikai naplókat. Korábban ez csak a natív alkalmazással volt lehetséges.
* Javítottuk az Apple készülékregisztrációs programjához (DEP) és a vállalatok által regisztrált eszközökhöz nyújtott támogatást. A részletekért lásd: [A regisztráláskor a rendszer felkéri az eszköz azonosítására](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* A regisztrált eszközök felhasználói listájában ezentúl zöld pipa jelzi a felhasználó által éppen használt eszközt. A pipa hiányában korábban nem lehetett megállapítani, hogy a regisztrált eszközök melyikét használta éppen a felhasználó.

**Windowsos Munkahelyi portál alkalmazás**

A Microsoft termék- és szolgáltatásfejlesztési célból automatikus módszerekkel név nélküli adatokat gyűjt a munkahelyi portál teljesítményéről és használatáról. A végfelhasználók bármikor kikapcsolhatják az adatok gyűjtését eszközük használati adatokra vonatkozó beállításával, rendszergazdák azonban nem szabályozhatják az adatgyűjtést, és nem módosíthatják e beállítás végfelhasználói szakaszát.



## 2015. november
### Alkalmazáskezelés
Az Intune támogatja a mobilalkalmazás-kezelési (MAM) házirendeket, amelyek meggátolják, hogy vállalati adatok szivárogjanak ki a fogyasztói alkalmazásokba vagy szolgáltatásokba. Korábban ezek a házirendek csak olyan eszközökön futó mobilalkalmazásokon voltak kikényszerítve, amelyeket mobileszköz-kezelésre regisztráltak az Intune-ba.

Az ehavi frissítéssel az Intune új eszközosztályokra bővíti ki MAM-képességeit. Az Intune-ban regisztrált eszközök mellett most a következőkön kényszeríthet ki MAM-házirendeket:
* más eszközkezelési megoldások által kezelt eszközök
* eszközkezelési rendszerekben nem regisztrált eszközök, általában saját eszközök

A következő blogbejegyzésekben talál további információt ezen új MAM-képességekről:
* [A felügyelt mobiltermelékenység növelése](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [A Microsoft új nagyvállalati mobilitási képességei](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Ezenkívül itt találhat néhány részletet és további információkat az Intune MAM-szolgáltatásairól:
* A vállalati adatok el vannak különítve az ügyféladatoktól az Intune-hoz felkészített alkalmazásokban, beleértve az Office Mobile alkalmazásokat, az Intune SDK-t alkalmazó külső alkalmazásokat és az Intune által becsomagolt üzletági alkalmazásokat.
* A vállalati adatok megoszthatók (**kivághatók/másolhatók/beilleszthetők**) a vállalati alkalmazások között, mialatt meggátolható a vállalati adatok személyes alkalmazásokba való megosztása. A részletekért lásd: [A MAM-szabályzatok és az alkalmazásadatok védelme](https://technet.microsoft.com/library/mt627825.aspx). Ebben [A Microsoft Word alkalmazás használata munkahelyi és személyes teendők elvégzésére](https://technet.microsoft.com/library/mt627827.aspx) című példa forgatókönyvben láthatja, hogyan gátolja meg a rendszer a vállalati adatok személyes alkalmazásokba való megosztását.
* Kulcsfontosságú adatvesztés-megelőzési házirendek, például alkalmazásonkénti PIN-kód, mentés másként vezérlők és felügyelt adatmegosztás az alkalmazások között. Az összes házirend listájáért lásd: [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](https://technet.microsoft.com/library/mt627829.aspx).
* A Word, az Excel, a PowerPoint, az Outlook, a OneNote és a OneDrive Vállalati verzió is rendelkezik ezekkel az új képességekkel és eszközregisztrációval vagy anélkül is felügyelhető. Az adatvesztés-megelőzési képességek natív módon vannak beépítve a szabványos Office-alkalmazásokba az Apple Store vagy a Google Play áruházban, és nem igényelnek alkalmazásburkolást vagy közvetlen telepítést.
* Az első lépésekért lásd: [Ismerkedés a mobilalkalmazás-felügyeleti szabályzatokkal az Azure-portálon](https://technet.microsoft.com/library/mt627830.aspx). A mobilalkalmazás-felügyeleti házirendek konfigurálásával és telepítésével kapcsolatban lásd: [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](https://technet.microsoft.com/library/mt627829.aspx).
* Amikor a végfelhasználók a vállalati hitelesítő adataikkal hitelesítést végeznek az alkalmazásban, az adatvesztés-megelőzési képességek automatikusan be vannak állítva. A [Microsoft Intune-alapú mobilalkalmazás-kezelési házirendek hatálya alá tartozó alkalmazásokkal kapcsolatos végfelhasználói folyamatok](https://technet.microsoft.com/library/mt627827.aspx) című témakörben talál néhány példa forgatókönyvet a OneDrive iOS- és Androidos-eszközökön való elérésére.
* iOS- és Android-eszközökön is működik.

[A Microsoft Intune mobilalkalmazás-kezelési házirendekkel használható Microsoft-alkalmazások](https://technet.microsoft.com/library/dn708489.aspx) listája frissült, és megjeleníti a legújabb alkalmazásokat.

### Eszközkezelés
 **Mac OS X eszközkezelés** Az Intune-nal Mac OS X-eszközöket regisztrálhat és kezelhet. A következőket teheti a Mac OS X-eszközökkel:
* Az eszközök regisztrálása az Intune általi kezeléshez. Lásd: [Az iOS kezelésének beállítása a Microsoft Intune-nal](https://technet.microsoft.com/library/dn408185.aspx).
* Eszközbeállítások vezérlése általános konfigurációs házirenddel. Lásd: [A Mac OS X-konfigurációs házirendek beállításai a Microsoft Intune-ban](https://technet.microsoft.com/library/mt627823.aspx).
* Az Apple Configuratorral létrehozott Mac OS X-beállítások alkalmazása. Lásd: [Egyéni Mac OS X-házirendbeállítások a Microsoft Intune-ban](https://technet.microsoft.com/library/mt627820.aspx)-
* Hardver- és szoftverleltár készítése Mac OS X-eszközökről. Lásd: [A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával](https://technet.microsoft.com/library/jj733634.aspx).
* Új jelentések futtatása, amelyek részleteket jelenítenek meg a kezelt Mac OS X-eszközökről. Lásd: [A Microsoft Intune-műveletek értelmezése jelentések segítségével](https://technet.microsoft.com/library/dn646977.aspx).

**ÚJ Edge böngészőbeállítások Windows 10-eszközökre** Új beállítások érhetőek el a Windows 10 általános konfigurációs házirendjéhez, amelyekkel kezelheti a Microsoft Edge böngésző beállításait és szolgáltatásait. Lásd: [A Windows 10 konfigurációs házirendjének beállításai a Microsoft Intune-ban](https://technet.microsoft.com/library/mt404697.aspx).

**E-mail-profilok** Új e-mail-profilokra vonatkozó házirend érhető el a Windows 10-es asztali és Windows 10-es mobileszközökön. Lásd: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](https://technet.microsoft.com/library/dn646984.aspx).

**Új megfelelőségiszabályzat-beállítások** Az alábbi új biztonsági és rendszerházirend-beállítások lettek hozzáadva a megfelelőségi szabályzatok listájához:
* Ahhoz, hogy a vállalati erőforrásokat elérő Windows 8.1-es vagy újabb verziójú eszközökön telepítve legyenek a legújabb frissítések, használja az **Automatikus frissítések megkövetelése** beállítást. Az automatikusan telepíteni kívánt frissítések típusát is meghatározhatja – vagy az összes fontosként megjelölt telepítendő frissítést, vagy az összes fontosként vagy ajánlottként megjelölt telepítést. A megfelelőségiházirend-beállítások teljes listájáért lásd: [A Microsoft Intune eszközmegfelelőségi házirendjeinek kezelése](https://technet.microsoft.com/library/dn705843.aspx).
* Az új **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból** beállítást a meglévő **Jelszó kérése ennyi perc inaktivitás után** beállítással kombinálva olyan megfelelőségi beállítást hozhat létre, amelyhez a végfelhasználónak jelszót kell beírnia a bizonyos ideig inaktív eszközök használatához.

**Új feltételes hozzáférésiszabályzat-beállítások** **Minden felhasználóra** feltételes hozzáférési szabályzatot alkalmazhat az új vagy meglévő feltételes hozzáférési szabályzatokban. Az Intune és Office 365 programokhoz licenccel rendelkező összes felhasználónak regisztrálnia kell az eszközét, és ha az Intune nem támogatja az eszköz platformját, a hozzáférés le lesz tiltva az [Active Directory-hitelesítésalapú bejelentkezést (modern hitelesítést)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) használó ügyfélalkalmazások esetében.

Azt is megadhatja, hogy a feltételes hozzáférési házirend **minden platformra** érvényes legyen.  Az [Active Directory-hitelesítésalapú bejelentkezést (modern hitelesítést)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) használó összes ügyfélalkalmazásra érvényes a feltételes hozzáférési házirend, és ha a platformot nem támogatja az Intune, akkor le lesz tiltva.

### A Microsoft Munkahelyi portál szolgáltatásának módosításai és frissítései
Ebben a kiadásban a következő módosítások lettek bevezetve a vállalati portál alkalmazásaival kapcsolatban:

* **Android**: Egy új üdvözlőképernyő érhető el az androidos Munkahelyi portál alkalmazásban, amellyel a felhasználók jobban megérthetik a Munkahelyi portál alkalmazás célját. Ez a képernyő csökkenti az azon felhasználók általi letöltések számát, akiknek a vállalata nem Intune-előfizető.

* **iOS**: Az Intune már a Mac OS X rendszerű eszközök regisztrálását is támogatja a [Vállalati portál webhely](https://portal.manage.microsoft.com) használatával. Ehhez a [Mac OS X-eszköz regisztrálása az Intune-ban](https://technet.microsoft.com/library/mt598622.aspx) című rész ad útmutatást.

* **Vállalati portál webhely**: Azok a felhasználók, akik regisztrálták az eszközeiket az Intune-ban, most már közvetlenül a Munkahelyi portál webhelyen tudnak új PIN-kódot készíteni maguknak az **Új PIN-kód** lehetőséget választva. Korábban ez csak a rendszergazdán keresztül volt lehetséges. Windows 8.1-es és Windows RT rendszerű eszközökön nem működik az Új PIN-kód lehetőség. Más rendszerű eszközökön pedig csak akkor jelenik meg, ha az adott eszköz regisztrálva van a mobileszköz-kezelési szolgáltatásban vagy az Exchange ActiveSync mobileszköz-kezelési moduljában. Az [Új PIN-kód készítése](https://technet.microsoft.com/library/mt590895.aspx) című részben útmutatást talál mindehhez.

### Változások a globális rendszergazdai licencelésben
Októberben megosztottuk, hogy a globális rendszergazdák (másnéven a bérlő rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a globális rendszergazdák a szolgáltatást szeretnék használni, például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük, mint minden más felhasználónak. Az alábbiakban további részleteket olvashat erről.
* A munkahelyi Intune portálon a végfelhasználók a következőket tehetik:
    * az eszköz regisztrálása;
    * Az eszközök állapotának megtekintése
    * olyan szoftver letöltése, amelyet globális rendszergazda telepített a szervezetbe;
    * a globális rendszergazda által közzétett hivatkozások megkeresése arról, hogyan léphetnek kapcsolatba az informatikai részleggel.

    [További információk a munkahelyi portálról](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) és [a munkahelyi portál testreszabásának módjáról](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Az Intune vagy az EMS megvásárlásához a szervezet nevében feliratkozó személy automatikusan az első globális rendszergazdává válik a bérlőben. Az ősszel az Intune elkezdett automatikusan hozzárendelni Intune- vagy EMS-licencet az első globális rendszergazdához az [Office 365 portálra](http://portal.office.com/) való átállás és az [Intune fiókportál](http://account.manage.microsoft.com/) megszűnésének részeként. Az összes további hozzáadott globális rendszergazda folytathatja a mindennapos adminisztrációt különálló Intune- vagy EMS-licenc nélkül. Ha végfelhasználói műveleteket végeznek, és regisztrálják a saját (vagy vállalati) eszközüket, vagy szoftvert töltenek le a vállalati portálról, akkor licencre van szükségük, mint bármely más felhasználónak.
* A változást fokozatosan vezetjük be 2016 januárjától.
* A Microsoft partnereit ez a változás nem befolyásolja abban, hogy az ügyfeleik nevében biztosítsák a szolgáltatást. A végfelhasználói feladatokhoz a felhasználóknak Intune- vagy EMS-licencre van szükségük az eszköz regisztrálásához és a szoftver a munkahelyi portálról való eléréséhez és letöltéséhez.

Ha kérdései vannak ezzel a változtatással kapcsolatban, vegye fel a kapcsolatot az Intune támogatási csapatával:
* [A Microsoft Intune támogatási csatornái](https://technet.microsoft.com/library/jj839713.aspx)
* [Közösségi támogatás](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Általános Microsoft Intune-visszajelzés, beleértve a tervátalakítási kérések (DCR-ek) elküldése vagy hibák jelentése érdekében látogasson el az [Intune felhasználói visszajelzési webhelyére](https://microsoftintune.uservoice.com/).


### Újdonságok az Intune-ban – 2015. november
**Új tartalom**
* [A Mac OS X-konfigurációs házirendek beállításai a Microsoft Intune-ban](https://technet.microsoft.com/library/mt627823.aspx): A Mac OS X-eszközök eszközbeállításainak és szolgáltatásainak vezérlése.
* [Egyéni Mac OS X-házirendbeállítások a Microsoft Intune-ban](https://technet.microsoft.com/library/mt627820.aspx): Az Apple Configurator eszközzel létrehozott Mac OS X-eszközbeállítások telepítése.
* [Adatveszteség-megelőzési alkalmazásszabályzatok konfigurálása Microsoft Intune-ban](https://technet.microsoft.com/library/mt627825.aspx): Azon forgatókönyvekről tartalmaz információt, amelyeket a mobilalkalmazás-kezelési házirendek támogatnak, valamint arról, hogyan védi a házirend az adatokat.
* [Ismerkedés a mobilalkalmazás-felügyeleti szabályzatokkal az Azure-portálon](https://technet.microsoft.com/library/mt627830.aspx): A mobilalkalmazás-kezelési házirendek használatának az Azure Betekintő portálon való elkezdéséhez szükséges információk.
* [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](https://technet.microsoft.com/library/mt627829.aspx): Részletes útmutató arról, hogyan hozhat létre mobilalkalmazás-kezelési házirendeket az Azure Betekintő portálon.
* [Mobilalkalmazás-felügyeleti szabályzatok figyelése a Microsoft Intune-nal](https://technet.microsoft.com/library/mt627824.aspx): Információ arról, hogyan figyelheti meg a mobilalkalmazás-kezelési házirendeket az Azure Betekintő portálon.
* [A Microsoft Intune mobilalkalmazás-kezelési házirendjei és az iOS megnyitási engedélyei](https://technet.microsoft.com/library/mt627821.aspx): Információ arról, hogyan működnek a mobilalkalmazás-kezelési házirendek az iOS megnyitás a következőben szolgáltatásával.
* [Microsoft Intune-alapú mobilalkalmazás-kezelési szabályzatok hatálya alá tartozó alkalmazásokkal kapcsolatos végfelhasználói folyamatok](https://technet.microsoft.com/library/mt627827.aspx): Milyen a végfelhasználói élmény mobilalkalmazás-kezelési házirenddel társított alkalmazások használatakor.
* [A Microsoft Intune-nal felügyelt vállalati alkalmazások adatainak törlése](https://technet.microsoft.com/library/mt627826.aspx): A vállalati alkalmazásadatok eltávolításának módja.

**Frissített tartalom**
* [A Windows 10 konfigurációs házirendjének beállításai a Microsoft Intune-ban](https://technet.microsoft.com/library/mt404697.aspx): Új Edge-böngészőbeállítások.
* [Az iOS kezelésének beállítása a Microsoft Intune-nal](http://technet.microsoft.com/library/dn408185.aspx): További információk a Mac OS X-eszközök regisztrálásáról.
* [A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával](https://technet.microsoft.com/library/jj733634.aspx): További információk a Mac OS X-eszközökről gyűjtött leltárról. Ezenkívül az összes eszközplatformra vonatkozó legújabb információkkal frissült a témakör.
* [A Microsoft Intune-műveletek értelmezése jelentések segítségével](https://technet.microsoft.com/library/dn646977.aspx): További információk a felügyelt Mac OS X-eszközökkel kapcsolatos információk megjelenítésére használt két új jelentésről.
* [A Microsoft Intune eszközmegfelelőségi házirendjeinek kezelése](https://technet.microsoft.com/library/dn705843.aspx): További információk az automatikus frissítések és jelszó megkövetelésének új megfelelőségi házirendjeiről, amikor egy eszköz inaktív állapotból tér vissza.
* [E-mail hozzáférés kezelése a Microsoft Intune-nal](https://technet.microsoft.com/library/dn705841.aspx): További információ arról, hogy a feltételes hozzáférési házirend hogyan alkalmazható az összes platformra és az összes felhasználóra.
* [A SharePoint Online-hozzáférés kezelése a Microsoft Intune-nal](https://technet.microsoft.com/library/dn705844.aspx): További információ arról, hogy a feltételes hozzáférési házirend hogyan alkalmazható az összes platformra és az összes felhasználóra.

## 2015. október

### Feltételes hozzáférés frissítései helyszíni Exchange esetén
**Most engedélyezheti az Exchange ActiveSync e-mailek elérését az Intune-nal regisztrált, az előírásoknak megfelelő eszközök számára, amikor a globális Exchange-szabály Letiltás vagy Karantén értékű** Eddig a regisztrált vagy az előírásoknak megfelelő eszközökön az e-mail-elérés engedélyezéséhez **Engedélyezés** értékűre kellett állítani az alapértelmezett globális Exchange-szabályt.

Ezzel a szolgáltatásfrissítéssel többé nincs szükség erre a beállításra a feltételes eléréshez. Ha az Exchange-környezet megköveteli, hogy az alapértelmezett globális szabály értéke **Letiltás/Karantén** legyen, jelölje be az Exchange helyszíni feltételes hozzáférési szabályzat lapján az **Alapértelmezett szabály felülbírálása** jelölőnégyzetet. Az [E-mail hozzáférés kezelése a Microsoft Intune-nal](https://technet.microsoft.com/library/dn705841.aspx) témakör további részleteket tartalmaz a szabályokról és az eredményül kapott végfelhasználói értesítésekről.

**Karantén mostantól egy kattintással** Egyszerűsítettük az e-mailek karanténba helyezését az egykattintásos regisztrálás engedélyezése érdekében. Ezzel a szolgáltatásfrissítéssel a végfelhasználók a karanténba helyezett e-mailben egyetlen hivatkozásra kattintva végezhetik el a regisztrációs folyamatot a munkahelyiportál-alkalmazásban.
### Mobileszköz- és alkalmazásfelügyeleti frissítések
**Android** Az Intune összes felügyeleti funkciója mostantól támogatja az Android 6.0 (Marshmallow) rendszert, a következő blogbejegyzésben leírtaknak megfelelően: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)(A Microsoft Intune azonnali támogatást nyújt az Android Marshmallow rendszerhez).

**iOS** Az iOS 7.1-es verziójánál régebbi rendszerű iOS-eszközökhöz már nem készíthetők új alkalmazástelepítések. Az ilyen eszközökhöz készült meglévő alkalmazáspéldányok azonban továbbra is működni fognak az Intune-ban, és a kezelésük is ott történik.

**Windows 10** Az Intune mostantól támogatja az univerzális Windows 10-alkalmazások telepítését a **Windows-alkalmazáscsomag** szoftvertelepítő-típus használatával. A követelményekkel kapcsolatban további információkat [Az alkalmazások telepítésének első lépései a Microsoft Intune-ban](http://technet.microsoft.com/en-US/library/dn646955.aspx) című témakörben talál.


### A Microsoft vállalati portál alkalmazásainak módosításai és frissítései
A következő módosításokat végeztük el a vállalati portál alkalmazások ezen kiadásain: **iOS** Új gombokkal bővült a Vállalati portál alkalmazás, így a felhasználók egyszerűbben tudják elküldeni a diagnosztikai naplókat a rendszergazdáknak:

|Gomb neve|Megjelenési helye|
|------------|---------------|
|Jelentés|Riasztási hibaüzenetek|
|Diagnosztikai jelentés küldése|A Munkahelyi portál alkalmazás Névjegy képernyője|



## 2015. szeptember
### Mobileszköz- és alkalmazásfelügyeleti frissítések
**Az Intune összes iOS-kezelési funkciója mostantól támogatja az iOS 9-et**Az iOS 9 kezelési lehetőségeiről [ebben a blogbejegyzésben](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx) olvashat.

**Új mobilalkalmazás-konfigurációs házirend iOS-hez** Az új mobilalkalmazás-konfigurációs házirenddel automatikusan megadhatók azok a beállítások, amelyekre egy iOS-alkalmazásnak szüksége lehet a futtatásakor. Megadhat például egy hálózati portot vagy egy felhasználónevet. Részletekért lásd: [Alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](https://technet.microsoft.com/library/mt481447.aspx).

**Egyszerűbb alkalmazáskezelés iOS 9-felhasználóknak**
 Ebben a kiadásban a már telepített alkalmazásokat iOS 9-felhasználók esetén az Intune felügyelete alá helyezheti. Ha az iOS korábbi verziói esetén telepít egy alkalmazást, és az alkalmazás nem felügyelt verziója már telepítve van az eszközön, továbbra is meg kell kérnie a felhasználót, hogy kézzel távolítsa el az alkalmazást, mielőtt az Intune telepítené a felügyelt alkalmazást.

 Az Intune jelen kiadásával kezdődően azonban arra kérheti az iOS 9-eszközök felhasználóit, hogy engedélyezzék az Intune számára az alkalmazás felügyeletének átvételét és a megfelelő mobilalkalmazás-felügyeleti szabályzatok alkalmazását.

 **A Windows 10 felügyelete** Az új [általános Windows 10-es konfigurációs házirend](https://technet.microsoft.com/library/mt404697.aspx) használatával konfigurálhatja a Windows 10 vagy Windows 10 Mobile rendszert futtató, regisztrált eszközök jelszó-, eszköz-, böngésző- és más beállításait.

 **Alkalmazások létrehozása és telepítése regisztrált Windows 10-eszközökre** A Windows Installer mobileszköz-felügyelettel (*.msi) új szoftvertelepítő-típussal Windows Installer-alkalmazásokat hozhat létre és telepíthet a Windows 10-et futtató regisztrált eszközökre. A részletekért lásd: [Az alkalmazások telepítésének első lépései a Microsoft Intune-ban](https://technet.microsoft.com/library/dn646955.aspx).

### A Microsoft vállalati portál alkalmazásainak módosításai és frissítései
Ebben a kiadásban a következő módosítások lettek bevezetve a vállalati portál alkalmazásaival kapcsolatban:

**iOS**
* A Microsoft termék- és szolgáltatásfejlesztési célból automatikus módszerekkel név nélküli adatokat gyűjt a vállalati portál teljesítményéről és használatáról. A végfelhasználók bármikor kikapcsolhatják az adatok gyűjtését eszközük használati adatokra vonatkozó beállításával, rendszergazdák azonban nem szabályozhatják az adatgyűjtést, és nem módosíthatják e beállítás végfelhasználói szakaszát.
* A teljes képernyős felbontás támogatása az iPhone 6 és 6 Plus eszközön
* Correction de bogues pour améliorer la sécurité

### Újdonságok az Intune-ban – 2015. szeptember
**Új témakörök**

|Név|Részletek|
|----|--------|
|[A Windows 10 konfigurációs házirendjének beállításai a Microsoft Intune-ban](https://technet.microsoft.com/library/mt404697.aspx)|Ez egy olyan új konfigurációs házirend, amellyel kezelheti a beállításokat és a funkciókat a Windows 10-et és Windows 10 Mobile-t futtató eszközökön.
| [Alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](https://technet.microsoft.com/library/mt481447.aspx)|Ez egy olyan új házirendtípus, amellyel automatikusan megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy iOS-alkalmazást futtat. |

**Frissített témakörök**

|Név|Részletek|
|----|-------|
|[Házirendek használata a számítógépek és mobileszközök kezeléséhez a Microsoft Intune-nal](https://technet.microsoft.com/library/dn743712.aspx)|A frissítés eredményeképpen tartalmazza a legújabb információkat, amelyek segítenek a házirendek megértésében és létrehozásában.|

## 2015. augusztus
### Mobileszköz- és alkalmazásfelügyeleti frissítések
* Az Intune-regisztráció és a vállalati hozzáférés**használati feltételei** [már házirendek használatával kezelhetők](https://technet.microsoft.com/library/mt405893.aspx). Az egyes felhasználói csoportok eltérő igényeinek kielégítéséhez különböző feltételkészleteket hozhat létre. A földrajzi elhelyezkedés alapján definiált felhasználói csoportok számára például különböző nyelveken teheti elérhetővé a használati feltételeket. A [használati feltételeket módosíthatja](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) is, és megadhatja, hogy a hogy a verziószámok növekedjenek-e, valamint megkövetelheti a felhasználóktól az új feltételek elfogadását, mielőtt megkezdenék a vállalati portál használatát.
* **Számos Intune-házirendet átneveztünk** a termékben való egységes megjelenés és a könnyebb keresés érdekében. Az összes elérhető Intune-házirend listájáért lásd: [Házirendek használata a számítógépek és mobileszközök kezeléséhez a Microsoft Intune-nal](https://technet.microsoft.com/library/dn743712.aspx).
* **PKCS #12 (. PFX) tanúsítványprofilok** érhetők el az Android 4.0 vagy újabb, illetve a Windows 10 vagy újabb (asztali és mobil-) rendszerhez. A .PFX használatához nincs szükség NDES-kiszolgálóra. A .PFX tanúsítványprofilok létrehozásával kapcsolatban lásd: [Vállalati erőforrások elérésének lehetővé tétele a Microsoft Intune tanúsítványprofiljaival](http://technet.microsoft.com/library/dn818904.aspx)
* **A Windows 10 asztali és mobil verziójának vállalati határbeállításai** lehetővé teszik a részletes VPN-beállítások használatát a következő témakörben leírtak szerint: [Segítség a felhasználóknak a munkájukhoz való csatlakozásban VPN-profilok használatával a Microsoft Intune-nal](https://technet.microsoft.com/library/dn818905.aspx)
* **Az androidos OneDrive alkalmazás már támogatja a többszörös identitás használatát**. Erről és a mobilalkalmazás-felügyeleti házirendekkel kapcsolatos egyéb frissítésekről a [felügyelhető Microsoft-alkalmazások listájában tájékozódhat](https://technet.microsoft.com/library/dn708489.aspx).
* **iOS-alapú aktiválási zár megkerülése**. Ha a céges iOS-eszközök aktiválási zárral vannak védve, egy adott eszköz törléséhez vagy újraaktiválásához először meg kell adni a felhasználó Apple ID azonosítóját és jelszavát. Ez kihívást jelenthet, ha a felhasználók elhagyják a vállalatot és az aktiválási zár kikapcsolása nélkül szolgáltatják vissza a céges eszközöket. A probléma megoldásához használhatja az [aktiválási zár megkerülését az Intune-ban](https://technet.microsoft.com/library/mt414176.aspx).

### Feltételes hozzáférés a PC-ken
Már PC-ken is konfigurálhat feltételes hozzáférési szabályzatokat. Ez lehetővé teszi az Office asztali alkalmazásai számára az Exchange Online és a SharePoint online szolgáltatás elérését.
Csak olyan PC-n engedélyezhetők a feltételes hozzáférési szabályzatok, amely tartományhoz van csatlakoztatva, vagy alkalmas a csatlakoztatásra.
* [Az e-mailek és a SharePoint hozzáférésének kezelése a Microsoft Intune használatával](http://technet.microsoft.com/library/dn818907).aspx) témakör **Első lépések** szakaszában megtalálható minden, a számítógépek feltételes hozzáférésének engedélyezésére vonatkozó követelmény.
* Az e-mail-hozzáférés esetén a feltételes hozzáférést engedélyező beállításokkal kapcsolatban lásd: [E-mail-hozzáférés kezelése a Microsoft Intune-nal](https://technet.microsoft.com/library/dn705841.aspx).
* A SharePoint Online feltételes hozzáférését engedélyező beállításokkal kapcsolatban lásd: [A SharePoint Online-hozzáférés kezelése a Microsoft Intune-nal](https://technet.microsoft.com/library/dn705844.aspx).

### A Microsoft vállalati portál alkalmazásainak módosításai és frissítései
Ebben a kiadásban a következő módosítások lettek bevezetve a vállalati portál alkalmazásaival kapcsolatban:

**Android**

Azon felhasználók számára, akik még nem regisztrálták eszközüket, a bejelentkezés után megjelennek az eszközregisztrációs utasítások.

### Újdonságok az Intune dokumentációjában -- 2015. augusztus
**Új témakörök**

|Cím|Részletek|
|-----|-------|
|[Az iOS-eszközök védelme a Microsoft Intune-hoz készült aktiválásizár-megkerüléssel](https://technet.microsoft.com/library/mt414176.aspx)|Annak ismertetése, hogy az Intune használatával miként kerülhető meg az iOS-alapú aktiválás zárolás, ha egy felhasználó kilép a cégtől, és egy zárolt eszközt ad vissza.|

**Frissített témakörök**

|Cím|Részletek|
|-----|-------|
|[A Microsoft Intune mobilalkalmazás-kezelési házirendekkel használható Microsoft-alkalmazások](https://technet.microsoft.com/library/dn708489.aspx)|Frissített információk a mobilalkalmazás-felügyeleti házirendekkel kezelhető alkalmazásokról.
|[Házirendek használata a számítógépek és mobileszközök kezeléséhez a Microsoft Intune-nal](http://technet.microsoft.com/library/dn743712.aspx)|Frissítve az Intune-hoz hozzáadott legújabb házirendekkel.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Sep16_HO5-->


