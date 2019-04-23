---
title: A Microsoft Intune-alkalmazást a céges eszközök regisztrálása |} A Microsoft Docs
description: Az Intune-ban egy vállalati Android-eszköz regisztrálását mutatja
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cf384bfcc0782226e363a6527ea47c4140f7faa
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901781"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>A vállalati eszköz, a Microsoft Intune alkalmazás regisztrálása

Vállalati tulajdonú Android-eszköz regisztrálása biztonságos hozzáférhet a vállalati e-maileket, alkalmazásokat és egyéb adatok, amelyeket a szervezet tesz elérhetővé. A Microsoft Intune-alkalmazás támogatja az Android 6.0-s vagy újabb rendszerű, vállalati tulajdonú eszközök. Ez lesz automatikusan új és a gyári-beállítások visszaállítása eszközökön regisztráció során települjön. 

Négy módon regisztrálásához. A szervezet kell lehetővé teszik, hogy melyik mód használatára.
 
* Kis hatótávolságú kommunikáció (NFC)  
* Jogkivonat  
* QR-kódot   
* Google Zero Touch  

Regisztráció előtt győződjön meg arról, tisztában lehetőséget akkor kell használni, hogy a megfelelő lépéseket követnie.  

## <a name="enroll-device"></a>Eszköz regisztrálása 
Hajtsa végre ezeket a lépéseket, és regisztrálja az eszközt.  

> [!NOTE]
> Az Androidos verziója vagy az eszköz gyártója, hogy további lépéseket, amelyek nem terjed ki az eljárás befejezéséhez szükség lehet. Színek és képernyőképeken látható szöveg is eltérhet az eszközön.  

