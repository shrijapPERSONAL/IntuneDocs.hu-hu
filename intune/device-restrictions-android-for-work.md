---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Android for Work rendszer esetén | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: A cikk az Intune eszközbeállítások és -funkciók Android for Work rendszerű eszközökön történő korlátozására szolgáló beállításait ismerteti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 857522ef4931407accf98b2a2ad97334278c138f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Az Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Munkahelyi profil beállításai
-     **Munkahelyi és személyes profilok közötti adatmegosztás** – ezzel a beállítással szabályozhatja, hogy a munkahelyi profilban szereplő alkalmazások megoszthatnak-e adatokat a személyes profilban szereplőkkel. A következő lehetőségek közül választhat:
    - **Alapértelmezett megosztási korlátozások** – ez az eszköz alapértelmezett megosztási működésmódja, amely a futtatott Android-verziótól függően eltérő. Alapértelmezés szerint a személyes profilból lehet a munkahelyi profilba megosztani, a munkahelyiből a személyesbe viszont nem. Ennek célja a munkahelyi profilból a személyesbe irányuló adatszivárgás megelőzése. A Google a 6.0-snál korábbi verziójú eszközökön nem nyújt lehetőséget a személyesből a munkahelyi profilba irányuló adatforgalom blokkolására.  
    - **A munkahelyi profilban lévő alkalmazások kezelhetik a személyes profilból érkező megosztási kérelmeket** – ezzel a lehetőséggel engedélyezheti a személyesből a munkahelyi profilba irányuló adatmegosztásra szolgáló beépített Android-funkciót. Ilyenkor a személyes profilban szereplő alkalmazásokban kezdeményezett megosztási kérés irányulhat a munkahelyi profilban szereplő alkalmazásokba. A 6.0-snál korábbi verziójú androidos eszközökön ez az alapértelmezett működés.
    - **A személyes profilban lévő alkalmazások kezelhetik a munkahelyi profilból érkező megosztási kérelmeket** – ezzel a lehetőséggel engedélyezheti a profilok közötti kétirányú adatmegosztást. Ilyenkor a munkahelyi profilban szereplő alkalmazások megoszthatnak adatokat a személyes profilban szereplő nem felügyelt alkalmazásokkal.  A beállítást csak körültekintően szabad használni, mert lehetővé teszi a munkahelyi profil adatainak átvitelét az eszköz nem felügyelt részére.


-     **Munkahelyi profil értesítései az eszköz zárolt állapotában** – ez a beállítás szabja meg, hogy a munkahelyi profilban szereplő alkalmazások megjeleníthetnek-e értesítéseket a képernyőn, ha az eszköz zárolva van.
-     **Alapértelmezett alkalmazásengedélyek** – itt adhatja meg a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett engedélyszabályzatot. Az Android 6-tal kezdődően egyes alkalmazásengedélyek elfogadását futtatáskor kéri a rendszer a felhasználótól. Ezzel a szabályzatbeállítással döntheti el, hogy a felhasználók adhassák-e meg a munkahelyi profilban szereplő alkalmazások engedélyeit, és ha igen, ezt milyen módon kérje tőlük a rendszer.
Leküldhet például egy olyan alkalmazást a munkahelyi profilba, amely helyadatokhoz kér hozzáférést. Az ilyen alkalmazás szokásosan egy párbeszédpanelen kéri a felhasználótól a helyadatokhoz való hozzáférési engedélyt, a felhasználó pedig engedélyezheti vagy letilthatja a hozzáférést. Ezzel a szabályzattal kérdés nélkül automatikusan engedélyezhet vagy letilthat minden hozzáférést, vagy átadhatja az eseti döntés jogát a felhasználónak. A következő lehetőségek közül választhat:
    -     **Eszköz alapértelmezése**
    -     **Rákérdezés**
    -     **Automatikus engedélyezés**
    -     **Automatikus elutasítás**

## <a name="password"></a>Jelszó

- **Jelszó minimális hossza** – itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**14**).
- **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – itt adhatja meg, hogy mennyi idő után zárolódjanak a tétlen eszközök.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről az adatokat.
- **Jelszó érvényessége (nap)** – itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**).
- **Kötelező jelszótípus** – itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
    - **Eszköz alapértelmezése**
    - **Alacsony biztonságú biometrikus**
    - **Kötelező**
    - **Legalább számok**
    - **Komplex numerikus** – (nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111”-et vagy az „1234”-et)
    - **Legalább betűk**
    - **Legalább alfanumerikus karakterek**
    - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása** – itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő zárolásfeloldás** – letilthatja, hogy a végfelhasználók az eszközt annak ujjlenyomat-olvasójával oldják fel.
- **Smart Lock és egyéb megbízhatósági ügynökök** – kompatibilis eszközökön ezzel vezérelheti az intelligens zárolási funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos képesség lehetővé teszi az eszköz zárolásiképernyő-jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van – például egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással akadályozhatja meg, hogy a felhasználók konfigurálják az intelligens zárolást.

## <a name="custom-policy-settings"></a>Egyéni szabályzatbeállítások
A Microsoft Intune **Android for Work egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel felügyelheti az Android for Work-eszközökön elérhető szolgáltatásokat. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat is érvénybe léptethet, amelyek nem konfigurálhatók Intune-szabályzatokkal.
Az Intune jelenleg csak korlátozott számú egyéni Android-szabályzatot támogat. E témakör példái alapján megtudhatja, mely szabályzatokat lehet konfigurálni.

### <a name="general-settings"></a>Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név** |Adjon egyedi nevet az egyéni Android-szabályzatnak, hogy az azonosítható legyen az Intune konzolján.|
    |**Leírás** |Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|

### <a name="oma-uri-settings"></a>OMA-URI-beállítások

  |Beállítás neve|Részletek|
  |--------|--------------------|
  |**Név** |Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
  |**Leírás** |Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)** |Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
  |**Adattípus** |Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc, Karakterlánc (XML), Dátum és idő, Egész szám, Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.|
  |**Érték** |Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