1. Kapcsolja be az új vagy a gyári – új eszközt.  
2. Az **Üdvözlőképernyőn** válasszon nyelvet.   Ha Ön már utasítást kapott regisztrálása a egy QR-kódot vagy egy bizonyos NFC hajtsa végre az alábbi, amely megfelel a metódus.  
     * NFC: Koppintson az NFC-támogatott eszköz elleni egy programozói eszközt a munkahelyi hálózathoz való csatlakozáshoz. Kövesse a képernyőn megjelenő utasításokat. Ha egyenlege eléri a képernyő a Chrome használati feltételeit, folytassa az 5. lépés.  

      * QR-kódot: Hajtsa végre a [QR-kód regisztrációs](#qr-code-enrollment).  

      Ha, hogy kapott utasítást, használjon másik módszert, folytassa a 3. lépés.    

1. Csatlakozás Wi-Fi, koppintson a **tovább**. Végezze el a lépést, amely megfelel a regisztrációs módszer. 

    * Token: Ha a Google bejelentkezési képernyőt kap, hajtsa végre a [regisztrációs jogkivonat](#token-enrollment).    
    * Google Zero Touch: Miután csatlakozott a Wi-Fi, akkor az eszköz a szervezet által ismerhető fel. Folytassa a 4. lépés, és kövesse a képernyőn megjelenő utasításokat, mindaddig, amíg a telepítés befejeződött.    
 
       ![Példa a képe Google feltételek képernyőt fog látni, ha a Google Zero Touch, kiemelés elfogadás és Folytatás gomb használ.](./media/google-zero-touch-intune-app-01.png)   
   
4. Tekintse át a Google feltételeket. Koppintson a **ELFOGADÁS és FOLYTATÁS**.  

      ![Példa a képe feltételek Google képernyőt, kiemelés elfogadás és Folytatás gombra.](./media/fully-managed-intune-app-04.png)   

6. Tekintse át a Chrome-ban a szolgáltatási feltételeket. Koppintson a **ELFOGADÁS és FOLYTATÁS**.  

   ![Példa a képe Chrome használati feltételeit képernyő, kiemelve az elfogadás és Folytatás gomb.](./media/fully-managed-intune-app-06.png)   

7. A bejelentkezési képernyők jelentkezzen be a munkahelyi vagy iskolai fiókjával.   

    a. Adja meg az e-mail címét és koppintson **tovább**.      
    b. Adja meg a jelszót, és koppintson **jelentkezzen be a**.  

8. A szervezet követelményeitől függően előfordulhat, hogy kéri frissíteni a beállításokat, például képernyőzár vagy titkosításra. Ha ezek a felkérések látja, koppintson **beállítása** , és kövesse a képernyőn megjelenő utasításokat.  

   ![Példa a kiemelés beállítás gombra a munkahelyi telefon képernyőt Set ábrázoló kép.](./media/fully-managed-intune-app-10.png)   

9. Az eszköz a munkahelyi alkalmazások telepítéséhez koppintson **telepítése**. Koppintson a telepítés befejezése után **tovább**.  

   ![Példa kép beállítása a munkahelyi telefon képernyőt, kiemelve a telepítés gombra.](./media/fully-managed-intune-app-11.png)   

10. Ha az üzenet, hogy az eszköz készen áll, koppintson **kész**. 

11. Nyissa meg az alkalmazások, és nyissa meg a Microsoft Intune-alkalmazást. Válassza ki **JELENTKEZZEN be a**. 

12. Az a **hozzáférés beállítása** képernyő, a függőben lévő feladatok listáját láthatja. Koppintson a **FOLYTATÁS**.  

       ![A Microsoft Intune-alkalmazás, például képe beállítása hozzáférési képernyőkép, függőben lévő feladatokat.](./media/fully-managed-intune-app-14.png)   

13. Ha az eszköz regisztrálása befejeződött, koppintson **FOLYTATÁS**. A Microsoft Intune kérheti, hogy további eszközbeállítások frissítése.   

       ![Példa alkalmazás képe látható a Microsoft Intune, frissítési eszköz beállítások képernyő.](./media/fully-managed-intune-app-15-2.png)   

14. Telepítés befejeződött, ha a listában szereplő összes zöld körön megjelenítése. Most már elérheti a vállalati erőforrásokhoz.  

       ![A példában a képe a Microsoft Intune-alkalmazást, állítsa be a hozzáférési képernyőn megjelenítése befejeződött feladatokat.](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>QR-kód regisztráció  
Ebben a szakaszban a vállalat által biztosított QR-kódot fog beolvasása.  Ha elkészült, azt fogja visszairányítja, az eszköz regisztrációs lépéseket.     
  
1. Az a **üdvözlő** koppintson a képernyő ötször a QR-kód telepítő indítása.  

   ![A példában a képe eszköz telepítő üdvözlőképernyőjén koppintson a képernyő utasításokat kiemelése.](./media/qr-code-intune-app-01.png)  

2. Kövesse a képernyőn kapcsolódni a Wi-Fi utasításokat.  
3. Ha az eszköz nem rendelkezik egy QR-kódolvasót, a telepítési képernyőn jelennek meg a folyamat állapotát a képolvasó telepítve van. Várjon, amíg a telepítés befejeződik.  
4. Amikor a rendszer kéri, vizsgálja meg a regisztrációs profilt, amely a szervezet kapott QR-kódot.  
5. Lépjen vissza [beléptetés eszköz](#enroll-device), a telepítés folytatásához a 4. lépés.  

## <a name="token-enrollment"></a>Jogkivonat-regisztráció  
Ebben a szakaszban a vállalat által biztosított jogkivonat kell adnia. Ha elkészült, azt fogja visszairányítja, az eszköz regisztrációs lépéseket.  

1. A Google bejelentkezési képernyőn az a **E-mail vagy telefonszám** mezőbe írja be **afw #setup**. Koppintson a **Következő** elemre. 

   ![Példa a képe a Google bejelentkezési képernyő, hogy "afw #setup" mezőbe beírt van.](./media/token-intune-app-01.png)   

2. Válassza a **telepítése** számára a **Android-eszköz házirend** alkalmazás. Folytassa a telepítést. Az eszköztől függően szükség lehet további feltételek elfogadásához.    

3. Az a **regisztrálja ezt az eszközt** képernyőn válassza ki **tovább**.  

   ![A példában a képe beléptetés az eszköz képernyőjén. Megjeleníti a QR-kód; ábrája kiemeli a Tovább gombra.](./media/token-intune-app-02.png)  

4. Válassza ki **kódot**.

   ![Egy aktív QR-kódolvasót képernyőképet. Kiemeli a Enter kód gombra.](./media/token-intune-app-03.png)  

5. Az a **vizsgálata, vagy adja meg a kódot** képernyőn írja be a kódot, amely a szervezet kapott.  Ezután kattintson a **Next** (Tovább) gombra.  

   ![A vizsgálat példaképen, vagy adja meg a kódot képernyő, kiemelve a Tovább gombra.](./media/token-intune-app-04.png)  

6. Lépjen vissza [beléptetés eszköz](#enroll-device), a telepítés folytatásához a 4. lépés.  



## <a name="next-steps"></a>További lépések   
További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.  
